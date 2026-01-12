Usamos Isard porque es una plataforma VDI libre pensada para educación, permite gestionar todas las máquinas virtuales de Extagram desde un punto central, escala fácilmente, funciona bien en PCs modestos, se accede por navegador y simplifica plantillas, snapshots y laboratorios reproducibles para todo el alumnado

# Análisis Comparativo: IsardVDI vs. AWS para el Despliegue del Proyecto Extagram

## Resumen Ejecutivo
Para el proyecto escolar "Extagram", que implica desplegar una aplicación PHP con una arquitectura multi-servidor, **IsardVDI es la plataforma recomendada y estratégicamente superior** frente a AWS. Esta decisión se basa en la alineación con los objetivos educativos, el coste, la simplicidad operativa y las funciones integradas para la colaboración.

## Comparación Detallada de Características

| Criterio de Comparación | **IsardVDI** | **AWS (Amazon WorkSpaces / EC2)** | **Veredicto para Nuestro Proyecto** |
| :--- | :--- | :--- | :--- |
| **Coste y Licencias** | **Gratuito y de Código Abierto (AGPLv3)**. Proporcionado como recurso institucional sin tarifas de uso. | **Pago por uso / licencias complejas**. Los servicios VDI (WorkSpaces) tienen tarifas por hora/mes y posibles costes de licencia. El cómputo general (EC2) genera cargos continuos. | **Gana IsardVDI.** Elimina el riesgo financiero y las preocupaciones presupuestarias para un proyecto estudiantil. |
| **Propósito de Diseño Principal** | **Construido específicamente para educación.** Diseñado para gestionar laboratorios, compartir plantillas y servir a escuelas con fondos limitados. | **Construido para uso empresarial y comercial.** Optimizado para negocios globales, fuerza laboral remota y entornos de producción. | **Gana IsardVDI.** Sus funciones coinciden directamente con nuestro escenario educativo y colaborativo. |
| **Valor de Aprendizaje Central** | **Administración profunda de sistemas.** Requiere configuración práctica de MV, redes, SO y servicios, construyendo habilidades fundamentales de TI. | **Gestión de plataforma cloud.** El enfoque se desplaza a navegar por la consola de AWS, IAM y servicios gestionados, lo cual es menos relevante para los objetivos de nuestro módulo. | **Gana IsardVDI.** Proporciona la experiencia práctica, "desde el metal", que nuestro proyecto pretende enseñar. |
| **Control de la Infraestructura** | **Acceso administrativo completo.** Tú controlas toda la pila de software en las máquinas virtuales, desde el SO hacia arriba. | **Responsabilidad abstracta o compartida.** Los servicios gestionados (como RDS) manejan la infraestructura subyacente, reduciendo el trabajo directo de administración de sistemas. | **Gana IsardVDI.** Esencial para aprender a configurar NGINX, PHP-FPM, MySQL y Docker según se requiere. |
| **Utilidad de Plantillas e Instantáneas** | **Funcionalidad central para laboratorios.** Crea una máquina virtual maestra "golden" con todo el software del proyecto y clónala instantáneamente para cada miembro del equipo. | **Disponible, pero en un contexto comercial.** Las Machine Images (AMIs) sirven un propósito similar, pero dentro del ecosistema AWS. | **Gana IsardVDI.** Creado específicamente para generar entornos de laboratorio perfectamente consistentes y reproducibles para todos los estudiantes. |
| **Colaboración y Acceso** | **Acceso basado en web y grupos de usuarios aislados.** Los equipos pueden trabajar en redes aisladas, y el profesor puede acceder fácilmente a todos los entornos para soporte/calificación. | **El acceso requiere una configuración cuidadosa de IAM y red.** Configurar un acceso seguro y compartido para un equipo es más complejo. | **Gana IsardVDI.** Simplifica el trabajo en equipo y se alinea con el requisito de que todos los miembros deben conocer y tener acceso a todo el proyecto. |
| **Contexto de Soporte** | **Institucional y impulsado por pares.** El soporte proviene de la escuela o de la comunidad del proyecto. Los profesores están familiarizados con la plataforma. | **Documentación general y soporte empresarial de pago.** Dependes de documentación genérica de AWS o de costosos planes de soporte. | **Gana IsardVDI.** El soporte directo y contextual de instructores que conocen la herramienta es invaluable para un proyecto de aprendizaje. |

## Conclusión y Recomendación Final

**Usa IsardVDI para este proyecto.** Es la herramienta correcta para un entorno educativo porque:

1.  **Es gratuita y conlleva riesgo financiero cero.**
2.  **Sus funciones centrales (plantillas, laboratorios aislados, acceso web) están diseñadas exactamente para lo que necesitamos:** crear entornos idénticos para un equipo y una clase.
3.  **Obliga al aprendizaje de habilidades fundamentales de administración de sistemas** (Linux, servidores web, bases de datos, contenedores), que es el objetivo principal de tu módulo.
4.  **Facilita la colaboración y la supervisión** de una manera que se alinea con el requisito de "responsabilidad de todo el equipo" de tu proyecto.

Si bien AWS es un estándar de la industria potente para despliegues de producción escalables, su complejidad, modelo de costes y abstracción de los sistemas subyacentes lo convierten en una opción menos adecuada para lograr los **resultados de aprendizaje específicos** de este proyecto académico.