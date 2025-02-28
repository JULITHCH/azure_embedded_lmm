# How-to use own data within GPT-4 prompt hosted on Azure Webservices
27. February 2025, JULITH GmbH, Thomas RIEHN
## Overview and Motivation
Embedding self-managed content into Large Language Models (LLMs) like GPT-4 offers numerous advantages and compelling reasons for its implementation. One key reason is that it allows for the **integration of domain-specific knowledge** that may not be universally available in the model's original training data. This is particularly beneficial in industries like healthcare, law, or engineering, where specialized information is crucial. By embedding such content, the model can provide more accurate, context-specific, and detailed responses, significantly improving its value in niche applications.

Another advantage is the ability to ensure **improved accuracy and relevance**. While LLMs like GPT-4 have a broad understanding of language and concepts, they may lack up-to-date or highly specialized information. Embedding self-managed content, such as proprietary datasets or specialized knowledge, ensures that the model delivers accurate, relevant, and timely information, which is particularly valuable when the model’s training data might not cover recent developments or unique subject matter.

Embedding self-managed content also enables **personalization**, allowing the model to adapt to user preferences, historical interactions, or specific contextual needs. This makes it possible for organizations to create tailored experiences, ensuring that the LLM aligns with individual user preferences or organizational standards. Additionally, by embedding carefully curated and up-to-date information, it becomes easier to reduce the likelihood of "hallucinations," which occur when an LLM generates plausible-sounding but inaccurate information. Self-managed content offers a controlled, verified source of information, enhancing the reliability of the model's outputs.

The ability to **continuously update and adapt** the model is another significant benefit. With embedded self-managed content, organizations can update the model’s knowledge base with new information as it becomes available. This means that the LLM can stay relevant and accurate over time without requiring complete retraining or relying on infrequent updates from the model's developers. Furthermore, organizations have greater control over the knowledge embedded in the LLM, allowing them to ensure that the model’s outputs are aligned with company policies, ethical standards, and legal requirements.

Embedding self-managed content also **reduces dependence on external data sources**, improving the speed and consistency of the model’s responses. Rather than relying on third-party systems or services, the LLM can directly access proprietary or frequently-used information, making it more efficient. This leads to operational efficiency as the model can handle specialized tasks, such as customer support or decision-making, without requiring human intervention for basic queries.

From a data security perspective, embedding self-managed content provides a **higher level of control over sensitive or confidential information**. Organizations can apply their own data governance policies, ensuring that the model’s outputs are secure and comply with privacy regulations. Moreover, integrating self-managed content with existing organizational systems, like databases or CRM platforms, allows for a seamless flow of information, enhancing the model’s capability to support complex tasks like analytics and reporting.

Finally, embedding self-managed content can be **cost-effective**, as it reduces the need for relying on external APIs or continuously updating training data, which can be expensive. This approach allows organizations to decrease their reliance on paid data sources and API calls, ultimately lowering operational costs. In summary, embedding self-managed content into LLMs like GPT-4 enables organizations to harness more accurate, secure, and tailored outputs, improving both the model's effectiveness and its operational efficiency.

## Basic Configuration of Azure-Webservices
### Advantages of Azure OpenAI Services 
Azure OpenAI Services offer several advantages when it comes to embedding self-managed content into Large Language Models (LLMs) like GPT-4, making it a powerful platform for organizations seeking to integrate their own proprietary data while maintaining control, security, and scalability. One of the key benefits is **customization**. Azure allows organizations to fine-tune models on their own datasets, enabling them to embed domain-specific, self-managed content directly into the model. This ensures that the model can generate more accurate and contextually relevant responses based on the unique data it has been provided. 

Another significant advantage is **scalability**. Azure's infrastructure is built to handle large-scale applications, so when self-managed content is embedded into models, it can efficiently scale across millions of queries or users without compromising performance. This is particularly beneficial for enterprises that require robust, high-performance AI services capable of managing large volumes of data while ensuring that embedded content remains effective and accessible.

**Security and compliance** are also notable advantages of Azure OpenAI Services. Azure provides enterprise-grade security and compliance frameworks, ensuring that organizations can embed sensitive or proprietary self-managed content securely. Data is protected with advanced encryption methods, and compliance with various regulations, such as GDPR and HIPAA, is facilitated by Azure’s comprehensive tools and certifications. This is especially crucial for businesses in industries that handle sensitive data and need to ensure that their AI solutions meet stringent legal and ethical requirements.

Additionally, **integration with existing Azure services** is another key benefit. Organizations that are already using other Azure services, such as Azure Cognitive Services, Azure Databases, or Azure Machine Learning, can seamlessly integrate their self-managed content into the OpenAI models. This interoperability allows for a more streamlined workflow, where data can be pulled from other internal systems and used to train or fine-tune models. This makes the embedding of self-managed content into LLMs much easier and more effective, enhancing the overall user experience.

