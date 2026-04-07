## Day 30: Create Azure SQL Database

## Task Details:

The Nautilus Devops team is strategizing the migration of a portion of their infrastructure to Azure. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition.
Recently, they started working on creating and configuring some database instances on Azure. 

For this task, create one `publicly` accessible Azure SQL Database instance along with the following details:

1) The name of the Azure SQL Database must be `devops-sqldb`

2) The server name must be `devops-server-19529` under `centralus`

3) The compute + storage configuration should be Basic (For less demanding workloads).

4) The backup storage redundancy should be Locally-redundant backup storage.

5) Set the login admin username to `devops-admin` and set an appropriate password.

6) Set the database size to 2 GiB.

7) Keep the rest of the configurations as `default` Finally, make sure the database is in the `Ready` state before submitting this task.

## Steps:

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. On the Azure dashboard, select SQL Databases and select Create

    <img width="958" height="341" alt="Screenshot 2026-03-02 195004" src="https://github.com/user-attachments/assets/e0c548c7-bf2c-425a-bedc-231b5c64c5b7" />

3. On the Basics tab, in the Database name field, enter `devops-sqldb`

   <img width="738" height="350" alt="557095981-88ec95df-918c-43eb-88d4-d1545522d629" src="https://github.com/user-attachments/assets/ec242900-114c-44d6-aeb2-df23e04ef067" />

4. Under Server, select Create new and configure the server with the following settings:

    <img width="748" height="741" alt="557097340-31a1713e-2c77-4ea0-9aa6-fe833539f5b9" src="https://github.com/user-attachments/assets/849a2b53-2cc2-40d0-8dc6-3d234bd2d1ab" />

5. Under Compute + storage > select Configure database > choose the Basic tier

    <img width="718" height="76" alt="Screenshot 2026-03-02 203639" src="https://github.com/user-attachments/assets/0b5a23d8-0ad4-44c2-9344-7860bbb8be34" />

6. Set Backup storage redundancy to `Locally-redundant backup storage`

    <img width="757" height="216" alt="557103488-af09c1f6-9839-4fc2-8519-267df57bb8c7" src="https://github.com/user-attachments/assets/064da0a6-7d67-412a-9b35-c48952b96585" />

7. Review + Create





