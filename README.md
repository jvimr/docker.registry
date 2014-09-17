Docker registry images for non-default ASW region
=================================================

created as a solution for https://github.com/docker/docker-registry/issues/400

Usage:
======

1 build image from docker file:
```
 git co git@github.com:jvimr/docker.registry.git
 cd eu-west-1
 sudo docker build -t="my.docker.registry.eu-west-1" .
```
```
 sudo docker run \
         -e SETTINGS_FLAVOR=s3 \
         -e AWS_BUCKET=acme-docker \
         -e STORAGE_PATH=/registry \
         -e AWS_KEY=YOUR_KEY \
         -e AWS_SECRET=YOUR_SECRET \
         -e SEARCH_BACKEND=sqlalchemy \
         -p 5000:5000 \
         my.docker.registry.eu-west-1
```


2 from existing image:
```
 sudo docker run \
         -e SETTINGS_FLAVOR=s3 \
         -e AWS_BUCKET=acme-docker \
         -e STORAGE_PATH=/registry \
         -e AWS_KEY=YOUR_KEY \
         -e AWS_SECRET=YOUR_SECRET \
         -e SEARCH_BACKEND=sqlalchemy \
         -p 5000:5000 \
         jvimr/docker.registry.eu-west-1:latest
```