Azure also enables **continuous updates** to embedded content. This flexibility allows organizations to frequently update their self-managed content, whether to reflect new knowledge, changing regulations, or evolving business needs. With Azure’s AI infrastructure, updates can be made quickly and efficiently without the need for re-training from scratch, ensuring that the model remains current and aligned with the organization’s requirements.

Furthermore, Azure offers **advanced monitoring and management tools** that help organizations oversee the performance of their embedded content in real time. Azure’s tools allow for detailed insights into how the model is performing, how the embedded content is influencing the responses, and where adjustments might be needed. This data-driven approach enhances decision-making and ensures that the integration of self-managed content is continuously optimized for the best results.

In summary, Azure OpenAI Services provide a comprehensive and flexible platform for embedding self-managed content into models like GPT-4. The advantages include customization for domain-specific knowledge, scalability to handle large data volumes, strong security and compliance features, seamless integration with existing Azure services, the ability for continuous updates, and advanced monitoring tools—all of which contribute to making the process of embedding self-managed content highly effective and secure for organizations.

### Getting started
In the following example we want to embed text documents. Therefore it is necessary to make use of several Azure services. But: first of all login to your azure account ;)

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

### Configure metadata of storage container
This is an optional step if you want to add some metadata to your data within the storage container. If you want to do so, you have to click on the three points on the right side next to the created storage container and select "Edit metadata" in the context menu.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 57 27" src="https://github.com/user-attachments/assets/caaf3505-5d49-4ff7-8177-ce86a403b310" />

We will add two fields for testing purposes (the documentname and URL) to demonstrate the possibilities.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 59 40" src="https://github.com/user-attachments/assets/92cd9928-1386-4cac-bee7-a6938587685c" />
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 00 49" src="https://github.com/user-attachments/assets/68f7ba77-6452-442a-885e-2bbbe3fa4a8a" />

### Import Data into Storage Container
Entering the container you have the possibility to upload content. For our test propose we decide to upload text files. For sure it is possible to import other data-formats as well. Azure is capable of identifying content within pictures as well. In regards to the data size we are limited to 64kb due to the pricing model we will select during the configuration of AI Search furtheron.

<img width="1334" alt="Bildschirmfoto 2025-02-27 um 09 20 43" src="https://github.com/user-attachments/assets/3434c36b-798b-46de-b37c-b62bbffa9d77" />

After clicking "upload" you can select the files to be uploaded. For demonstration purposes we selected "Cool" as Access tier.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 58 00" src="https://github.com/user-attachments/assets/ac7f8aa2-40b5-418c-8cce-3833b237900d" />

After uploading the overview should look like this.
<img width="1290" alt="Bildschirmfoto 2025-02-27 um 11 22 12" src="https://github.com/user-attachments/assets/394e2753-e010-4e4e-8676-700c84716fdd" />


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

### Change Authentication to RBAC
Within the keys section we have to switch from API-keys to Role-based access control.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 15 22 51" src="https://github.com/user-attachments/assets/72e1856c-69a1-4d2c-a64f-baefa56ce16b" />
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 15 22 56" src="https://github.com/user-attachments/assets/9cbe1682-98c2-4db2-8374-95826c1ae191" />

After the successful switch it should look like this:
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 15 23 04" src="https://github.com/user-attachments/assets/1e6c679a-abce-4bfe-9586-2ad641ed9705" />


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

### Role and role assignments
#### Step 1: Set-up Role-Identity
Within the "Resource Management" we can find the possibility of switching to Azure role-based access control (Azure RBAC). The doing is quite the same compared to the AI Search service.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 13 21" src="https://github.com/user-attachments/assets/d962e0ee-a8e4-49d8-808c-b0cb0e3fc503" />

After having saved the status change from "Off" to "On" we can see the created Azure Object ID.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 10 13 52" src="https://github.com/user-attachments/assets/024afdae-53aa-4727-9d9b-9d4c35118094" />

#### Step 2: Set-up Azure role assignments
We need to click "Azure role assignments" first.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 15 03 42" src="https://github.com/user-attachments/assets/ff9bba0d-56c7-48e4-b0c0-d914094f1104" />

#### Step 3: Search Service Contributor
We add within the scope of the resource group the role "Search Service Contributor".
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 15 02 46" src="https://github.com/user-attachments/assets/54ea0842-7776-4a5a-a779-98ac0ef21768" />

#### Step 4: Search Index Data Reader
We add within the scope of the resource group the role "Search Index Data Reader".
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 15 03 13" src="https://github.com/user-attachments/assets/87e962f7-7f8b-40e1-a2f3-6aacf24457ec" />

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

## Import data into the 



## Vectorize Content for Azure Search
We switch back again into the created search service within our created resource group and click on "Import and vectorize data".
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 22 35" src="https://github.com/user-attachments/assets/e934afc2-b2a7-47fd-bd71-dab8f034431f" />

### Step 1: Data connection
In the first step we need to set-up our data connection (Azure Blob Storage in our case).
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 22 44" src="https://github.com/user-attachments/assets/0ab95ea5-2abf-4893-81bf-0e3133645eed" />

