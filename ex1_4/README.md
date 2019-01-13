# Dockerfile

This section introduces a simple
[Dockerfile](https://docs.docker.com/engine/reference/builder/) that
**defines** an image from the ubuntu kernel.

The apt-get tool is further installed to facilitate installation of
other packages and tools. In this dockefile, wget, curl and emacs
(editor) are installed.

The Image's working directory is set to the root "/" and a shell
script is copied from the current working directory to the root of the
container.
