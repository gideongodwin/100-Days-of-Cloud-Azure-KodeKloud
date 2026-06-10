## Day 1 - Create SSH Key Pair for Azure Virtual Machine

## Task Details:

The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the Azure cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. To achieve this, they have segmented large tasks into smaller, more manageable units. 

This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations. By breaking down the migration into smaller tasks, the Nautilus DevOps team can systematically progress through each stage, allowing for better control, risk mitigation, and optimization of resources throughout the migration process.

For this task, create an SSH key pair with the following requirements:

- The name of the SSH key pair should be `xfusion-kp`

- The key pair `type` must be `rsa`

## STEPS

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Search for and select "SSH Keys" in the azure portal search bar.

3. From the results, select the SSH Keys service

   <img width="882" height="274" alt="Screenshot 2026-03-29 190847" src="https://github.com/user-attachments/assets/5a4b39e3-23bb-4dfe-b7ef-fad2e3e23701" />

4. On the SSH Key page, select Create

   <img width="677" height="233" alt="Screenshot 2026-02-20 132915" src="https://github.com/user-attachments/assets/174b88d5-8e71-4f73-bb0c-2bfe071e8bc7" />

5. On the Basics tab, select the existing resource group and enter the following.

   <img width="641" height="525" alt="536434843-c039854e-9aaf-4ed8-b86b-13f81168414b" src="https://github.com/user-attachments/assets/a53aba01-a2a2-40fd-924a-ab5700ebd5b0" />

6. Review + Create

7. Go to the SSH Keys page to view the newly created SSH key.

   <img width="930" height="259" alt="552693531-e0412319-ab47-4d21-b4b3-7283d0b97207" src="https://github.com/user-attachments/assets/38f36414-cd83-4d47-8c0c-500fe78e7365" />

