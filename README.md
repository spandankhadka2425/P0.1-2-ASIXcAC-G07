# P0.1 - Despliegue de la Aplicación Extagram

## Información del Proyecto

- **Módulo:** 0379 - Proyecto intermodular en administración de sistemas informáticos en red  
- **Actividad:** P0.1 - Despliegue de aplicación Extagram  
- **Grupo:** ASIXcAC-G07  
- **Duración:** 6 semanas (finaliza 15/01/2026)  
- **Metodología:** Sprints quincenales (3 sprints de 10 horas cada uno)  

---

## Objetivo

El objetivo principal consiste en desplegar una aplicación web multicapa (Extagram) que permita compartir imágenes, seguir usuarios y comentar publicaciones, utilizando contenedores Docker para facilitar su despliegue y administración.

---

## Estructura del Proyecto

---

## Componentes y Servicios
- **Base de datos:** MySQL o PostgreSQL en contenedor independiente
- **Red interna Docker:** Comunicación segura entre servicios

---

## Requisitos

- Docker y Docker Compose instalados en el sistema
- Acceso a la terminal o Docker Desktop

---

## Despliegue Rápido (Drag & Drop)

1. Descarga y descomprime la carpeta del proyecto.
2. Abre Docker Desktop.
3. Arrastra y suelta la carpeta del proyecto sobre Docker Desktop.
4. Docker detectará el archivo `docker-compose.yml` y permitirá iniciar los servicios.
5. Accede a la aplicación en [http://localhost:3000](http://localhost:3000).

---

## Comandos Útiles

- **Iniciar servicios:**  
---

## Variables de Entorno

Copia `.env.example` a `.env` y ajusta los valores según tu entorno antes de iniciar los servicios.

---

## Credenciales Comunes (si aplica)

- Usuario administrador: admin
- Contraseña: admin123

---

## Documentación Técnica

Toda la configuración, scripts y documentación técnica están centralizados en este repositorio para facilitar el despliegue reproducible y la administración eficiente del entorno.

---



