## Day 49 - VM Setup with Web Storage Integration

## Task Details:
The Nautilus DevOps team is tasked with setting up an environment to host a static web application. The application will serve static content from an Azure Storage Account, and a Virtual Machine (VM) will be configured to fetch and display this content using Nginx. The Azure Storage Account is used as a secure, centralized location for storing the index.html file. The team intentionally keeps this file outside the main source code repository, since that repository contains additional internal application code that should not be exposed to or accessed by the VM. By placing only the required static file in the Storage Account, the team can distribute this asset safely and independently of the full codebase.

The VM should securely download the index.html blob directly from the designated container (e.g., using Azure CLI, SAS URL, or REST API) and place it in Nginx’s web root directory so that it is served locally by Nginx. The Storage Account is not mounted, and the Static Website feature is not used. The VM retrieves the file during deployment and may re-fetch it whenever updates are needed. The resources must follow best practices for security, performance, and accessibility.


Task Details:

- **Create a Virtual Network (VNet) and Subnet:**

  - Create a VNet named `devops-vnet` in the `East US` region.
  
  - Create a subnet named `devops-subnet` within the VNet for the VM.

- **Create an Azure Storage Account:**
  
  - Create a storage account named `devopsstor22055` in the `East US` region with `Locally-redundant storage (LRS)`
  
  - Create a Blob container named `devops-container` in the storage account.
  
  - Upload the `index.html` file located at `/root` on the client host to the container `devops-container`
  
  - Ensure the Storage Account is `private` and not publicly accessible by disabling public access for the storage account.

- **Create a Virtual Machine (VM):**

  - Create a VM named `devops-vm` in the `East US` region.
  
  - Use the `devops-vnet` and subnet `devops-subnet` for the VM.
  
  - Authentication: Use `SSH public key` authentication. (Please select use existing public key option, create public-key locally and paste contents of ~/.ssh/id_rsa.pub)

- Install `Nginx` on the VM.

- Download the `index.html` file using a command such as:

    ```
    sudo az storage blob download --account-name devopsstor6110 --account-key xxxxx --container-name devops-container --name index.html --file /var/www/html/index.html`
    ```
> Ensure `Nginx` is configured to serve the file from `/var/www/html/index.html`

- Verify Setup:

  - Verify that the Nginx web server on the client host serves the index.html file correctly when accessing the VM's public IP address.

 
## Steps:

1. Sign in to the [Azure Portal](https://portal.azure.com/) 

2. Search for and select “Virtual network” in the azure portal search bar

3. From the Virtual Network dashboard, click on create button
    
    <img width="547" height="221" alt="Screenshot 2026-03-31 151447" src="https://github.com/user-attachments/assets/1faa5baf-f8a3-4b10-beed-4a78af9e05d5" />

4. On the Basics tab, configure the following;

<img width="576" height="294" alt="Screenshot 2026-03-31 151507" src="https://github.com/user-attachments/assets/be32dc09-2fac-473a-a549-87ad6350be52" />

5. On the IP addresses tab, Edit the existing subnet name to `devops-subnet`

   <img width="580" height="422" alt="Screenshot 2026-03-31 151541" src="https://github.com/user-attachments/assets/df38388e-b352-42a1-8e48-c69bb1b7d120" />

   <img width="638" height="550" alt="Screenshot 2026-03-31 151605" src="https://github.com/user-attachments/assets/80ed2dd0-3bae-4aea-b204-2c5b6c0ebc08" />

6. Review + Create

7. From the Azure portal dashboard, select and create storage account

    <img width="602" height="216" alt="Screenshot 2026-03-31 151759" src="https://github.com/user-attachments/assets/3d56ae1e-8191-4486-a968-9680772e3b24" />

8. On the Basics tab, select the existing resource group, and enter the following:

    <img width="585" height="433" alt="Screenshot 2026-03-31 151825" src="https://github.com/user-attachments/assets/c7c5ad86-e8a7-4b04-9962-f6716297f7f5" />

9. Review + Create

10. In the storage account `devopsstor6110` > Data storage > Containers, add the Blob container `devops-container`

    <img width="659" height="499" alt="Screenshot 2026-03-31 152040" src="https://github.com/user-attachments/assets/5a229a20-30f3-4561-b89c-5f93a64328c7" />

11. From the Azure portal dashboard, select and create Virtual machine.

  <img width="577" height="159" alt="Screenshot 2026-03-31 152104" src="https://github.com/user-attachments/assets/cfb0be89-6978-4543-b805-b491f16e0651" />

12.  On the Basics tab, select the existing resource group, and enter the following:

  <img width="596" height="357" alt="Screenshot 2026-03-31 152250" src="https://github.com/user-attachments/assets/c73042da-91db-44ab-912c-9d683d2cb802" />

13. In the Azure CLI, run the following command to create an SSH key:
    ```
    ssh-keygen
    ```

14. Copy the contents of the public key and paste
    ```
    cat .ssh/id_rsa.pub
    ```
  <img width="590" height="430" alt="Screenshot 2026-03-31 160055" src="https://github.com/user-attachments/assets/814d331b-49b6-485e-99ec-5d81dffc890f" />


16. Review + Create

17. Upload the `index.html` file to the container `devops-container`
    ```
    az storage blob upload --account-name devopsstor22055 --container-name devops-container --name index.html --file index.html
    ```

18. SSH into `devops-vm`
    ```
    ssh azureuser@<vm's public ip>
    ```

19. Install Nginx
    ```
    sudo apt update
    sudo apt install nginx -y
    ```

20. Install Azure CLI
    ```
    curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
    ```

21. In the Azure portal, navigate to the Storage Account `devopsstor22055`

22. Under Security + Networking > Access Keys, copy the connection string (key1)

    <img width="719" height="383" alt="Screenshot 2026-03-31 153744" src="https://github.com/user-attachments/assets/6b874400-eed9-48aa-9a4b-9528e57c7c1f" />

22. Download index.html to Nginx Web Root
    ```
    sudo az storage blob download \
      --account-name devopsstor22055 \
      --account-key <your-account-key> \
      --container-name devops-container \
      --name index.html \
      --file /var/www/html/index.html
    ```

23. Verify index.html file exists on the vm
    ```
    cd /var/www/html
    ls
    cat index.html
    ```

24. Start and Enable Nginx
    ```
    sudo systemctl start nginx
    sudo systemctl enable nginx
    ```

25. Verify in Browser
    ```
    http://<vm-public-ip>
    ``` 



