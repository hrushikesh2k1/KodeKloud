One of the DevOps team members was working on to create a new custom docker image on App Server 1 in Stratos DC. 
He is done with his changes and image is saved on same server with name news:datacenter. 
Recently a requirement has been raised by a team to use that image for testing, but the team wants to test the same on App Server 3. 
So we need to provide them that image on App Server 3 in Stratos DC. 

a. On App Server 1 save the image news:datacenter in an archive. 
b. Transfer the image archive to App Server 3. 
c. Load that image archive on App Server 3 with same name and tag which was used on App Server 1.

Approach:
1. ssh into app server 1
   ```bash
   ssh tony@stapp01
   ```
2. save the image
   ```bash
   docker save -o news_datacenter.tar news:datacenter
   ```
3. transfer the image to app server 3
   ```bash
   scp news_datacenter.tar banner@stapp03:/home/banner/
   ```
4. ssh into app server 3 and load the image
   ```bash
   ssh banner@stapp03
   docker load -i news_datacenter.tar
   ```

1️) docker save -o news_datacenter.tar news:datacenter
docker save	Exports one or more Docker images
-o news_datacenter.tar	Output file name
news:datacenter	Image name and tag

2️) scp news_datacenter.tar banner@stapp03:/home/user/
scp	Secure copy command
news_datacenter.tar	File to copy
banner@stapp03	User + remote server
:/home/user/	Destination path on remote server

3) docker load -i news_datacenter.tar
docker load	Imports image from tar archive
-i	Input file
news_datacenter.tar	Archive file
   

