FROM ubuntu:16.04

# Install and update ubuntu tools
RUN apt-get update && apt-get install -y curl

# Install nodes
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs

# The working directory where the app is copied
WORKDIR /App

# Install app dependencies
COPY package*.json ./

# Install the application
RUN npm install

# Copy the app's source files
COPY . .

# The port to serve the app
EXPOSE 8000

# Start the app at the launch of the container
CMD ["npm", "start"]

## Notes
# Build the image
# docker build -t nodesback .

# run the image with a file(logs) shared between container and host at the current working directory
# docker run -v $(pwd):/logs.txt -d --rm -it --name sixthex -p 8000:8000 nodesback

# Log into the container:
# docker exec -it sixthex bash