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

## composer
- `docker-compose.yml` file in site root

```yml
jekyll:
  image: jekyll/jekyll:pages
  command: jekyll serve --watch --livereload
  ports:
    - 4000:4000
    - 35729:35729
  volumes:
    - .:/srv/jekyll
```

- To ignore file in Jekyll add `docker*` in `.gitignore`
- `docker-compose up --remove-orphans` start container
-  script in `<head>`

```liquid
{% if site.environment == "development" %}
<script> document.write('<script src="//' + (location.hostname || 'localhost').split(':')[0] + ':35729/livereload.js?snipver=1"></' + 'script>')</script>
{% endif %}
```

- `.bash_aliases` `alias dcu="docker-compose up --remove-orphans"`

## composer alias

Script for `.bash_aliases` and source with `. ~/.bashrc`

```bash
# Docker
dcu() {
	if [ -f ".gitignore" ]; then
		if ! grep -q "docker*" ".gitignore"; then
			echo "docker*" >> .gitignore
		else
			echo ".gitignore already contain docker*"
		fi
		if [ -f "docker-compose.yml" ]; then
		    docker-compose up --remove-orphans
		else 
		    echo "jekyll:
  image: jekyll/jekyll:pages
  command: jekyll serve --watch --livereload
  ports:
    - 4000:4000
    - 35729:35729
  volumes:
    - .:/srv/jekyll" >> docker-compose.yml
	    docker-compose up --remove-orphans
		fi
		else
			echo ".gitignore not present"
		fi
}
```
