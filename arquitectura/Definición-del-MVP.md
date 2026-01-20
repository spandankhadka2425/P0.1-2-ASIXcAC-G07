# Definición del MVP
## MVP = Extagram funcionando en un solo servidor web Linux que permite al usuario:
- Escribir un post de texto.
- Seleccionar y subir una imagen.
- Publicar el post en un muro visible al recargar la página.​

# Componentes mínimos del servidor
- Servidor web: NGINX o Apache recibe las peticiones HTTP.​
- PHP/PHP-FPM: ejecuta extagram.php (muestra formulario y muro) y upload.php (procesa subida).​
- Almacenamiento de datos: Método elegido: Carpeta uploads/ (simplifica Sprint 1, S6). Alternativa: MySQL extagramdb.posts (S5).​
- Recursos estáticos: style.css y preview.svg servidos por el servidor web (S6).​

# Flujo funcional mínimo
- Usuario accede por navegador → extagram.php muestra formulario.
- Usuario escribe texto + selecciona imagen → formulario POST a upload.php.
- upload.php guarda imagen en /var/www/storage/ y post en BBDD → redirige a extagram.php.
- extagram.php consulta BBDD → muestra todos los posts con sus imágenes.
