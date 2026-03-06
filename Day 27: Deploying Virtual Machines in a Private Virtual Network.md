## Day 27 Deploying Virtual Machines in a Private Virtual Network

#### Task Details 
The Nautilus DevOps team is expanding their Azure infrastructure and requires the setup of a private Virtual Network (VNet) along with a subnet. This VNet and subnet configuration will ensure that resources deployed within them remain isolated from external networks and can only communicate within the VNet. Additionally, the team needs to provision a Virtual Machine (VM) under the newly created private VNet. 
This VM should be accessible over SSH from within the VNet only, allowing for secure communication and resource management within the Azure environment. The name of the VNet must be `nautilus-priv-vnet`
- Create a subnet named nautilus-`priv-subnet` under the same. Further, create a Virtual Machine named `nautilus-priv-vm` under this VNet
- Additionally, create a Network Security Group (NSG) named `nautilus-priv-nsg` and ensure that the NSG rules for the VM allow access only from within the VNet's CIDR block
- Ensure all resources are created in the `Central US` region

#### STEPS
1. Sign in to the [Azure Portal](https://portal.azure.com/) 
2. Use the global search bar to search for “Virtual network.” From the results, select “Virtual network.”
3. From the Virtual Network dashboard, click on create button

<img width="578" height="232" alt="Screenshot 2026-02-24 094524" src="https://github.com/user-attachments/assets/f332f62d-726e-46c3-96fe-93bef0af0d91" />

4. On the Basics tab of the Create virtual network page, enter the VM name and select the appropriate region.

<img width="605" height="492" alt="Screenshot 2026-02-24 094615" src="https://github.com/user-attachments/assets/65d20b5f-102b-4fd3-a28f-df4f85166dc1" />

5. On the IP addresses tab, select + Add subnet. In the Add subnet pane, enter a name for the subnet, and then enable Private subnet.

<img width="678" height="234" alt="Screenshot 2026-02-24 094824" src="https://github.com/user-attachments/assets/695d1749-e203-48a6-afe8-5be33791eb42" />

6. Select Create

<img width="680" height="593" alt="Screenshot 2026-02-24 094935" src="https://github.com/user-attachments/assets/f9325d8f-82cf-4565-8979-ed9eb82b3cd5" />

7. Use the global search bar to search for “Virtual Machines.” From the results, select “Virtual Machines.”

<img width="633" height="238" alt="Screenshot 2026-02-24 095244" src="https://github.com/user-attachments/assets/1f51aef4-bb64-4aed-911a-eda1ad68b8cc" />

8. Create the vm

<img width="678" height="263" alt="Screenshot 2026-02-24 095333" src="https://github.com/user-attachments/assets/6649e652-5ce1-4ed1-bb9f-0d97de1224e8" />

9. On the Basics tab, select the existing resource group, enter the VM name, and choose the region

<img width="681" height="295" alt="Screenshot 2026-02-24 095820" src="https://github.com/user-attachments/assets/f8d092c0-3220-4c26-850e-621433f049e9" />

10. On the Networking tab, create a new Network security group, then add an inbound security rule.

<img width="680" height="428" alt="Screenshot 2026-02-24 100630" src="https://github.com/user-attachments/assets/254d0795-6100-4e15-a341-47aefc1547da" />
<img width="681" height="295" alt="Screenshot 2026-02-24 095820" src="https://github.com/user-attachments/assets/8829c5d1-fd18-49ae-b13d-9a71eff0b932" />

11. Create the vnm

<img width="684" height="595" alt="Screenshot 2026-02-24 100726" src="https://github.com/user-attachments/assets/5d9d3835-94e4-4e58-b263-c6895d2601c7" />



