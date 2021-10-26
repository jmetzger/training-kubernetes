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

  1. Kubernetes 
     * [Deployments](kubernetes/deployments.md)

  1. Gitlab CI/CD 
     * [Predefined Variables](gitlab-ci-cd/predefined_variables.md)

  1. Tipps & Tricks 
     * [kubectl-Autovervollständigung](autocomplete.md) 

  1. Examples 
     * [Kuard pod](examples/01-kuard-pod.md)
     * [Pod nginx port exposed](examples/02-pod-nginx-exposed.md)
     * [Deployment nginx](examples/03-deployment-nginx.md
     * [Ingress Nginx](examples/04-ingress-nginx.md) 



