The Nautilus DevOps team is planning to host an application on a nginx-based container. There are number of tickets already been created for similar tasks. One of the tickets has been assigned to set up a nginx container on Application Server 1 in Stratos Datacenter. Please perform the task as per details mentioned below:


a. Pull nginx:alpine-perl docker image on Application Server 1.


b. Create a container named blog using the image you pulled.


c. Map host port 6400 to container port 80. Please keep the container in running state.


Approach:
1. ssh into app server 1
```
ssh tony@stapp01
```
2. Pull the nginx:alpine-perl image
```
docker pull nginx:alpine-perl
```
3. create the container named "blog"
```
docker run -d --name blog -p 6400:80 nginx:alpine-perl
```
4. To confirm the container is running and check the traffic
```
curl http://localhost:6400
```
