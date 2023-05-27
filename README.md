# NGINX Reverse Proxy Docker

A Nginx reverse proxy in Docker, to serve other Docker applications.

## Startup
```
docker build -t rev_prox .
```

```
docker run -d -p 8080:80 \
-v ./html:/usr/share/nginx/html \
-v ./default.conf:/etc/nginx/conf.d/default.conf \
--name running_rev_proxy rev_prox
```
