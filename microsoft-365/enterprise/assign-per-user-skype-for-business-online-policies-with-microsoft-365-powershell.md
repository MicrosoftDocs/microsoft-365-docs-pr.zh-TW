---
title: 將每一使用者商務用 Skype Online 原則指派給 Microsoft 365 的 PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 摘要：使用 Microsoft 365 的 PowerShell，將每位使用者的通訊設定指派給商務用 Skype Online 原則。
ms.openlocfilehash: 6ee237e5d2ee0c9f472f372a6aa66c9612336265
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514977"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>將每一使用者商務用 Skype Online 原則指派給 Microsoft 365 的 PowerShell

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

使用 Microsoft 365 PowerShell，是一種將每一使用者通訊設定指派給商務用 Skype Online 原則的有效方式。
  
## <a name="prepare-to-run-the-powershell-commands"></a>準備執行 PowerShell 命令

使用下列指示設定執行命令 (略過已完成的步驟) ：
  
  > [!Note]
   > 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。

1. 安裝 [團隊 PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示字元，然後執行下列命令： 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   出現提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱和密碼。
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>更新使用者帳戶的外部通訊設定

假設您想要變更使用者帳戶上的外部通訊設定。 例如，您想要允許 Alex 與同盟使用者通訊 (EnableFederationAccess 等於 True) 但不是與 Windows Live 使用者 (EnablePublicCloudAccess 等於 False) 。 若要這麼做，您必須執行下列兩項動作：
  
1. 尋找符合我們準則的外部存取原則。
    
2. 將該外部存取原則指派給 Alex。
    
如何判斷哪個外部存取原則要指派 Alex？ 下列命令會傳回 EnableFederationAccess 設定為 True 且 EnablePublicCloudAccess 設定為 False 的所有外部存取原則：
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

除非您已建立 Microsoft.rtc.management.writableconfig.policy.externalaccess.externalaccesspolicy 的任何自訂實例，否則該命令會傳回符合我們準則 (FederationOnly) 的一個原則。 範例如下：
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

現在，您知道要將哪一個原則指派給 Alex，我們可以使用 [授與 get-csexternalaccesspolicy](https://go.microsoft.com/fwlink/?LinkId=523974) Cmdlet 指派該原則。 範例如下：
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

指派原則非常簡單：您只需指定使用者的身分識別及要指派之原則的名稱即可。 
  
在原則和原則指派方面，您並不局限于每次使用使用者帳戶。 例如，假設您需要可與同盟夥伴和 Windows Live 使用者進行通訊的所有使用者清單。 我們已經知道這些使用者均被指派外部使用者存取原則 FederationAndPICDefault。 因為我們知道這一點，您可以執行一個簡易命令來顯示所有這些使用者的清單。 命令如下：
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

換句話說，向我們展示 Microsoft.rtc.management.writableconfig.policy.externalaccess.externalaccesspolicy 屬性設定為 FederationAndPICDefault 的所有使用者。  (，為了限制螢幕上顯示的資訊數量，請使用 Select-Object Cmdlet 來顯示 [只顯示每位使用者的顯示名稱]。 )  
  
若要將所有使用者帳戶設定為使用相同原則，請使用下列命令：
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

這個命令會使用 Get-CsOnlineUser 傳回已啟用 Lync 的所有使用者的集合，然後將所有該資訊傳送至授與 Get-csexternalaccesspolicy，這會將 FederationAndPICDefault 原則指派給集合中的每個使用者和每個使用者。
  
另一個範例是，假設您先前已指派 Alex FederationAndPICDefault 原則，而現在您已變更了您的想法，而且想要由全域外部存取原則來管理。 您無法將全域原則明確指派給任何人。 相反地，如果沒有任何個別使用者原則指派給該使用者，就會將全域原則用於指定的使用者。 因此，如果我們想要透過全域原則來管理 Alex，您必須  *取消*  指派先前指派給他的任何個別使用者原則。 範例命令如下：
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

這個命令會將指派給 Alex 的外部存取原則的名稱，設定為 null 值 ($Null) 。 Null 表示 "nothing"。 換句話說，也就是沒有任何外部存取原則指派給 Alex。 當沒有任何外部存取原則指派給使用者時，該使用者就會受到全域原則的管理。
  

## <a name="managing-large-numbers-of-users"></a>管理大量使用者

若要管理大量使用者 (1000 或以上) ，您必須使用 [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) Cmdlet 透過腳本區塊批命令。  在先前的範例中，每次執行 Cmdlet 時，必須先設定此呼叫，然後等候結果，再將其傳送回來。  使用腳本區塊時，這可讓 Cmdlet 以遠端方式執行，並在完成之後傳送資料回來。 

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

這會在不具備用戶端原則的時刻找到500使用者。 它會授與他們用戶端原則 "ClientPolicyNoIMURL" 和外部存取原則 "FederationAndPicDefault"。 結果會批分為50群組，而每批次50都會傳送至遠端電腦。
  
## <a name="see-also"></a>另請參閱

[使用 PowerShell 管理商務用 Skype Online](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
