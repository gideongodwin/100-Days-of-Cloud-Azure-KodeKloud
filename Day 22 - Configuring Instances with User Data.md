## Day 22: Configuring Instances with User Data

#### Task Details:
The Nautilus DevOps Team is working on setting up a new virtual machine (VM) to host a web server for a critical application. The team lead has requested you to create an Azure VM that will serve as a web server using Nginx. This VM will be part of the initial infrastructure setup for the Nautilus project. Ensuring that the server is correctly configured and accessible from the internet is crucial for the upcoming deployment phase.
As a member of the Nautilus DevOps Team, your task is to create a VM with the following specifications:

- Instance Name: The VM must be named `xfusion-vm`
- Image: Use any available Ubuntu image to create this VM
- Custom Script Extension/User Data: Configure the VM to run a custom script during its launch. This script should:
- Install the Nginx package
- Start the Nginx service
- Network Security Group (NSG): Ensure that the VM allows HTTP traffic on port `80` from the internet

#### STEPS
1. Sign in to the [Azure Portal](https://portal.azure.com/)
2. From the Azure portal dashboard, Click on Virtual Machines and Create.

<img width="681" height="347" alt="Screenshot 2026-02-16 120542" src="https://github.com/user-attachments/assets/6746109f-dbde-4f5b-9070-87d713125c1b" />

3. On the Basics tab, enter `xfusion-vm` in the Virtual machine name field

<img width="683" height="597" alt="Screenshot 2026-02-16 121012" src="https://github.com/user-attachments/assets/5c7017e1-e8bb-4597-89d6-063284c8fac2" />

4. Select an available Ubuntu Server image

<img width="677" height="311" alt="Screenshot 2026-02-16 121049" src="https://github.com/user-attachments/assets/31374468-0190-4684-8bd1-3d31cadc7b17" />

5. On the Networking tab, under Network interface, select Advanced and create a new Network Security Group (NSG)

<img width="682" height="388" alt="Screenshot 2026-02-16 121419" src="https://github.com/user-attachments/assets/b6279c4e-07d1-496c-868d-faff2aa76dee" />

6. In the newly created Network Security Group (NSG), add a new inbound security rule and select HTTP as the service to allow traffic on port 80

 <img width="679" height="598" alt="Screenshot 2026-02-16 121554" src="https://github.com/user-attachments/assets/ffe641a0-6404-4658-9c0d-e85bf88868b7" />

7. On the Tags tab, under Custom data, paste the following script to run during VM launch:
`#!/bin/bash`
`apt update -y && apt install nginx -y`
`systemctl start nginx`

8. On Review + create, verify settings and click Create

<img width="684" height="595" alt="Screenshot 2026-02-16 122235" src="https://github.com/user-attachments/assets/923735a0-0051-4b84-921e-f873eb2a091b" />



