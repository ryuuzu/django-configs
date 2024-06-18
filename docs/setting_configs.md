---
layout: default
title: Setting Configurations
---

# Setting Configurations

The following are extra URL configurations that can be used in the `urls.py` file of your Django project.

1. **URL Configuration for adding media files as static.**

    ```python
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
    ```
  