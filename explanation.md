##Choice of image on which to build each container
   - I chose node alpine since the alpine is often cited  for its incredibly small image size.
...
##Docker file directives
##backend
  FROM node:16.18.1-alpine- base image to be pulled from docker hub
  WORKDIR /usr/src/app/backend- defines the working directory
  COPY package*.json ./ - copies the package into the image
  RUN npm install- install dependencies
  COPY . .- copies the rest of your application's code into the image
  EXPOSE 5000-Exposes the container on port 5000
  CMD [ "npm", "start" ]- sets the command to be executed when running the image
...
##client
  FROM node:16.18.1-alpine- base image to be pulled from docker hub
  WORKDIR /usr/src/app/backend- defines the working directo
  COPY package*.json ./ - copies the package into the image
  RUN npm install- install dependencies
  COPY . .- copies the rest of your application's code into the image
  EXPOSE 5000-Exposes the container on port 5000
  CMD [ "npm", "start" ]- sets the command to be executed when running the image
  