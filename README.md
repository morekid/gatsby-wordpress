# Wordpress + Docker setup

### How to start

    ./compose.sh

Wordpress will be served on port `1980`, PHPMyAdmin on port `1970`.

To investigate the running container logs:

    docker logs $CONTAINER_ID

_List all running containers to find your container ID: `docker ps`._

### Run shell inside container

    ./bash.sh $CONTAINER_ID

_List all running containers to find your container ID: `docker ps`._

### Clean (before rebuilding)

    ./rm_containers.sh

Will stop and remove all running containers.

    ./clean.sh

Wil remove all stopped and dangling containers/images.

### Notes

If the database you're importing through phpMyAdmin is big, you might need to set parameters in the `php.ini`:

    echo 'upload_max_filesize = 128M\npost_max_size = 128M\nmax_execution_time = 1000' > /usr/local/etc/php/php.ini
