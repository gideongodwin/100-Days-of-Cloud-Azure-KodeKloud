## Day 22: Configuring Instances with User Data

## Task Details:

The Nautilus DevOps Team is working on setting up a new virtual machine (VM) to host a web server for a critical application. The team lead has requested you to create an Azure VM that will serve as a web server using Nginx. This VM will be part of the initial infrastructure setup for the Nautilus project. Ensuring that the server is correctly configured and accessible from the internet is crucial for the upcoming deployment phase.
As a member of the Nautilus DevOps Team, your task is to create a VM with the following specifications:

- Instance Name: The VM must be named `xfusion-vm`

- Image: Use any available `Ubuntu` image to create this VM

- Custom Script Extension/User Data: Configure the VM to run a custom script during its launch. This script should:

  - Install the Nginx package
  
  - Start the Nginx service

- Network Security Group (NSG): Ensure that the VM allows HTTP traffic on port `80` from the internet

## STEPS

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. From the Azure portal dashboard, Click on Virtual Machines and Create.

    <img width="607" height="347" alt="550433996-6746109f-dbde-4f5b-9070-87d713125c1b" src="https://github.com/user-attachments/assets/dd25cc8c-5c36-482a-9a3a-9ac176ce2178" />

3. On the Basics tab, enter `xfusion-vm` in the Virtual machine name field

    <img width="597" height="366" alt="550436834-5c7017e1-e8bb-4597-89d6-063284c8fac2" src="https://github.com/user-attachments/assets/b5c4be54-1b2d-4077-9383-fe8b954cb212" />
 
4. Select an available Ubuntu Server image

    <img width="657" height="143" alt="550438992-31374468-0190-4684-8bd1-3d31cadc7b17" src="https://github.com/user-attachments/assets/6982acd0-4e2a-4c63-8144-08e6f813654c" />

5. On the Networking tab > Network interface > Advanced, then create a new Network Security Group (NSG)

    <img width="656" height="337" alt="550442808-b6279c4e-07d1-496c-868d-faff2aa76dee" src="https://github.com/user-attachments/assets/761ce960-4e5c-43ba-94a5-f36c688442bb" />
 
6. In the newly created Network Security Group (NSG), add a new inbound security rule and select `HTTP` as the service to allow traffic on port `80`

    <img width="666" height="562" alt="550447363-ffe641a0-6404-4658-9c0d-e85bf88868b7" src="https://github.com/user-attachments/assets/e36bc265-ec40-4ffc-af3b-bf4cf825f1cc" />

 
7. On the Tags tab, under Custom data, paste the following script to run during VM launch:
    ```
    #!/bin/bash
       apt update -y && apt install nginx -y
       systemctl start nginx
    ```

8. Review + Create



