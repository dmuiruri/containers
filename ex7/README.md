## Instructions 

In this part the front end container is connected to the backend
container. The front end container is configured to access the API
resources provided by the backend. The backend is also configured to
allow the specific frontend client to access the API resources.

These configurations are passed to the docker run command.

Run the backend bind the container's port 8000 to the host's port 8000
allowing for access the container through the local host. The
environment variable `FRONT_URL` allows the backend to process Cross
Origin Requests `(CORS). When properly configured, the parameter
`Access-Control-Allow-Origin http://localhost:5000` can be seen from
the network tab in the browsers developer console.

`docker run -v $(pwd)/logs.txt:/App/logs.txt -d --rm -it --name sixthex -p 8000:8000 -e FRONT_URL="http://localhost:5000" nodesback`

Run the frontend at port 5000 and bind the containers port to the
host's port 5000. Set the environment variable API_URL that instructs
the container where access the resource.

`docker run -d --rm -it --name fifthex -p 5000:5000 -e API_URL="http://localhost:8000" nodes`

