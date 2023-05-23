---
layout: default
title: MySQL Setup Template
parent: Setup Guide Templates
---
# MySQL Setup Template

The following is the MySQL Setup template for the setup guides. Please change the `database_name`, `user_name`, and `user_password` to your desired values.

[View Raw Content](https://raw.githubusercontent.com/ryuuzu/django-configs/main/docs/setup-guide-templates/mysql_setup_template.md){: .btn .btn-purple target="_blank"}

## MySQL Setup Guide

This guide will help you setup MySQL for your server.

1. Log into the database as `root`.
2. Create a database.

    ```sql
    CREATE
    DATABASE `database_name`;
    ```

3. Create a user.

    ```sql
    CREATE
    USER `user_name`@`localhost` IDENTIFIED BY 'user_password';
    ```

4. Grant the user access to the database.

    ```sql
    GRANT ALL PRIVILEGES ON `database_name`.* TO `user_name`@`localhost`;
    ```

5. Flush the privileges.

    ```sql
    FLUSH
    PRIVILEGES;
    ```
