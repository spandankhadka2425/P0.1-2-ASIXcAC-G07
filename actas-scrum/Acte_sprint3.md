## Sprint 3

**Fecha:** 03/02/2026 - 9/02/2026

El día 19/01/2026 hemos realizado la segunda acta para nuestro proyecto. En esta acta participaron:

**Participantes:**  
- Product Owner: Spandan
- Miembro: Anmol  

**Propósitos del Sprint 3:**  
Completar las tareas pendientes del sprint 2, configurar NGINX/PHP-FPM para los servicios S1-S7, documentar la arquitectura distribuida y asegurar que la página web Extagram funcione completamente en contenedores Docker con proxy inverso y balanceo de carga.

**Tareas trasladadas del Sprint 2 al Sprint 3:**  
- Implementar contenedores PHP-FPM para S2, S3 y S4 (Dockerfile PHP con extensiones, adaptar código para Docker, volumen compartido, etc.).
- Configurar `docker-compose.yml`, red Docker y servicios S1-S7 (crear la red extagram-net, MySQL S7 con base de datos, usuario y tabla, y NGINX S1 como proxy inverso).
- Configurar NGINX para S5 (imágenes) y S6 (estáticos), y realizar pruebas completas de flujo y balanceo entre S1, S2 y S3.

