## Day 48 - VM and ACR Integration for Storage

## Task Details:

The Nautilus DevOps team needs to set up an Azure Virtual Machine (VM) to interact with an Azure Blob Storage container for storing and retrieving data. The team must create a private storage account, configure Blob Storage, and test the functionality.
Task:

1. **Azure Virtual Machine Setup:**

   - Create a VM named `datacenter-vm` in the `East US` region.
   - Authentication: Use SSH public key authentication. (Please select use existing public key option, create `public-key` locally and paste contents of `~/.ssh/id_rsa.pub`).
   - Install `Docker` and `Azure CLI` on the VM.
   - Pull the Docker image from the ACR and run it on the VM, ensuring it listens on port `80`.

2. **Azure Container Registry (ACR) Setup:**

   - Create an ACR named `datacenteracr10390` in the `East US` region.
   - The repository name should be `datacenter/python-app`.
   - Build the Docker image using the `Dockerfile` already given under `/root/pyapp`.
   - Push the Docker image to the ACR with the tag `latest`.

3. **Create a Storage Account and Blob Container:**

   - Create a storage account named `datacenter20684` in the `East US` region with `Locally-redundant storage (LRS)`.
   - Create a Blob container named `datacentern-config`.
   - Upload a file named `config.json` (available under `/root/`) to the container.

4. **Validation:**
   - Confirm that the application can be accessed on the browser.

## Steps:

1. Sign in to the [Azure Portal](https://portal.azure.com/) 

2. From the Azure portal dashboard, select and create Virtual machine.

      <img width="893" height="331" alt="Screenshot 2026-03-30 203004" src="https://github.com/user-attachments/assets/851d38dc-a619-4470-bace-dacbb1b46601" />

3. On the Basics tab, select the existing resource group, and enter the following:

      <img width="802" height="604" alt="Screenshot 2026-03-30 215737" src="https://github.com/user-attachments/assets/544e21f5-e01a-4b3c-a423-dfdb894374d1" />

4. In the Azure CLI, run the following command to create an SSH key:
    ```
    ssh-keygen
    ```

5. Copy the contents of the public key and paste
    ```
    cat .ssh/id_rsa.pub
    ```
      <img width="856" height="653" alt="Screenshot 2026-03-30 215808" src="https://github.com/user-attachments/assets/0e70f8f1-9a7f-488d-8bd4-778c4f47c81a" />

6. On the Disks tab, select disk size and type.

      <img width="808" height="174" alt="Screenshot 2026-03-30 215825" src="https://github.com/user-attachments/assets/1970a5da-9dde-45ba-9bb6-1690440a39cf" />

7. Review + Create

8. Search for and select “Container registries” in the azure portal search bar

      <img width="873" height="285" alt="Screenshot 2026-03-30 203704" src="https://github.com/user-attachments/assets/1b3ceb57-b66c-43c4-b4d0-ef02de991dc4" />

9. From the Container registries page, click on create button

      <img width="932" height="234" alt="Screenshot 2026-03-30 220040" src="https://github.com/user-attachments/assets/5f34c086-0ca2-4fc2-b084-3c469a037d69" />

10. On the Basics tab, configure the following:

      <img width="793" height="599" alt="Screenshot 2026-03-30 220102" src="https://github.com/user-attachments/assets/67e651fd-e860-41d8-80c6-cebc6214edaf" />

11. From the Azure portal dashboard, select and create storage account

      <img width="876" height="209" alt="Screenshot 2026-03-30 220126" src="https://github.com/user-attachments/assets/8276e543-ed37-4673-89da-ce1456cc943e" />

12. On the Basics tab, configure the following:

      <img width="800" height="666" alt="Screenshot 2026-03-30 220333" src="https://github.com/user-attachments/assets/0f4a9597-c49c-4397-8825-7d8b24495b9d" />

13. In the storage account `datacenter10390` > Data storage > Containers, add the Blob container `datacenter-config`

      <img width="924" height="676" alt="Screenshot 2026-03-30 220620" src="https://github.com/user-attachments/assets/2f348a1a-01be-4957-9d76-b4c711d65ffb" />

14. In the Azure CLI, navigate to the pyapp directory
      ```
      cd pyapp
      ```

15. Login to the ACR
      ```
      az acr login --name datacenteracr10390
      ```

16. Build Docker Image
      ```
      docker build -t datacenteracr10390.azurecr.io/datacenter/python-app:latest .
      ```

16. Push Image
      ```
      docker push  datacenteracr10390.azurecr.io/datacenter/python-app:latest
      ```

16. SSH into the `datacenter-vm`
      ```
      ssh azureuser@<vm's public ip>
      ```

17. Install Docker
      ```
      sudo apt update
      sudo apt install -y docker.io
      sudo systemctl enable docker
      sudo systemctl start docker
      sudo usermod -aG docker azureuser
      ```

18. Install Azure CLI
      ```
      curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
      ```

19. Exit the vm
      ```
      exit
      ```

20. Go back to home directory
      ```
      cd ../
      ```

21. Copy Config File to VM
         ```
         scp config.json azureuser@<vm's public ip>:/home/azureuser/
         ``` 

22. SSH into the `datacenter-vm`
      ```
      ssh azureuser@<vm's public ip>
      ```

23. On the ACR `datacenteracr10390` > Settings > Access Keys > Enable Admin User

      <img width="1113" height="483" alt="Screenshot 2026-03-30 222145" src="https://github.com/user-attachments/assets/166bc337-666c-4ad2-811a-5b9df3cb192b" />

24. Login to ACR
      ```
      docker login xfusionacr20684.azurecr.io
      ```
      > Use the credentials gotten from step 19

25. Run Container
      ```
      docker run -d -p 80:80 \
      -v /home/azureuser/config.json:/app/config.json \
      --name datacenter-app \
      datacenteracr10390.azurecr.io/datacenter/python-app:latest
      ```

26. Verify Docker container is running successfully 
      ```
      docker ps
      ```

27. Upload Config File to Storage Account
      ```
      az storage blob upload \
      --account-name datacenterstor10390 \
      --container-name datacenter-config \
      --name config.json --file config.json
      ```

28. Verify in browser
      ```
      http://<vm-public-ip>
      ```
