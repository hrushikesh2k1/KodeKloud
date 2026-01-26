The Nautilus DevOps team is expanding their Azure infrastructure and requires the setup of a private Virtual Network (VNet) along with a subnet. This VNet and subnet configuration will ensure that resources deployed within them remain isolated from external networks and can only communicate within the VNet. Additionally, the team needs to provision a Virtual Machine (VM) under the newly created private VNet. This VM should be accessible over SSH from within the VNet only, allowing for secure communication and resource management within the Azure environment.

The name of the VNet must be xfusion-priv-vnet, create a subnet named xfusion-priv-subnet under the same. Further, create a Virtual Machine named xfusion-priv-vm under this VNet. Additionally, create a Network Security Group (NSG) named xfusion-priv-nsg, and ensure that the NSG rules for the VM allow access only from within the VNet's CIDR block. Ensure all resources are created in the East US region.


Approach:
1. Create the Vnet and subnet
   <img width="1906" height="850" alt="image" src="https://github.com/user-attachments/assets/8e4960ab-b001-47b7-93d7-217b7481fb92" />
2. Create the VM with following steps
   1. Allow inbound traffic = None
   2. Click on advanced option of NSG and create the NSG named "xfusion-priv-nsg" with following rule
      <img width="726" height="807" alt="image" src="https://github.com/user-attachments/assets/d2f665f2-c070-4688-8447-2d16af256c02" />
   3. Select public ip as None from drop down
