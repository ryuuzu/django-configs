---
layout: default
title: Nginx Server Block Template
parent: Hosting Config Templates
---

# Nginx Server Block Template

The following is the Nginx Server Block template for the hosting configurations. Please change the `domain.com`, `path_to/django_root_folder`, `path_to/domain.com.access.log`, `path_to/domain.com.error.log`, and`gunicorn_socket_name.sock` to your desired values.

```nginx
server {
    listen 80;
    server_name domain.com;
    root path_to/django_root_folder;

    access_log  path_to/domain.com.access.log;
    error_log  path_to/domain.com.error.log;

    location = /favicon.ico { access_log off; log_not_found off; }
    location /static/ {
    }
    location /media/ {
    }

    location / {
        include proxy_params;
        proxy_pass http://unix:/run/gunicorn_socket_name.sock;
    }
}
```
