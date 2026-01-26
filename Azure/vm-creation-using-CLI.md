The Nautilus DevOps team is in the process of migrating some of their workloads to Azure. One of the tasks involves creating a new Virtual Machine (VM) using the Azure CLI. The team does not have access to the Azure portal but can manage Azure resources via the azure-client host (the landing host for this lab).

1) Create a new Azure Virtual Machine named nautilus-vm using the Azure CLI.

2) Use the Ubuntu2204 image and set the VM size to Standard_B2s.

3) Make sure the admin username is set to azureuser and SSH keys are generated for secure access.

4) Use Standard_LRS storage account, disk size must be 30GB and ensure the VM nautilus-vm is in the running state after creation.



Approach:
   We will be already logged into azure using az login.
   1. Identify the default resource group and store it in some varible.
      ```
      az group list
      RG_NAME=<resource_group_name>
      ```
   2. create the vm in the deafult resource group.
      ```
      az vm create \
      --resource-group $RG_NAME \
      --name nautilus-vm \
      --image Ubuntu2204 \
      --size Standard_B2s \
      --admin-username azureuser \
      --generate-ssh-keys \
      --storage-sku Standard_LRS \
      --os-disk-size-gb 30
      ```
   

   
