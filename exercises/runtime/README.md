# Start a web server in a container

 - start a (small) nginx container (use docker run)
 - list running containers
 - inspect the nginx container (`docker inspect`)
  - with the container name
  - with the container hash
 - curl the default nginx html page
  - with host port mapping (-p)
  - with container IP (use inspect to get local IP)
 - mount the current index.html instead of the default one (situated in /usr/share/nginx/html) (-v)
 - expose the nginx to the Private IP of your host on the port 80
 - try to reach your peer web server! (if training is local)

# Help

Use the Hub luke:

https://hub.docker.com

`docker help run`

http://devdocs.io/docker~1.12/engine/reference/commandline/run/index
https://docs.docker.com/engine/reference/run/
