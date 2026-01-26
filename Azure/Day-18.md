The Nautilus DevOps team is presently immersed in data migrations, transferring data from on-premise storage systems to Azure Blob containers. They have recently received some data that they intend to copy to one of the Blob containers.

A Blob container named datacenter-blob-9450 already exists in the East US region under the storage account datacenterst25924. Copy the file /tmp/datacenter.txt to the Blob container datacenter-blob-9450.

Approach:
Prerequisites:
  1. Azure CLI installed
  2. Logged into Azure
  3. storage account access permissions
1. Set variables
   ```
   STORAGE_ACCOUNT=datacenterst25924
   CONTAINER_NAME=datacenter-blob-9450
   FILE_PATH=/tmp/datacenter.txt
   ```
2. Upload the document
   ```
   az storage blob upload \
     --account-name $STORAGE_ACCOUNT \
     --container-name $CONTAINER_NAME \
     --name datacenter.txt \
     --file $FILE_PATH \
     --auth-mode login
   ```
3. Confirm the upload
   ```
   az storage blob list \
   --account-name $STORAGE_ACCOUNT \
   --container-name $CONTAINER_NAME \
   --output table \
   --auth-mode login
  ```
