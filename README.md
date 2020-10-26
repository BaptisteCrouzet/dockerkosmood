# A docker system for Kosmood

The aim of this docker is to be able to run the Kosmood's code easily whitout losing time in any configuration.

## Prerequisities

* Docker [[installation link](https://docs.docker.com/get-docker/)]
* Docker-compose [[installation link](https://docs.docker.com/compose/install/)]

Add the kosmood project to the right directory : `git clone https://github.com/Incubateur-Web/Kosmood.git www`

## Structure

`data` folder is the data where are stored and persisted the datas, the files belonging to MySQL.
`docker` folder contains Dockerfiles and configuration files for each containers.
`www` folder contains the code of the project.
`Makefile` file containing some useful commands.

## Services

* PHP 7.4 => its associated php.ini file is copied when building the image, see `/docker/php/php.ini`.
* MySQL 8 => fastest version of MySQL
* NGINX => same as PHP, configuration is copied on building, see `/docker/nginx/` folder.
* *beekeeper-studio* => this container is not up yet but you can use the installable software here : [https://www.beekeeperstudio.io/](https://www.beekeeperstudio.io/).

## Available commands

Some commands are made easier with the Makefile's help :

```=bash
make {command}
```

See Makefile for more details :

* `make build` -> Build the dockers containers, all and hard
* `make up`-> launch the containers for the project
* `make up-build`: -> build the containers and launch
* `make up-silent`-> launch in background
* `make sf-terminal`-> enter with the terminal inside the symfony's container

## Run the Kosmood project

1. Clone kosmood code
2. Run `make build`
3. Run `make up`
4. Install kosmood dependencies
5. Set up the DB and access it with the help of PHPMyAdmin, Adminer or Beekeeper-studio. Port to use 3306 and set up credentials inside `docker-compose.yaml` line 8 to 11.
6. Clear cache
7. Access the application on [http://localhost:80](http://localhost:80)
