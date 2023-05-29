---
layout: default
title: PostgreSQL Setup Template
parent: Setup Guide Templates
---
# PostgreSQL Setup Template

The following is the PostgreSQL Setup template for the setup guides. Please change the `database_name`, `user_name`, and `user_password` to your desired values.

[View Raw Content](https://raw.githubusercontent.com/ryuuzu/django-configs/main/docs/setup-guide-templates/postgresql_setup_template.md){: .btn .btn-purple target="_blank"}

<!-- Copy from here -->
## PostgreSQL Setup Guide

This guide will help you setup PostgreSQL for your server.

1. Login as superuser in PostgreSQL.
2. Create a user in PostgreSQL with the following command.

    ```sql
    CREATE USER ryuu WITH LOGIN PASSWORD 'abc123';
    ```

3. Setup default encoding and locale for the user.

    ```sql
    ALTER ROLE ryuu SET client_encoding TO 'utf8';
    ALTER ROLE ryuu SET default_transaction_isolation TO 'read committed';
    ALTER ROLE ryuu SET timezone TO 'UTC';
    ```

4. Create a database for the user and grant access to it.

    ```sql
    CREATE DATABASE ryuu_site_db WITH OWNER ryuu;
    GRANT ALL PRIVILEGES ON DATABASE ryuu_site_db TO ryuu;
    ```
<!-- Copy to here -->