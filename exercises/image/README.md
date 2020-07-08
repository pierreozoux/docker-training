# Build an immutable docker image

Build an nginx docker image with your personal index.html.
(default index.html in nginx is located in /usr/share/nginx/html)
(You'll need FROM and COPY)

help:
http://devdocs.io/docker~1.12/engine/reference/builder/index
https://docs.docker.com/engine/reference/builder/

# Build an image for echo (optional)

Understand differences between ENTRYPOINT and CMD

The objective is to build an image that would copy current behaviour of "echo" command.

It should by default echo "Hello".
If we pass arguments, it would echo what we pass.

```
docker run echo
Hello
docker run echo toto
toto
```

# Build the beginning of a discourse docker image

1. clone the git into a new folder:

```
git clone https://github.com/discourse/discourse.git
git checkout v2.4.5
```

(commit while progressing to make sure you track your progresses)

2. create the dockerfile based on `ruby 2.6.6`

Here are the instructions to install discourse in a fresh debian environment:
Intall the project in the folder discourse in the home of user discourse.
(Yes, you need to create the user discourse)

Add latest nodejs repo in debian:

```
curl --silent --location https://deb.nodesource.com/setup_10.x | bash -
```

Intall Following building dependencies (`apt-get update && apt-get install -y`):
```
autoconf
advancecomp
libbz2-dev
libfreetype6-dev
libjpeg-dev
libjpeg-turbo-progs
libtiff-dev
pkg-config
```

Install the following dependencies:

```
ghostscript
gsfonts
imagemagick
jhead
jpegoptim
optipng
libxml2
nodejs
```

Install the following node packages:
```
npm install svgo uglify-js -g
```

Configure bundle and install gems:
```
gem update --system
gem install bundler --force
bundle config build.nokogiri --use-system-libraries
bundle install --deployment --without test --without development --retry 3 --jobs 4
```

The application uses 3 env variable to configure itself:
```
DISCOURSE_DB_HOST
DISCOURSE_DB_PASSWORD
DISCOURSE_REDIS_HOST
```

The command to start the project is:
```
bundle exec rails server -b 0.0.0.0
```

Build it with the tag `fat`!

Good luck!

(Write down the size and the number of layers of this image)

(There are still many things missing, but you get the idea.)

# Size does matter!

And now, how to reduce the size of it?
(copy the old image to Dockerfile.fat, and work on the Dockerfile)
(when you build it tag it `compacted`)

(Write down the size and the number of layers of this image)

# Side note

Read the doc

What is the first line you see when you build?
Can you increase the speed of your build?
(dockerignore is your friend!)
