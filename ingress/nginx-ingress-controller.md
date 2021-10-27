# Nginx Ingress Controller 


## Example redirecting/rewriting

  * https://medium.com/ww-engineering/kubernetes-nginx-ingress-traffic-redirect-using-annotations-demystified-b7de846fb43d

## Snippet: permanent redirect 

```
apiVersion: v1
kind: Service
metadata:
  name: my-redirect-service
spec:
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376

---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
   annotations:
     nginx.ingress.kubernetes.io/permanent-redirect: https://www.google.de
     nginx.ingress.kubernetes.io/permanent-redirect-code: '308'
   name: redirect-google.de
spec:
   rules:
   - host: redirect.training.local
     http:
       paths:
       - backend:
           service:
             name: my-redirect-service
             port:
               number: 80
         path: /
         pathType: Prefix

```

## Use multiple hosts 

```
# this i yaml magic - yaml - ids 
spec:
  rules:
  - host: foobar.com
    http: &http_rules
      paths:
      - backend:
          serviceName: foobar
          servicePort: 80
  - host: api.foobar.com
    http: *http_rules
  - host: admin.foobar.com
    http: *http_rules
  - host: status.foobar.com
    http: *http_rules
```

## Full example 

```
# remember to set in your hosts - file or properly in dns 
apiVersion: v1
kind: Service
metadata:
  name: my-redirect-service
spec:
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376

---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
   annotations:
     nginx.ingress.kubernetes.io/permanent-redirect: https://www.google.de
     nginx.ingress.kubernetes.io/permanent-redirect-code: '308'
   name: redirect-google.de
spec:
   rules:
   - host: redirect.training.local
     http: &http_rules
       paths:
       - backend:
           service:
             name: my-redirect-service
             port:
               number: 80
         path: /
         pathType: Prefix
   - host: redirect2.training.local
     http: *http_rules
```



# Ref:
https://github.com/kubernetes/kubernetes/issues/43633


```


## Documentation 

  * [Github](https://github.com/kubernetes/ingress-nginx)
  * [Using custom Template](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/custom-template/)


