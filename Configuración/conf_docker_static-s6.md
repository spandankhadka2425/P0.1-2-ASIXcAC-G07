# S6 - Static Assets Server

## Descripción
S6 sirve archivos estáticos (CSS, SVG) requeridos por extagram.php. Nginx ligero optimizado para assets con caché máximo, proxy desde S1 en ruta /static/.

## Arquitectura
- **Imagen base:** nginx:alpine
- **Puerto interno:** 80/tcp
- **Volumen:** `./html:/var/www/html` (assets)
- **Red:** extanet

---

## Archivos

### 1. Dockerfile

**Ubicación:** `s6_static/Dockerfile`

**Código:**

![Dockerfile S6](ruta/a/screenshot_dockerfile_s6.png)

**Explicación:**
- `FROM nginx:alpine`: Nginx mínimo (5MB RAM)
- `COPY nginx.conf /etc/nginx/conf.d/default.conf`: Config personalizada
- `mkdir -p /var/www/html`: Directorio para montar assets
- `chown nginx:nginx`: Usuario correcto nginx
- `VOLUME ["/var/www/html"]`: Persistencia assets

---

### 2. nginx.conf

**Ubicación:** `s6_static/nginx.conf`

**Código:**

![nginx.conf S6](ruta/a/screenshot_nginx_s6.png)

**Explicación:**
```nginx
server {
  listen 80;
  root /var/www/html;
  location / { }
}
