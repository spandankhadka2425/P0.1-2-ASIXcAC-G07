```
# Análisis de Configuración NGINX

## Estructura Principal
```nginx
events {}
http {
  upstream extagram_php { server s2:9000; server s3:9000; }
  upstream upload_php { server s4:9000; }
  
  server {
    listen 80;
    root /var/www/html;
    
    # Reglas de enrutamiento...
  }
}
```

## Partes Principales:

### 1. **Balanceo de Carga**
```nginx
upstream extagram_php { server s2:9000; server s3:9000; }
```
- Distribuye tráfico entre **S2 y S3** (servidores de aplicación)

### 2. **Servicio Dedicado para Uploads**
```nginx
upstream upload_php { server s4:9000; }
```
- Uploads van **solo a S4** (servicio especializado)

### 3. **Enrutamiento por Ruta**

**Homepage (/) → S2/S3**
```nginx
location = / {
  fastcgi_pass extagram_php;
}
```

**Upload.php → Solo S4**
```nginx
location = /upload.php {
  fastcgi_pass upload_php;
}
```

### 4. **Servicio de Imágenes**
```nginx
location /uploads/ { 
  proxy_pass http://s5/storage/uploads/; 
}
```
- Imágenes servidas desde **S5** (almacenamiento dedicado)

## Arquitectura Resultante:
- **S1** = Proxy (NGINX)
- **S2/S3** = Aplicación principal (balanceada)
- **S4** = Procesador de uploads
- **S5** = Almacenamiento de imágenes

```
