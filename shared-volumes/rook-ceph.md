# Shared Volumes with rook/ceph

## General

  * cephfs arbeitet als Objektspeicher (RADOS)
  * Es wird eine Schnittstelle als Blockspeicher zur Verfügung gestellt
  * Ceph verwendet intern Monitoring - Server (MONs)
  * Um ceph in Kubernetes auszurollen sind MON's und OSDs notwendig

## Rook

  * Rook liegt zwischen Ceph und Kubernetes und kümmert sich um dessen Verwaltung praktisch komplett automatisch.
  * Ein Rook-Cluster mit laufendem CEPH entsteht, wenn
    * die vorgefertigten Rook-Definitionen aus dessen Git-Repository auf die Kubernetes-Instanz angewendet wird.
   
## RADOS

  * RADOS hat mehrere Komponenten 
  * Die Object Storage Daemons (OSDs) sind die Speichersilos in Ceph

## Please do not/Be careful (as of: 2019/12), not sure, if this is still the case (2021/10)!

  * Bitte nicht über HELM ausrollen, dies ist (Stand: 11/2021) nicht funktional komplett

## Walkthrough 

```
### Achtung: Stand 2021/10 walkthrough funktioniert aktuell nicht

# Do this on your client 
git clone https://github.com/rook/rook.git
cd rook/cluster/examples/kubernetes/ceph
kubectl create -f crds.yaml -f common.yaml -f operator.yaml

# Check if pod is running 
kubectl -n rook-ceph get pod -l app=rook-ceph-operator

# First proceed if pod is running (last action)
kubectl create -f cluster.yaml
kubectl -n rook-ceph get pods  
# Wait till all pods are ready

# Install the toolbox 
kubectl create -f toolbox.yaml

kubectl -n rook-ceph exec -it deploy/rook-ceph-tools -- bash
```



## Ref: 

  * https://faun.pub/deploy-rook-ceph-on-kubernetes-3a2252f3732e (best choice for walkthrough)
  * https://www.linux-magazin.de/ausgaben/2019/12/rook-2/4/
