# NGINX

In this project, an nginx reverse proxy server is set up to allow the
service to process access requests in a rather intuitive
manner. [Nginx](https://hub.docker.com/_/nginx) is an open source
reverse proxy server for multiple protocols (HTTP, HTTPS, SMTP, POP3,
and IMAP), as well as a load balancer, HTTP cache, and a web server
(origin server).

With a proxy server in place, we don't need to `expose` the ports that
the frontend and backend are running on. The proxy is setup such that
visiting the link http://localhost/ leads to the front end withouth
the need to indicate at which port the frontend is being served on.
