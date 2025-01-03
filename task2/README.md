# To build and deploy the application using docker-compose 
## Build and tag the code using the Dockerfile
```bash
  docker build -t platof/node-server:<tag> .
```
## Push the tagged image to the docker registry
```bash
  docker push platof/node-server:<tag>   
```
## Run the docker-compose to start the services 
```bash
  docker-compose up -d 
```
## To view all running services
```bash
  docker-compose ps -a 
```
## To access the application on browser
```bash
  http://<server-ip>
```
## To check the logs
```bash
docker-compose logs node-app
docker-compose logs nginx
```
## To stop the services 
```bash
  docker-compose down 
```
