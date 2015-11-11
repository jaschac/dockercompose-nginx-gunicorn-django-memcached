# nginx-gunicorn-django-memcached
#### Table of Contents
1. [Overview](#overview)
2. [Application Description](#application-description)
3. [Setup](#setup)
4. [Usage](#usage)
    * [Manually running and linking containers](#manually-running-and-linking-containers)
    * [Docker Compose](#docker-compose)
5. [Limitations](#limitations)

### Overview
This multi-container application deploys an Nginx web server serving a Django application, supported by Memcached, through the Gunicorn Web Server Gateway Interface HTTP Server. 

### Application Description
The nginx-gunicorn-django-memcached multi-container application is responsible of:

 * Deploying an Nginx web server listening to, and exposing to the host, port 80, through which it will serve the content of the Django application.
 * Deploying a Gunicorn WSGI Server that will listen for connections coming through the Nginx web server on port 8001. By default it will fire up 2 workers ready to serve the incoming requests. No port is exposed to the host.
 * Deploying a Memcached container that will be used to cache requests already served by Django.

This multi-container application is **not** responsible of:

 * Providing a Django web application to serve. The client must provide one to the containers as a volume, as described below.

### Setup
The nginx-gunicorn-django-memcached multi-container application relies on the following images:

 * jaschac/gunicorn-django: [Docker Hub]( https://hub.docker.com/r/jaschac/gunicorn-django/), [GitHub](https://github.com/jaschac/docker-gunicorn-django)
 * jaschac/nginx: [Docker Hub](https://hub.docker.com/r/jaschac/nginx/), [GitHub](https://github.com/jaschac/docker-nginx)
 * memcached: [Docker Hub](https://hub.docker.com/_/memcached/)

All of the images required can be pulled from the Docker Hub. Pulling images from the Docker Hub is very simple.

```bash
$ sudo docker pull jaschac/gunicorn-django:latest
$ sudo docker pull jaschac/nginx:latest
$ sudo docker pull memcached:latest
```

### Usage
The nginx-gunicorn-django-memcached multi-container application can be run either manually, by running and linking together the different containers, or through Docker Compose, which will take care of doing it all for us.

#### Manually running and linking containers
Setting it all up manually requires the containers to be run and linked together in a specific order.
@TODO: explain container by container

#### Docker Compose
@TODO

### Limitations
@TODO
