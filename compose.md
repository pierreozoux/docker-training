# docker-compose



## Idea

Describe an application composed of services provided by containers.



## Install

Install docker-compose

https://docs.docker.com/compose/install/



## Example

docker-compose.yml

```
version: '3'
services:
  web:
    build: .
    ports:
    - "5000:5000"
    volumes:
    - .:/code
    networks:
    - front-tier
    - back-tier
  redis:
    image: redis
    environment:
    - MY_ENV_VARIABLE:development
    - SESSION_SECRET
    volumes:
    - redis-data:/var/lib/redis
    networks:
    - back-tier
volumes:
  redis-data:
    driver: local
networks:
  front-tier:
    driver: bridge
  back-tier:
    driver: bridge
```

[reference](https://docs.docker.com/compose/compose-file/)


# Services

 - build/image
 - ports
 - volumes
 - networks
 - environment


## Nice pattern for environment

put an `.env` file in the root of project.


## For secret management

https://www.vaultproject.io/



## Command line

```
docker-compose up
docker-compose stop
docker-compose rm
docker-compose exec
```

[reference](https://docs.docker.com/compose/reference/overview/)



## Exercise!

```
cd exercises/compose
```
