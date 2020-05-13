---
title: EOP 設定的範例腳本-多個承租人
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
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何使用 PowerShell，將設定設定套用至 Microsoft Exchange Online Protection （EOP）中的承租人。
ms.openlocfilehash: c25bafe9ece71264931d8f059dd726147a6d28a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209136"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="e94d9-103">套用 EOP 設定至多個租用戶的範例指令碼</span><span class="sxs-lookup"><span data-stu-id="e94d9-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="e94d9-104">下列範例指令碼可讓管理多個承租人 (公司) 的 Microsoft Exchange Online Protection (EOP) 系統管理員，利用 Windows PowerShell 將組態設定套用至他們的承租人。</span><span class="sxs-lookup"><span data-stu-id="e94d9-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="e94d9-105">對多個承租人執行指令碼或指令程式</span><span class="sxs-lookup"><span data-stu-id="e94d9-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="e94d9-106">使用應用程式 (例如 Excel) 來建立 .csv 檔案 (例如，c:\scripts\inputfile.csv)：</span><span class="sxs-lookup"><span data-stu-id="e94d9-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="e94d9-107">在 .csv 檔案中，指定兩個欄名：UserName 和 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e94d9-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="e94d9-p101">對於 .csv 檔案的每一列，在 UserName 欄中加入承租人的管理員名稱，在 Cmdlet 欄中加入要對該承租人執行的指令程式。例如，使用 admin@contoso.com 和 Get-AcceptedDomain。</span><span class="sxs-lookup"><span data-stu-id="e94d9-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="e94d9-110">將[RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1)腳本複製到 [記事本]，然後將檔案儲存至容易尋找的位置（例如，c：\scripts）。</span><span class="sxs-lookup"><span data-stu-id="e94d9-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="e94d9-111">使用下列語法執行指令碼：</span><span class="sxs-lookup"><span data-stu-id="e94d9-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="e94d9-112">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="e94d9-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="e94d9-113">每個租使用者將會登入，並且會執行腳本。</span><span class="sxs-lookup"><span data-stu-id="e94d9-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="e94d9-114">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="e94d9-114">RunCmdletOnMultipleTenants.ps1</span></span>

```powershell
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
