## Day 2 - Create an Azure Virtual Machine

## Task Details:
The Nautilus DevOps team is planning to migrate a portion of their infrastructure to the Azure cloud incrementally. As part of this migration, you are tasked with creating an Azure Virtual Machine (VM).
The requirements are:
- Use the existing resource group.

-  The VM name must be `xfusion-vm`, it should be in West us region.

-  Use the `Ubuntu 22.04 LTS` image for the VM.

-  The VM size must be `Standard B1s`.

-  Attach a default Network Security Group (NSG) that allows inbound SSH (port 22).

-  Attach a 30 GB storage disk of type `Standard HDD`.

-  The rest of the configurations should remain as default.

## STEPS

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Select the "Virtual Machines" from the Azure portal  

3. From the Virtual Machines page > Create VM

   <img width="683" height="246" alt="536767839-8164100d-1c26-4cac-9bcd-7c36bd3caffc" src="https://github.com/user-attachments/assets/dc9877bf-7bad-47f4-bbb6-bee818569e71" />

4. On the Basics tab, enter the VM name, and choose the appropriate region

   <img width="681" height="423" alt="536775124-cdf98ba7-3514-4d49-a571-7306e728cdc6" src="https://github.com/user-attachments/assets/875bc398-c66e-4ed2-8a0a-24e75a24a37f" />

5. Select the image and size

   <img width="668" height="363" alt="536776020-a2c947ae-86d9-4f8a-b997-cfee2aa62524" src="https://github.com/user-attachments/assets/901dcbff-b876-431f-9d5c-bf0effb442f7" />

6. Allow inbound traffic for SSH on `port 22`

   <img width="665" height="346" alt="536780230-59d52dd5-4ade-4a74-8d8f-db1035fdbb22" src="https://github.com/user-attachments/assets/c40ea47a-8508-48df-9b16-5fdf77d00081" />

7. On the Disks tab, attach a `30GB` storage disk of type `Standard HDD`

   <img width="681" height="177" alt="6" src="https://github.com/user-attachments/assets/3b39acd1-e805-4fd5-9f93-72ab9a824ff8" />

 

