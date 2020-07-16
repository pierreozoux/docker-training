# Redis

Create a simple docker-compose file that start a small redis.

# Network

Create an isolated network, called backend,  and put the redis in it.
Create another isolated network called web.

# Postgres

Add a small postgres container to the network.

# Discourse

Add our disourse service to the web and backend network.

# Make sure it works

Exec into the discourse container with the discourse user and make sure you can compile assets.

# volumes and ports

Add volumes to persist the db and the assets, and expose discourse to the port 80 of your host.
