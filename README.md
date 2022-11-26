![Logo](http://shadowd.zecure.org/img/logo_small.png)

**Shadow Daemon** is a *web application firewall* that intercepts requests at the application level.
This repository contains a simple docker-compose wrapper to manage Shadow Daemon installations.

# Requirements

Install [Docker](https://docs.docker.com/install/) and [Docker Compose](https://docs.docker.com/compose/install/).

# Setup

You can use the following command to start Shadow Daemon:

    sudo ./shadowdctl up -d

Modify the file `docker-compose.yml` for fine-grained control.
For more information about other commands and configuration options check out the [Docker Compose manual](https://docs.docker.com/compose/).

## Configuration

You can change the paths of the database and the database password in the file `.env`.
