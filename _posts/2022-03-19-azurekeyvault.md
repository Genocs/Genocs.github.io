---
title: "User Assigned Managed Identity"
date: 2022-03-19
---

User Assigned Managed Identity
---

In this section we are going to illustrate the steps needed to provide access to Key Vault to an Azure Resource like an App Service.

## Create User Assigned Managed Identity

``` PS
az identity create -g RG-genocs -n genocs-identity
```


## Assign role

1) Get access to the resource
2) Go to *Access policies* section
3) Go to the application


### Get access to the resource
- Go the resource (for instance Azure Key vault)
- Select *Access control (IAM)*
- Select *Role Assigments tab*
- Click on *+Add*
- Then *Add role assignment*
- Select *Key Vault Contributor*
- Click option *Assign access to => Managed identity* 
- Click on *+Select members*
- Add the Managed Identity

### Go to *Access policies* section
- Click on *Add Access Policy* to the Identity

### Go to the application
- Select Identity
- Select User assigned
- Add the Managed identity
