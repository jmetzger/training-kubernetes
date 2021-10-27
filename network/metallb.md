# Using Load-Balancer on bare-metal 

## Example:

```
apiVersion: v1
kind: ConfigMap
metadata:
  namespace: metallb-system
  name: config
data:
  config: |
    address-pools:
    - name: default
      protocol: layer2
      addresses:
      - 203.0.113.10-203.0.113.15
```

## Refs:

  * https://kubernetes.github.io/ingress-nginx/deploy/baremetal/
  * https://metallb.universe.tf/
