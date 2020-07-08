# Docker Basics



## Terminology

 - image
 - layer
 - container
 - Dockerfile
 - registry 


## Image

An image is a state of a file system.
It is the rootfs and everything you put on it like libs, bin...
You can think of it as the folder where you chroot.


![docker image](/images/docker-filesystems-debian.png)

[source](http://docs.docker.com/terms/image/)


## Create one with debootstrap

[create a debian docker image](https://docs.docker.com/develop/develop-images/baseimages/)


## Layer

A layer is a set of data you can add to another layer.
Together they can form an image.
You can think of it as the commit in a git history


![docker layers](/images/docker-filesystems-multilayer.png)

[source](http://docs.docker.com/terms/layer/#layer)


## Container

A container is a running image.


![docker layers](/images/docker-filesystems-multilayer.png)


## Dockerfile

A Dockerfile is a text document that contains all the commands you would normally execute manually in order to build a Docker image.

[example](https://github.com/indiehosters/docker-git/blob/master/Dockerfile)

[source](https://docs.docker.com/engine/reference/builder/)


## Registry

Docker Registry stores and distributes images centrally. It's where you push images to and pull them from.

[source](https://docs.docker.com/registry/)


https://hub.docker.com



## Illustration of Basics

Hands on!


## image/layer/registry/container

```
docker run alpine:3.12 echo hello world
```


## Dockerfile

```bash
cat > Dockerfile <<EOF
FROM alpine:3.12
CMD echo hello world
EOF

docker build -t myimage .
docker run myimage
```
