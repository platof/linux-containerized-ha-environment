# Troubleshooting log

## 1. Checked Service Logs to get more information about the issue
```bash
  journalctl -u node-service 
```

## 2. Validated File path and Modified config to the correct path
```bash
ls -al /path/to/server.js
```
## 3. Configured Logging 
Added StandardError and StandardOutput to capture logs for future Troubleshooting

## 4. Restarted service 
```bash
sudo systemctl daemon-reload
sudo systemctl restart node-service
```
## 5. Verified service
```bash
 systemctl status node-service
```