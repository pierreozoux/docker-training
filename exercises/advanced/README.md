# Namespace

Start a debian intereactive container and run the following commands:
(Compare to what you see on the host)

 - NET: ifconfig -a
 - PID: ps -aux
 - USER: ps -aux
 - Mount: df -h
 - UTS: hostname

Hint for one command, you'll need to install ifconfig (in net-tools in debian)


# data

Add the following line on our grunt container:

```
VOLUME /usr/src/app
```

rebuild your image and restart your container.

What do you see under `docker volume ls` command?

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

`docker run -d nginx`

Find it's name and exec a bash on its side.
(used to debug inside containers)

`docker exec --help`

# Network

Create an nginx image with the configuration of this folder.

Create a container to proxy the grunt conainer.
The 2 containers have to be in an isolated network.

help: https://docs.docker.com/engine/userguide/networking/work-with-networks/