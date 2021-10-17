# Aufbau 

## Schaubild 



## Grundbegriffe 

### Node 

  * Ein Knoten (Node in Englisch) ist eine Arbeitsmaschine in Kubernetes
  * Ref: https://kubernetes.io/de/docs/concepts/architecture/nodes/

### Pod/Pods 

  * Pods sind die kleinsten einsetzbaren Einheiten, die in Kubernetes erstellt und verwaltet werden können.
  * Ein Pod (übersetzt Gruppe) ist eine Gruppe von einem oder mehreren Containern
    * gemeinsam genutzter Speicher- und Netzwerkressourcen   
    * Befinden sich immer auf dem gleich virtuellen Server 
    
## Control Plane Node (former: master) - components 

### General 

  * For best performance we should only have the Kubernetes core-components on master

### Components 

#### etcd 

  * key/pair value store, were kubernetes store its setting

#### kubernetes api server 

  * provides api-frontend for administration (no gui)
  * Exposes an HTTP API (users, parts of the cluster and external components communicate with it)
  * REST API
  
#### Kubernetes scheduler 

  * Monitors newly created pods, which are not yet tiied to a node

## Node (Minion) - components 

### General 

  * On the nodes we will rollout the applications
  
  
