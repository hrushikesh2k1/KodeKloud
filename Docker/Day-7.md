What is the base Operating System used by the python:3.6 image?

If required, run an instance of the image to figure it out.


Approach:
1. ```bash
   docker run -it python:3.6 cat /etc/os-release

   or

   docker inspect python:3.6 --this only tells the OS not the distro
   ```
