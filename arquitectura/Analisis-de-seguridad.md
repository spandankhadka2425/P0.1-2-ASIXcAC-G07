#  Tarea 1 - Análisis Riesgos COMPLETADA
**Sprint 4 Securització Extagram - 23/02/2026**

## Arquitectura
S1 nginx proxy (80)
S2/S3 PHP extagram.php
S4 PHP upload.php ← CRÍTICO
S5 nginx imágenes
S6 nginx estáticos
S7 MySQL + Elastic

## Tests realizados

**SQLi:** `' OR 1=1` → **PROTEGIDO** (hecho)
**Upload shell.php.jpg:** Rechazado → **BLOQUEADO** (hecho)
**Nmap:** 9200/3306 **BLOQUEADOS** (hecho)  
**UFW:** INPUT DROP + 80/22 OK (hecho)
**XSS:** Solo texto seguro (hecho)

## Estado
| Riesgo | Estado |
|--------|--------|
| Elastic 9200 | (asegurado) OK |
| MySQL 3306 | (asegurado) OK |
| SQLi | (cortafuegos) OK |
| Upload | (cortafuegos) OK |
| MySQL privs | (asegurado) OK |
| XSS | (cortafuegos) OK |


- [index.md](../index.md)
