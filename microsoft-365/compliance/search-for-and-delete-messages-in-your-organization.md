---
title: 搜尋並刪除 Office 365 組織中的電子郵件 - 系統管理說明
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用 Office365 中之安全性與合規性中心的搜尋和清除功能，可搜尋並刪除組織中所有信箱的電子郵件。
ms.openlocfilehash: cd592ca48fdb2390e8449672920aa697cc297495
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076198"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>搜尋並刪除 Office 365 組織中的電子郵件 - 系統管理說明

**本文適用於系統管理員。您正嘗試在信箱中尋找要刪除的項目嗎？請參閱[使用立即搜尋尋找郵件或項目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
您可以使用 Office365 中的內容搜尋功能來搜尋並刪除組織中所有信箱的電子郵件。 這可幫助您找出並移除可能有害或高風險的電子郵件，例如：
  
- 含有危險附件或病毒的郵件
    
- 網路釣魚郵件
    
- 包含敏感資料的郵件
    
> [!CAUTION]
> 搜尋和清除是一個強大的功能，可讓獲指派必要權限的任何人刪除組織信箱的電子郵件。 
  
## <a name="before-you-begin"></a>開始之前

- 若要建立和執行內容搜尋，您必須是「eDiscovery 管理員」**** 角色群組的成員，或者獲指派「合規性搜尋」**** 管理角色。 若要刪除郵件，您必須是「組織管理」**** 角色群組的成員，或者獲指派「搜尋及清除」**** 管理角色。 如需新增使用者至角色群組的詳細資訊，請參閱[讓使用者能夠存取 Office 365 安全性與合規性中心](/security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
    
- 您必須使用安全性與合規性中心 PowerShell 來刪除郵件。 如需如何連線的相關指示，請參閱[步驟 2](#step-2-connect-to-security--compliance-center-powershell)。
    
- 每個信箱一次可以移除最多 10 個項目。 因為搜尋和移除郵件的功能應該是事件回應工具，此限制可以協助確保從信箱快速移除郵件。 這項功能不是用來清除使用者信箱。 若要刪除超過 10 個項目，您可以使用 Exchange Online PowerShell 中的 **Search-Mailbox -DeleteContent** 命令。 請參閱[搜尋並刪除郵件 - 系統管理說明](search-for-and-delete-messagesadmin-help.md)。
    
- 透過搜尋和清除動作，您最多可以在內容搜尋刪除 50,000 個信箱內的項目。 如果內容搜尋 (您在[步驟 1 ](#step-1-create-a-content-search-to-find-the-message-to-delete)中建立) 中有超過 50,000 個來源信箱，則您在步驟 3 中建立的清除動作將失敗。 請參閱[詳細資訊](#more-information)章節以取得搜尋並清除超過 50,000 個信箱的執行提示。 
    
- 本文所述的程序只能用於刪除 Exchange Online 信箱和公用資料夾中的項目。 您無法使用這個程序來刪除 SharePoint 或商務用 OneDrive 上的內容。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>步驟 1：建立內容搜尋來尋找要刪除的郵件

第一個步驟是建立和執行內容搜尋，以尋找您想要從組織中的信箱移除的郵件。 您可以使用安全性與合規性中心或執行 **New-ComplianceSearch** 以及 **Start-ComplianceSearch** Cmdlet 來建立搜尋。 藉由在[步驟 3](#step-3-delete-the-message) 中執行 **New-ComplianceSearchAction -Purge** 命令，會刪除符合此搜尋查詢的郵件。 如需如何建立內容搜尋及設定搜尋查詢的資訊，請參閱下列主題： 
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [內容搜尋的關鍵字查詢](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> 在此步驟中建立的內容搜尋，其搜尋的內容位置不能包含 SharePoint 或商務用 OneDrive 網站。 您只能在內容搜尋中包含將用於電子郵件的信箱和公用資料夾。 如果內容搜尋包含網站，則在步驟 3 中執行 **New-ComplianceSearchAction ** Cmdlet 時會收到錯誤。 
  
### <a name="tips-for-finding-messages-to-remove"></a>尋找要移除郵件的提示

搜尋查詢的目標是將搜尋結果縮減為只有您想要移除的郵件。以下是一些提示：
  
- 如果您知道郵件主旨行中使用的確切文字或片語，請在搜尋查詢中使用 **Subject** 屬性。 
    
- 如果您知道郵件的實際日期 (或日期範圍)，請在搜尋查詢中包含 **Received** 屬性。 
    
- 如果您知道郵件的寄件者，請在搜尋查詢中包含 **From** 屬性。 
    
- 預覽搜尋結果，以確認內容搜尋僅傳回您想要刪除的郵件。
    
- 使用搜尋預估統計資料 (在安全性與合規性中心的搜尋詳細資料窗格中顯示，或使用 [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) Cmdlet) 以取得結果總數。 
    
以下是尋找可疑電子郵件訊息的兩個查詢範例。
  
- 此查詢傳回 2016 年 4 月 13 日和 2016 年 4 月 14 日之間使用者所接收的郵件，且在主旨列中包含文字「動作」和「必要」。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- 此查詢傳回 chatsuwloginsset12345@outlook.com 所送出的郵件，且在主旨列中包含精準字詞「更新您的帳戶資訊」。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步驟 2︰連線至安全性與合規性中心 PowerShell

下一步是將組織連線至安全性與合規性中心 PowerShell。 如需逐步指示，請參閱[連線至安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
如果您的 Office 365 帳戶使用多重要素驗證 (MFA) 或同盟驗證，您就無法使用前個主題中的指示來連線至安全性與合規性中心 PowerShell。 您應改為參閱[使用多重要素驗證連線至安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)中的指示。
  
## <a name="step-3-delete-the-message"></a>步驟 3：刪除郵件

在您建立內容搜尋並進行調整以傳回您想要移除的郵件，並且連線至安全性與合規性 PowerShell 之後，最後一步是執行 **New-ComplianceSearchAction** Cmdlet 來刪除郵件。 您可以虛刪除或實刪除郵件。 虛刪除的郵件會移至使用者的 [可復原的項目] 資料夾並保留，直到刪除項目的保留期限到期為止。 實刪除的郵件則會在信箱中標示為永久移除，並在受管理的資料夾助理員下次處理信箱時將其永久移除。 如果信箱啟用了單一項目復原，則會在刪除項目的保留期限到期後，永久刪除實刪除的項目。 如果信箱處於保留狀態，則會保留已刪除的郵件，直到該郵件的保留期限到期或從信箱移除保留為止。
  
在下列範例中，命令將會虛刪除名為「移除網路釣魚郵件」的內容搜尋所傳回的搜尋結果。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

若要實刪除「移除網路釣魚郵件」內容搜尋所傳回的項目，您可以執行下列命令：

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

請注意，當您執行上述命令來虛刪除或實刪除郵件時，*SearchName* 參數指定的搜尋是您在步驟 1 建立的內容搜尋。 
  
如需詳細資訊，請參閱 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。

## <a name="more-information"></a>詳細資訊

- **如何取得搜尋和移除作業的狀態？**

    執行 **Get-ComplianceSearchAction** 可取得刪除作業的狀態。 請注意，當您執行 **New-ComplianceSearchAction** Cmdlet 時所建立的物件會使用下列格式命名：`<name of Content Search>_Purge`。 
    
- **刪除郵件後，會發生什麼情況？**

   使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 命令刪除的郵件將被移至 [清除] 資料夾，且使用者無法再存取此郵件。 郵件移至 [清除] 資料夾後，如果已針對信箱啟用單一項目復原，則會根據刪除項目的保留期限來保留郵件。 (在 Office 365 中，建立新信箱時即會預設啟用單一項目復原。) 刪除項目的保留期限到期後，郵件將標示為永久刪除，並在受管理的資料夾助理員下次處理信箱時將其從 Office 365 永久清除。 

   如果您使用 `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 命令，郵件會移至使用者 [可復原的項目] 資料夾中的 [刪除] 資料夾。 它不會立即從 Office365 中清除。 使用者可以根據為信箱設定的刪除項目保留期間，在持續時間之內復原 [刪除的郵件] 資料夾中的郵件。 此保留期間到期 (或者如果使用者在到期之前清除郵件) 之後，郵件會移至 [清除] 資料夾且使用者無法再存取。 郵件位在 [清除] 資料夾後，如果已針對信箱啟用單一項目復原，則會根據為信箱設定的刪除項目的保留期限來保留郵件。 (在 Office 365 中，建立新信箱時即會預設啟用單一項目復原。) 刪除項目的保留期限到期後，郵件將標示為永久刪除，並在受管理的資料夾助理員下次處理信箱時將其從 Office 365 永久清除。 
    
- **如果要從 50,000 個以上的信箱刪除郵件，該怎麼辦？**

    如先前所述，您可以針對最多 50,000 個信箱執行搜尋和清除作業。 如果必須對超過 50,000 個信箱執行搜尋和清除作業，請考慮建立臨時搜尋權限篩選條件，以便將搜尋到的信箱數減少為小於 50,000 個信箱。 例如，如果您的組織包含不同部門、州或國家/地區的信箱，則可以基於其中一個信箱屬性建立信箱搜尋權限篩選條件，以搜尋組織中的信箱子集。 建立搜尋權限篩選條件後，您可以建立搜尋 (如步驟 1 所述)，然後再刪除郵件 (如步驟 3 所述)。 您可以編輯篩選條件來搜尋及清除不同組信箱中的郵件。 如需建立搜尋權限篩選條件的詳細資訊，請參閱[設定內容搜尋的權限篩選](permissions-filtering-for-content-search.md)。
    
- **搜尋結果中包含的未索引項目是否會被刪除？**

    不會，`New-ComplianceSearchAction -Purge 命令不會刪除未索引的項目。 
    
- **如果將已放置在就地保留或訴訟資料暫留的信箱中的郵件刪除，或將郵件指派給 Office 365 保留原則，會發生什麼情況？**

    清除郵件並將其移動到 [清除] 資料夾後，郵件會保留，直到保留期限到期為止。 如果保留期限無限制，則項目會保留到移除保留或變更保留期限為止。
    
- **為何搜尋和移除工作流程在不同的安全性與合規性中心角色群組之間是分開的？**

    如先前所述，使用者必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色才能搜尋信箱。 若要刪除郵件，該人員必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。 這樣就可以控制誰能夠在組織中搜尋信箱以及誰能夠刪除郵件。 
