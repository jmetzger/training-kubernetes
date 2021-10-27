# Ist ipv6 mit ipsec Verschlüsseling in Kubernetes möglich

## General 

  * Ist möglich, aber noch nicht produktionsreif (Stand 10/2021) 
  * Jedes Kubernetes-Cluster cluster braucht einen Netzwerk-Dienst 
  * By microk8s ist dieser Netzwerkdienst calico 
  * Dieser unterstützt experimentell ipv mit ipsec

## Ref:

  * https://docs.projectcalico.org/getting-started/kubernetes/vpp/ipsec
  * https://docs.projectcalico.org/getting-started/kubernetes/vpp/getting-started
