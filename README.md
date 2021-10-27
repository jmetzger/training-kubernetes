# Kubernetes Training ( 3 days )

## Agenda 

  1. Grundlagen 
     * [Welches System ? (minikube, micro8ks etc.)](welches-system.md)
     * [Aufbau](architecture.md)
  1. Installation
     * [Überblick](overview-distros.md)
     * [Linux Client aufsetzen](linux-client-ubuntu-kubectl.md)
  1. microk8s 
     * [Installation Ubuntu - snap](microk8s/installation-ubuntu-snap.md)
     * [Patch to next major release - cluster](microk8s/patch-next-major.md)
     * [Remote-Verbindung zu Kubernetes (microk8s) einrichten](microk8s/connect-from-remote.md)
     * [Create a cluster with microk8s](microk8s/cluster.md)
     * [Arbeiten mit der Registry](microk8s/registry.md)
  1. kubectl
     * [alle Ressourcen (Möglichkeiten) der Api anzeigen](kubectl/api-resources.md)
     * [pod starten mit beispiel](kubectl/run-with-example.md)
     * [alle pods anzeigen](kubectl/get-pods.md)
     * [auf welcher Node läuft ein pod](kubectl/get-pods-o-wide.md)
     * [pods löschen](kubectl/delete-pod.md)
     * [Mit pod verbinden - terminal](kubectl/exec.md)

  1. Kubernetes 
     * [Deployments](kubernetes/deployments.md)

  1. Gitlab CI/CD 
     * [Predefined Variables](gitlab-ci-cd/predefined_variables.md)
     * [Example pipelines](gitlab-ci-cd/)

  1. Ingress 
     * [Nginx Ingress Controller](ingress/nginx-ingress-controller.md) 

  1. Monitoring 
     * [Prometheus Operator](https://prometheus.io/docs/introduction/overview/)

  1. Logging 
     * [Logging on Node - Level (fluentd)](https://medium.com/kubernetes-tutorials/cluster-level-logging-in-kubernetes-with-fluentd-e59aa2b6093a)

  1. Netzwerk 
     * [Ist ipv6 mit ipsec möglich ? (Stand: Experimentell)](network/ipv6-ipsec.md)
     * [Metallb als LoadBalancer vor Ingress verwenden](network/metallb.md)
     * [Calico (Default Netzwerk-Dienst microk8s) - Netzwerk Policies](network/calico-default-microk8s.md)

  1. Shared Volumes 
     * [Shared Volumes with Rook & Ceph](shared-volumes/rook-ceph.md)
     * [Shared Volumes with nfs](share-volumes/nfs.md)
     
  1. Tipps & Tricks 
     * [kubectl-Autovervollständigung](autocomplete.md) 
     * [Install plugin kubectl-convert](install-kubectl-convert.md)

  1. Examples 
     * [Kuard pod](examples/01-kuard-pod.md)
     * [Pod nginx port exposed](examples/02-pod-nginx-exposed.md)
     * [Deployment nginx](examples/03-deployment-nginx.md)
     * [Ingress Nginx](examples/04-ingress-nginx.md) 
     * [Combind example in manifest (ubuntu-nginx)](05-combined-ubuntu-nginx.md)
     * [Combined example in manifest (ubuntu-nginx-service)](06-combined-ubuntu-nginx-with-service.md)

  1. Use Cases 
     * [Use Cases Foundation](https://www.cncf.io/case-studies/)
     * [Use Cases Kubernetes](https://kubernetes.io/case-studies/)
     * [Use Cases](https://dzone.com/articles/how-big-companies-are-using-kubernetes)



