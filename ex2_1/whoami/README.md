# Scaling Containers

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

The file *docker-compose_vs.yml* is the intitial configuration used to
run the service in its basic form.

*docker-compose.yml* configuration introduces of a proxy service to
 manage multiple instances running. In a server setting, a
 load-balancer would be more appropriate.

With a proxy service configured the containers are started in the
typical way:

`docker-compose up -d --scale whoami=3`

```
curl localhost:80
whoami $ curl localhost:80
<html>
<head><title>503 Service Temporarily Unavailable</title></head>
<body bgcolor="white">
<center><h1>503 Service Temporarily Unavailable</h1></center>
<hr><center>nginx/1.14.1</center>
</body>
</html>
```

