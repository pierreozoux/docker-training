# MultiStage build

Use the MultiStage build to create a discourse docker image, only with the web assets:
 - /home/discourse/discourse/public
 - /home/discourse/discourse/plugins

Use this docker image as base: https://hub.docker.com/r/libresh/discourse/tags

They will be serverd by nginx.

You can find the nginx config (/etc/nginx/nginx.conf) in this folder.