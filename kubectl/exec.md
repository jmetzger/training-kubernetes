# Connect to pods with exec 

## Connect to specific pod 

```
kubectl exec -it ubuntu-deployment-557dfb95d4-jc57t -- bash 
```

## Connect to 1 random pod in deployment

```
## This connects to one random pod within deployment 

# ubuntu-deployment was the name of the deployment
kubectl exec -it deploy/ubuntu-deployment -- bash
```
