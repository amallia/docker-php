apache-php-dev docker image
===========================

A Docker image with apache and php and various tools which can be used for development.

* Apache and PHP (uses dockerimage [yoshz/apache-php](https://registry.hub.docker.com/u/yoshz/apache-php/))
* System tools:
  * Node.js
  * Ruby
  * Rubygems
  * Bundler
* PHP tools:
  * Drush 6.x
  * Phing
  * Phpunit
  * PHP Code Sniffer (including standards for Drupal and Symfony2)
* Build tools:
  * Bower
  * Grunt-cli
  * Gulp
  * Fontforge & sfnt2woff


Download image
--------------

This image is available on [Docker Hub Registry](https://registry.hub.docker.com/u/yoshz/apache-php-dev/).


    docker pull yoshz/apache-php-dev:5.5


Build image
-----------

    docker build -t yoshz/apache-php-dev:5.5 .


Start a new container
---------------------

It is possible to autocreate a new system user when the container starts:

    docker run -p 80:80 -p 2022:22 \
        -v www:/var/www \
        -e USER_CREATE=`id -un` \
        -e USER_PUBLIC_KEY=`cat ~/.ssh/id_rsa.pub` \
        -e GIT_NAME=username \
        -e GIT_EMAIL=username@domain \
        yoshz/apache-php-dev:5.5

The following optional environment variables are available:

* *USER_CREATE*: Name of the user to create
* *USER_PUBLIC_KEY*: Public key to attach to the system user
* *USER_PASSWORD*: Password to attach to the system user
* *USER_ID*: User id of the new user
* *GIT_NAME*: GIT username to attach to system user
* *GIT_EMAIL*: GIT email to attach to system user

The user will be created with sudo rights.

Contact
-------

For issues, questions or more docker images go to:
[https://github.com/yoshz/docker-php](https://github.com/yoshz/docker-php)
