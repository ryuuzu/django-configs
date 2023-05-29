---
layout: default
title: Gunicorn Socket Template
parent: Hosting Config Templates
---

# Gunicorn Socket Template

The following is the Gunicorn Socket template for the hosting configurations. Please change the `gunicorn_socket_name.sock` to your desired value.

```
[Unit]
Description=gunicorn socket

[Socket]
ListenStream=/run/gunicorn_socket_name.sock

[Install]
WantedBy=sockets.target
```
