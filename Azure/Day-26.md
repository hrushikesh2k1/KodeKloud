The Nautilus DevOps Team has received a request from the Networking Team to set up a new public VNet to support a set of public-facing services. This VNet will host various resources that need to be accessible over the internet. As part of this setup, you need to ensure the VNet has public subnets with automatic public IP assignment for resources. Additionally, a new VM will be launched within this VNet to host public applications that require SSH access. This setup will enable the Networking Team to deploy and manage public-facing applications.

Create a public VNet named devops-pub-vnet, and a subnet named devops-pub-subnet under the same, make sure public IP is being auto-assigned to resources under this subnet. Further, create a VM named devops-pub-vm under this VNet. Make sure SSH port 22 is open for this instance and accessible over the internet. Use the Azure portal to complete the task and ensure that SSH access is configured correctly.

Approach:
1. Create the Vnet and Subnet inside it.
   <img width="984" height="806" alt="image" src="https://github.com/user-attachments/assets/9b8fc2fe-9092-4b8c-a5e7-4947ad392cda" />
2. Create the vm within the vnet created
   <img width="1137" height="806" alt="image" src="https://github.com/user-attachments/assets/86789f4e-8fbc-4e76-bbaa-df23dbe1dbde" />
   
