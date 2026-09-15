# Exercise 3 - Consumption (with developer hub) & analytics.

## Overview

After deploying and verifying an API, the next step is to govern and expose it through Developer Hub. Developer Hub acts as a centralized catalogue for publishing and discovering APIs, Events, and MCP Servers. It enables organizations to create API Products, add documentation and metadata, and manage access through subscriptions and applications. In this blog, you will publish an API Product, create and subscribe a developer application, obtain credentials, and securely invoke the API. 
This completes the lifecycle: 

**Discover → Create Product → Publish → Create Application → Subscribe → Obtain Credentials → Consume API.**


## Exercise 3.1 Create your first API artifact product.


1. To get govern access to API artifact, click to developer hub.

  
<br>![](/exercises/ex3/images/ex3_01.png)
    


2. Navigate to Admin center → Content.

<br>![](/exercises/ex3/images/ex3_02.png) 


3. Select the business system.

<br>![](/exercises/ex3/images/ex3_03.png) 

> [!NOTE]
> Developer Hub can aggregate APIs from multiple Integration Suite runtimes. Business Systems act as the logical source of published integration assets, allowing organizations to build a unified enterprise API catalog across landscapes. Select the business system that contains the deployed API artifact. Developer Hub retrieves all published integration assets from the selected business system and makes them available for creating products.


4. Select TicketCreationAPI from list to create product & click to Create product button.


<br>![](/exercises/ex3/images/ex3_04.png)

5. Provide details of product mentioned below. and **click to Publish** button.
   
 | Field | Value |
   | --- | --- |
   | Name| FirstProduct_Userxxx (replace your user instead of xxx - ex. User001)|
   | ID| FirstProduct_Userxxx (replace your user instead of xxx - ex. User001)|
   | Short Text | Creation of first product for ticket creation API. |

<br>![](/exercises/ex3/images/ex3_05.png)


Once click on Publish. You will see below message, **click to close**.  

> [!NOTE]
> The **Scheduled Requests** page provides a centralized view of all content creation and update operations within Developer Hub. Publication involves synchronizing metadata across multiple platform services. Processing requests asynchronously improves scalability while allowing administrators to monitor publication progress through Scheduled Requests. Initially, the product publication request appears with the status **In Progress**, indicating that Developer Hub is validating the product and synchronizing the content.

<br><br>


## Exercise 3.2 Discover, Subscribe and Consume API artifact.

1. **Discover the Product Catalog.**

   Now navigate to Developer hub main page, and new product will be visible in list. Click to **FirstProduct_userXXX** from list.


<br>![](/exercises/ex3/images/ex3_06.png)


2. Details are visible here in overview and API tab. You can explore the product.

<br>![](/exercises/ex3/images/ex3_07.png)


3. **Subscribe**

API Products remain inaccessible until an application subscribes to them. Subscriptions establish the trust relationship between an application and the published product while enabling controlled access through OAuth credentials. To consume a protected API, an application must first subscribe to the published API product.
From the product page, 
**select Subscribe → Create New Subscription for Application.**

<br>![](/exercises/ex3/images/ex3_08.png)


4. Provide the application details that identify the consumer application. And **click to create**.

   
 | Field | Value |
   | --- | --- |
   | Name| FirstProductSubscription_Userxxx (replace your user instead of xxx - ex. User001)|
   | Short Text| FirstProductSubscription_Userxxx (replace your user instead of xxx - ex. User001)|
   | Description | Creation of first product subscription for ticket creation. |

<br>![](/exercises/ex3/images/ex3_09.png)


5. Now Please wait for few minutes to generate the credentials.

   After 1 or 2 min credentionals will generate.

<br>![](/exercises/ex3/images/ex3_10.png)


6. You can bruno installed already into your system to test this API Artifact. You can copy deployed API artifact URL from package, and copy paste client id and secret.  ???????************************


## Exercise 3.3 Modern API Analytics.
  
