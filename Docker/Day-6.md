Inspect the environment variables set on the running container and identify the value set to the APP_COLOR variable.

Approach:
1. ```bash
   docker ps
   ```
2. ```bash
   docker exec <container_name> printenv

   or

   docker inspect <container_name> | grep APP_COLOR
   ```
   
