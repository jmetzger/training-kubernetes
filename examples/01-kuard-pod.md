# Kuard Pod mit manifest deployen 

## kuard-pod.yml 


```
apiVersion: v1
kind: Pod
metadata:
  name: kuard
spec:
  containers:
  - image: gcr.io/kuar-demo/kuard-amd64:1
    name: kuard
    ports:
    - containerPort: 8080
      name: http
      protocol: TCP
```

## kuard-pod apply 

```
kubectl apply -f kuard-pod.yml
```
