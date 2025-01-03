# Helm chart was used to create the deployment

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
## To upgrade the release after modification of values.yaml file
```bash
  helm upgrade node-app ./node-app -n web
```

## To check the type of deployment and replicas
```bash
  kubectl -n web get deployment node-app -o yaml
```
## To delete the application
```bash
  helm uninstall node-app -n web
```
