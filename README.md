# vue-cli-docker-compose
A simple docker compose file to create a new vue-cli project on a host without a node installation (windows in my case)

## Simple
Using ebiven/docker-vue-cli this is a simple docker-compose file that mounts the PWD as the location where the new 
vue-cli generated project will be located. It is intended to be run with `docker-compose run ...`.  

If you want the new project to be generated at a different location change `docker-compose.yml` to mount the desired 
location to the container's /code like this:
```yaml
volumes:
  - <relative_desired_output_path_here>:/code
```

### Usage
> **Note:** This method requires an interactive terminal session with the Docker container and will only work if you have an 
interactive capable docker installation ([Docker for Windows](https://www.docker.com/docker-windows), 
[Docker for Mac](https://www.docker.com/docker-mac), 
[Linux](https://store.docker.com/search?offering=community&type=edition)). 
[Docker Toolbox](https://www.docker.com/products/docker-toolbox) will **not** work by default on Windows as it 
does not have interactive capabilities.

[webpack](https://github.com/vuejs-templates/webpack)
```commandline
docker-compose run web vue init webpack <project_name>
```
[webpack-simple](https://github.com/vuejs-templates/webpack-simple) 
```commandline
docker-compose run web vue init webpack-simple <project_name>
```

##### Example
```commandline
docker-compose run --rm web vue init webpack-simple <project_name>
Creating network "vueclidockercompose_default" with the default driver                                                

  This will install Vue 2.x version of the template.

  For Vue 1.x use: vue init webpack-simple#1.0 vue-django-channels

/bin/sh: 1: git: not found
? Project name <project_name>
? Project description <project_description>
? Author <your_name>
? Use sass? <yes/no>

   vue-cli · Generated "<project_name>".

   To get started:

     cd <project_name>
     npm install
     npm run dev.
```