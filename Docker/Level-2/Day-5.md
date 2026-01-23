As per recent requirements shared by the Nautilus application development team, they need custom images created for one of their projects. Several of the initial testing requirements are already been shared with DevOps team. Therefore, create a docker file /opt/docker/Dockerfile (please keep D capital of Dockerfile) on App server 3 in Stratos DC and configure to build an image with the following requirements:



a. Use ubuntu:24.04 as the base image.


b. Install apache2 and configure it to work on 5000 port. (do not update any other Apache configuration settings like document root etc).

Approach:
1. ssh into app server 3
   ```bash
   ssh banner@stapp03
   ```
2. cd into /opt/docker/ and create and Dockerfile
   ```bash
   FROM ubuntu:24.04
   RUN apt-get update && \
       apt-get install -y apache2 && \
       sed -i 's/Listen 80/Listen 5000/' /etc/apache2/ports.conf
   EXPOSE 5000
   ```

