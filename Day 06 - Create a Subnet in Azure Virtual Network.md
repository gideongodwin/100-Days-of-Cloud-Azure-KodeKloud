## Day 6: Create a Subnet in Azure Virtual Network

## Task Details:

The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the Azure cloud. 
Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition.

- Create a Virtual Network (VNet) named `devops-vnet` and one subnet named `devops-subnet` within the VNet in the `East US` region. Make sure the IPv4 address range is `10.0.0.0/16`

## STEPS:

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Search for and select "Virtual Network" in the azure portal search bar.

   <img width="874" height="265" alt="571040243-84e71c27-1095-4988-84d4-9b3c1d063abf" src="https://github.com/user-attachments/assets/97694604-6724-4c1c-9b4a-16f8244e0474" />

3. From the Virtual Network page, click on create

   <img width="957" height="291" alt="552716420-48ed7850-0d4c-4e7a-8543-b19386d21a0d" src="https://github.com/user-attachments/assets/511d5df8-eb4f-4003-a7a0-b05d7d09bc93" />

4. On the Basics tab, Enter the VM name and select the appropriate region.

   <img width="617" height="402" alt="552719988-d89f26e4-212e-4121-8c8d-0cca5c5874b6" src="https://github.com/user-attachments/assets/07f81dce-2912-4233-926e-d8d54bb83040" />

5. On the IP address tab, click Next, update the default subnet name to devops-subnet, and then select Save

   <img width="657" height="560" alt="537735216-d67555b3-977a-4767-b542-f3bf8464f10f" src="https://github.com/user-attachments/assets/01d7f196-a984-42e6-a46d-90978c25dff5" />

6. Review + Create
