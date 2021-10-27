# Install plugin kubectl-convert

## Why ?

  * It used to be part of kubernetes 
  * It was deprecated like so because it was not cleanly implemented
  * Ref: https://github.com/kubernetes/kubectl/issues/725#:~:text=kubectl%20convert%20is%20deprecated,functionality%20is%20removed%20from%20kubectl%20.

## What does it do ?

```
If converts old version of your manifests
to the versions that work on your server 
```

## Walkthrough 

```
curl -LO https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl-convert
# verify checksum 
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl-convert.sha256"
echo "$(<kubectl-convert.sha256) kubectl-convert" | sha256sum --check
# install it to the appropriate place being in $PATH
sudo install -o root -g root -m 0755 kubectl-convert /usr/local/bin/kubectl-convert
# Test it
kubectl-convert --help
```
