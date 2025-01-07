# To deploy the application using kubernetes and helm chart

## Prerequisites

- Kubernetes
- Helm

```sh
   git clone https://github.com/platof/linux-containerized-ha-environment.git
   cd task3
```
## The values.yaml file contains values which can be modified accordingly 

## create a namespace for the appliction
```bash
  kubectl create namespace web
```
## To deploy the application using helm chart
```bash
  helm install node-app ./node-app -n web
```
## To check the running application pods
```bash
  kubectl get pods -n web
```
## To check the service type is loadbalancer
```bash
  kubectl get svc -n web
```
## To check the ingress of the application
```bash
  kubectl get ingress -n web
```
## To test the application on browser
```bash
  http://<loadbalancer-ip>
```
## To get logs of the application
```bash
  kubectl logs <pod> -n web
```
## To perform rolling update deployment, update the image in the values file and run the following command
```bash
  helm upgrade node-app ./node-app -n web
```
## To verify the rolling update
```bash
  helm status node-app -n web
```
## Inspect the deployment
```bash
  kubectl -n web get deployment node-app -o yaml
```
## check the pods
```bash
  kubectl get pods -l app=node-app -n web
```
## To delete the application
```bash
  helm uninstall node-app -n web
```
