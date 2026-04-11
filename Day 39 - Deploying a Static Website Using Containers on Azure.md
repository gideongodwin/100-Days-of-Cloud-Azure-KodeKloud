## Day 39: Deploying a Static Website Using Containers on Azure

## Task Details:

The Nautilus DevOps team has been tasked with creating an internal information portal for public access. As part of this project, they need to host a static website on Azure using an Azure Storage account. The Storage account must be configured for public access to allow external users to access the static website directly via the Azure Storage URL.

Task Requirements:

- Create an Azure Storage account named `nautiluswebst19485` in an existing resource group.

- Configure the Storage account for static website hosting with `index.html` as the index document.R

- Allow public access to the static website so that the website is publicly accessible.

- Upload the `index.html` file from the `/root/` directory of the Azure client host to the Storage account's `$web` container.

- Verify that the website is accessible directly through the Azure Storage static website URL.

## Steps:

1. Sign in to the [Azure Portal](https://portal.azure.com/)

2. On the Storage Accounts page, click on create.

    <img width="627" height="237" alt="Screenshot 2026-03-13 112443" src="https://github.com/user-attachments/assets/6249033d-8d87-40d7-bfc9-4db5de3fabd5" />

3. On the Basics tab, configure the following:

    <img width="577" height="575" alt="Screenshot 2026-03-13 112604" src="https://github.com/user-attachments/assets/108a3393-48c0-47c2-a1e2-7db8d84a782b" />

4. Review + Create

5. In the storage account, under Data management > Static website >  enable it, set `index.html` as the index document > Save

    <img width="645" height="422" alt="Screenshot 2026-03-13 113059" src="https://github.com/user-attachments/assets/ffe0b8d2-d9fb-4480-8719-365da0dc49dd" />

6. Under Settings > Configuration, > Enable `Allow Blob Anonymous Access` > Save.

    <img width="558" height="422" alt="Screenshot 2026-03-13 113739" src="https://github.com/user-attachments/assets/941610ab-c434-4498-a86d-de35ca8d7f8a" />

7. Under Data storage > Containers, choose the `$web` container and then select Change access level.

    <img width="665" height="327" alt="Screenshot 2026-03-13 114026" src="https://github.com/user-attachments/assets/d7a34c66-1a42-44f3-b4fe-0fb4e1ee63e3" />
  
8. On the Azure client, upload `/root/index.html` to the storage account’s `$web` container \
    ```
    az storage blob upload \
      --account-name nautiluswebst19485 \
      --container-name '$web' \
      --name index.html \
      --file ./index.html
    ```

9. Verify that the website is publicly accessible using the Azure Storage static website URL.

    <img width="676" height="460" alt="Screenshot 2026-03-13 114545" src="https://github.com/user-attachments/assets/40651580-5be3-4d54-8e75-8113dbe56b62" />

