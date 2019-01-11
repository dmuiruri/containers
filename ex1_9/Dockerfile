FROM continuumio/anaconda3

# Ubuntu setup by updating the apt-get tool
RUN apt-get update -y && apt-get install -y curl wget

# Install editor
RUN apt-get install -y emacs


# Start python
CMD ["ipython"]


### ======== Notes ======== ###

# TODO: Installing anaconda manually fails, specifically "/bin/sh:
# 1:conda: not found" error is indicated when running the Dockerfile
# with the instructions below. Continuunmio provides an official image
# containing the anaconda environment

# FORM ubuntu:latest
# RUN wget https://repo.continuum.io/archive/Anaconda3-2018.12-Linux-x86_64.sh
# RUN bash Anaconda3-2018.12-Linux-x86_64.sh -b
# RUN rm Anaconda3-2018.12-Linux-x86_64.sh

# Set path to conda
# ENV PATH /home/ubuntu/anaconda3/bin $PATH

# Updating Anaconda packages
# RUN conda update conda
# RUN conda update anaconda
# RUN conda update --all
