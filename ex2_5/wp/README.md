## Setting up a Wordpress container

This project is a setup of a Wordpress system on a docker environment.

The official mysql docker image pages gives an example where the
docker compose confgurations are contained in a `stack.yml` file, in
that case docker compose is invocked with the following command : 

- `docker-compose -f stack.yml up -d`

- `docker-compose up -d` if the normal `docker-compose.yml` is used

To start up the wordpress appliction:

- `docker-compose up -d`

The service can then be accessed at http://localhost:9999 and the
relevant configuration undertaken. To check which files were changed
after confuguration, compose's *diff* command can is run.

-`docker diff $(docker-compose ps -q wordpress)`

A database dump can be created to save the contents of the databasefor
example when an upgrade is to be conducted,

-`docker exec -i $(docker-compose ps -q db) mysqldump mydb -uroot
 -pagoodpwd > dump.sql`

A handy command to stop and delete containers during the development
process:

- `docker-compose down`

Notably, stopping and deleting the containers does not erase the
volumes, if erasing the volumes is required these can be deleted with:

- `docker-compose down -- volumes

It is also possible to start one specific service listed in a
docker-compose file:

- `docker-compose up -d db` (will only start the database)

After configuring the Wordpress site, docker can be used to check for
the changes that have taken place:

- `docker diff $(docker-compose ps -q wordpress)`

The previous contents of the database can be reloaded using:

- `docker exec -i $(docker-compose ps -q db) mysql -u root -p agoodpwd
  < ./dump.sql`