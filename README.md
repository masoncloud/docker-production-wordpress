# WordPress Docker Container

This Dockerfile installs WordPress 5x (with latest WP-CLI), nginx 1.14 and php-fpm 7.2 (ondemand PM) over Alpine Linux. Currently using it on multiple heavy load production sites without any problems.

Attached wp-config.php in this container is designed to use with configuration parameters as a environments variables, making its management lot easier.

nginx configuration has a lot of tweaks, and this container run a cron via system instead of WP cron because is not very reliable.

Currently image size is 152 MB, but the goal of this project is to slim it as possible.

## Installing

If you want to get this docker image, just puill from the Docker registry

    $ docker pull nidr0x/wordpress:latest 

## Using with Docker-Compose

If you want to spin a running environment, you can do it vía docker-compose

    $ docker-compose up

Please note: Attached docker-compose is focused on production environment, which is why it has Traefik with SSL via Letsencrypt.

## References 

* https://github.com/docker-library/wordpress
* https://codeable.io/wordpress-developers-intro-to-docker-part-one/
* https://codeable.io/wordpress-developers-intro-to-docker-part-two/
* https://github.com/TrafeX/docker-php-nginx/
* https://hub.docker.com/_/wordpress/