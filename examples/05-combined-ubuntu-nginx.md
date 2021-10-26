# Combined ubuntu/nginx 

## Example 

```
# vi combined-nginx-ubuntu.yml

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 4 # tells deployment to run 2 pods matching the template
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.21.1
        ports:
        - containerPort: 80
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ubuntu-deployment
spec:
  selector:
    matchLabels:
      os: ubuntu
  replicas: 4 # tells deployment to run 2 pods matching the template
  template:
    metadata:
      labels:
        os: ubuntu
    spec:
      containers:
      - name: ubuntu-os
        image: localhost:32000/myubuntu

```

```
kubectl apply -f combined-nginx-ubuntu.yml
```
