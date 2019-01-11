## Instructions

In this part, the frontend container is connected to the backend
container, allowing for the backend to service API calls from the
frontend application. The backend is configured to allow the specific
frontend client to access the API resources.

These configurations are passed through the docker run command.

### Backend
Run the backend and bind the container's port 8000 to the host's port
8000, allowing for access to the container through
http://localhost:8000. The environment variable `FRONT_URL` allows the
backend to process Cross Origin Requests `(CORS)` from the localhost's
port 5000. When properly configured, the parameter
`Access-Control-Allow-Origin` can be observed to be set to
`localhost:5000` from the network tab in the browser's developer
view. The backend app was cloned from this
[repo](https://github.com/docker-hy/backend-example-docker).

`docker run -v $(pwd)/logs.txt:/App/logs.txt -d --rm -it --name sixthex -p 8000:8000 -e FRONT_URL="http://localhost:5000" nodesback`

### Frontend

Run the frontend at port 5000 and bind the containers port to the
host's port 5000. Set the environment variable API_URL that instructs
the container where to access the API resource. The frontend app was
cloned from this
[repo](https://github.com/docker-hy/frontend-example-docker). If the app runs correctly, it can be accessed at http://localhost:5000

`docker run -d --rm -it --name fifthex -p 5000:5000 -e API_URL="http://localhost:8000" nodes`
