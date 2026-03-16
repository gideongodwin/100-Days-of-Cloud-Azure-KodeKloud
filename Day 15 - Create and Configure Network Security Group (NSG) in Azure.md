## Day 15: Create and Configure Network Security Group (NSG) in Azure

#### Task Details:
The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the Azure cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. To achieve this, they have segmented large tasks into smaller, more manageable units. This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations. By breaking down the migration into smaller tasks, the Nautilus DevOps team can systematically progress through each stage, allowing for better control, risk mitigation, and optimization of resources throughout the migration process.

For this task, create a network security group (NSG) with the following requirements:
- Name of the NSG should be `devops-nsg`
- Add an inbound security rule named `Allow-HTTP` for `HTTP` service on port `80`, with the source CIDR range of `0.0.0.0/0`
- Add another inbound security rule named `Allow-SSH` for `SSH` service on port `22`, with the source CIDR range of `0.0.0.0/0`

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Search for Network Security Group (NSG) using the Azure portal search bar, then select Network Security Groups from the results

<img width="956" height="250" alt="Screenshot 2026-02-07 182045" src="https://github.com/user-attachments/assets/a995f64e-008d-4775-ad88-8e19a033127a" />

3. Then click on create

<img width="955" height="736" alt="Screenshot 2026-02-07 182107" src="https://github.com/user-attachments/assets/1897918c-8711-4a6a-a5aa-060797c11fa9" />

4. On the Basics tab, select the existing resource group and enter a name for the NSG

<img width="955" height="867" alt="Screenshot 2026-02-07 182147" src="https://github.com/user-attachments/assets/9cd0ff5f-873c-4ef3-ad93-8506fd5b7d95" />

5.  Click on create.

<img width="957" height="864" alt="Screenshot 2026-02-07 182216" src="https://github.com/user-attachments/assets/ea7594d3-324b-4022-a56d-70d362e47f64" />

6. From the NSG, select Settings and then Inbound security rules.
7. Click on the Add button to add inbound security rule
8. Configure the rule with the following values:

    | Setting                 | Value      |
    |-------------------------|------------|
    | Name                    | Allow-HTTP |
    | Service                 | HTTP       |
    | Destination port ranges | 80         |
    | CIDR ranges             | 0.0.0.0/0  |

9. Select Add to create the rule.

<img width="959" height="862" alt="Screenshot 2026-02-07 182509" src="https://github.com/user-attachments/assets/e07ad8bb-c2ca-426c-82de-4ef6e15cc677" />
<img width="959" height="307" alt="Screenshot 2026-02-07 182523" src="https://github.com/user-attachments/assets/7d683195-9cc9-41de-a95e-bde107288606" />

10. Select Add inbound security rule again
11. Configure the rule with the following values:

    | Setting                 | Value      |
    |-------------------------|------------|
    | Name                    | Allow-SSH  |
    | Service                 | SSH        |
    | Destination port ranges | 22         |
    | CIDR ranges             | 0.0.0.0/0  |

12. Select Add to create the rule.

<img width="954" height="864" alt="Screenshot 2026-02-07 182657" src="https://github.com/user-attachments/assets/acc804b7-94cc-4a6a-83ba-0b7c7a5e0896" />
<img width="957" height="305" alt="Screenshot 2026-02-07 182708" src="https://github.com/user-attachments/assets/4dab0b32-1127-49b3-a3ff-336fe5b03c97" />





