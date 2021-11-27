# Website [![Build Status](https://travis-ci.org/moritzschueler96/moritzschueler96.github.io.svg?branch=main)](https://travis-ci.org/moritzschueler96/moritzschueler96.github.io)

## Install Ruby

```bash
sudo apt-get install build-essential patch ruby-dev zlib1g-dev liblzma-dev
```

## Write

```bash
bundle exec jekyll post "My New Post"
```

## Run

```bash
bundle exec jekyll serve --livereload
```

## Run with Docker

```bash
docker run \
  --volume="$PWD:/srv/jekyll" \
  -p 4000:4000 -p 35729:35729 \
  -it jekyll/jekyll \
  jekyll serve --livereload
```
