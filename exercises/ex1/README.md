# Exercise 1 - Overview

API-centric integration brings API design and integration capabilities together in a unified experience. It enables you to create APIs that directly connect to backend systems, mediate and transform requests and responses, compose multiple services, and expose simplified interfaces to API consumers. With this approach, you can build APIs ranging from simple managed endpoints to rich integration scenarios while applying security, traffic management, and lifecycle governance as part of the same development experience. In this exercise you will see 3 different ways how to create this api artifact.

## Exercise 1.1 Enable/check integration cell runtime

1. Log on to your assigned SAP Integration Suite tenant

[SAP Integration suite tenant for user 1 to user 20]([https://workshop02a.integrationsuite-cpi049.cfapps.eu10-003.hana.ondemand.com/shell/home])
    
   Log on to the SAP Integration Suite tenant using the user ID and password that has been provided by the instructors.

> [!NOTE]
> If you are attending ASUG TechConnect, you are currently in the wrong GitHub branch — please switch to the asug2026 branch and follow the instructions provided there. If you are uncertain about which tenant to use, consult your workshop instructors.

<br>![](/exercises/ex1/images/01_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

