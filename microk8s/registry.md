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

```
