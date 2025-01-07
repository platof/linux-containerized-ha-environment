# Management and Troubleshooting of a Talos-based Cluster
Talos provides a command-line tool called talosctl. This tool is used for the management, troubleshooting and bootstraping talos clusters.

```sh
   git clone https://github.com/platof/linux-containerized-ha-environment.git
   cd task5
```

## Talos cluster Management 
Talos nodes require a Configuration file to define their role and settings
To modify configuration for a node
```bash
  talosctl apply-config --insecure -n <node-ip> --file node.yaml
```
Talos uses declarative YAML files for configuration. To update a configuration 
```bash
  talosctl edit machineconfig --node <node-ip>
```
## To view the node configuration
```bash
  talosctl get nodes --nodes <node-ip>
```
## To reboot a node
```bash
  talosctl reboot --node <node-ip>
```
## Talos cluster troubleshooting
To check the status of the Nodes and Pods
```bash
  kubectl get nodes
  kubectl get pods -A
```
## for deeper insights
```bash
  talosctl health --nodes <node-ip>
```
## To Analyze logs
```bash
  talosctl logs --nodes <node-ip>
  kubectl logs <pod_name> -n <namespace>
```
## Inspect node configuration
```bash
  talosctl get config --nodes <node-ip>
```

## To upgrade a node
```bash
  talosctl upgrade --nodes <node-ip> --image ghcr.io/siderolabs/installer:<VERSION>
```

## deploying a sample workload
```bash
  kubectl apply -f nginx-deployment.yaml
```
## verify the deployment
```bash
  kubectl get pods
  kubectl get svc
```
## accessing the service by noting the External IP address
```bash
  kubectl get svc nginx-service
```
## access the service
```bash
  curl http://<EXTERNAL_IP>
```
