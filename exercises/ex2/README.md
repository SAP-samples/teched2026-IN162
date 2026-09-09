# Exercise 2 - Secure & Monitor the New API Artifact.

## Overview

The exercise will typically cover:<br>
- Secure: Configure authentication, authorization, API policies, and access controls to protect the API.<br>
- Test: Verify that the API works correctly by sending requests, checking responses.<br>
- Monitor: Track API usage, message processing, errors, performance, and runtime logs to identify and resolve issues.<br>


## Exercise 2.1 Secure the API Artifact.

> **Note:** This is just informative exercise where you don’t need to execute anything but you will get knowledge about securing options.
<br>

1. **Authentication** 

**Note**: The Authentication policy is the first policy executed in the processing flow and is mandatory for every API Artifact. It verifies the identity of the API consumer before allowing the request to proceed. The policy supports multiple authentication mechanisms, including Basic Authentication, OAuth 2.0, and Client Certificate authentication. For newly created API Artifacts, it also supports External OAuth (OIDC), enabling token validation from external identity providers such as Microsoft Entra ID, Google, and Okta. Multiple authentication methods can be enabled simultaneously, allowing APIs to support different client applications and security requirements.

Now **navigate to any API artifact** created before, and open **policy** tab. 

2. click on **edit**.
  
  <br>![](/exercises/ex1/images/ex2_01.png)


3. Double click on **Authentication**. And now **enable checkbox** is visible for External OAuth. 

> Note: External OAuth (OIDC) means that your API trusts and validates tokens from an external identity provider to secure access to the API artifact.

  
  <br>![](/exercises/ex1/images/ex2_02.png)

  **Simple Example**: 
  Suppose your company uses Microsoft Entra ID. A user or application obtains a token from Entra ID and calls your SAP API artifact. 
  The API artifact checks:
  - Whether the token was issued by the trusted identity provider.
  - Whether the token is still valid.
  - Whether the token has the correct audience.
  - Verify client key
  Only authorized requests are passed to next steps.



 <br>
  <br>


## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
