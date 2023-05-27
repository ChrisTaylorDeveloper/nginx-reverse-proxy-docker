# NGINX Reverse Proxy Docker

A Nginx reverse proxy in Docker, to serve other Docker applications.

Build the image
```
docker build -t rev_prox .
```

Run the reverse proxy image
```
docker run --rm -p 80:80 \
-v ./html:/usr/share/nginx/html \
-v ./includes:/etc/nginx/conf.d/includes \
-v ./default.conf:/etc/nginx/conf.d/default.conf \
--name running_rev_proxy rev_prox
```

Test agains two stand alone apps
```
docker run --rm -p 81:80 --name web1 nginx
docker run --rm -p 82:80 --name web2 nginx
```

Required in /etc/hosts
```
127.0.0.1 web1
127.0.0.1 web2
```
