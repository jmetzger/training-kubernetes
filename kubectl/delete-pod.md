# Delete pods 

```
# Variante 1
kubectl delete pods/mypod 

# Variante 2
kubectl apply -f pod-manifest.yml 
kubectl get pods
# now delete 
kubectl delete -f pod-manifest.yml 
```
