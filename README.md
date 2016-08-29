Linux, Nginx, PHP-FPM, MariaDB
=================

A light Docker based sandbox image for PHP web development that is based on a Ubuntu 14.04 OS. 

![Docker logo](http://upload.wikimedia.org/wikipedia/commons/7/79/Docker_(container_engine)_logo.png "Docker logo")

This image with comes built with nginx, PHP-FPM, Drush, MySQL.

## Getting Started
1. Install docker, as explained here: https://docs.docker.com/engine/installation/
2. Clone this repo locally and go the cloned folder.
3. Run the following command for initializing the configuration: 

```
$ docker-compose build
$ docker-compose up -d
```

Add the following lines to your local hosts file in order for your computer to recognize the docker hosts.

```
127.0.0.1 drupal8.docker wordpress.docker db database
```

Add a Drupal8 or Wordpress site to the `sites/` directory and you're done.

```
Here goes terminus command to add a site.
```
