# Using docker-compose

Compose is used to facilitate the running of an application with
multiple containers. Without using compose, running an application
with multiple containers means issuing individual commands to run each
container, this approach becomes quickly tedious as the number of
configuration options and flags required for a container increase in
number. Compose simplifies running multiple containers by making use
of a `YAML` file where the configurations are entered. Once a service
is "composed" the application can be created and started with a single
command

In order make use of compose on an application,

- A working `Dockerfile` (A Dockerfile defines an application
  environment) is required

- Create a `docker-compose.yml` file that defines the services that
  comprise the application

- Run the application using `docker-compose up -d`
