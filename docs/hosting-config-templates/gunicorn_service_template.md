---
layout: default
title: Gunicorn Service Template
parent: Hosting Config Templates
---

# Gunicorn Service Template

The following is the Gunicorn Service template for the hosting configurations. Please change the `path_to/django_root_folder` and `path_to/gunicorn_socket_name.sock` to your desired values.

```
[Unit]
Description=gunicorn daemon
Requires=gunicorn.socket
After=network.target

[Service]
User=root
Group=www-data
WorkingDirectory=path_to/django_root_folder
ExecStart=path_to/gunicorn \
          --access-logfile - \
          --workers 3 \
          --bind unix:/run/gunicorn_socket_name.sock \
          personal_site_backend.wsgi:application

[Install]
WantedBy=multi-user.target
```
