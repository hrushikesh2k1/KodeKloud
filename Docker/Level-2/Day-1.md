Nautilus project developers are planning to start testing on a new project. As per their meeting with the DevOps team, they want to test containerized environment application features. As per details shared with DevOps team, we need to accomplish the following task:


a. Pull busybox:musl image on App Server 1 in Stratos DC and re-tag (create new tag) this image as busybox:news.

Approach:
1. ssh into app server 1
   ```
   ssh tony@stapp01
   ```
2. pull the image
   ```
   docker pull busybox:musl
   ```
3. Update the tag
   ```
   docker tag <SOURCE_IMAGE:TAG> <TARGET_IMAGE:TAG>
   ```
   for finding the commmand to update the tag
   ```
   docker --help
   ```
   This lets you find all the commands related to docker
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ecff7ac7-9755-4119-b6f8-153728f04c27" />
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0dec99af-7a14-4d5b-a360-1a32fb3e4aae" />
