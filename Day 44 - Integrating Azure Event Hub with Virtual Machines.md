## Day 44: Integrating Azure Event Hub with Virtual Machines

## Task Details:

The Nautilus DevOps team wants to integrate an Azure Virtual Machine with Azure Event Hubs for centralized log collection. Follow these steps to complete the task:

- Create Azure Event Hubs Namespace:
  - Create an Event Hubs namespace named `datacenter-namespace` in the `East US` region.

  > Select the `Standard` pricing tier. Make sure to enable `Enable Auto-inflate`

- Create an Event Hub:
  > Within the namespace, create an Event Hub named `datacenter-hub`

- Verify the Virtual Machine Configuration: A VM named `datacenter-vm` already exists

- A Python script named `send_logs.py` already exists on the VM under `/home/azureuser` This script is used to send logs to the Event Hub.
  > Make sure to execute this script mutiple times.

- Verify Logs: Ensure the logs are successfully sent to the Event Hub by checking the Event Hubs metrics in the Azure portal.

## Steps:

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. Search for and select Event Hub in the azure portal search bar

    <img width="760" height="277" alt="Screenshot 2026-03-24 220320" src="https://github.com/user-attachments/assets/ed9dd3ab-0cb3-43d3-a2d2-9c0345c35f12" />

3. Select + Create

    <img width="743" height="260" alt="Screenshot 2026-03-24 220331" src="https://github.com/user-attachments/assets/6256762a-6879-4f09-9bf1-139d31b8b2ee" />

4. On the Basics tab, enter the following:

    <img width="759" height="713" alt="Screenshot 2026-03-24 220445" src="https://github.com/user-attachments/assets/fa980745-dcc6-49cf-b18f-d1dbac46e1cf" />

5. Review + create

6. On the newly created namespace `datacenter-namespace`, Under Entities, select + Event Hubs.

    <img width="909" height="547" alt="Screenshot 2026-03-24 220654" src="https://github.com/user-attachments/assets/399d47c3-1ce8-445d-944a-1e42e13d09f7" />

7. On the Basics tab, enter the following:

    <img width="771" height="411" alt="568680167-8ef2d3b1-c3b1-496a-bfed-b5047d2f56ee" src="https://github.com/user-attachments/assets/9f9c5a26-9ab5-453f-8de4-f55f15dd9396" />

8. Review + Create

9. Search for and select Virtual Machine in the azure portal search bar

10. Select the VM named `datacenter-vm` and and copy its IP address.

11. In the Azure CLI, SSH into the vm
    ```
    ssh azureuser@<vm's pubic ip>
    ```

12. Verify the log sending script exists
    ```
    ls
    ```

13. In the Azure portal, navigate to the Event Hub namespace `datacenter-namespace`

14. Under Settings > Shared access policies > RootManageSharedAccessKey > copy the Connection string–primary key.

    <img width="1091" height="821" alt="Screenshot 2026-03-24 221455" src="https://github.com/user-attachments/assets/0513b637-5c68-4d5f-bdb2-3380e68c1583" />

15. Update the Python Script
    ```
    vi send_logs.py
    
    ## replace the <your_event_hub_connection_string> with with the actual key from Azure
    <connection_str = "<your_event_hub_connection_string>"
    ```

16. Run the Python script multiple times to send logs to Event Hubs
    ```
    python3 send_logs.py
    ```

17. Navigate to the Event Hub namespace `datacenter-hub` and verify message flow by checking relevant metrics.



