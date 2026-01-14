---
title: "Granting Owner Role in PowerShell"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_grant_owner_role.html"
last_updated: "7/8/2025"
product_version: ""
---

# Granting Owner Role in PowerShell

In this article

To grant the Owner role to the Microsoft 365 Global Admin account that the Microsoft Entra application uses to log in to Microsoft 365, do the following:

1. Connect to Exchange Online PowerShell. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps).
2. Use the following example to grant the role:

|  |
| --- |
| $folders = get-publicfolder "\" -recurse  foreach($folder in $folders)  {  Add-PublicFolderClientPermission -Identity $folder.identity -user <user\_account> -AccessRights Owner  } |

Page updated 7/8/2025
