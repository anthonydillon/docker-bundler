# canonicalwebteam/bundler docker image

A docker image for automatically managing ruby dependencies with a [bundler Gemfile](http://bundler.io/gemfile.html).

This image will detect changes in the Gemfile and update dependencies before running any commands.

## usage

For example, in a [Jekyll](https://jekyllrb.com/) project:

``` bash
docker run \
  --tty --interactive                               `# Attach an interactive terminal`  \
  --user $(id -u):$(id -g)                          `# Run everything as the current user`  \
  --volume `pwd`:`pwd` --workdir `pwd`              `# Run in the current working directory`  \
  --volume bundler-dependencies:/bundler            `# Persist ruby dependencies in a docker volume`  \
  --publish 4000:4000                               `# Attach port 4000`  \
  canonicalwebteam/bundler jekyll serve -H 0.0.0.0  `# Run the jeklyll server`
```
