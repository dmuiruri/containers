# Container dependencies

In this section three containers are used to set up an application,
the three containers run as the frontend, backend and an additional
machine learning container that provides a training model.

When setting up a service with multiple containers (*micro services*)
we can configure the dependency structure to ensure that services that
depend on others are started after the dependencies are up and
running. The `depends_on` config indicates the dependency between
services, docker-compose starts services following the dependency
order.

**Docker Networking**: Note that only the front end exposes an access
port in its Dockerfile, the backend does not expose the port its
running on but other containers(specifically the frontend) can still
access the backend using the given service name and the dependency
structure of the service. The frontend will therefore be able to
connect through `backend:5000`.

Volumes can also be shared by multiple services allowing containers to
access the same resources across the service.

Recall that if a service's port is not mapped to a
specific port number on the host, the port is mapped automatically and
can be obtained by running the command 