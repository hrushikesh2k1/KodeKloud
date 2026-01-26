The system admins team of xFusionCorp Industries has set up some scripts on jump host that run on regular intervals and perform operations on all app servers in Stratos Datacenter. To make these scripts work properly we need to make sure the thor user on jump host has password-less SSH access to all app servers through their respective sudo users (i.e tony for app server 1). Based on the requirements, perform the following:



Set up a password-less authentication from user thor on jump host to all app servers through their respective sudo users.


Approach:
1. Generate the ssh keys
   ```
   ssh-keygen -t rsa -b 2048
   ```
2. The public key and private key are stored in .ssh folder under home directory
3. copy the public key.
4. ssh into app server 1.
   ```
   ssh user@ip_address
   ```
5. create a .ssh folder with home directory.
   ```
   mkdir -p .ssh
   ```
6. create athorized_keys file and paste the public key.
7. follow the same steps (2-6) for remaining app servers.
