# Exercise 3 - Consume (with developer hub) & analyze the New API Artifact.

## Overview

After deploying and verifying an API, the next step is to govern and expose it through Developer Hub. Developer Hub acts as a centralized catalog for publishing and discovering APIs, Events, and MCP Servers. It enables organizations to create API Products, add documentation and metadata, and manage access through subscriptions and applications. In this exercise, you will publish an API Product, create and subscribe a developer application, obtain credentials, and securely invoke the API. 
This completes the lifecycle: 

**Discover → Create Product → Publish → Create Application → Subscribe → Obtain Credentials → Consume API.**


## Exercise 3.1 Create your first API artifact product.


1. To get govern access to API artifact, Open to developer hub.

  
<br>![](/exercises/ex3/images/ex3_01.png)
    


2. Navigate to Admin center → Content.

<br>![](/exercises/ex3/images/ex3_02.png) 


3. Select the business system.

<br>![](/exercises/ex3/images/ex3_03.png) 

> [!NOTE]
> Developer Hub can aggregate APIs from multiple Integration Suite runtimes. Business Systems act as the logical source of published integration assets, allowing organizations to build a unified enterprise API catalog across landscapes. Select the business system that contains the deployed API artifact. Developer Hub retrieves all published integration assets from the selected business system and makes them available for creating products.


4. Select TicketCreateionAPI_userXXX from list to create product & click **Create product** button.


<br>![](/exercises/ex3/images/ex3_04.png)

5. Provide details of product mentioned below. and click **Publish** button.
   
 | Field | Value |
   | --- | --- |
   | Name| FirstProduct_Userxxx (replace your user instead of xxx - ex. User001)|
   | ID| FirstProduct_Userxxx (replace your user instead of xxx - ex. User001)|
   | Short Text | Creation of first product for ticket creation API. |

<br>![](/exercises/ex3/images/ex3_05.png)


Once click on Publish. You will see below message, click **close**.  

> [!NOTE]
> The **Scheduled Requests** page provides a centralized view of all content creation and update operations within Developer Hub. Publication involves synchronizing metadata across multiple platform services. Processing requests asynchronously improves scalability while allowing administrators to monitor publication progress through Scheduled Requests. Initially, the product publication request appears with the status **In Progress**, indicating that Developer Hub is validating the product and synchronizing the content.

<br><br>


## Exercise 3.2 Discover, Subscribe and Consume API artifact.

1. **Discover the Product Catalog.**

   Now navigate to Developer hub main page, and new product will be visible in list. Click **FirstProduct_userXXX** from list.


<br>![](/exercises/ex3/images/ex3_06.png)


2. Details are visible here in overview and API tab. You can explore the product.

<br>![](/exercises/ex3/images/ex3_07.png)


3. **Subscribe**

API Products remain inaccessible until an application subscribes to them. Subscriptions establish the trust relationship between an application and the published product while enabling controlled access through OAuth credentials. To consume a protected API, an application must first subscribe to the published API product.
From the product page, 
**select Subscribe → Create New Subscription for Application.**

<br>![](/exercises/ex3/images/ex3_08.png)


4. Provide the application details that identify the consumer application. And click **create**.

   
 | Field | Value |
   | --- | --- |
   | Name| FirstProductSubscription_Userxxx (replace your user instead of xxx - ex. User001)|
   | Short Text| FirstProductSubscription_Userxxx (replace your user instead of xxx - ex. User001)|
   | Description | Creation of first product subscription for ticket creation. |

<br>![](/exercises/ex3/images/ex3_09.png)


5. Now, please wait a few minutes for the credentials to be generated.

   The credentials will be generated after one or two minutes.
   
   **Meanwhile please move to exercise 3.3 to check API analytics.**

<br>![](/exercises/ex3/images/ex3_10.png)


6. You can copy deployed **API artifact URL** from package, and copy paste **client id and secret & token URL**.(We will use these for testing purposes in the next exercise).


## Exercise 3.3 Modern API Analytics.

API Analytics is a built‑in capability that gives you usage, performance, and error insights specifically for your API artifacts.

1. Now, navigate to **Analyse** tab, select runtime as **Integration Cell**, and choose Artifact type as **API**.

<br>![](/exercises/ex3/images/ex3_11.png)


> [!NOTE]
> many metrics has been exposed to analyse API artifact. You can check more details https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/api-artifact-charts with this help document.


2. You can create custom charts. Click **Add Custom View.**
   
<br>![](/exercises/ex3/images/ex3_12.png)


3. And Provide View name - **Custom_View_userXXX**
> [!NOTE]
> **Replace XXX by any unique characters as numbers will not be accepted.**

and click **Create**.
   
<br>![](/exercises/ex3/images/ex3_13.png)


4. Click **Create** button to create custom chart.

<br>![](/exercises/ex3/images/ex3_14.png)

5. Now, we will create a custom chart for APIs with the highest response times.
First, provide dimensions as **API name, API Product Name & Developer Name.** and Measures as **Response Time**.
Please enter the details as mentioned below -

<br>![](/exercises/ex3/images/ex3_15.png)


6. Then if you scroll down, you can verify that the chart has been generated and review the details of the APIs with the highest response times.

   
<br>![](/exercises/ex3/images/ex3_16.png)


7. Now you can save newly created custom chart. 


🎉 🎉**Congratulations! You have successfully completed Exercise 3.**
   
## Summary

You have create your first API artifact product, published it and created subscription. Also completed a few steps in the analytics section..  

Now, you can test your first API artifact using the Bruno application.


Continue to - [Exercise 4 - Test the API artifact using Bruno application ](../ex4/README.md)
