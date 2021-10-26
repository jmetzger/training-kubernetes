# Arbeiten mit der lokalen Registry 

```
microk8s enable registry 

mkdir ~/docker-images/ubuntu/
cd ~/docker-images/ubuntu 
vi Dockerfile 

FROM ubuntu:latest
RUN apt-get update
RUN apt-get install -y inetutils-ping
RUN apt-get install -y telnet
RUN echo 'while true; do sleep 15 ; done' > /bootstrap.sh
RUN chmod +x /bootstrap.sh

CMD /bootstrap.sh

docker build -t myubuntu . 
docker images 
docker tag myubuntu localhost:32000/myubuntu 

# testrun,ob container im Hintergrund laufen kann
docker run -d localhost:32000/myubuntu 
docker ps 

# vernichten 
docker rm -f <id-des-containers>

# manifests erstellen
vi ubuntu.yml 
apiVersion: v1
kind: Pod
metadata:
  name: static-ubuntu

spec:
  containers:
  - name: ubuntu-os
    image: localhost:32000/myubuntu

# apply'en 
kubectl apply -f ubuntu.yml 





```
