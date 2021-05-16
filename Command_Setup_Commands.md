## Adding Labels to Nodes
- kubectl label nodes <node-name> <label-key>=<label-value>
- kubectl get nodes --show-labels 
- kubectl describe node "nodename"

## Generating Deployment Manifests via CLI
```
kubectl create deployment --help

but not all deployment options/features update/add available through cli. Hence use yaml file approach better for advance questiond

kubectl create deployment DEP_NAME --image=[IMAGE-NAME]

kubectl create deployment DEP_NAME --image=[IMAGE-NAME] --dry-run=client -o yaml

```

## Generating Pod Manifests via CLI
```
1. Create a Pod from Nginx Image

kubectl run [NAME-OF-POD] --image=[IMAGE=NAME] --restart=Never
kubectl run nginx --image=nginx --restart=Never

2. Create a Pod and Expose a Port

kubectl run nginx --image=nginx --port=80 --restart=Never


3. Output the Manifest File

kubectl run nginx --image=nginx --port=80 --restart=Never --dry-run -o yaml 

```
