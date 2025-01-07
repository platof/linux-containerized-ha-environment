# To deploy the application using systemd service

## Prerequisites

- Node.js
- Systemd

```sh
  git clone https://github.com/platof/linux-containerized-ha-environment.git
   cd task1
```
### In the node-service.service file ensure to put in the right user, working directory and log directory and this file should be in systemd directory.

## Reload the service after creation of server.js and systemd service file
```bash
  sudo systemctl daemon-reload 
```
## Start the service
```bash
  sudo systemctl start node-service
```
## Enable the service
```bash
  sudo systemctl enable node-service
```
## Verfiy the service
```bash
  sudo systemctl status node-service
``` 
## Check logs for troubleshooting
```bash
  journalctl -u node-service
```
## Test application of browser
```bash
  http://<server-ip>:8080
```
## stop the service
```bash
  sudo systemctl stop node-service
```
## Example
```bash
  [Unit]
  Description=Simple Node.js HTTP Server
  After=network.target

  [Service]
  User=ubuntu
  WorkingDirectory=/home/ubuntu/my-node-service
  ExecStart=/usr/bin/node server.js
  Restart=always
  StandardOutput=file:/home/ubuntu/my-node-service/access.log
  StandardError=file:/home/ubuntu/my-node-service/error.log

  [Install]
  WantedBy=multi-user.target
```
### Troubleshooting
If you encounter port conflicts, ensure that no other services are using the same ports.
