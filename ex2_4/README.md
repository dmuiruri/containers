# Introduction

In this section three containers are used to set up the service, the
three containers run as the frontend, backend and an additional
machine learning container that provides a training model.

When setting up a service with multiple containers (micro services) we
can configure the dependency structure to ensure that services that
depend on others are started after the dependencies are up and
running. The `depends_on` config indicates the dependency between
services, docker-compose starts services following the dependency
order.

Volumes can also be shared by multiple services is similar resources
are accessed across services.