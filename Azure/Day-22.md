The Nautilus DevOps Team has received a new request from the Development Team to set up a new Azure Virtual Machine (VM). This VM will be used to host a new application that requires a stable public IP address. To ensure that the VM has a consistent public IP, a Static Public IP address needs to be associated with it. The VM will be named devops-vm, and the Static Public IP will be named devops-pip. This setup will help the Development Team to have a reliable and consistent access point for their application.

Create an Azure VM named devops-vm using any available Ubuntu image, with the VM size Standard_B1s.
Generate an SSH public key on the azure-client host and associate it with the VM for SSH access.
Associate a Static Public IP address named devops-pip with this VM.
Ensure the VM is accessible via SSH using the generated public key.

Approach:
1. Create a public ip address with name devops-pip
2. Create a virtual machine with name devops-vm with existing public key that is generated from azure host client and select the devops-pip public_ip from dropdown
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b835b2bb-0077-45fd-9c25-a0de1af0f24f" />
3. ssh into devops-vm from azure host client
   ```bash
   ssh azureuser@ip
   ```
   
