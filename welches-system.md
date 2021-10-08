# Überblick der Systeme 

```

Minikube
Minikube can run on Windows and MacOS, because it relies on virtualization (e.g. Virtualbox) to deploy a kubernetes cluster in a Linux VM. You can also run minikube directly on linux with or without virtualization. It also has some developer-friendly features, like add-ons.

Minikube is currently limited to a single-node Kubernetes cluster (for details, see this issue). Although, it is on their roadmap.

Microk8s
Disclaimer: of all the K8s offerings, I know the least about this one

Microk8s is similar to minikube in that it spins up a single-node Kubernetes cluster with its own set of add-ons.

Like minikube, microk8s is limited to a single-node Kubernetes cluster, with the added limitation of only running on Linux and only on Linux where snap is installed.

K3s
K3s runs on any Linux distribution without any additional external dependencies or tools. It is marketed by Rancher as a lightweight Kubernetes offering suitable for edge environments, IoT devices, CI pipelines, and even ARM devices, like Raspberry Pi's. K3s achieves its lightweight goal by stripping a bunch of features out of the Kubernetes binaries (e.g. legacy, alpha, and cloud-provider-specific features), replacing docker with containerd, and using sqlite3 as the default DB (instead of etcd). As a result, this lightweight Kubernetes only consumes 512 MB of RAM and 200 MB of disk space. K3s has some nice features, like Helm Chart support out-of-the-box.

Unlike the previous two offerings, K3s can do multiple node Kubernetes cluster. However, due to technical limitations of SQLite, K3s currently does not support High Availability (HA), as in running multiple master nodes. The K3s team plans to address this in the future.

Now, on to some honorary mentions...

Kind
Kind (Kubernetes-in-Docker), as the name implies, runs Kubernetes clusters in Docker containers. This is the official tool used by Kubernetes maintainers for Kubernetes v1.11+ conformance testing. It supports multi-node clusters as well as HA clusters. Because it runs K8s in Docker, kind can run on Windows, Mac, and Linux.

Kind is optimized first and foremost for CI pipelines, so it may not have some of the developer-friendly features of other offerings.

Desktop Docker
Docker for Mac/Windows now ships with a bundled Kubernetes offering.

However:

Kubernetes versions are tightly coupled with the Docker version (i.e. Docker stable channel ships with K8s v1.10. If you want K8s v1.13, you need to switch to Docker edge channel).

Not as easy to destroy and start a new K8s cluster. AFAIK, you would have to disable Kubernetes and re-enable it through the Docker desktop app preferences.

K3d
A new project that aims to bring K3s-in-Docker (similar to kind).

They're still working through some issues, like exposing the right docker ports ...etc.

Kubeadm
The official CNCF tool for provisioning Kubernetes clusters in a variety of shapes and forms (e.g. single-node, multi-node, HA, self-hosted)

Although this is the most manual way to create and manage a cluster of all the offerings listed here.

... And there are plenty more that I do not remember off the top of my head.

So, it all depends on what you want to get out these tools and out of Kubernetes.

Are you a developer who wants a simple K8s cluster and don't need or care about multi-node/HA features?

Are you a developer working on a distributed application that runs on Kubernetes and need to test various failure scenarios (e.g. node failure)?

Are you trying to learn about Kubernetes from a cluster administrator's perspective?

I hope you find this information helpful.
```
Let me know if you have any questions.
