## Day 41: Working with Azure Table Storage

#### Task Details:
The Nautilus DevOps team is developing a simple 'To-Do' application using Azure Table Storage to store and manage tasks efficiently.
The team needs to create an Azure Table to hold tasks, each identified by a unique taskId.
Each task will have a description and a status, which indicates the progress of the task (e.g., 'completed' or 'in-progress').

Your task is to:
- Create an Azure Storage Account named `datacentertablest4661` with a Table Storage table called `tasks`
- Insert the following tasks into the table:
  - Task 1: PartitionKey: 'tasks', RowKey: '1', description: 'Learn Table Storage', status: 'completed'
  - Task 2: PartitionKey: 'tasks', RowKey: '2', description: 'Build To-Do App', status: 'in-progress'
  - Verify that Task 1 has a status of `'completed'` and Task 2 has a status of `'in-progress'`
  - Note: Use the `Azure CLI` to insert these tasks into the table.

#### STEPS:
1. Sign in to the [Azure Portal](https://portal.azure.com/)

<img width="579" height="245" alt="Screenshot 2026-03-17 120525" src="https://github.com/user-attachments/assets/0643d088-04c3-4100-8cac-8c1276454cf2" />

2. From the Storage Accounts dashboard, click on create button

<img width="559" height="195" alt="Screenshot 2026-03-17 120539" src="https://github.com/user-attachments/assets/242697bb-d9db-4bf0-954f-b10668e67b47" />

3. On the Basics tab, select the existing Resource group, and then enter a name for the Storage account.

<img width="587" height="548" alt="Screenshot 2026-03-17 120627" src="https://github.com/user-attachments/assets/725186ca-4398-451e-9fa4-46d05301a246" />

4. Under Data storage, select Tables, and then select + Table to create a new table named `tasks`

<img width="568" height="396" alt="Screenshot 2026-03-17 120820" src="https://github.com/user-attachments/assets/c9450924-0706-44c0-b7b6-22eb1933a72a" />

5. On the Azure CLI, Insert Task 1:
```
az storage entity insert \
  --table-name tasks \
  --account-name datacentertablest4661 \
  --entity PartitionKey=tasks RowKey=1 description="Learn Table Storage" status="completed"
```

6.  Insert Task 2
```
az storage entity insert \
  --table-name tasks \
  --account-name datacentertablest4661 \
  --entity PartitionKey=tasks RowKey=2 description="Build To-Do App" status="in-progress"
```

7. Under Storage browser, select Tables to verify the status of Task 1 and Task 2

<img width="1067" height="344" alt="Screenshot 2026-03-17 121312" src="https://github.com/user-attachments/assets/20148bf2-8916-4031-8b53-e7d5b1d611cb" />