Within this step it is necessary to select the authentication using a system-assigned managed identity.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 22 59" src="https://github.com/user-attachments/assets/d0344ee5-06b6-49e9-af71-8aed1141cd94" />

### Step 2: Vectorization model
In the next step it is necessary to select the OpenAI Service and the deployed text-embedding model. 
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 23 24" src="https://github.com/user-attachments/assets/628c28c5-5219-4ee1-92b4-d4e8da74ae07" />

### Step 3: Vectorization of images
In our test-case we leave this blank.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 23 31" src="https://github.com/user-attachments/assets/98dee971-1c8e-4ac3-9296-666e2b1fd12a" />

### Step 4: Advanced Settings
We highly recommend to enable the semantic ranker and leave the schedule for indexing by once.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 23 53" src="https://github.com/user-attachments/assets/619cf391-5247-4995-9bd6-90f343787dbe" />

### Step 5: Review and create
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 23 57" src="https://github.com/user-attachments/assets/24daeaeb-0491-4f76-b13a-9bc19e2243c3" />
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 24 09" src="https://github.com/user-attachments/assets/fdc2ded9-08a6-4e9c-985b-eb0fe3a1a9d9" />

After clicking start-searching you reach the vector.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 24 14" src="https://github.com/user-attachments/assets/6eed5fb7-ff0f-42ef-813f-c7b0d7c64117" />

Within that final process the index
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 24 26" src="https://github.com/user-attachments/assets/2529af12-d36a-49ed-b60c-84b2be4c50e7" />

the indexers
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 24 22" src="https://github.com/user-attachments/assets/2d8c6bbc-4be7-4777-8db5-504c0fe59480" />

and the skillset
<img width="1290" alt="Bildschirmfoto 2025-02-27 um 11 24 35" src="https://github.com/user-attachments/assets/18819308-22e6-44f1-96d2-a83a2fafdf6b" />
has been generated.

During the indexing process you can see the progress like this:
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 24 44" src="https://github.com/user-attachments/assets/ea2f90ae-f964-4caf-bea0-92e2b53d733a" />

The final result should hopefully look like this:
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 11 35 53" src="https://github.com/user-attachments/assets/7d832574-2247-457e-b018-7a8e4c189df5" />


## Configure Azure OpenAI Prompt
### Add data source
Before we are able to finally set-up the chat-prompt we need to add our data source within the chat-playground.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 14 53 08" src="https://github.com/user-attachments/assets/d7de535b-c047-4fc5-96e4-352583274db4" />

#### Step 1: Selection of data source
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 14 53 55" src="https://github.com/user-attachments/assets/2b40fbec-7fdc-4b8c-9153-d59efe814c55" />

We select "Azure AI Search" and our "Search Index"
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 14 54 11" src="https://github.com/user-attachments/assets/5b75b315-aad4-4db8-871e-8becd7ac6183" />

We select, that we want to embed the vectorsearch to this search resource and need to select the embedding model.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 14 54 24" src="https://github.com/user-attachments/assets/d7901e5b-813a-43e1-8a22-4256efe7a328" />

#### Step 2: Data managment
We stay with the hybrid and semantic search type and select the exisiting semantic search configuration.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 14 54 46" src="https://github.com/user-attachments/assets/e96c8c2e-236b-4128-a8e7-f6e355b35f21" />

#### Step 3: Data connection
We select that we want to use the system managed identity.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 14 54 54" src="https://github.com/user-attachments/assets/c147acfc-932b-414e-922f-d400731da196" />

If you get an error like this, you need to step back once again and set-up the roles correctly.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 14 59 47" src="https://github.com/user-attachments/assets/101af095-88c4-4066-afeb-a4d88eda5566" />

#### Step 4: Review & Create
We have to review and create the settings.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 15 25 07" src="https://github.com/user-attachments/assets/087a1fc7-01a2-4a2c-ba92-4bf8c282babc" />

#Conclusion
Now you are able to use the prompt on the right-hand side.
<img width="1290" alt="Bildschirmfoto 2025-02-27 um 18 07 05" src="https://github.com/user-attachments/assets/f51eabf1-d546-4410-9f4b-28cd0ee2a620" />


#Remark
It could be necessary to add the user to the roles of the "Azure OpenAI" object as well.
## Assigning role to the asking user
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 17 44 58" src="https://github.com/user-attachments/assets/f51478cc-7ac7-42f9-b796-dea2bf4e6359" />

Select the role.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 17 45 18" src="https://github.com/user-attachments/assets/9cd41ab1-744b-4d28-bd81-c24a5a7d70ae" />

Add the necessary user to the role.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 17 45 36" src="https://github.com/user-attachments/assets/7e374847-109d-4c71-a4f1-c0e395dc0cb4" />

And "Review + assign" the role membership.
<img width="1334" alt="Bildschirmfoto 2025-02-27 um 17 45 41" src="https://github.com/user-attachments/assets/49f08884-30e5-469f-b429-6c5e9215a28b" />

