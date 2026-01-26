In response to heightened security concerns, the xFusionCorp Industries security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:



a. Create a user named rose on App server 1 within the Stratos Datacenter.


b. Assign a unique UID 1396 and designate the home directory as /var/www/rose.


Approach:
1. ssh into app server 1
2. create a user names rose with uid 1396 and home directory /var/www/rose
   ```
   sudo useradd -u 1396 -d /var/www/rose rose
   ```
3. confirm the user and home directory.
   ```
   cat /etc/passwd
   ```
   
