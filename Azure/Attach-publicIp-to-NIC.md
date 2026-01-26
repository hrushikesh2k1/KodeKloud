The Nautilus DevOps team has already set up a virtual machine and allocated a public IP address. The final task is to attach this public IP to the VM's network interface card (NIC).

An existing VM named devops-vm-pip and a public IP address named devops-pip already exist.

Attach the public IP devops-pip to the network interface of the VM devops-vm-pip.
Make sure the VM is properly assigned the public IP.

Approach:
1. Go to portal.azure.com
2. The NIC "devops-vm-pipVMNic" is already attached to VM "devops-vm-pip"
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dcad7985-3d57-459e-84bb-5da0fbb0dd91" />
3. Go to public Ip address "devops-pip", click on associate, select Network interface from dropdown and select "devops-vm-pipVMNic"
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8f5a2ba0-7318-4a06-84a9-1069ea3f7a7f" />
4. You can confirm from the fields Associated to & Virtual machine.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2267ce48-3018-4878-a664-b527494317db" />
