# Installation on Ubuntu (snap)

```
sudo snap install microk8s --classic
microk8s status

# Execute kubectl commands like so 
microk8s kubectl
microk8s kubectl cluster-info

# Make it easier with an alias 
echo "alias kubectl='microk8s kubectl'" >> ~/.bashrc
source ~/.bashrc
kubectl

```
