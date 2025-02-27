# How-to use own data within GPT-4 hosted on Azure Webservices

## Basic Configuration of Azure-Webservices

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

### Import Data into Storage Container
Entering the container you have the possibility to upload content. For our test propose we decide to upload text files. For sure it is possible to import other data-formats as well. Azure is capable of identifying content within pictures as well. In regards to the data size we are limited to 64kb due to the pricing model we will select during the configuration of AI Search furtheron.

<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 20 43" src="https://github.com/user-attachments/assets/3434c36b-798b-46de-b37c-b62bbffa9d77" />



## Configuring AI Search Component
Next we want to set-up the AI Search. First of all we need to create a corresponding resource.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 23 10" src="https://github.com/user-attachments/assets/aec14bf9-0eb8-42cc-8b0c-85b6f929cf3a" />

### Creating an AI Search
After clicking "+ Create" we are asked for the details. 
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 24 59" src="https://github.com/user-attachments/assets/d7315f8e-861a-4eed-889f-d251879e4449" />

Within the selection of the "Pricing Tier" you can differentiate between following models
![image](https://github.com/user-attachments/assets/39885959-110d-4b8a-b83d-22f552377af9)Table from: https://learn.microsoft.com/en-us/azure/search/search-sku-tier

After clickign "Review + Create" we see th summary of the sotrage account.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 25 21" src="https://github.com/user-attachments/assets/37b6777f-d8c7-4d11-9c29-419f68050920" />

After clicking "Create" the AI Search will be created.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 25 45" src="https://github.com/user-attachments/assets/bea8a74f-fd9a-4309-81b2-d269681e0207" />

<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 25 53" src="https://github.com/user-attachments/assets/6b74f144-70f2-4405-a7fc-4ccbbb7d8614" />

### Setting-up the necessary identities
For the seamless integration of the services we highly recommend to set-up an identity based configuration. It is necessary to change the identiy to system-assigned.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 26 11" src="https://github.com/user-attachments/assets/ccd38ae5-8ebf-4e3e-9a20-4055e86806bc" />

After commiting the change with the "Save" button, an Azure Object will be created.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 50 26" src="https://github.com/user-attachments/assets/24d26246-3c8f-45fb-b318-73ae519833f7" />

Next it is necessary to change the "Azure role assignments" by clicking on the samenamed button.
<img width="1290" alt="Bildschirmfoto 2025-02-27 um 09 51 05" src="https://github.com/user-attachments/assets/155aa4ce-c4d7-44c2-9546-e774a836af6a" />

There are to role assignments wich are necessary to implement, one for the resource group an one for the storage account. With the "+ Add role assignment" button we go futheron.

#### Resource Group
We define "Resource Group" as scope and select the created resource group from above. The role wich needs to be selected is the "Cognitive Services User" role. 
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 52 17" src="https://github.com/user-attachments/assets/9ddc8c6e-06f2-41c2-b72c-9f76b4178346" />

#### Storage Account
We define "Storage" as scope and select the created storage account from above. The role wich needs to be selected is the "Storage Blob Data Reader" role. 
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 53 32" src="https://github.com/user-attachments/assets/57b49f69-291b-4935-8c60-a2974e7b1b97" />

### Conclusion
After both has been done, it should look like this.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 56 17" src="https://github.com/user-attachments/assets/cc882049-7f7c-4128-9fc9-0431fd081793" />

## Configure metadata of storage container
This is an optional step if you want to add some metadata to your data within the storage container. If you want to do so, you have to click on the three points on the right side next to the created storage container and select "Edit metadata" in the context menu.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 57 27" src="https://github.com/user-attachments/assets/caaf3505-5d49-4ff7-8177-ce86a403b310" />

We will add two fields for testing purposes (the documentname and URL) to demonstrate the possibilities.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 59 40" src="https://github.com/user-attachments/assets/92cd9928-1386-4cac-bee7-a6938587685c" />
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 00 49" src="https://github.com/user-attachments/assets/68f7ba77-6452-442a-885e-2bbbe3fa4a8a" />


## Create an Azure OpenAI Service
### Add Azure OpenAI to your subscription
To add Azure OpenAI to your subscription search for "OpenAI"
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 00 49" src="https://github.com/user-attachments/assets/1462b92f-c0fc-429a-8cda-48cb9246f833" />
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 13 54 43" src="https://github.com/user-attachments/assets/32dfde76-9a32-4cd2-8e56-ead8372865a4" />

After having found the service you can start to create the service instance. Within that process we need to select a region, a name and the pricing tier.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 07 29" src="https://github.com/user-attachments/assets/e5b7b3e5-ef26-448c-9aa4-64b3a1a2a3bf" />

After clicking "Next" we are asked to select the type of network security we want for the AI Services resource.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 07 35" src="https://github.com/user-attachments/assets/f0f1f3c9-c1d7-4fcf-817f-bb99013a58ff" />

After clicking "Next" we are asked to enter additional tags, which we will leave blank.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 07 49" src="https://github.com/user-attachments/assets/2413a297-0499-4b3b-90ca-bfd25a7be22b" />

After clicking "Next" and "Review + create" the service will be created.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 10 48" src="https://github.com/user-attachments/assets/5a64abe9-7069-4700-b8d0-7b1f738fe7cb" />
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 11 13" src="https://github.com/user-attachments/assets/1abf3fa7-c9df-452b-8cc6-a6f26aaa9ed5" />

### Resource Group overview
Our resource group should now look like this.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 11 22" src="https://github.com/user-attachments/assets/f7a9432f-5edd-4bbf-94b7-253d7cf9a495" />

### Azure OpenAI Overview
By clicking on the OpenAI resource the following window opens.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 11 32" src="https://github.com/user-attachments/assets/3853b65b-9b6d-46d6-87c3-ffd79e8fd91e" />

### Configure Service
By clicking on "Explore Azure AI Foundry portal" a new tab opens up in the browswer an d you enter the Chat-Playground
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 11 43" src="https://github.com/user-attachments/assets/40666ed8-108f-49c3-9837-188847f44671" />

### Append Language Models
We now want to add two different language models.
#### GPT-4 as lanugage model for the chat-prompt
Referring to the first steps we select the model cataloge.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 12 14" src="https://github.com/user-attachments/assets/d2e0d7c1-93bf-4c3c-98ef-384ca5f39e6c" />

After having found, we can deploy this language model.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 12 23" src="https://github.com/user-attachments/assets/7d2c0580-1ff6-47e9-972f-56037bc71038" />

<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 12 30" src="https://github.com/user-attachments/assets/06115134-3931-46d8-85a5-66569119e207" />

#### ada-002 as language model for the embedding
We search within the model catalog for "ada".
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 12 49" src="https://github.com/user-attachments/assets/ad63906e-eb83-4465-a8df-b78fcc1489ae" />

After having found, we can deploy this language model.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 12 53" src="https://github.com/user-attachments/assets/be6ed206-de59-47d6-b82c-c96b17dd5700" />

<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 12 57" src="https://github.com/user-attachments/assets/38372cdb-50df-4a87-a46b-17379a302e2e" />




### Set-up Role-Identity

## Vectorize Content for Azure Search


