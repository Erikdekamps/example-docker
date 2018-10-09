# Example localhost.

Index:
```
- Docker
  - Database
  - Proxy
  - Web
  - Getting started
  - Docs
```

# Docker

The docker directory contains files needed inside the development containers.
Files that need to be shared with the containers at run time, should live in
these directories.

### Database

The local `docker/database` directory will be mounted to 
`/docker-entrypoint-initdb.d`. 
Any `sql` files in this directory will be loaded as fixtures by `mysql`.
Also contains a settings file for mysql to ensure that we can handle
larger databases and requests in docker.

### Proxy

0. nginx reverse proxy/ssl termination config file
0. ssl certificate `.crt` file
0. private key `.key` file

### Web

Contains dev / live php.ini (dev will be used in docker).

### Getting started

* Install docker (preferably the edge version) if you have docker skip this
step.
* Add database dump in ./docker/database
* Execute all steps from the Docs section below
* Run docker-compose up.

### Docs

* [Configure https](docs/configure-https.md)
* [Add environment to hosts file](docs/hosts.md)

# Docker in development

To enter the php container with bash, run:

```
docker exec -it example_php bash
```

Once inside, install and update composer, run:

```
composer install 
composer update 
```
