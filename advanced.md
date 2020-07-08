# advanced



## Namespace

Hands on!

 - NET
 - PID
 - USER
 - Mount
 - UTS




## Multiprocess

2 schools:


## 12factor app

one container - one process


## VM school

supervisord
init system


## Conclusion

 - supervision of processes
 - sshd? seriously?
 - postfix case, couldn't avoid multiprocess
 - forking daemon like HAproxy
 - pod



## User

You should specify the USER that execute the command and own the data.


If you don't it is fine, Namespace translations!
(To configure in docker deamon)



# Logs


## Stdout/Stderr

The recommended!


## get logs from a container

Hands on!


## Special Log file

```
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log
```

Like on [nginx](https://github.com/nginxinc/docker-nginx/blob/master/stable/alpine/Dockerfile#L133-L134)


## Log file

You could mount a host file where your process will log


## log facility

complicated


### 1st way

mount /dev/log from host/another container


### 2nd way

expose the UDP port to inside the container


## If sending logs to stdoud/stderr

Then you can specify a [log driver](https://docs.docker.com/config/containers/logging/configure) to docker:
 - syslog
 - journald
 - gelf



## Monitoring

docker can 'monitor' processes for you

--always-restart flag

Note:
That's what some people don't like


### do not monitor the client

`docker run` is just an API call.



## Central logging and Monitoring

 - ELK
 - Prometheus
 - [Netdata](https://github.com/firehol/netdata)
 - https://github.com/uschtwill/docker_monitoring_logging_alerting



# local storage

how to manage locally images, containers and volumes!


Hands on!

```
docker images
docker ps
docker volumes
```


https://microblog.pierre-o.fr/2015/i-know-how-to-clean-docker

https://github.com/spotify/docker-gc



# docker exec

execute a process on the side of the main process.

Hands on!
