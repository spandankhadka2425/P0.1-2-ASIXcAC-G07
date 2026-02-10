## Sprint 3 - Seguridad y Logs

**Duración:** 28/01/2026 - 04/02/2026 (10 horas)

**Objetivo:**  
Añadir autenticación y un sistema de logs a la arquitectura de microservicios.

### Entregables Principales

1. **Servicio de Autenticación**  
   - Crear S7 como servicio de autenticación independiente  
   - Implementar JWT para generar y validar tokens de acceso

2. **Seguridad en el Proxy**  
   - Configurar S1 (Proxy) para validar tokens  
   - Proteger rutas que requieran autenticación

3. **Sistema Centralizado de Logs**  
   - Implementar un servicio para recolectar logs de todos los contenedores  
   - Configurar S1-S7 para enviar sus logs al sistema central

4. **Certificados HTTPS**  
   - Configurar HTTPS en S1 (Proxy) con certificados TLS

### Entregables Obligatorios

- Código de autenticación en GitHub
- Servicio de logs funcionando
- HTTPS configurado en el proxy
- Documentación de los nuevos componentes

---

### Tareas trasladadas del Sprint 2 al Sprint 3

- Completar la creación de todos los Dockerfiles y las tareas pendientes del sprint 2
- Configurar NGINX/PHP-FPM para los servicios S1-S7
- Documentar la arquitectura distribuida
- Asegurar que la página web Extagram funcione completamente en contenedores Docker con proxy inverso y balanceo de carga

