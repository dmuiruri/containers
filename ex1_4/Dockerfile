# Get the ubuntu kernel version 16.04
FROM ubuntu:16.04

# Ubuntu setup by updating the apt-get tool
RUN apt-get update -y
RUN apt-get install -y wget
RUN apt-get install -y curl wget
RUN apt-get install -y emacs

# Working directory
WORKDIR /

# Copy the script from local to root of the container
COPY sc.sh /

# The command to run when the container is up and running.
