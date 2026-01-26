The Nautilus development team has provided requirements to the DevOps team for a new application development project, specifically requesting the establishment of a Git repository. Follow the instructions below to create the Git repository on the Storage server in the Stratos DC:



Utilize yum to install the git package on the Storage Server.


Create a bare repository named /opt/demo.git (ensure exact name usage).


Approach:
1. ssh into storage server
2. check whether git is available.
   ```
   git --version
   ```
3. Install git
   ```
   sudo yum install -y git
   ```
4. Creating bare repo
   ```
   sudo git init --bare /opt/demo.git
   ```
   what a bare repo?
   A bare Git repository is a repository that contains only Git’s internal data (commits, branches, tags, and history) and does not have a working directory with checked-out source code.
   It is designed to act as a central remote repository that developers push to and pull from, rather than a place where code is edited or run.
   Platforms like GitHub, GitLab, and Azure Repos host repositories in this bare form internally.
   In on-prem or server-based setups, creating a bare repository (for example using git init --bare) serves the same purpose as a remote GitHub repository,
   ensuring safe collaboration, avoiding working-tree conflicts, and providing a clean, authoritative source of truth for version control.
