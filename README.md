# Demo app - developing with Docker
This demo app shows a simple user profile app set up using:

- index.html with pure js and css styles
- nodejs backend with express module
- mongodb for data storage

All components are docker-based

# To start the application
sudo docker pull mongo
sudo docker pull mongo-express

To start the application
Step 1: Create docker network
sudo docker network create mongo-network

Step 2: start mongodb
sudo docker run -d --name mongodb  --network mongo-network -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -eMONGO_INITDB_ROOT_PASSWORD=password  mongo

(last mongo means the image that we want to create an image from it)


Step 3: start mongo-express
sudo docker run -d --name mongo-express --net mongo-network  -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express

(-e ME_CONFIG_MONGODB_SERVER=mongodb : uses the mongodb container as a database server)   

Step 4: open mongo-express from browser
http://localhost:8081

Step 5: create user-account db and users collection in mongo-express
Step 6: Start your nodejs application locally - go to app directory of project
Step 7: Access you nodejs application UI from browser

http://localhost:3000



