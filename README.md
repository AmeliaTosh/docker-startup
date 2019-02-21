# Docker local debugging

Quick little run through of how to set up a docker container to run locally to debug any Pipeline scripts you may be running.

h2.Setup

1) Clone repo

2) Open the [Dockerfile](Dockerfile) and change the `DOCKER_IMAGE` value to the image you wish to use (e.g. `selenium/standalone-chrome`).

3) Open the [docker-compose.yml](docker-compose.yml) and make the following changes:
    -   Change `DOCKER_IMAGE_BASE` to whatever image you are using (from the `Dockerfile`)
    -   Change `../RELATIVE_DIRECTORY_TO_COPY` to the directory you wish to copy into the Docker container for debugging.

4) Build the docker container with `docker-compose build`

5) Start-up the docker container with `docker-compose up -d`

6) SSH into the docker container with `docker-compose exec NAME_OF_IMAGE bash`

7) Run any scripts you need to run from `/usr/lib/DIRECTORY_YOU_COPIED`
