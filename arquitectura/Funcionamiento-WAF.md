# Funcionament WAF – S1 (Hardening Web)

## Descripció

S1 actua com a proxy invers nginx i té integrat un WAF (Web Application Firewall)
mitjançant regles natives de nginx.
Totes les peticions HTTP passen per S1 abans d'arribar als servidors PHP (S2/S3/S4)
i a la base de dades MySQL (S7).

## Arquitectura

Client → S1 (nginx + WAF) → S2/S3 (PHP extagram.php)
→ S4 (PHP upload.php)
→ S5 (imatges)

## Implementació tècnica

Les regles WAF estan definides a `s1_proxy/nginx.conf` mitjançant blocs `map` i `if`.

### Regles actives

#### Anti-SQLi
Detecta patrons típics d'injecció SQL als paràmetres de la petició (`$args`):
- `UNION SELECT`, `SELECT FROM`, `INSERT INTO`, `DROP TABLE`
- Comentaris SQL: `--`, `/*`
- Funcions de temps: `sleep()`, `benchmark()`
- Patrons clàssics: `OR 1=1`

#### Anti-XSS
Detecta patrons de Cross-Site Scripting als paràmetres (`$args`):
- Etiquetes: `<script>`
- Protocols: `javascript:`, `vbscript:`
- Gestors d'events: `onerror=`, `onload=`, `onclick=`
- Funcions: `alert()`, `eval()`, `document.`, `window.`

#### Anti-Path Traversal
Detecta intents d'accés a fitxers del sistema a la URI (`$request_uri`):
- Seqüències: `../`, `..\`, `%2e%2e`
- Rutes sensibles: `/etc/passwd`, `/proc/`

#### Límit d'upload
- Mida màxima de fitxer: **10MB** (`client_max_body_size 10M`)
- Aplicat únicament a `/upload.php`

#### Proves realitzades
| Tipus d'atac   | Payload                            | Resposta esperada                    | Resultat |
| -------------- | ---------------------------------- | ------------------------------------ | -------- |
| Web normal     | GET /                              | 200 OK                               | Bien     |
| XSS            | ?caption=<script>alert(1)</script> | 403 Blocked: XSS detected            | Bien     |
| SQL Injection  | ?caption=UNION+SELECT+*+FROM+users | 403 Blocked: SQLi detected           | Bien     |
| Path Traversal | ?caption=../../etc/passwd          | 403 Blocked: Path traversal detected | Bien     |
| Upload normal  | .jpg / .png / .webp                | 200 OK                               | Bien     |


- [index.md](../index.md)
