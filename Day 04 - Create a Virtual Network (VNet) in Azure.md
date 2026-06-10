## Day 4 - Create a Virtual Network (VNet) in Azure

## Task Details: 
The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the Azure cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. 

To achieve this, they have segmented large tasks into smaller, more manageable units. This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations.

- Create a Virtual Network (VNet) named `xfusion-vnet` in the `East US` region with any `IPv4` CIDR block

## STEPS

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Search for and select "Virtual Network" in the azure portal search bar.

    <img width="874" height="265" alt="Screenshot 2026-03-29 230500" src="https://github.com/user-attachments/assets/12b77b43-2540-4711-b73e-c8790e3381ef" />

3. From the Virtual Network page, click on create

    <img width="941" height="290" alt="537216920-84acae21-67f0-4f3e-9725-389521f3a5b0" src="https://github.com/user-attachments/assets/2e7e5257-cc83-4ce5-ac5c-bec2901d9264" />

4. On the Basics tab, enter the vm name and select the appropriate region.

    <img width="773" height="603" alt="552708970-10d31f0d-a69f-4232-90c9-952e14161548" src="https://github.com/user-attachments/assets/3dcb4f09-c48f-43bd-8a8c-4b06c02e25a7" />

5. On the IP Addresses tab, keep the default address space `10.0.0.0/16` or update it to any valid CIDR block, such as `172.16.0.0/16`

   <img width="875" height="330" alt="Screenshot 2026-06-10 173155" src="https://github.com/user-attachments/assets/4fb3fbcc-516a-4972-8f71-33bd85dd7271" />

6. Then Review + create
