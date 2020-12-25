# Use NodeJS base image
FROM node:13
# Create app directory in Docker
WORKDIR /usr/src/app
# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./
# Install dependencies in Docker
RUN npm install
# Install Ionic Framework's Command Line tools
RUN npm install -g ionic
# Compile the files into static files
COPY . .
# Set the API’s port number
RUN ionic build
# Copy app from local environment into the Docker image
EXPOSE 8100
# Define Docker’s behavior when the image is run
CMD ["ionic", "serve"]