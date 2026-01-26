The Nautilus DevOps team is testing applications containerization, which is supposed to be migrated on docker container-based environments soon. In today's stand-up meeting one of the team members has been assigned a task to create and test a docker container with certain requirements. Below are more details:


a. On App Server  2 in Stratos DC pull nginx image (preferably latest tag but others should work too).


b. Create a new container with name news from the image you just pulled.


c. Map the host volume /opt/security with container volume /tmp. There is an sample.txt file present on same server under /tmp; copy that file to /opt/security. Also please keep the container in running state.

Approach:
1. ssh into app server 2
   ```bash
   ssh steve@stapp02
   ```
2. docker pull nginx:latest
   ```
   docker pull nginx:latest
   ```
3. Copy the sample.txt from /tmp/ to /opt/security/ in the same server
   ```bash
   cp /tmp/sample.txt /opt/security/
   ```
4. Create the container
   ```bash
   docker run -d --name news -v /opt/security/:/tmp/ nginx:latest
   ```
   
