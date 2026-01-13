The Nautilus DevOps team has been using Azure Blob Storage to manage their data. Recently, they realized that one of their containers, currently public, needs to be restricted for internal use only. Your task is to convert a public Azure Blob container to private.

Two blob containers named nautilus-container-25291 and nautilus-priv-7457 are available in the East US region within the storage account nautilusst12489. The nautilus-container-25291 is currently public, and nautilus-priv-7457 is private.

1) Convert the blob container nautilus-container-25291 from public to private while leaving nautilus-priv-7457 unchanged.

2) Make sure the access level for nautilus-container-25291 is set to private with no public access.

Approach:
1. Go to portal.azure.com
2. Go to storage account named "nautilusst12489".
3. Go to blob container "nautilus-container-25291".
4. click on change access level and select private(anonymous access) from drop down.
   
