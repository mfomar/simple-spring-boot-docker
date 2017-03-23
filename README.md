# simple-spring-boot-docker
Simple Spring Boot Docker 


You need to have Docker up and running.

$ mvn package docker:build -DpushImage

The -DpushImage part won;t work, so just type:

$ mvn package docker:build

which builds the image.

Then type:

$ docker run -p 8080:8080 -t springio/gs-spring-boot-docker

Test by browsing to localhost:8080


