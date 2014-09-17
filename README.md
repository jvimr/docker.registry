Docker registry images for non-default ASW region
=================================================

created as a solution for https://github.com/docker/docker-registry/issues/400

Usage:
======

1 build image from docker file:
```
 git co .....
 cd eu-west-1
 sudo docker -t="my.docker.registry.eu-west-1" .
```
```
 sudo docker run \
         -e SETTINGS_FLAVOR=s3 \
         -e AWS_BUCKET=acme-docker \
         -e STORAGE_PATH=/registry \
         -e AWS_KEY=AKIAHSHB43HS3J92MXZ \
         -e AWS_SECRET=xdDowwlK7TJajV1Y7EoOZrmuPEJlHYcNP2k4j49T \
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
         -e AWS_KEY=AKIAHSHB43HS3J92MXZ \
         -e AWS_SECRET=xdDowwlK7TJajV1Y7EoOZrmuPEJlHYcNP2k4j49T \
         -e SEARCH_BACKEND=sqlalchemy \
         -p 5000:5000 \
         jvimr/docker.registry.eu-west-1:latest
```