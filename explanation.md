##Choice of image on which to build each container
   - I chose node alpine since it is  often cited  for its incredibly small image size

##Docker file directives
##backend
  FROM node:16.18.1-alpine- base image to be pulled from docker hub
  WORKDIR /usr/src/app/backend- defines the working directory
  COPY package*.json ./ - copies the package into the image
  RUN npm install- install dependencies
  COPY . .- copies the rest of your application's code into the image
  EXPOSE 5000-Exposes the container on port 5000
  CMD [ "npm", "start" ]- sets the command to be executed when running the image

##client
  FROM node:16.18.1-alpine- base image to be pulled from docker hub
  WORKDIR /usr/src/app/backend- defines the working directory
  COPY package*.json ./ - copies the package into the image
  RUN npm install- install dependencies
  COPY . .- copies the rest of your application's code into the image
  EXPOSE 5000-Exposes the container on port 5000
  CMD [ "npm", "start" ]- sets the command to be executed when running the image

##Docker compose Networking
  Containers exit with code 0 
    - Added `tty:true` to the backend and client definitions which enables the containers to stay running.
  Containers exit with code 1
  
## Docker compose volume
  Added a volume in the mongodb to ensure data persistance.

## Git workflow
  Used git commit and push to push to github
  Cloned the repository to my local machine

##Good practices such as docker image tags
  Naming of docker images with tags

  #IP4

  I created the K8s folder to host the manifest files. The manifest files created include both the client and backend-deployment.yml. 
  Created the service yaml files to create connection between the client and the backend. Created the mongo-srvc.yml to deploy the mongo service. 
  The deployment files consist of the metadata, which consists of the labels, annotations and names about the deployment, the spec, declares the desired state and characteristics i want to have, eg number of replicas, image name, all ontainer information the pod should have, the container image info, port information, ENV variables and the command arguments.
  The service files are responsible for enabling network access to the set of pods.

  Created a k8s cluster on google cloud and deployed  the files using the kubectl command. The images used to create the containers were the images from the 2nd IP. 

  The containers keep crashing, hence unable to share the website url but still working on it

  