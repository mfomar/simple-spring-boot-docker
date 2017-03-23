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


------------------

When it is running you can see in the list of containers, e.g:

$ docker ps
CONTAINER ID        IMAGE                             COMMAND                CREATED             STATUS              PORTS     
81c723d22865        springio/gs-spring-boot-docker:latest   "java -jar /app.jar"   34 seconds ago      Up 33 seconds       0.0.0.0:8080->8080/tcp 

and to shut it down again you can docker stop with the container ID from the listing above (yours will be different):

$ docker stop 81c723d22865
81c723d22865



If you like you can also delete the container (it is persisted in your filesystem under /var/lib/docker somewhere) when you are finished with it:

$ docker rm 81c723d22865


Using Spring Profiles
=====================

Running your freshly minted Docker image with Spring profiles is as easy as passing an environment variable to the Docker run command

$ docker run -e "SPRING_PROFILES_ACTIVE=prod" -p 8080:8080 -t springio/gs-spring-boot-docker
or

$ docker run -e "SPRING_PROFILES_ACTIVE=dev" -p 8080:8080 -t springio/gs-spring-boot-do


