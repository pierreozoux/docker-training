# Runtime

```
docker run [options] registry/image:tag [command]
```

options:
 - -p [[IP]:[HOST_PORT]]:CONTAINER_PORT
 - -v /host/path:/container/path
 - --name
 - -it
 - --rm
 - -d

[reference](https://docs.docker.com/engine/reference/run/)



## some basic docker commands

 - ps - list container
 - inspect - get details about a container


## Exercise!

```
cd exercises/runtime
```



## Advanced run options

 - --user
 - --network
 - -e/--environment 
