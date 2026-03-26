The Nautilus DevOps team wants to integrate an Azure Virtual Machine with Azure Event Hubs and Azure Blob Storage for centralized log collection and backup. Follow these steps to complete the task:

Create Azure Event Hubs Namespace:

Create an Event Hubs namespace named nautilus-namespace in the East US region.
Select the Standard pricing tier. Make sure to enable Enable Auto-inflate.
Create an Event Hub:

Within the namespace, create an Event Hub named nautilus-hub.
Set Up Azure Blob Storage for Log Backup:

Create a Storage Account named nautilusst1338 in the East US region.
Create a container named nautilus-backup-29309 within the Storage Account.
Ensure the container is publicly accessible for read operations.
Verify the Virtual Machine Configuration:

The client host already has a Python script named send_logs.py located under /root. This script is used to send logs to the Event Hub.
Create a Virtual Machine named nautilus-vm in the East US region.
Copy the send_logs.py script from the client host to the /home/azureuser directory of the nautilus-vm.
Modify the script on the VM to also back up the logs to the nautilus-backup-29309 container in the Azure Blob Storage account.
Verify Logs:

Ensure the logs are successfully sent to the Event Hub by checking the Event Hubs metrics in the Azure portal.
Verify that the logs are backed up to the nautilus-backup-29309 container in the Azure Blob Storage.
