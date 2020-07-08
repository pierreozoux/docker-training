# simple bridge

Create a simple bridge network called `discourse` and inspect it.

# attach to a network

Start a (small) redis container and attach it to the network.
(Give it `redis` name)

Inspect the redis container, and what do you see?

# run in a network

Start a (small) postgres container in the network.
(use these env: -e POSTGRES_USER=discourse -e POSTGRES_DB=discourse -e POSTGRES_PASSWORD=discourse)
(Give it `postgres` name)

Inspect it, and describe what you see.

# Discourse

Start an interactive `bash` in your fat dicourse image, in the network, and start it with the user `discourse`.
Try to ping the 2 previous containers by name or hash.
What do you see?

# let's start it!

```
rake db:migrate assets:precompile
bundle exec rails server -b 0.0.0.0
```

(change the puma conf in your docker to avoid deamonizing)
