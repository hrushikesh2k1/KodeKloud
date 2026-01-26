One of the Nautilus project developers need access to run docker commands on App Server 2. This user is already created on the server. Accomplish this task as per details given below:



User john is not able to run docker commands on App Server 2 in Stratos DC, make the required changes so that this user can run docker commands without sudo.


Approach:
1. ssh into app server 2
   ```
   ssh steve@stapp02
   ```
2. confirm the users in docker group
   ```
   cat /etc/group
   ```
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c97af262-52df-46a3-a23e-0309f9596d8c" />
3. Update the permission
   ```
   sudo usermod -aG docker john
   ```
4. Confirm John user is added to docker group
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/21beeecd-0756-4ed2-98ae-f138b96435b6" />
5. Now switch to john and run docker docker command
   ```
   sudo su john
   docker run hello-world
   ```
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0774e499-b4a6-42fe-a0b1-9aafbba93376" />
