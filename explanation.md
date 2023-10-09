1:Choice of base image
#react-app and node js backend; I used the node:20-slim since is only comes 
#with just the necessary packages to have the two apps up and running
#this prevents un-necessary packages that otherwise might make the images 
#Huge in size.

2:Docker directive used in creation and running of each container
#since both the apps have the base image being the same i.e Node js the
#commands are pretty much similar.
#Dockerfile(both frontend and backend): The dockerfile sets the working directory, copies the package.json
# and package-lock.json files to instapp dependencies efficiently, copies
#the application code, exposes the necessary port (5000-backend) and 
#(3000-frontend), then it specifies the command to start the app (backend 
#and frontend have same start command) due to same base image

3:Docker-compose Networking
#e-commerce-network: The docker-compose file which merges the both images
#and creates a container for both apps also creates a network to map
#the three resources together the network is defined under the custom
#bridge network. By connecting all the containers in the network allows
#them to communicate with each other using service names as hostnames
#Both containers have exposed different ports for connection with 
#backend exposing port 5000 while frontend has exposed port 3000
#this is to allow connection to those two app

4:Docker-compose Volume Definition and usage:
#There is a volumen named 'mongo-data' for the Mongodb container. The volume
#persists data and ensures that the data is stored in mongoddb container 
#'/data/db' directory and is preserved even if the container is stopped or
# removed

