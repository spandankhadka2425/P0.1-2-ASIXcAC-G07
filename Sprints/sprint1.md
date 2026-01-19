# Análisis del Sprint 1 - Proyecto Extagram

## Duración del Sprint 1
**Período:** Del **15 de diciembre de 2025** al **19 de enero de 2026**.
**Duración total:** Un sprint **quinzenal** con una carga estimada de **10 horas**.

## Objetivo Principal del Sprint 1
El objetivo central del primer sprint es establecer una **base operativa y documentada** para la aplicación Extagram. Esto se concreta en dos entregables clave:

### 1. Análisis y Documentación Técnica
- Realizar un **análisis completo** del proyecto, sus requisitos y las tecnologías que se van a emplear (p.ej., Apache, PHP, MySQL).
- Toda esta **documentación técnica** debe quedar registrada y disponible en un **repositorio de GitHub** del proyecto.

### 2. Diseño Mínimo Viable (MVP) Funcional
- Desplegar una **versión monolítica funcional** de la aplicación en una **sola máquina**.
- Configurar un **servidor web** (Apache o Nginx) con todos los módulos y servicios necesarios para ejecutar PHP.
- Lograr que la aplicación sea capaz de **publicar posts y cargar imágenes**, utilizando **uno de los dos métodos** especificados:
    - Almacenamiento de imágenes en la **base de datos** (como BLOB).
    - Almacenamiento de imágenes en una **carpeta del servidor** (`uploads/`).

## Conexión con los Sprints Posteriores
Este MVP monolítico sentará las bases para los **Sprints 2 y 3**, donde esta arquitectura se **dividirá en microservicios** utilizando contenedores Docker (simulando los servidores S1 a S7 del diagrama) y se implementarán características avanzadas como el balanceo de carga.