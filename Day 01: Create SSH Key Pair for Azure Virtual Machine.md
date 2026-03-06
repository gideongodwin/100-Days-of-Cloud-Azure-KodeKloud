## Day 1: Create SSH Key Pair for Azure Virtual Machine

#### Task Details:
Create an SSH key pair with the following requirements:
- The name of the SSH key pair should be `xfusion-kp`
- The key pair `type` must be `rsa`

#### STEPS

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Use the global search bar to search for "SSH keys"

3. From the results, select the SSH Keys service

<img width="820" height="309" alt="536431227-33a3a878-2133-4b82-9771-3fd75ab6c6b9" src="https://github.com/user-attachments/assets/c027615b-edac-42e8-b044-a0c5822dbcc6" />

4. Click on Create

<img width="677" height="233" alt="Screenshot 2026-02-20 132915" src="https://github.com/user-attachments/assets/174b88d5-8e71-4f73-bb0c-2bfe071e8bc7" />

5. Fill in the details and then click on review + create button at the bottom
- Resource Group: Select an existing one
- Key pair name: xfusion-kp
- SSH public key source: Select Generate new key pair
- Key type: Select RSA

 <img width="958" height="909" alt="4" src="https://github.com/user-attachments/assets/c039854e-9aaf-4ed8-b86b-13f81168414b" />

6. Click the refresh button to view the SSH key you just created

<img width="958" height="358" alt="536435625-a57ab822-5580-4a2a-8409-5f928d56159f" src="https://github.com/user-attachments/assets/e0412319-ab47-4d21-b4b3-7283d0b97207" />

 
