# Docker-compose

Compose is used to facilitate the running of an application with
multiple containers. Without using compose, running an application
with multiple containers means issuing individual commands to run each
container, this approach becomes quickly tedious as the number of
configuration options and flags required for a container increase in
number. Compose simplifies running multiple containers by making use
of a `YAML` file where the configurations are entered. Once a service
is "composed" the application can be created and started with a single
command

In order make use of compose in an application,

- A working `Dockerfile` (A Dockerfile defines an application's
  environment) is required

- Create a `docker-compose.yml` file that defines the services that
  comprise the application

- Run the application using `docker-compose up -d`

Further details of docker compose can be obtained from the
[documentation](https://docs.docker.com/compose/overview/#features) as
well as the reference for various `Versions` of the [Compose
File](https://docs.docker.com/compose/compose-file/) which differ in
syntax.

## Running an application with compose

In reference to the `YAML` in this repo, an application with frontend
and backend services in different containers is run using docker
compose. The frontend and backend are contained in parts \ex1_5 and
\ex1_6 respectively. The `build` instruction indicates where the
Dockerfile used to build an image is located relative to the
docker-compose file.
