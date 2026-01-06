A container named kke-container was created by one of the Nautilus project developers on App Server 2. It was solely for testing purposes and now requires deletion. Execute the following task:



Delete the kke-container on App Server 2 in Stratos DC.

Approach:
1. ssh into app server 2
   ```
   ssh steve@stapp02
   ```
2. check the running containers
   ```
   docker ps
   ```
3. stop the container before deleting it.
   ```
   docker stop <sontainer_id>
   ```
4. delete the container
   ```
   docker rm <container_id>
   ```
