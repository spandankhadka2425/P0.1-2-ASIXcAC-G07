# Arquitectura Servicios S1-S7

## Descripción general
Arquitectura distribuida de Extagram usando 7 contenedores Docker conectados por red bridge `extagram-net`. S1 actúa como punto único de entrada con proxy inverso y balanceo de carga. [file:34]

## Tabla de servicios

| Servicio | Rol | Tecnología | Puerto interno | Rutas gestionadas | Dependencias |
|----------|-----|------------|----------------|-------------------|--------------|
| **S1** | Proxy inverso + balanceo | NGINX alpine | 80 → host:8080 | `/` → S2/S3 (extagram.php)<br>`/upload.php` → S4<br>`/images/` → S5<br>`/static/` → S6 | S2, S3, S4, S5, S6 |
| **S2** | PHP-FPM posts (redundante 1) | PHP-FPM | 9000 | extagram.php (muestra formulario/muro) | S7 (MySQL) |
| **S3** | PHP-FPM posts (redundante 2) | PHP-FPM | 9000 | extagram.php (muestra formulario/muro) | S7 (MySQL) |
| **S4** | PHP-FPM uploads | PHP-FPM | 9000 | upload.php (procesa subida imagen) | S7 (MySQL), volumen storage |
| **S5** | Servidor imágenes | NGINX alpine | 80 | `/images/*` (fotos subidas) | volumen storage (compartido con S4) |
| **S6** | Servidor estáticos | NGINX alpine | 80 | `/static/style.css`<br>`/static/preview.svg` | directorio estático |
| **S7** | Base de datos | MySQL | 3306 | extagram_db.posts (posts + photourl) | volumen datos persistente |

## Diagrama de flujo
Navegador → S1 (NGINX proxy)
- ↳ extagram.php → S2/S3 (balanceo) → S7 (MySQL)
- ↳ upload.php → S4 → storage → S5 (imágenes)
- ↳ style.css, preview.svg → S6