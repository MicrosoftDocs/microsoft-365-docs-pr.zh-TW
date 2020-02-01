---
title: 套用 EOP 設定至多個承租人的範例指令碼
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
description: 下列範例指令碼可讓管理多個承租人 (公司) 的 Microsoft Exchange Online Protection (EOP) 系統管理員，利用 Windows PowerShell 將組態設定套用至他們的承租人。
ms.openlocfilehash: 83199e809b6001b8b5b3b51d2cd15a6e44d83b03
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598490"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>套用 EOP 設定至多個租用戶的範例指令碼

下列範例指令碼可讓管理多個承租人 (公司) 的 Microsoft Exchange Online Protection (EOP) 系統管理員，利用 Windows PowerShell 將組態設定套用至他們的承租人。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>對多個承租人執行指令碼或指令程式

1. 使用應用程式 (例如 Excel) 來建立 .csv 檔案 (例如，c:\scripts\inputfile.csv)：

2. 在 .csv 檔案中，指定兩個欄名：UserName 和 Cmdlet。

3. 對於 .csv 檔案的每一列，在 UserName 欄中加入承租人的管理員名稱，在 Cmdlet 欄中加入要對該承租人執行的指令程式。例如，使用 admin@contoso.com 和 Get-AcceptedDomain。

4. 將 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 指令碼複製到記事本之類的編輯器，然後將檔案儲存到很容易找到 .ps1 檔案的位置 (例如 c:\scripts)。

5. 使用下列語法執行指令碼：

   ```Powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   以下為範例：

   ```Powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. 將登入每個承租人並執行指令程式。

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

```Powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
