# How-to use own data within GPT-4 hosted on Azure Webservices

## Howto enrich GPT-4 with own content.

First of all login to your azure account. 

<img width="1290" alt="Bildschirmfoto 2025-02-27 um 08 55 44" src="https://github.com/user-attachments/assets/99b12ebe-9098-4ac1-b743-36e97001910c" />

### Creating a new subscription
We start our project using a new and dedicated subscription. You can skip this chapter, if you don't want to have a separate subscription.

You click on "Subscriptions" and the subscription overview opens up
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 08 57 08" src="https://github.com/user-attachments/assets/96cc0777-cdd3-4828-af98-2fccb9ba5c13" />
After clicking "Add" you can enter the details for the new subscription.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 08 57 55" src="https://github.com/user-attachments/assets/8ea46eec-e4f9-40f2-9847-ddbe31ab2353" />
After clicking "Review + Create" you see the details of your subscription to be created.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 08 58 10" src="https://github.com/user-attachments/assets/626746dc-de14-4b2d-a5ea-ecfb4bf31160" />
After clicking "Create" the subscription will be created.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 08 58 28" src="https://github.com/user-attachments/assets/dfe93827-7dfc-4f9e-8490-e33859555016" />
<img width="1290" alt="Bildschirmfoto 2025-02-27 um 08 58 50" src="https://github.com/user-attachments/assets/a7a93de6-ebe5-42e5-8a3d-4246cea002d6" />

### Creating a new resource group
We continue to set-up a new resource group within the newly created subscription.

We create a resource group by clicking "Create" within the overview of the existing resource groups ("Settings" -> "Resource Groups")
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 12 01" src="https://github.com/user-attachments/assets/0b106cd0-5a58-4531-a052-337f3df6aaa4" />

<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 14 12" src="https://github.com/user-attachments/assets/65acd765-ad41-4f51-af65-43b26e9e9d84" />
<img width="1290" alt="Bildschirmfoto 2025-02-27 um 09 14 42" src="https://github.com/user-attachments/assets/ef1bfd83-961f-4353-b751-f85eb06b89bd" />

### Creating a new storage account
With clicking "+ Create Resources" we create a storage account.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 16 58" src="https://github.com/user-attachments/assets/cd6d551e-6b8f-489c-a5fd-b0cdc739e4e2" />

As primary service we select "Azure Blob Storage or Azure Data Lake Storage Gen 2"
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 18 09" src="https://github.com/user-attachments/assets/7e6f3164-e393-4c03-8562-e2dad3293a13" />

After clicking "Review + Create" we see the summary of the storage account.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 18 49" src="https://github.com/user-attachments/assets/bf012c50-2fdf-45cc-ba54-62a5f47adb6f" />

After clicking "Create" the storage account will be created.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 19 38" src="https://github.com/user-attachments/assets/be6954a2-3abe-4f1b-bf76-f8cfb6b662c1" />

### Creating a new storage container
We go to the storage account by clicking "Go to resource".
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 19 52" src="https://github.com/user-attachments/assets/cb66fc3a-9b87-41bf-921e-feae4f9526d1" />

In the following step we need to create an container ("Data storage" -> "Containers"). After clicking "+ Container" we can define the name of the container within the subwindow on the right hand side. 
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 20 20" src="https://github.com/user-attachments/assets/00ddfb81-97b0-4749-9ca4-8a8b10421714" />



