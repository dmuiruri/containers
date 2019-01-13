# REDIS

Redis is an in-memory data structure store that can be used in a
variety of ways to achieve temporal storage capabilities that may be
required in an application. It can be used as a database, cache (to speed up application response) as well as message broker system. More details on REDIC can be found from the [redis project](https://redis.io/) site.

## Adding Redis to the YAML file

In this section, we setup Redis an a cache for the backend and that
speeds up the application since the backend server first checks for
requested resource from the cache before making a API call to the
external resources.

A redis service is added to the docker-compose.yml file and the
applications default port 6379 is exposed for accessing the service.
