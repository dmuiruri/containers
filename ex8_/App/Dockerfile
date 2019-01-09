FROM ubuntu:16.04

# Install and update ubuntu tools
RUN apt-get update && apt-get install -y curl

# Install nodes into image
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs

# Working dir /App
WORKDIR /App

# Install app dependencies
COPY package*.json ./
RUN npm install

# Copy the app source files
COPY . .

# Expose a port to serve the app
EXPOSE 3000

# Start the app on the launch of the container
CMD ["npm", "start"]

## Notes
## Command to run the application
#  docker run -d --rm -it --name speedtest -p 3000:3000 speedtest