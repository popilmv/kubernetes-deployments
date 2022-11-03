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
Add flux to bash:
```
gedit ~/.bashrc
```
add this **source <(flux completion bash)**

Save changes:
```
source ~/.bashrc
```

Make sure to have your Git credentials (I use GitHub):

```
export GITHUB_TOKEN=<your-token>
export GITHUB_USER=<your-username>
```
  
You can find the token within the following path https://github.com/settings/tokens
  
Next, ensure that you have access to your Kubernetes cluster through the CLI. I usually just check whether I have access to nodes:

```
kubectl get nodes
```

Then, check your cluster is compatible and ready for Flux:

```
flux check --pre
```
![image](https://user-images.githubusercontent.com/115075056/198820427-20045ba4-e55b-4030-b487-ba0686aebf1a.png)

To install Flux into our Kubernetes cluster, this is done with the Flux bootstrap command:

```
flux bootstrap github --owner=$GITHUB_USER --repository=kubernetes-deployments --branch=main --path=./clusters/flux --personal
```
___
--repository = your repository name
___
--branch = your branch
___
--path = you can rename it for yourself



