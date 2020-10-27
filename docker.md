# docker

## list
- `docker ps` list running
- `docker ps -a` list all
- `docker system prune (y)` remove containers, networks, images and build cache

## run
- `docker start -a -i <name/id>` start attach interactive
- `docker kill <name/id>` allow graceful stop
- `docker stop <name/id>` need `start` or `restart`
- `docker pause <name/id>` pause
- `docker unpause <name/id>` unpause

## jekyll
- `docker run --name <name> --volume="$PWD:/srv/jekyll" -p 4000:4000 -it jekyll/jekyll:3.8 jekyll serve --livereload --incremental`
