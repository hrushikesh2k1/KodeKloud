One of the Nautilus DevOps team members was working to configure services on a kkloud container that is running on App Server 3 in Stratos Datacenter. Due to some personal work he is on PTO for the rest of the week, but we need to finish his pending work ASAP. Please complete the remaining work as per details given below:


a. Install apache2 in kkloud container using apt that is running on App Server 3 in Stratos Datacenter.


b. Configure Apache to listen on port 8088 instead of default http port. Do not bind it to listen on specific IP or hostname only, i.e it should listen on localhost, 127.0.0.1, container ip, etc.


c. Make sure Apache service is up and running inside the container. Keep the container in running state at the end.


Approach:
1. ssh into app server 3.
   ```bash
   ssh banner@stapp03
   ```
2. exec into docker container kkloud
   ```bash
   docker exec -it kkloud /bin/bash
   ```
3. install apache2
   ```bash
   apt install -y apache2
   ```
4. Update the port number from 80 to 8088
   ```bash
   vim /etc/apache2/ports.conf
   ```
5. Update the port number in Virtual Host. (Virtual Host actually serves the traffic, while ports.conf declares which port is open for traffic. So, both should be same)
   ```bash
   vim /etc/apache2/sites-available/000-default.conf
   ```
6. Start the apache2
   ```bash
   service apache2 start
   ```
   
