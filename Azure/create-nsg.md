The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the Azure cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. To achieve this, they have segmented large tasks into smaller, more manageable units. This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations. By breaking down the migration into smaller tasks, the Nautilus DevOps team can systematically progress through each stage, allowing for better control, risk mitigation, and optimization of resources throughout the migration process.

For this task, create a network security group (NSG) with the following requirements:

Name of the NSG should be devops-nsg.

Add an inbound security rule named Allow-HTTP for HTTP service on port 80, with the source CIDR range of 0.0.0.0/0.

Add another inbound security rule named Allow-SSH for SSH service on port 22, with the source CIDR range of 0.0.0.0/0.


Approach:
1. Go to portal.azure.com
2. search for NSG service and click on create.
3. Name it "devops-nsg"
4. Go to devops-nsg resource and click on In-bound security rule blade on left and add HTTP & SSH service with Allow-HTTP & Allow-SSH names respectively
5. <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d20c8f90-250d-402e-832f-e60e15d92e1c" />
