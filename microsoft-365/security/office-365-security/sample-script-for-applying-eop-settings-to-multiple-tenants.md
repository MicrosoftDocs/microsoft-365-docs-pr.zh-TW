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
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何使用 PowerShell 將設定設定套用至 Microsoft Exchange Online Protection (EOP) 中的承租人。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928505"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>套用 EOP 設定至多個租用戶的範例指令碼

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
-  [Exchange Online Protection 獨立](exchange-online-protection-overview.md)

下列範例腳本可讓 Microsoft Exchange Online Protection (EOP) 系統管理員管理多個承租人 (公司) 使用 Exchange Online PowerShell 來查看和/或將設定設定套用至其承租人。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>對多個承租人執行指令碼或指令程式

1. 若尚未安裝，請 [安裝 Exchange Online V2 模組](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。

2. 使用試算表應用程式 (例如，Excel) ，使用下列詳細資料建立 .csv 檔案：

   - UserName 欄：您用來連線 (（例如，) ）的帳戶 `admin@contoso.onmicrosoft.com` 。
   - Cmdlet 欄：執行 (範例或) 的指令程式或命令 `Get-AcceptedDomain` `Get-AcceptedDomain | FT Name` 。

   檔案看起來會像這樣：

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. 將 .csv 檔案儲存在容易尋找的位置 (例如，c:\scripts\inputfile.csv) 。

4. 將 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 腳本複製到 [記事本]，然後將檔案儲存到易於 (尋找的位置，例如，c：\scripts) 。

5. 使用下列語法執行指令碼：

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   以下為範例：

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 每個租使用者將會登入，並且會執行腳本。

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> 您可能需要修改 `Connect-IPPSSession` 腳本中的行，使其符合您的環境。 例如，Office 365 德國要求的 _ConnectionUri_ 值不同于腳本中的目前值。 如需詳細資訊，請參閱 Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

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