## Day 24 - Securing Virtual Machine SSH Access

## Task Details:

The Nautilus DevOps team needs to set up a new Virtual Machine (VM) on the Azure cloud that can be accessed securely from their landing host (azure-client). Follow the steps below to complete this task:

- Create an SSH Key
    - On the `azure-client` host, check if an SSH key already exists. If it doesn’t exist, create a new `SSH key` on the `azure-client` host that will be used for password-less SSH access.

- Create a Virtual Machine
    
    - Use the `Azure Portal` or `Azure CLI` to create a new Virtual Machine named `datacenter-vm` in the `westus` region.
    
    - Set the VM size to `Standard_B1s` and configure the VM with SSH access for the azureuser account using the newly created SSH key.

- Configure SSH Access
   
    - Ensure that the SSH key from the `azure-client` host is added to the azureuser account on `datacenter-vm` enabling secure, password-less SSH access from the azure-client host.

- Verify Connectivity
    
    - Test the connection from azure-client to datacenter-vm using SSH to confirm that password-less access has been set up correctly

## Steps:

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. From the Azure portal dashboard, Click on Virtual Machines and Create.

    <img width="607" height="347" alt="550433996-6746109f-dbde-4f5b-9070-87d713125c1b" src="https://github.com/user-attachments/assets/1c1f0177-803f-4161-8b21-b4c7f1324a68" />

3. On the Basics tab, enter `datacenter-vm` in the Virtual machine name field

    <img width="586" height="329" alt="552121238-64d68207-709d-414b-84e9-1c84fb1fe342" src="https://github.com/user-attachments/assets/5551f464-b705-4a31-aa7d-711f43b0d053" />

4. In the Azure CLI, run the following command to create an SSH key:
    ```
    ssh-keygen
    ```

5. Copy the contents of the public key and paste
    ```
    cat .ssh/id_rsa.pub
    ```
     <img width="661" height="197" alt="552122099-b0f46183-feb6-4426-af6d-d309a156ee9e" src="https://github.com/user-attachments/assets/67464f1d-f557-49b1-abf8-5c7a9a38b9da" />

6. Set the VM size to `Standard_B1s`

    <img width="654" height="252" alt="552126336-90eaba80-96d9-419b-a5f8-8d863ebbb3f5" src="https://github.com/user-attachments/assets/a4f399e6-6a20-4c51-ac14-02ff967b081e" />

7. Review + Create
 
8. In the Azure CLI, run the following command to verify connectivity
    ```
    ssh azureuser@<vm-public>
    ```
