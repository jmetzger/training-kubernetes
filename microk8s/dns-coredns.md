# coredns/dns (microk8s) 

## Aktivieren

```
microk8s dns 

# Achtung dns wird erst bei neuen pods richtig eingetragen) 
```

## Deaktiveren 

```
microk8s disable 
```

## Aktiveren mit speziellen DNS - Servern 

```
micro8ks enable dns:1.1.1.1,2.2.2.2
# Ref: https://microk8s.io/docs/addon-dns
```
## Nachträglich aktivieren von alternativen DNS-Servern (schlechter Weg)

```
# Achtung --save-config is necessary, that changes get applied 
# https://microk8s.io/docs/addon-dns <- is wrong here (2021/10/25)
kubectl -n kube-system edit configmap/coredns --save-config
```

## Nachträglich DNS forwarder ändern: guter Weg

```
mkdir manifests
cd manifests 
kubectl -n kube-system get configmap/coredns -o yaml > configmap_coredns.yml 
# Änderung vornehmen 
# am besten Annotations raus und alle Zeitstemple, Versionen raus.
# Änderungen in Data/core z.b forward... 
kubectl apply -f configmap_coredns.yml
```



