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
  tail -f /home/ubuntu/my-node-service/access.log
  tail -f /home/ubuntu/my-node-service/error.log
```
## Test application of browser
```bash
  http://<server-ip>:8080
```