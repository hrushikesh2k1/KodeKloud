One of the Nautilus developer was working to test new changes on a container. He wants to keep a backup of his changes to the container. A new request has been raised for the DevOps team to create a new image from this container. Below are more details about it:


a. Create an image ecommerce:devops on Application Server 2 from a container ubuntu_latest that is running on same server.

Approach:
1. ssh into app server 2
   ```bash
   ssh steve@stapp02  #ssh user@servername/ip
   ```
2. Use docker commit command to create new image from the running new container. Takes a snapshot of the container’s current filesystem.
   ```bash
   docker commit ubuntu_latest ecommerce:devops
   ```
   
