## Day 33: Integrating Virtual Machines with Application Load Balancer

#### Task Details:
The Nautilus DevOps team is currently working on setting up a simple application on the Azure cloud. They aim to establish an Azure Load Balancer in front of a Virtual Machine (VM) where an Nginx server is currently running. While the Nginx server currently serves a sample page, the team plans to deploy the actual application later.

Set up an Azure Load Balancer named `devops-lb`
Configure the Load Balancer’s frontend IP configuration with the name `devops-lb-ip` and assign a public IP address with the same name `devops-lb-ip`
Create a backend pool named `devops-backend-pool` and add the VM running Nginx to this pool.
Create a health probe named `devops-health-probe` on port `80` to check the VM's health.
Set up a load balancer rule named `devops-lb-rule` to route traffic on port `80` to the backend pool on port `80`
Add an inbound rule to the existing NSG of the VM to allow HTTP traffic on port `80`

#### STEPS:
1. Sign in to the [Azure Portal](https://portal.azure.com/)
2. Search for Load balancer in the global search bar and select Load balancers.

<img width="588" height="254" alt="Screenshot 2026-03-05 100103" src="https://github.com/user-attachments/assets/b612cfbf-6044-4b2b-8f49-e5ec4a4dbcb9" />

3. Select Create, then choose Standard Load Balancer.

<img width="540" height="277" alt="Screenshot 2026-03-05 100112" src="https://github.com/user-attachments/assets/5b8df4a9-e94a-4cf6-a166-5b079577faf3" />

4. On the basics tab, give the load balancer a name and set the type to `public`

<img width="593" height="441" alt="Screenshot 2026-03-05 100154" src="https://github.com/user-attachments/assets/8487e8c6-81b5-4b3b-bce4-eb8d7583d086" />

5. On the Frontend IP configuration tab, configure the following settings.

<img width="659" height="568" alt="Screenshot 2026-03-05 100245" src="https://github.com/user-attachments/assets/08eac6d2-5dec-4a6c-805d-ccbc5c9974c1" />

6. On the Backend pools tab, select Add backend pool

<img width="652" height="288" alt="Screenshot 2026-03-05 100353" src="https://github.com/user-attachments/assets/022a465f-5f48-4aba-b494-ab9ff2cff1bc" />

7. Enter a name for the backend pool and add IP configurations.

<img width="633" height="424" alt="Screenshot 2026-03-05 100427" src="https://github.com/user-attachments/assets/0d1f6f97-906f-4b39-9534-be6f815161af" />



