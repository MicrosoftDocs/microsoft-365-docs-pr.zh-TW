---
title: EOP 設定的範例腳本-多個承租人
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何使用 PowerShell 將設定設定套用至 Microsoft Exchange Online Protection (EOP) 中的承租人。
ms.openlocfilehash: b18fc71171a93e2a2f415800bcf2b5abd5c5a526
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615861"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="780a7-103">套用 EOP 設定至多個租用戶的範例指令碼</span><span class="sxs-lookup"><span data-stu-id="780a7-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="780a7-104">下列範例腳本可讓 Microsoft Exchange Online Protection (EOP) 系統管理員管理多個承租人 (公司) 使用 Exchange Online PowerShell 來查看和/或將設定設定套用至其承租人。</span><span class="sxs-lookup"><span data-stu-id="780a7-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="780a7-105">對多個承租人執行指令碼或指令程式</span><span class="sxs-lookup"><span data-stu-id="780a7-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="780a7-106">若尚未安裝，請 [安裝 Exchange Online V2 模組](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="780a7-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="780a7-107">使用試算表應用程式 (例如，Excel) ，使用下列詳細資料建立 .csv 檔案：</span><span class="sxs-lookup"><span data-stu-id="780a7-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="780a7-108">UserName 欄：您用來連線 (（例如，) ）的帳戶 `admin@contoso.onmicrosoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="780a7-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="780a7-109">Cmdlet 欄：執行 (範例或) 的指令程式或命令 `Get-AcceptedDomain` `Get-AcceptedDomain | FT Name` 。</span><span class="sxs-lookup"><span data-stu-id="780a7-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="780a7-110">檔案看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="780a7-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="780a7-111">將 .csv 檔案儲存在容易尋找的位置 (例如，c:\scripts\inputfile.csv) 。</span><span class="sxs-lookup"><span data-stu-id="780a7-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="780a7-112">將 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 腳本複製到 [記事本]，然後將檔案儲存到易於 (尋找的位置，例如，c：\scripts) 。</span><span class="sxs-lookup"><span data-stu-id="780a7-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="780a7-113">使用下列語法執行指令碼：</span><span class="sxs-lookup"><span data-stu-id="780a7-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="780a7-114">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="780a7-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="780a7-115">每個租使用者將會登入，並且會執行腳本。</span><span class="sxs-lookup"><span data-stu-id="780a7-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="780a7-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="780a7-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="780a7-117">您可能需要修改 `Connect-IPPSSession` 腳本中的行，使其符合您的環境。</span><span class="sxs-lookup"><span data-stu-id="780a7-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="780a7-118">例如，Office 365 德國要求的 _ConnectionUri_ 值不同于腳本中的目前值。</span><span class="sxs-lookup"><span data-stu-id="780a7-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="780a7-119">如需詳細資訊，請參閱 Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="780a7-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {

# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
