You are tasked with modifying an ARM template for deploying a virtual network. The current template is located in the /root/arm-templates directory under the filename vnet-deployment-template.json. You need to make the following changes to the template:

Change the name and displayName tag of the virtual network to arm-vnet-devops.

Update the addressPrefixes to 192.168.0.0/16.

Add one more tag named Environment with value KKE-devops.

After making these changes, you need to deploy the ARM template using the Azure CLI.

Use the following command to find out the resource group to use:

az group list --query '[].name' --output table | grep 'km

Approach:
1. Go to json file and edit as per task
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3c080521-f0bf-481d-a42e-db9f61074a5f" />
2. Deploy the ARM template
```
az deployment group create \
  --resource-group <RESOURCE_GROUP_NAME> \
  --template-file /root/arm-templates/vnet-deployment-template.json
```

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4fdee36d-d1a3-4e34-af20-b985e58c7d07" />
