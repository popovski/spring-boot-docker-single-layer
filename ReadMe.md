1. Create image from docker file - "docker image name springboot/testjar1", "." means you look for docker file in the folder where we
are executing the command
1.1 docker build -t springboot/testjar1 .

2. After the image was build we create container from the image, for the host we are exposing 7071 as a port 
2.1 docker run -p 7071:8080 springboot/testjar1

3. execute commands in the docker image 
3.1 docker exec -it <image:id> /bin/sh


Usint the maven plugin

1. mvn clean package spring-boot:build-image
- this will create the image in the local repository
2. docker push popovskinikola/test-spring-boot:2
- this will push only the layers that were changed