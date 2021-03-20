---
title: 使用 PowerShell 管理商務用 Skype Online 原則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 摘要：使用 PowerShell，使用原則來管理商務用 Skype Online 使用者帳戶屬性。
ms.openlocfilehash: a10929bbdce499ad26f9714127f675beeef58765
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916699"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>使用 PowerShell 管理商務用 Skype Online 原則

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

若要管理商務用 Skype Online 之使用者帳戶的許多屬性，您必須使用 Microsoft 365 的 PowerShell，將其指定為原則的屬性。
  
## <a name="before-you-begin"></a>開始之前

使用下列指示設定執行命令 (略過已完成的步驟) ：

  > [!Note]
  > 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。

1. 安裝[Teams PowerShell 模組安裝](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示字元，然後執行下列命令： 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   出現提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱和密碼。
    
## <a name="manage-user-account-policies"></a>管理使用者帳戶原則

許多商務用 Skype Online 使用者帳戶屬性是使用原則進行設定。 原則只是可套用至一或多個使用者的設定集合。 若要查看原則的設定方式，您可以對 FederationAndPICDefault 原則執行此範例命令：
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

反過來，您應該會收到類似以下的內容：
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

在此範例中，此原則中的值會決定在與同盟使用者通訊時，可使用或無法執行的動作。 例如，EnableOutsideAccess 屬性必須設定為 True，使用者才能夠與組織外部的人員進行通訊。 請注意，此屬性不會出現在 Microsoft 365 系統管理中心中。 相反地，此屬性會根據您所做的其他選擇，自動設定為 True 或 False。 其他兩個感興趣的屬性如下：
  
- **EnableFederationAccess** 指出使用者是否可以與同盟網域的使用者進行通訊。
    
- **EnablePublicCloudAccess** 指出使用者是否可以與 Windows Live 使用者進行通訊。
    
因此，您不會直接變更使用者帳戶上的同盟相關屬性 (例如 **Set-CsUser EnableFederationAccess $True**) 。 相反地，您會指派具有所需屬性值預先設定的外部存取原則。 若要讓使用者能夠與同盟使用者和 Windows Live 使用者進行通訊，則必須將該使用者帳戶指派給允許通訊類型的原則。
  
如果您想要知道某人是否可以與組織外部的使用者進行通訊，您必須：
  
- 判斷已指派哪個外部存取原則給該使用者。
    
- 判斷該原則允許或不允許哪些功能。
    
例如，您可以使用下列命令來執行這項操作：
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

這個命令會尋找指派給使用者的原則，然後尋找該原則中啟用或停用的功能。
  
若要使用 PowerShell 管理商務用 Skype Online 原則，請參閱下列的 Cmdlet：

- [用戶端原則](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [會議原則](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [行動原則](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [線上語音信箱原則](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [語音路由原則](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> 商務用 Skype Online 撥號對應表是除了名稱以外的每個原則中的原則。 已選擇名稱「撥號對應表」，而不是 "撥號原則"，以便提供與 Office 通訊伺服器及 Exchange 的回溯相容性。 
  
例如，若要查看所有可供使用的語音原則，請執行下列命令：
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> 這會傳回所有可用的語音原則清單。 不過，請記住，並非所有原則都可以指派給所有使用者。 這是因為授權和地理位置的各種限制。  (所謂的「[使用位置](/previous-versions/azure/dn194136(v=azure.100))」。) 如果您想知道可指派給特定使用者的外部存取原則及會議原則，請使用類似下列的命令： 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

[ApplicableTo] 參數會對可指派給特定使用者 (例如，Alex Darrow) 的原則限制傳回的資料。根據授權及使用位置的限制，這可能代表所有可用原則的子集。 
  
在某些情況下，原則的屬性不會與 Microsoft 365 搭配使用，而有些則只能由 Microsoft 支援人員管理。 
  
透過商務用 Skype Online，使用者必須以某種類型的原則來管理。 如果有效的原則相關屬性為空白，這表示有問題的使用者是由全域原則所管理，這是自動套用至使用者的原則，除非使用者特別指派每個使用者原則。 因為我們沒有看到針對使用者帳戶所列出的用戶端原則，所以它是由全域原則所管理。 您可以使用下列命令來判斷全域用戶端原則：
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>另請參閱

[使用 PowerShell 管理商務用 Skype Online](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)