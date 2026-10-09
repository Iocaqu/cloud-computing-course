# Multi-Tier Architecture

## What Is a Two-Tier Architecture?
A two-tier architecture splits an application into two layers that communicate over a network: a **web/application tier** that users interact with, and a **database tier** that stores the data. In this laboratory, the two tiers run as separate Docker containers: Nextcloud (web/application) and MariaDB (database).

## The Web/Application Tier
This tier is the part users interact with. Its role is to:
- Serve the user interface to the browser
- Handle HTTP requests and responses
- Run the application logic (logins, file uploads, sharing)
- Query the database tier when data is needed

In this lab, the **Nextcloud container** is the web/application tier, reachable on port 8080 (mapped to container port 80).

## The Database Tier
This tier is responsible for storing and retrieving persistent data. Its role is to:
- Store user accounts and credentials
- Store file metadata and application settings
- Answer queries sent by the application tier

In this lab, the **MariaDB container** is the database tier. It is not exposed to the outside; only the Nextcloud container talks to it.

## Why Separate Them?
Keeping the web server and the database in two separate containers lets each be updated, restarted, scaled or troubleshot independently, so a failure or upgrade in one does not bring down the other. Each container also has a single responsibility, which makes the system easier to secure (the database is never exposed publicly) and easier to maintain than a single container running both.
