# Nginx Ingress Controller 


## Example redirecting/rewriting

  * https://medium.com/ww-engineering/kubernetes-nginx-ingress-traffic-redirect-using-annotations-demystified-b7de846fb43d

## Snippet: permanent redirect 

```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
   annotations:
     nginx.ingress.kubernetes.io/permanent-redirect: https://nginx.redirect/destination
     nginx.ingress.kubernetes.io/permanent-redirect-code: '308'
   name: destination-home
 spec:
   rules:
   - host: redirect.training.local
     http:
       paths:
       - backend:
           serviceName: http-svc
           servicePort: 80
         path: /
```

## Documentation 

  * [Github](https://github.com/kubernetes/ingress-nginx)
  * [Using custom Template](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/custom-template/)


