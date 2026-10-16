# Exercise 1 - Design & deploy API artifact by different ways

🔗 – API-centric integration brings API design and integration capabilities together in a unified experience.<br>
🚀 – It enables you to create APIs that directly connect to backend systems, mediate and transform requests and responses, compose multiple services, and expose simplified interfaces to API consumers.<br>
🛠️ – With this approach, you can build APIs ranging from simple managed endpoints to rich integration scenarios while applying security, traffic management, and lifecycle governance as part of the same development                experience.<br>
🎯 – In this exercise you will see 3 different ways how to create this API artifact.<br>

## Exercise 1.1 Enable/check Integration Cell runtime

1. Log on to your assigned SAP Integration Suite tenant<br>

   - [SAP Integration suite tenant for user 001 to user 020](https://workshop02a.integrationsuite-cpi049.cfapps.eu10-003.hana.ondemand.com/shell/home)
   - [SAP Integration suite tenant for user 021 to user 040](https://workshop02b.integrationsuite-cpi050.cfapps.eu20-002.hana.ondemand.com/shell/home)
    
   Log on to the SAP Integration Suite tenant using the user ID and password that has been provided by the instructors.

2.	Enable or check Integration Cell runtime.
   
   > [!NOTE]
   > We have activated Integration Cell runtime already. but in case if you want to enable into your company's specific tenant please follow this screenshot.

  Click to runtime on left side on main page and check in the list if Integration Cell is activated or not.<br>
  Newly available API artifact should be deployed on newly available cloud-based runtime ‘Integration Cell’. <br>
  Click to **activate** button if not activated. 

<br>![](/exercises/ex1/images/ex1_01.png)


## Exercise 1.2 create your first API artifact via URL/ Open spec file.

After enabling Integration Cell runtime, We can now actually create API artifact.<br>  

Usecase / real world example :<br>  


<br>![](/exercises/ex1/images/POusecase.png)


🏢 Use case: A company receives purchase requests from a supplier portal, procurement application, or AI assistant, and each one must be sent to SAP S/4HANA Cloud to create a purchase order. SAP Integration Suite exposes a governed API artifact for this process.<br>  

🧩 In this exercise, you will get modelling experience of API artifact in SAP Integration Suite via first method URL/specification. <br>  


Following instructions to follow to create your first API artifact. <br> 
(security and monitoring part will be covered in next exercise 2 with different usecases)<br> 

1.	Create a package in your SAP Integration Suite tenant.<br> 
   
   Now that you are logged into the tenant.<br> 
   **Create a new Package** from the **Integration and APIs** sub-menu under the **Design** menu (Click on the 'hamburger' icon on the left to launch the menu, if it's
   hidden).

<br>![](/exercises/ex1/images/ex1_02.png)


2.	Click to **create** button.
   
<br>![](/exercises/ex1/images/ex1_03.png)

3. Enter the following details to describe the package and **Save** it.<br>

   | Field | Value |
   | --- | --- |
   | Name| TechEd 2026 IN162-0** (replace ** with your assigned user identifier)|
   | Short Description| `This package demonstrates three different methods for creating API artifacts in SAP Integration Suite: using a backend URL, importing an existing API definition, and creating an API from an API specification.`
   | Version | ```1.0.0``` |
   | Vendor | ```SAP``` |

<br>![](/exercises/ex1/images/ex1_04.png)

4. After the Package is successfully created, navigate to the **Artifacts** tab of this package, and click on **Add -> API**.
   
<br>![](/exercises/ex1/images/ex1_05.png)

5. Choose runtime profile **Integration Cell** and click to **next**.

<br>![](/exercises/ex1/images/ex1_06.png)   

> [!NOTE]
> An API artifact can be added to either runtime profile. However, the same artifact cannot be deployed to a second runtime if it is already deployed on the first runtime.

6. Select first method **URL or Specification**

 <br>![](/exercises/ex1/images/ex1_07.png)    

7. Now choose option via uploading speciation file. Click to **Upload'**.

   Enter the following details to create API by uploading open api specification file and click to **Add**.

   | Field | Value |
   | --- | --- |
   | File name|  download this json and upload to your file name <br> [click here](https://github.com/SAP-samples/teched2026-IN162/blob/main/exercises/ex1/images/OP_PURCHASEORDER_0001.json)|
   | Target/ Destination|  <br>![](/exercises/ex1/images/ex1_09.png)  |
   | Name| Purchase Order |
   | ID| Purchase_Order |
   | Relative URL| /sap/purchase_order | 
   | Service Type| ODATA | 
   | API Base path | /purchaseorders_userXXX (please add your username number) |
   | API State |Active |
   | API Version | 1.0.0  | 
 
 <br>![](/exercises/ex1/images/ex1_08.png)  

 After successfully adding API artifact, we can see detailed information about API in **Overview & Target EndPoint** tabs.
 

8. **Now you have successfully added your first API artifact.** 
<br>
<br>

9. **For more learning you can check this additional info or else you can move to next step.**

    
> [!NOTE]
> **Resources**
> You can see details of all resources included in this API artifact in ***Resources*** tab.
> And with edit option we can add more resources too.
> <br>![](/exercises/ex1/images/ex1_10.png)


10. Deploy your first API artifact. Click to **deploy** and select **Integration Cell** as runtime profile and click **Yes**.

<br>![](/exercises/ex1/images/ex1_11.png)  

Once successfully deployed, you should see successfull message at bottom. 


> [!NOTE]
> If you are facing any issue on deploying api artifact, please call your instructors.<br>



11. **Now you have successfully added your first API artifact and deployed it.** <br><br>



## Exercise 1.3 Create API artifact via API Provider.

Usecase / real world example :<br>  

<br>![](/exercises/ex1/images/servicenowusecase.png)  


🏢 Use case: A company's monitoring system detects a critical server failure and automatically sends the incident details to ServiceNow.<br>  

🧩 In this exercise, an API artifact is created using API Provider ➡️ ServiceNow system, exposing a GET operation to retrieve existing incidents or tickets.
   (The artifact can later be extended with a POST operation to create ServiceNow incidents. and Authentication, validation, quota, and monitoring are handled centrally.)<br>


You will get modelling experience of API artifact in SAP Integration Suite via 2nd method API provider. <br>  


1. Now navigate to your package **TechEd 2026 IN162-0**** and inside **Artifact** tab
   **click to add** new API artifact and now choose another option via **API provider**.

> [!NOTE]
> please select runtime profile as **Integration Cell**. 


<br>![](/exercises/ex1/images/ex1_12.png)  



2. Select Destination of Service now.


<br>![](/exercises/ex1/images/ex1_13.png)  


3. Provide following API details and **click to Next**.<br>


   | Field | Value |
   | --- | --- |
   |name 	|TicketCreationAPI_userXXX|
   |ID|TicketCreationAPI_userXXX|
   |API Provider | 	servicenow|
   |Relative URL|	/api/now/table/incident |
   |Service type |	REST|
   |API Base path	|/ticketcreation_userXXX (please add your username number)|
   |API state| 	Active|
   |API version|	1.0.0|
   |Runtime profile |	Integration Cell|

<br>![](/exercises/ex1/images/ex1_14.png)  


4. Now **copy** below prompt to generate open API specificiation file and ***click to Generate***.

```Prompt
Create a REST API with three operations for managing ServiceNow incidents. The base path already points to the incident table (/api/now/table/incident), so all operation paths below are relative to that.
Operation 1 — Query incidents. Method GET on path /. Retrieves incidents matching an encoded query. Optional query parameters: sysparm_query (string, an encoded query like number=INC0010002 or active=true^priority=1), sysparm_limit (integer, max number of records), sysparm_fields (string, comma-separated list of fields to return), and sysparm_display_value (string, one of true, false, or all). Returns a JSON object with a result array; each item has number, short_description, description, state, and sys_id (all strings).
Operation 2 — Get incident by sys_id. Method GET on path /{sys_id}, where sys_id is a required string path parameter. Returns a JSON object with a result object containing number, short_description, description, state, and sys_id.
```

<br>![](/exercises/ex1/images/ex1_15.png)  

Once Generated, click to **add**.<br>

> [!NOTE]
> Generation of open api specification might take few seconds.


5. **First Deploy new Artifact. Now you have successfully created API artifact via API provider.**
   
  <br>![](/exercises/ex1/images/ex1_39.png)  
   
<br>


## Exercise 1.4 – Create API artifact via reusable API


Usecase / real world example :<br>  

<br>![](/exercises/ex1/images/reusableapiusecase.png)  


🏢 Use case: Here we will continue with same usecase related to service now in Exercise 1.3.<br> 
             🚨 After the critical server failure is reported, the support team wants each ServiceNow incident to show which server failed and who owns it, not just the
             ticket details. The company already deployed a reusable API artifact that returns client details for other teams.<br>
   
🧩 In this exercise, You will create rusable API artifact and deploy it, and the same ServiceNow incidents API artifact, you add a reference to this deployed artifact instead of rebuilding that logic.<br>
♻️ The API artifact stays reusable for other APIs, and the existing authentication, validation, quota, and monitoring remain handled centrally.<br><br>


1. Now navigate to your package **TechEd 2026 IN162-0**** and inside **Artifact** tab
   **click to add** new API artifact and now choose another option via **Reusable API**.

> [!NOTE]
> please select runtime profile as **Integration Cell**. 


<br>![](/exercises/ex1/images/ex1_22.png)  

> [!NOTE]
> A Reusable API artifact does not require a target URL or a virtual host since it is designed for internal invocation only via a calling API  using the API Direct adapter. Therefore, it does not have an externally invokable endpoint.

> [!NOTE]
> The sender adapter in a Reusable API is automatically set to API Direct. This is important because it allows the calling API artifact to invoke the Reusable API internally
   without an HTTP endpoint and without external exposure.


2. Provide below details of Reusable API. and **Click to Add.**
   | Field | Value |
   | --- | --- |
   | Name 	| ReusableAPI_userXXX (replace XXX with your number ex 010)|
   |ID |ReusableAPI_userXXX (replace XXX with your number ex. 010)|
   |API Base path	|/reusableapi_userXXX (please add your username number) |
   |API version|	1.0.0|
   |Runtime Profile | Integration Cell|
   
<br>![](/exercises/ex1/images/ex1_23.png)  


3. Click to **Policies** tab.
   
   <br>![](/exercises/ex1/images/ex1_24.png)

> [!NOTE]
> The sender adapter in a Reusable API is automatically set to API Direct. This is important
> because it allows the calling API artifact to invoke the Reusable API internally—without an HTTP
> endpoint and without external exposure. 


4. Now, let’s add a few security policies like Authentication and Authorization to it. Click to **edit**

   <br>![](/exercises/ex1/images/ex1_25.png)

5. **Add Authentication and Authorization Policies.** (click and drag to position where you would like to add).

   <br>![](/exercises/ex1/images/ex1_26.png)

6. Add **Json Thread Protection policy** too as shown below:

   <br>![](/exercises/ex1/images/ex1_41.png)


> [!NOTE]
> In addition to security policies, you can add mediation policies to extend functionality.
> For example: Use a Content Modifier to enrich or adjust the message payload.

We can now save and deploy this reusable API artifact.

   <br>![](/exercises/ex1/images/ex1_27.png)

7. Now let's Consume reusable API. Go back to you package **TechEd 2026 IN162-0****.
   Open artifact **TicketCreationAPI_userXXX**.
   **Click to Edit and navigate to Policies tab**.


   <br>![](/exercises/ex1/images/ex1_28.png)


8. After edit, **Click to references -> Global -> Add References -> API**.

   <br>![](/exercises/ex1/images/ex1_29.png)


9. Select **ReusableAPI_userXXX*** API from list. (XXX will be replaced by your user number)

    <br>![](/exercises/ex1/images/ex1_30.png)


10. To consume the reusable API, **add a Request-Reply** step along with a **Receiver System to invoke
   the** reusable API.

   <br>![](/exercises/ex1/images/ex1_31.png)

   <br>![](/exercises/ex1/images/ex1_32.png)

   
   Add request reply and Receiver system as below screenshot. 

    <br>![](/exercises/ex1/images/ex1_33.png)

   
11. Click to Request Reply 1(drag line to receiver), and add adapter. 
   From the list of adapters, **select API Direct** only.  

   <br>![](/exercises/ex1/images/ex1_34.png)


12. Open connection tab of API direct, and select source.

   <br>![](/exercises/ex1/images/ex1_35.png)


13. Select ReusableAPI_userXXX (with your user number).
    
   <br>![](/exercises/ex1/images/ex1_36.png)

14. Now we have modelled and consumed a Reusable API into the caller API.

> [!NOTE]
> Please note that if the Reusable API is not deployed, then you will not be allowed to deploy the
> caller API referring that Reusable API .

  
  Now let’s deploy the caller API.

  <br>![](/exercises/ex1/images/ex1_37.png)


15. **Now You have successfully created & Deployed your API artifact via Reusable API method.**


🎉 **Congratulations!!!!!! You have finished your first exercise**
    
<br>


## Summary

You have now activated the Integration Cell runtime, created your first API Artifact via 3 different ways, explored its design and runtime components, deployed it successfully.
Now in next exercise we can secure & monitor these api artifacts. <br> 

Continue to - [Exercise 2 - Secure & Monitor the New API Artifact](../ex2/README.md)

