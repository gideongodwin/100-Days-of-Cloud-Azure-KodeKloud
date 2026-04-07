## Day 33 - Integrating Virtual Machines with Application Load Balancer

## Task Details:

The Nautilus DevOps team is currently working on setting up a simple application on the Azure cloud. They aim to establish an Azure Load Balancer in front of a Virtual Machine (VM) where an Nginx server is currently running. While the Nginx server currently serves a sample page, the team plans to deploy the actual application later.

- Set up an Azure Load Balancer named `devops-lb`

- Configure the Load Balancer’s frontend IP configuration with the name `devops-lb-ip` and assign a public IP address with the same name `devops-lb-ip`

- Create a backend pool named `devops-backend-pool` and add the VM running Nginx to this pool.

- Create a health probe named `devops-health-probe` on port `80` to check the VM's health.

- Set up a load balancer rule named `devops-lb-rule` to route traffic on port `80` to the backend pool on port `80`

- Add an inbound rule to the existing NSG of the VM to allow `HTTP` traffic on port `80`

## Steps:

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Search for and select "Load balancer" in the azure portal search bar.

<img width="588" height="254" alt="Screenshot 2026-03-05 100103" src="https://github.com/user-attachments/assets/b612cfbf-6044-4b2b-8f49-e5ec4a4dbcb9" />

3. Select Create, then choose Standard Load Balancer.

<img width="540" height="246" alt="558651125-5b8df4a9-e94a-4cf6-a166-5b079577faf3" src="https://github.com/user-attachments/assets/031df9a6-fa05-43f5-a52d-5813a8671c19" />

4. On the Basics tab, configure the following:

<img width="593" height="441" alt="Screenshot 2026-03-05 100154" src="https://github.com/user-attachments/assets/8487e8c6-81b5-4b3b-bce4-eb8d7583d086" />

5. On the Frontend IP configuration tab, configure the following settings.

<img width="648" height="540" alt="558668594-08eac6d2-5dec-4a6c-805d-ccbc5c9974c1" src="https://github.com/user-attachments/assets/56e3384d-a8bb-4353-9477-6c16e97681cb" />

6. On the Backend pools tab, select Add backend pool

<img width="652" height="188" alt="558670727-022a465f-5f48-4aba-b494-ab9ff2cff1bc" src="https://github.com/user-attachments/assets/82112990-628e-4352-b7c7-f7c38e8905b5" />
 
7. In the Add a backend pool window, configure the following:.

    <img width="633" height="395" alt="558673313-0d1f6f97-906f-4b39-9534-be6f815161af" src="https://github.com/user-attachments/assets/60c98f86-5524-4376-8571-f443b05950f7" />

    <img width="657" height="291" alt="558676373-3c9412fc-07dc-446e-842f-79eddb18b171" src="https://github.com/user-attachments/assets/a961d5ba-3dfc-4ab6-9ae0-885e47e17c99" />

8. On the Inbound rules tab, add a new rule and configure the settings as follows

    <img width="638" height="549" alt="558680834-6d98ce87-5ebd-4547-b15e-2695cb8b2f7e" src="https://github.com/user-attachments/assets/56800039-016d-4b85-8300-0bb78d7b789d" />

9. Create new Health Probe

    <img width="643" height="350" alt="558683730-3a3f1faf-080f-4904-ac90-9b15dd213672" src="https://github.com/user-attachments/assets/1bbddaad-b205-4e3d-ab52-5081e749a99e" />

10. Review + Create.

<img width="602" height="577" alt="Screenshot 2026-03-05 100805" src="https://github.com/user-attachments/assets/2d376840-cfc7-4fdc-b444-5f16ea91f8b3" />

11. In the Azure dashboard, select Resource groups

<img width="527" height="174" alt="Screenshot 2026-03-05 101123" src="https://github.com/user-attachments/assets/cf09b020-6a73-43b4-9aae-28f065b4a09a" />

12. Select the existing resource.

<img width="639" height="378" alt="Screenshot 2026-03-05 101133" src="https://github.com/user-attachments/assets/88fecfd7-9dd2-4daa-bdab-886422bf2aec" />

13. Select the existing NSG

<img width="652" height="511" alt="Screenshot 2026-03-05 101158" src="https://github.com/user-attachments/assets/b7a82aba-8b32-4cb7-8df4-ea86b0d2fc39" />

14. Add an inbound rule to the existing NSG of the VM to allow HTTP traffic on port `80`

<img width="631" height="569" alt="Screenshot 2026-03-05 101237" src="https://github.com/user-attachments/assets/95d3e95d-c6bb-4bd5-8db5-c8871e3f9d53" />



