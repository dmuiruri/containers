# Docker Compose

We can scale an application using docker. Before scaling the
application, the ports configuration entry needs to be edited to avoid
binding an application's port at the host since multiple containers
cannot be bound to the same host port.
```
ports:
 - 8000
```

The command to run multiple containers as shown below will run three
containers from the whoami image. 

 `docker-compose up -d whoami=3`

Each container will run on port 8000 which are mapped in random order
at the host side. To check where each running container is mapped,
compose's port command can be run as follows.

`docker-compose port --index 1 whoami 8000`
`0.0.0.0:32774`
