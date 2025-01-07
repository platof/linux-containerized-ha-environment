# To deploy the application using docker-compose 

## Prerequisites

- Docker
- Docker Compose

```sh
   git clone https://github.com/platof/linux-containerized-ha-environment.git
   cd task2
```
## Run the docker-compose to start the services 
```bash
  docker-compose up -d 
```
## Ensure the services are running
```bash
  docker-compose ps
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
**Note:**
## The docker image was build and tagged  using the Dockerfile
```bash
  docker build -t platof/node-server:<tag> .
```
## The tagged image was pushed to the docker registry
```bash
  docker push platof/node-server:<tag>
```
### Troubleshooting
If you encounter port conflicts, ensure that no other services are using the same ports. You can change the ports in the docker-compose.yml file if needed.
