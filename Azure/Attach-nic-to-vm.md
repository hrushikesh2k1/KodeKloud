The Nautilus DevOps team is migrating services to Azure. They are breaking down tasks to ensure better control and optimization. You are tasked with attaching an existing network interface (NIC) to a virtual machine (VM).

An existing VM named devops-vm and a network interface named devops-nic already exist in the West US region.

Attach the network interface devops-nic to the VM devops-vm.
Ensure the NIC's status is attached before submitting the task.
Make sure that the virtual machine initialization has been completed before submitting this task.


Approach:
1. Go to portal.azure.com
2. Go to VM called "devops-vm"
3. Stop the virtual machine before attaching the NIC.
4. Go to Network settings, click on "Attach network interfaces"
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eaf69656-c4af-49bd-b1a2-e8f31df8e17a" />
5. select devops-nic from drop down.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/40e55a7e-9b8f-4dfd-8522-2b40c290eaad" />
6. Start the VM
7. Confirm that the NIC "devops-nic" is attached.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1264cb85-d519-4688-ade1-808407d76b33" />
