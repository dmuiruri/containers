# React and docker 

This is a React app that implements a simple speedtest game, the main
goal is to setup a docker container with the relevant dependencies to
support running the app from a docker container.

### Building the image
Run the command from the same directory containing the Dockerfile
`docker build --tag speedtest .`

### Running the app
To run the app in a dockerized environment, run the command:
`docker run -d --rm -it --name speedtest -p 3000:3000 speedtest`
Once the container is running successfully, the application can be
accessed via http://localhost:3000