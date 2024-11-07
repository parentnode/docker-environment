# parentNode Webstack / Docker environment

This is a repo for the parentNode webstack docker development environment which allows you to run a containerised version of the production environment for your convenient local development.

The php-8.2-apache-extensions folder contains the Dockerfile for building the customized php-8.2-apache image used for the environment. On top of that we are using the default MariaDB and the Redis images.

This will typically be deployed in a custom project version, using the docker-compose.yml file in this repos as a blueprint. The currently included one is customised for use with our janitor development site.


To run this container successfully, follow these steps:

1: Clone the janitor_parentnode_dk project from Github (https://github.com/parentnode/janitor_parentnode_dk) to your local computer.


2: Then use the following command to start container stack:

PROJECT_PATH=/#PATH-TO-CLONED-REPOS#/janitor_parentnode_dk docker compose up -d

Fx, if you cloned the repos to /Users/martin/Sites/janitor_parentnode_dk:
PROJECT_PATH=/Users/martin/Sites/janitor_parentnode_dk docker compose up -d


3: Go to http://janitor.local:8080/janitor/admin/setup in your browser to start the Janitor setup.


With minor adaptations you can make it run any parentNode webstack based project.


# Building

Maintainers should see [MAINTAINERS.md](MAINTAINERS.md).

### To build:

cd php-8.2-apache-extensions
docker build --tag "php-8.2-apache" .


### To tag:

docker tag php-8.2-apache parentnode/php-8.2-apache:latest


### To push

docker push parentnode/php-8.2-apache:latest
