# Useful Docker Commands
The following lists a number of useful Docker commands.

### Delete all containers with 'exited' status
``` shell
docker rm $(docker ps -a -f status=exited -q)
```
### Stop all containers
``` shell
docker container stop $(docker container ls -aq)
```
### Power down all 'local' docker networks
``` shell
docker-compose down -v $(docker network ls --filter name=_local -q)
```
### Remove all local docker networks
``` shell
docker network rm $(docker network ls --filter name=_local -q)
```
### Kill one or more running containers
``` shell
docker kill $(docker ps -q)
```
### SSH into existing docker build
``` shell
docker run -t -d --name dockerhub-php-fpm-7.4 php:7.4-fpm
docker exec -it dockerhub-php-fpm-7.4 bash
php -m
```
