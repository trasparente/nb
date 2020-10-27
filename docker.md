# docker

## containers
- `docker ps -a` all
- `docker ps` running
- `docker system prune` remove containers, networks, images and build cache

## jekyll
- `docker run --volume="$PWD:/srv/jekyll" -p 4000:4000 -it jekyll/jekyll:3.8 jekyll serve --livereload --incremental`
