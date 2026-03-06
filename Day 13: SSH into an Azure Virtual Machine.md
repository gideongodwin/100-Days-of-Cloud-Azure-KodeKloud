## Day 13: SSH into an Azure Virtual Machine

#### Task Details:
The Nautilus DevOps team is working on setting up secure SSH access for their virtual machines in Azure. One of the requirements is to add the SSH public key of the root user from the Azure client host (landing host) to the `xfusion-vm`  Azure VM's `authorized_keys` file. This ensures secure and password-less SSH access to the VM.

1. VM Detalla
- The VM is named `xfusion-vm` and is running in the `East US` region.
- You need to add the root user's SSH public key from the Azure client host to the `authorized_keys` file of the VM's root user.
- The SSH public key of the root user on the Azure client host is located at `/root/.ssh/id_rsa.pub`

2. Public Key Addition
- Copy the public key located at `/root/.ssh/id_rsa.pub` on the Azure client host to the `authorized_keys` file of the root user on `xfusion-vm`
- Ensure that the proper permissions for the `.ssh` folder and `authorized_keys` file are set on the VM.

3. Verification:
After adding the public key, make sure that you are able to SSH into the `xfusion-vm` VM from the Azure client host without needing a password

Important Notes:
Ensure that the VM is up and running before attempting to SSH.
You may need to adjust the firewall or security group rules for the VM to allow SSH access.

#### STEPS:
1. Identify the Resource Group
    `az group list`
2. Retrieve the Virtual Machine Public IP Address
   `az vm list-ip-addresses -g <resource-group> -n xfusion-vm`
   - Record the public IP address for use in the following steps.
3. Copy the SSH Public Key to the Virtual Machine
   - Use scp to copy the root user’s SSH public key from the Azure client host to a temporary directory on the virtual machine.
     `scp /root/.ssh/id_rsa.pub azureuser@<VM_PUBLIC_IP>:/tmp/`
4. Add the Public Key to Root Authorized Keys
   -Connect to the virtual machine, switch to the root user, and add the public key to the root user’s `authorized_keys` file.
   - `ssh -T azureuser@<VM_PUBLIC_IP> <<-EOF`
   - `sudo -i`
   - `cat /tmp/id_rsa.pub > /root/.ssh/authorized_keys`
   - `rm /tmp/id_rsa.pub`
   - `EOF`
5. Verify that password-less SSH access is enabled by connecting as the root user.
   - `ssh root@<VM_PUBLIC_IP>`
6. Exit the session after verification
   - `exit`


