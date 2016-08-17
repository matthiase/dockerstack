# Docker Stack

An example application to demonstrate using Docker to set up a full-stack development environment. The application assumes a working Docker installation and is comprised of three separate services:

* db - a PostgreSQL database instance
* api - an API implemented in Ruby on Rails
* web - a front-end web application using Node

## Bootstrapping with Docker Compose

To build all of the Docker images:
```
docker-compose build
```

To start the containers:
```
docker-compose up
```

Create the database and run migrations with:
```
docker-compose run api rake db:setup
```

This project is still a work-in-progress and the sevices are not hooked together yet. For now all you can really do is visit the web and api urls to confirm the servies are running:  

Web
```
open http://localhost:8080
```

API
```
open http://localhost:3000
```

## Useful Docker Commands

To list all containers:
```
$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                    NAMES
7a0922e423dd        dockerstack_api     "bundle exec rackup -"   41 seconds ago      Up 40 seconds       0.0.0.0:3000->3000/tcp   dockerstack_api_1
7c4f51fd5fae        postgres            "/docker-entrypoint.s"   42 seconds ago      Up 41 seconds       5432/tcp                 dockerstack_db_1
```

To enter a container:
```
docker exec -it <CONTAINER ID OR NAME> /bin/bash
```

To remove a container:
```
docker rm <CONTAINER ID or NAME>
```

To remove all containers:
```
docker rm `docker ps -aq`
```

To list all images:
```
docker images -a
```

To delete a specific image:
```
docker rmi <IMAGE ID or NAME>
```

