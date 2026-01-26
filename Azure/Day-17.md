As part of the data migration process, the Nautilus DevOps team is actively creating several storage containers on Azure. They plan to utilize public Blob containers to store the relevant data. Given the ongoing migration of other infrastructure to Azure, it is logical to consolidate data storage within the Azure environment as well.

Create a new storage account named devopsst28787 and a public Blob container named devops-blob-31920 within the storage account. Make sure anonymous read access for containers and blobs is enabled.

Approach:
1. Go to portal.azure.com
2. Search for storage account service and click on create, name it as "devopsst28787".
3. Change "Allow Blob Anonymous Access" to "Enabled"
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e1a1073e-d611-412e-8ec4-96d248a83d97" />
4. Now create the blob container with access level as "Blob(Anonymous read access to Blobs only)"
    <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7dc10215-6204-43af-a7bd-7b0dc6521a33" />

 
