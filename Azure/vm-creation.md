The Nautilus DevOps team is planning to migrate a portion of their infrastructure to the Azure cloud incrementally. As part of this migration, you are tasked with creating an Azure Virtual Machine (VM).

The requirements are:

1) Use the existing resource group.

2) The VM name must be datacenter-vm, it should be in West US region.

3) Use the Ubuntu 22.04 LTS image for the VM.

4) The VM size must be Standard_B1s.

5) Attach a default Network Security Group (NSG) that allows inbound SSH (port 22).

6) Attach a 30 GB storage disk of type Standard HDD.

7) The rest of the configurations should remain as default.

After completing these steps, make sure you can SSH into the virtual machine.

Approach:
1. Go to portal.azure.com
2. Search for Virtual machine service and click on create
3. <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c52ac489-99a9-41e8-8472-1043e0a3d07a" />
4. <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6fb52c22-1e3c-45cc-9d9d-2e36801fe5dd" />
5. <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6a268138-0068-45fb-959f-1a516cd1428c" />
6. <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8fe29178-25ad-4ea7-bac3-33d8017e94da" />
7. Deployment is completed
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/62f03be2-48c9-4874-9832-e76cff003622" />
8. Identify the public ip
   <img width="1920" height="1080" alt="Screenshot (226)" src="https://github.com/user-attachments/assets/05cbedab-0b4e-4c91-b953-36e1bc769d00" />
9. Open terminal and ssh into vm
   ```
   ssh -i <private-key-file-path> azureuser@20.57.196.119
   ```
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ef4862cf-7b8c-45a3-ad82-6b9912196c72" />

