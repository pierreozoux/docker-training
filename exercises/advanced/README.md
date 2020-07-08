# Namespace

Start a bash inside an alpine interactive container and run the following commands:

```
docker run -it alpine bash
# install ifconfig
apk --no-cache add net-tools
```

(Compare to what you see on the host)

 - NET: ifconfig -a
 - PID: ps -ax
 - USER: (We'd need to configure docker daemon for that)
 - Mount: df -h
 - UTS: hostname

# explore 

```
ll /var/lib/docker
ll /proc/$PID
docker images
docker ps
docker volumes
```

# exec

Start an nginx container in detach mode:

`docker run -d nginx:alpine`

Find it's name and exec a bash on its side.
Cat the current index.html.
(used to debug inside containers)

`docker exec --help`

# data

Add the following line on our nginx Dockerfile:

```
VOLUME /etc/nginx/
```

rebuild your image and recreate your container.

What do you see under `docker volume ls` command?

# Network

The objective is to serve nginx though nginx proxy.

Create an nginx image with the configuration in this folder (nginx configuration is situated in /etc/nginx/nginx.conf).

Create an nginx container to proxy the nginx container.
The 2 containers have to be in an isolated network.

help: https://docs.docker.com/engine/userguide/networking/work-with-networks/
