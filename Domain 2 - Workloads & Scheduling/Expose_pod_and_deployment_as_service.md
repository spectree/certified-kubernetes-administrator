## Create a deployment or Expose existing deployment as service

###a. kubectl run echoserver --image=gcr.io/google_containers/echoserver:1.4 --port=8080 --replicas=2 deployment 
```
kubectl get deployments
kubectl get replicasets
kubectl get pods
```

### b. To access our echoserver, we need to expose the pods though a service:
```
kubectl expose deployment echoserver --type=NodePort service

kubectl describe services/echoserver
```

## Expose nginx pod as service

### Start a single instance of nginx.
```
kubectl run nginx --image=nginx

kubectl get pods 
```
### Expose pod as service
```
kubectl expose pod nginx --name nginx-pod-svc --port=80 --target-port=80 

kubectl get svc 

# Observe the end-points
kubectl describe svc nginx-pod-svc
```
