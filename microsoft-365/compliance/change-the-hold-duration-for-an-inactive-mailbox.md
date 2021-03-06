---
title: 變更非作用中信箱的保留持續時間
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Office 365 信箱變為非使用中之後，請變更保留期間或指派給非使用中信箱之 Office 365 保留原則的持續時間。
ms.openlocfilehash: 49d133c64763cee12cb26e27d372a16ba4ad7e94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918199"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>變更非作用中信箱的保留持續時間

非使用中的信箱會在使用者離開組織之後，用來保留離職員工的電子郵件。 當訴訟暫止、In-Place 暫止、Microsoft 365 保留原則，或與 eDiscovery 案例相關聯的保留原則或已刪除的使用者帳戶已刪除時，信箱會變成非使用中。 非使用中信箱的內容會保留在信箱停用的保留期間內，直到未使用中的信箱為止。 保留期間會定義 [可復原的專案] 資料夾中的專案保留的時間。 當 [可復原的專案] 資料夾中某一專案的保留期間到期時，會永久刪除該專案 (清除從非使用中信箱的) 。 信箱變為非使用中之後，您可以變更保留或 Microsoft 365 指派給非使用中信箱的保留原則的持續時間。
  
> [!IMPORTANT]
> 當我們繼續以保留信箱內容的不同方式投資時，我們宣佈 Exchange 系統管理中心的退休 In-Place 封存。 這表示您應該使用訴訟保留和 Microsoft 365 保留原則，以建立非使用中的信箱。 從2020年4月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。 不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。 不過，在2020年7月1日開始，您將無法變更保留期間。 您只能移除 In-Place 保留才能刪除非使用中的信箱。 在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。 如需停用 In-Place 保留的詳細資訊，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。
  
## <a name="connect-to-powershell"></a>連線 PowerShell

- 您必須使用 Exchange Online PowerShell 變更非使用中信箱的訴訟暫止保留期間。 您無法使用 Exchange 系統管理中心 (EAC) 。 不過，您可以使用 Exchange Online PowerShell 或 EAC 來變更 In-Place 保留的保留期間。 您可以使用「安全性與合規性中心」或「安全性 & 合規性中心」 PowerShell 變更 Microsoft 365 保留原則的保留期間。
    
- 若要連接至 Exchange Online PowerShell 或安全性 & 規範中心 PowerShell，請參閱下列其中一個主題：
    
  - [連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)
    
- 與 eDiscovery 案例相關聯的保留是無限保留，這表示沒有可以變更的保留期間。 專案會永遠保留，或直到移除保留，並刪除非作用中的信箱為止。
    
