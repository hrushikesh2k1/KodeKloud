The Nautilus DevOps team is expanding their Azure infrastructure and requires the setup of a private Virtual Network (VNet) along with a subnet. This VNet and subnet configuration will ensure that resources deployed within them remain isolated from external networks and can only communicate within the VNet. Additionally, the team needs to provision a Virtual Machine (VM) under the newly created private VNet. This VM should be accessible over SSH from within the VNet only, allowing for secure communication and resource management within the Azure environment.

The name of the VNet must be devops-priv-vnet, create a subnet named devops-priv-subnet under the same. Further, create a Virtual Machine named devops-priv-vm under this VNet. Additionally, create a Network Security Group (NSG) named devops-priv-nsg, and ensure that the NSG rules for the VM allow access only from within the VNet's CIDR block. Ensure all resources are created in the East US region.

Approach:
1. create a vnet and subnet inside it.
   <img width="852" height="795" alt="image" src="https://github.com/user-attachments/assets/d89405ed-a5ec-43de-bd46-771acb1284bd" />
2. Create the VM with
    1) public in-bound ports = None
3. Create the NSG
   <img width="1899" height="854" alt="image" src="https://github.com/user-attachments/assets/d0e3357a-e9a2-4643-b313-eeca9ace9ad7" />

