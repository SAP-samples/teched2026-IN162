# Exercise 1 - Overview

API-centric integration brings API design and integration capabilities together in a unified experience. It enables you to create APIs that directly connect to backend systems, mediate and transform requests and responses, compose multiple services, and expose simplified interfaces to API consumers. With this approach, you can build APIs ranging from simple managed endpoints to rich integration scenarios while applying security, traffic management, and lifecycle governance as part of the same development experience. In this exercise you will see 3 different ways how to create this api artifact.

## Exercise 1.1 Enable/check integration cell runtime

1. Log on to your assigned SAP Integration Suite tenant<br>

   - [SAP Integration suite tenant for user 1 to user 20](https://workshop02a.integrationsuite-cpi049.cfapps.eu10-003.hana.ondemand.com/shell/home)
   - [SAP Integration suite tenant for user 21 to user 40](https://workshop02b.integrationsuite-cpi050.cfapps.eu20-002.hana.ondemand.com/shell/home)
    
   Log on to the SAP Integration Suite tenant using the user ID and password that has been provided by the instructors.

   > [!NOTE]
   > If you are attending ASUG TechConnect, you are currently in the wrong GitHub branch — please switch to the asug2026 branch and follow the instructions provided there.
   > If  you are uncertain about which tenant to use, consult your workshop instructors.

2.	Enable or check Integration cell runtime.
   > [!NOTE]
   > We have activated integration cell runtime already. but in case if you want to enable into your company's specific tenant please follow this screenshot.

  Click to runtime on left side on main page and check in the list if integration cell is activated or not.<br>
  Newly available API artifact should be deployed on newly available cloud-based runtime ‘integration cell’. <br>
  Click to **activate** button if not activated. 

<br>![](/exercises/ex1/images/ex1_01.png)
********************************check with Marco **************************************

## Exercise 1.2 create your first API artifact via URL/ Open spec file.

After enabling Integration cell runtime, following instructions to follow to create your first API artifact. 

1.	Create a package in your SAP Integration Suite tenant.
   
   Now that you are logged into the tenant.<br> 
   **Create a new Package** from the **Integration and APIs** sub-menu under the **Design** menu (Click on the 'hamburger' icon on the left to launch the menu, if it's hidden).

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

5. Choose runtime profile **Integration cell** and click to **next**.

<br>![](/exercises/ex1/images/ex1_06.png)   

> [!NOTE]
> An API artifact can be added to either runtime profile. However, the same artifact cannot be deployed to a second
> runtime if it is already deployed on the first runtime.

6. Select first method **URL or Specification**

 <br>![](/exercises/ex1/images/ex1_07.png)    

7. Now choose option via uploading speciation file. Click to **Upload'**.

   Enter the following details to create API by uploading open api specification file and click to **Add**.

   | Field | Value |
   | --- | --- |
   | File name|  download this json and upload to your file name <br>![click here](https://github.com/SAP-samples/teched2026-IN162/blob/main/exercises/ex1/images/OP_PURCHASEORDER_0001.json)|
   | Target/ Destination|  <br>![](/exercises/ex1/images/ex1_09.png)  |
   | ID| `` |
   | URL | `` |

 <br>![](/exercises/ex1/images/ex1_08.png)  


 After successfully adding API artifact, we can see detailed information about API in **Overview & Target EndPoint** tabs.

8. ***Now you have successfully added your first API artifact.***

> [!NOTE]
> For more learning you can check this additional info or else you can move to next step.
> ***Resources***
> You can see details of all resources included in this API artifact in ***Resources*** tab.
> And with edit option we can add more resources too.
> <br>![](/exercises/ex1/images/ex1_10.png)


9. Deploy your first API artifact. Click to **deploy** and select **Integration Cell** as runtime profile and click **Yes**.

<br>![](/exercises/ex1/images/ex1_11.png)  

Once successfully deployed, you should see successfull message at bottom. 


> [!NOTE]
> If you are facing any issue on deploying api artifact, please call your instructors.



10. **Now you have successfully added your first API artifact and deployed it.**


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

