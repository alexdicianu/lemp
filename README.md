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

Add a Drupal8 or Wordpress site to the `sites/` directory and you're done. You can visit the site at either http://drupal8.docker:8088/ or http://wordpress.docker:8088/

```
Here goes terminus command to add a site. Database credentials are:

host: db
user: root
password: root
port: 3306
```

## One liner install

```
curl -O https://gist.githubusercontent.com/alexdicianu/350b5db4e78573793673b90711cb7398/raw/74347335b24af503f6a2b901c4dd46edbe980138/install.sh && chmod +x install.sh && ./install.sh
```
