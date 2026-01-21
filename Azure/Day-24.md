The Nautilus DevOps Team is working on setting up a new virtual machine (VM) to host a web server for a critical application. The team lead has requested you to create an Azure VM that will serve as a web server using Nginx. This VM will be part of the initial infrastructure setup for the Nautilus project. Ensuring that the server is correctly configured and accessible from the internet is crucial for the upcoming deployment phase.

As a member of the Nautilus DevOps Team, your task is to create a VM using Azure CLI with the following specifications:

Instance Name: The VM must be named nautilus-vm.

Image: Use any available Ubuntu image to create this VM.

Custom Script Extension/User Data: Configure the VM to run a custom script during its launch. This script should:

Install the Nginx package.
Start the Nginx service.
Network Security Group (NSG): Ensure that the VM allows HTTP traffic on port 80 from the internet.

Instructions:

Use Azure CLI commands to set up the VM in the specified configuration.
Ensure the VM is accessible from the internet on port 80.
The Nginx service should be running after setup.


Use the Azure CLI commands to complete the task.

Approach:
1. Write the custom script and save it with name "nginx.txt"
   ```bash
   #!/bin/bash
   apt update -y
   apt install -y nginx
   systemctl enable nginx
   systemctl start nginx
   ```
2. Create the VM
   ```bash
   az vm create \
   --resource-group <RESOURCE_GROUP_NAME> \
   --name nautilus-vm \
   --image Ubuntu2204 \
   --size Standard_B1s \
   --admin-username azureuser \
   --generate-ssh-keys \
   --custom-data nginx.txt \
   --storage-sku Standard_LRS
   ```
3. Open HTTP port
   ```bash
   az vm open-port \
   --resource-group <RESOURCE_GROUP_NAME> \
   --name nautilus-vm \
   --port 80
   ```
   
