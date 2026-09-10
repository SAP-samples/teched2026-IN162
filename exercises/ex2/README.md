# Exercise 2 - Secure & Monitor the New API Artifact.

## Overview

The exercise will typically cover:<br>
- Secure: Configure authentication, authorization, API policies, and access controls to protect the API.<br>
- Test: Verify that the API works correctly by sending requests, checking responses.<br>
- Monitor: Track API usage, message processing, errors, performance, and runtime logs to identify and resolve issues.<br>


## Exercise 2.1 Secure API Artifact.

> **Note:** T
> his is just informative exercise where you don’t need to execute anything but you will get knowledge about securing options.
<br>

1. **Authentication Policy** 

**Note**: The Authentication policy is the first policy executed in the processing flow and is mandatory for every API Artifact. It verifies the identity of the API consumer before allowing the request to proceed. The policy supports multiple authentication mechanisms, including Basic Authentication, OAuth 2.0, and Client Certificate authentication. For newly created API Artifacts, it also supports External OAuth (OIDC), enabling token validation from external identity providers such as Microsoft Entra ID, Google, and Okta. Multiple authentication methods can be enabled simultaneously, allowing APIs to support different client applications and security requirements.

Now **navigate to any API artifact** created before, and open **policy** tab. 

2. Click on **edit**.
  
  <br>![](/exercises/ex2/images/ex2_01.png)


3. Double click on **Authentication**. And now **enable checkbox** is visible for External OAuth. 

> Note: External OAuth (OIDC) means that your API trusts and validates tokens from an external identity provider to secure access to the API artifact.

  
  <br>![](/exercises/ex2/images/ex2_02.png)

  **Simple Example**: 
  Suppose your company uses Microsoft Entra ID. A user or application obtains a token from Entra ID and calls your SAP API artifact. 
  The API artifact checks:
  - Whether the token was issued by the trusted identity provider.
  - Whether the token is still valid.
  - Whether the token has the correct audience.
  - Verify client key
  Only authorized requests are passed to next steps.<br>

4. **Authorization Policy**

   After a request is successfully authenticated, the **Authorization policy** determines whether the authenticated caller is permitted to invoke the API. It evaluates access
   based on OAuth Scopes, Developer Keys, or a combination of both, providing flexible authorization for different API consumption scenarios.
   Now **navigate to any API artifact** created before, and open **policy** tab.<br>

5. Click on **edit**.
  
  <br>![](/exercises/ex2/images/ex2_01.png)

6. Double click to **Authorization**, and then to **Policy settings**.

  <br>![](/exercises/ex2/images/ex2_03.png)


  The policy supports the following authorization modes:
   - OAuth Scope or Developer Key (Default) – Access is granted if the caller presents either the required OAuth scope or a valid Developer Key.
   - OAuth Scope and Developer Key – Both a valid OAuth scope and a Developer Key are required.
   - OAuth Scope Only – Access is granted only if the access token contains the configured OAuth scope.
   - Developer Key Only – Access is granted only to subscribed applications presenting a valid Developer Key.
     
   Trust Upstream MCP authorization – you can enable this to expose API artifact as mcp server.

   For OAuth-based authorization, the policy validates the configured Scope Key (JWT claim) and the required Scope value. By default, the scope is set to API.invoke, ensuring
   that only callers with the appropriate permission can invoke the API. <br>
    
7. Beyond the default template, SAP Integration Suite provides a rich set of policies that can be added to the processing flow to address different API management
   requirements. Common policy categories include:
   - Security – Authenticate and authorize API consumers, validate requests, and protect APIs against malicious or malformed traffic.
   - Traffic Management – Apply policies such as Quota and Spike Arrest to control API consumption and protect backend systems.
   - Transformation and Mediation – Modify request and response payloads, convert data formats, enrich messages, invoke external services, or execute JavaScript and Python
     scripts as part of the API flow.<br>
  <br>


## Exercise 2.2 Monitor API Artifact

1. Once the API Artifact has been successfully deployed, you can monitor its runtime status and operational details from the Monitor view in SAP Integration Suite.

   Navigate to **Monitor** and select runtime as **Integration cell** and click **Manage Integration Content**.

 <br>![](/exercises/ex2/images/ex2_04.png)


2. Select any api artifact which is already deployed to view details of specific deoployment or go with **PurchaseOrder_userXXX**.<br>

 <br>![](/exercises/ex2/images/ex2_05.png)
 
The details page displays comprehensive runtime information about the deployed artifact, including:
- Deployment Status – Indicates whether the artifact is successfully deployed and running.
- Endpoints – Displays the runtime endpoint through which the API can be invoked.
- Artifact Details – Provides deployment metadata and quick navigation to the Artifact Editor or message monitoring.
- Status Details – Shows the current deployment state and any deployment-related messages.
- Download and Undeploy – Allows you to download the deployed artifact or remove it from the runtime.<br>

This view serves as the primary operational console for managing deployed API Artifacts on the Integration Cell runtime.

3. For troubleshooting and diagnostics, the runtime log level of an API Artifact can be configured directly from the monitoring view.
   Supported log levels include:
   - None – Disables runtime logging.
   - Info – Records high-level execution events and is recommended for normal operation.
   - Error – Logs only error conditions and exceptions.
   - Debug – Captures detailed execution information for in-depth troubleshooting.

4. **Congratulations you are successfully finished with exercise 2.**

<br>
<br>


## Summary

You have activated the Integration Cell runtime, created your first API Artifact, explored its design and runtime components, deployed it successfully, and verified its deployment using the monitoring console.

At this stage, the API is available on the Integration Cell runtime but is not yet discoverable by application developers. The next step is to govern its consumption by publishing it through Developer Hub.

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
