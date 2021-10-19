# Run pod with example 

## Example 

```
# Synopsis (most simplistic example 
# kubectl run NAME --image=IMAGE_EG_FROM_DOCKER
# example
kubectl run nginx --image=nginx 

kubectl get pods 
# on which node does it run ? 
kubectl get pods -o wide 
```

## Ref:

  * https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#run
