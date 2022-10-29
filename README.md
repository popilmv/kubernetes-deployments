# kubernetes-deployments
Precontition: 
1. You must have a cluster in Google Cloud
2. Through the CLI or any other method, you must connect to the cluster
3. There should be a kubectl command

This repository contains files yaml for deployment, **service**, create own **namespace** and **ingress**
Use the next command to deploy:
```
kubectl apply -f namespase.yaml
kubectl apply -f deployment.yaml -n app
kubectl apply -f service.yaml -n app
kubectl apply -f ingress.yaml -n app
```

For working with **FluxCD** - go to [Installation guide](https://fluxcd.io/flux/installation/#install-the-flux-cli) 
For bash i use this:
```
curl -s https://fluxcd.io/install.sh | sudo bash
```
