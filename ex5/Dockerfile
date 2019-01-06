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

# Install the application in development mode
RUN npm install

# Copy the app's source files
COPY . .

# The port to serve the app, can be bound to the host on the same or different port
EXPOSE 5000

# Start the app at the launch of the container
CMD ["npm", "start"]


# The app can be accessed via
# docker run -d --rm -it --name fifthex -p 5000:5000 nodes