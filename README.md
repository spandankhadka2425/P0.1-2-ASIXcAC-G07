# P0.1 - Despliegue de la Aplicación Extagram

## Información del Proyecto

- **Módulo:** 0379 - Proyecto intermodular en administración de sistemas informáticos en red  
- **Actividad:** P0.1 - Despliegue de aplicación Extagram  
- **Grupo:** ASIXcAC-G07  
- **Duración:** 6 semanas (finaliza 15/01/2026)  
- **Metodología:** Sprints quincenales (3 sprints de 10 horas cada uno)  

## Objetivo

El objetivo principal consiste en desplegar una aplicación web multicapa (Extagram) que permita compartir imágenes, seguir usuarios y comentar publicaciones, utilizando contenedores Docker para facilitar su despliegue y administración.

## Estructura del Proyecto

## Componentes y Servicios
- **S1:** NGINX Proxy inverso + balanceo  
- **S2/S3:** PHP-FPM (extagram.php) redundantes  
- **S4:** PHP-FPM (upload.php)  
- **S5:** NGINX servidor imágenes  
- **S6:** NGINX archivos estáticos  
- **S7:** MySQL base de datos  
- **Red interna Docker:** `extagram-net` (bridge)

## Requisitos

- Docker y Docker Compose instalados  
- Sistema Linux (Ubuntu/Debian recomendado)  
- 4GB RAM mínimo, 8GB recomendado  
- Puerto 8080 libre en el host  

## Despliegue Rápido

# Iniciar todos los servicios
docker compose up -d

# Verificar que todo funciona
docker compose ps