# SPRINT 2 - Arquitectura Contenida y Red

**Duración:** 19/01/2026 - 27/01/2026 (10 horas)

**Objetivo:** Transformar la aplicación monolítica del Sprint 1 en una **arquitectura de microservicios con Docker**, implementando el diseño inicial de red.

## Entregables Principales:

### 1. Dockerización Completa
- Crear contenedores Docker para cada servidor (S1-S7 según diagrama)
- Configurar **red bridge** para la comunicación entre todos los contenedores

### 2. Proxy Inverso y Balanceo
- Configurar **S1 como proxy inverso** (Nginx)
- Implementar **balanceo de carga** entre S2 y S3
- **Segregar peticiones** por ruta hacia S4, S5 y S6

### 3. Diseño de Red
- Crear **diagrama de red** con Packet Tracer o herramienta similar
- Documentar esquema de direccionamiento IP y comunicaciones

### 4. Gestión de Imágenes
- Implementar **S6 como servidor de imágenes** independiente
- Configurar upload y recuperación de imágenes desde los otros servidores

## Entregables Obligatorios:
- Código Docker en GitHub
- docker-compose.yml funcional
- Diagrama de red
- Documentación técnica