- 如需非使用中信箱的相關資訊，請參閱[Microsoft 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步驟1：識別非使用中信箱上的封存

因為不同類型的保留或一或多個 Microsoft 365 保留原則可能會放在非使用中的信箱上，所以第一步是在非使用中的信箱上識別保留。
  
在 Exchange Online PowerShell 中執行下列命令，以顯示組織中所有非使用中信箱的保留資訊。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

**True** 的 **LitigationHoldEnabled** 屬性值表示非使用中的信箱處於訴訟暫止狀態。 如果 In-Place 保留、eDiscovery 保留或 Microsoft 365 保留原則放在非使用中的信箱上，保留原則的 GUID 會顯示為 **InPlaceHolds** 屬性的值。 例如，下列會顯示五個非作用中信箱的結果。 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

下表識別用來使每個信箱非使用中的五種不同保留類型。
  
|**非使用中信箱**|**保留類型**|**如何在非使用中的信箱上識別保留**|
|:-----|:-----|:-----|
|王小姐 Beebe  <br/> |訴訟暫止  <br/> |*LitigationHoldEnabled* 屬性設定為 `True` 。  <br/> |
|Pilar Pinilla  <br/> |原有範圍暫止  <br/> |*InPlaceHolds* 屬性包含放在非使用中信箱上的 In-Place 保留 GUID。 您可以告知這是 In-Place 保留，因為識別碼不是以前置詞開頭。  <br/> 您可以使用 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Exchange Online PowerShell 中的命令，取得非使用中信箱上 In-Place 保留的相關資訊。  <br/> |
|Mario Necaise  <br/> |安全性 & 規範中心內的全組織 Microsoft 365 保留原則  <br/> |*InPlaceHolds* 屬性是空的。 這表示一或多個組織範圍或 (Exchange 寬) Microsoft 365 保留原則會套用至非使用中的信箱。 在此情況下，您可以 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 在 Exchange Online PowerShell 中執行命令，以取得整個組織 Microsoft 365 保留原則的 guid 清單。 套用至 Exchange 信箱的組織範圍保留原則的 GUID 會以前置詞開始 `mbx` ; 例如， `mbxa3056bb15562480fadb46ce523ff7b02` 。  <br/> <br/>若要識別套用至非使用中信箱的 Microsoft 365 保留原則，請在安全性 & 規範中心 PowerShell 中執行下列命令。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |套用至特定信箱之安全性 & 規範中心的 Microsoft 365 保留原則  <br/> |*InPlaceHolds* 屬性包含套用至非使用中信箱之 Microsoft 365 保留原則的 GUID。 您可以告知這是套用至特定信箱的保留原則，因為 GUID 會以前置詞開頭  `mbx` 。 如果套用至非使用中信箱的保留原則 GUID 是以前置詞開始 `skp` ，則表示將保留原則套用至商務用 Skype 交談。  <br/><br/> 若要識別套用至非使用中信箱的 Microsoft 365 保留原則，請在安全性 & 規範中心 PowerShell 中執行下列命令。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>`mbx` `skp` 當您執行此命令時，請務必移除或首碼。  <br/> |
|Abraham McMahon  <br/> |安全性 & 規範中心的 eDiscovery 案例保留  <br/> |*InPlaceHolds* 屬性包含放在非使用中信箱上的 eDiscovery 案例保留 GUID。 您可以告訴這是 eDiscovery 案例保留，因為 GUID 是以前置詞開頭  `UniH` 。  <br/> 您可以使用  `Get-CaseHoldPolicy` 安全性 & 規範中心 PowerShell 中的指令程式，取得與非作用中信箱相關聯之 eDiscovery 案例的相關資訊。 例如，您可以執行命令  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 以顯示非使用中信箱上之案例保留的名稱。 `UniH`當您執行此命令時，請務必移除前置詞。  <br/><br/> 若要識別與非作用中信箱上之保留相關的 eDiscovery 案例，請執行下列命令。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **附注：** 建議您不要對非使用中的信箱使用 eDiscovery 保留。 That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. 在某些情況下，法律案例可能會被移除，與案例相關聯的封存也會被移除，並且 eDiscovery 案例會關閉 (或) 中刪除。 實際上，如果放在非使用中信箱的保留與 eDiscovery 案例相關聯，且已發行保留或 eDiscovery 案例已關閉或已刪除，則系統會永久刪除非作用中的信箱。 

如需 Microsoft 365 保留原則的詳細資訊，請參閱[瞭解保留原則和保留標籤](retention.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>步驟2：變更非使用中信箱的保留期間

在您識別在非使用中的信箱上放置何種保留類型之後 (，以及是否有多個保留) 時，下一步是變更保留的持續時間。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>變更訴訟暫止持續時間

以下說明如何使用 Exchange Online PowerShell 變更放在非使用中信箱的訴訟暫止保留期間。 您無法使用 EAC。 執行下列命令來變更保留期間。 在此範例中，保留期間會變更為無限制的時段。
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

結果是非使用中信箱中的專案會無限期保留，或直到移除保留或保留期間變更為不同的值。
  
> [!TIP]
> 識別非使用中信箱的最佳方式是使用其 **辨別名稱** 或 **Exchange GUID** 值。 使用其中一個值可協助避免意外指定錯誤的信箱。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>變更 In-Place 保留的持續時間

 已停用 In-Place 保留，而且無法再修改。 如果非使用中的信箱已套用 In-Place 保留，您就無法變更保留期間。 您只可以移除 In-Place 保留，這會導致刪除非使用中的信箱。 如需詳細資訊，請參閱 [刪除非使用中的信箱](delete-an-inactive-mailbox.md#remove-in-place-holds)。
  
## <a name="more-information"></a>其他資訊

- **如何計算非使用中信箱之專案的保留期間？** 工期是從接收或建立信箱專案的原始日期開始計算。 
    
- **保留期間到期時，會發生什麼情況？** 當 [可復原的專案] 資料夾中的信箱專案的保留期間到期時，會永久刪除該專案 (清除從非使用中信箱的) 。 若未針對非使用中信箱的保留指定持續時間，則永遠不會 (清除 [可復原的專案] 資料夾中的專案，除非非使用中信箱的保留期間變更) 。 
    
- **是否仍在非使用中的信箱上處理 Exchange 保留原則？** 如果 Exchange 保留原則 (通訊記錄管理或 MRM，Exchange Online) 中的功能會在信箱停用時套用至信箱，則會繼續在非使用中的信箱上處理使用 [**刪除** 保留] 動作所設定之保留標記的刪除原則 (。 這表示使用刪除原則標記的專案會移至 [可復原的專案] 資料夾，保留期間到期時。 當專案的保留期間到期時，這些專案便會從非使用中信箱清除。 
    
    相反地，任何封存原則 (，其是以指派給非使用中信箱之保留原則中所包含的 **MoveToArchive** 保留動作) 所設定的保留標記會被忽略。 這表示使用封存原則標記的非作用中信箱中的專案會在保留期間到期時保留在主要信箱中。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 由於使用者無法登入非使用中的信箱，因此沒有必要使用資料中心資源來處理封存原則。 

- **若要檢查新保留期間的訴訟暫止狀態，請執行下列命令：** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **如同一般信箱，受管理的資料夾助理 (MFA) 也會處理非使用中的信箱。** 在 Exchange Online 中，MFA 大約每7天處理一次信箱。 在您變更非使用中信箱的保留期間之後，您可以使用 **Start-ManagedFolderAssistant** Cmdlet 立即開始處理非使用中信箱的新保留期間。 執行下列命令。 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果有多個保留放在非使用中的信箱上，則不會顯示所有保留 Guid。** 您可以執行下列命令來顯示所有保留 (的 Guid，但不包括已在非使用中信箱上的訴訟保留) 。 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```