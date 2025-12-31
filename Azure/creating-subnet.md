The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the Azure cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition.

For this task, create a Virtual Network (VNet) named devops-vnet and one subnet named devops-subnet within the VNet in the East US region. Make sure the IPv4 address range is 10.0.0.0/16.

Approach:
1. Go to portal.azure.com
2. Search for Virtual networks service and create one.
3. Give devops-vnet as name and East US as location.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b84af557-e7a2-49d2-8273-56e95d085be5" />
4. Under IP address section, a default vnet address block is created. Change the name of default subnet to devops-subnet, click save.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/15372dac-9851-4fd1-a0d3-490fbb187d8e" />
5. click on review + create.
