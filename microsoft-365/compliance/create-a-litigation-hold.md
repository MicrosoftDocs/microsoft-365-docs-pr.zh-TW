---
title: 建立訴訟資料暫留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: e6201fc938f7481a524a8d3c4171d4c1b67997e9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076521"
---
# <a name="create-a-litigation-hold"></a>建立訴訟資料暫留

您可以將信箱置於訴訟暫止來保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。 當您啟用使用者信箱訴訟暫止時，使用者的封存信箱中的內容 （如果已啟用） 會也保留。 當您建立保留時，您可以指定保留期間 （也稱為*時間型保留*），以便刪除和修改過的項目會保留在指定期間內然後永久刪除信箱。 您可以只會無限期保留內容或者 （稱為*無限期的保留*），或直到訴訟暫止已移除。 如果您指定暫止持續時間，它會計算從日期接收郵件，或建立信箱項目。 
  
以下是當您建立訴訟暫止狀態時，會發生什麼事。
  
- 根據使用者時，會永久刪除的項目會保留在使用者的信箱中的 [可復原的項目] 資料夾保留期間。
    
- 會從 [可復原的項目] 資料夾清除使用者的項目會保留的保留期間。
    
- 從 30 GB 增加可復原的項目] 資料夾的儲存配額為 110 GB。
    
- 使用者的主要和封存信箱中的項目會保留
    
## <a name="before-you-begin"></a>開始之前

- 若要啟用 Exchange Online 信箱訴訟暫止，它必須指派 Exchange Online Plan 2 授權。 如果信箱指派 Exchange Online Plan 1 授權，您必須指派不同 Exchange Online Archiving 授權，才能將它放在保留它。
    

## <a name="place-a-mailbox-on-litigation-hold"></a>將信箱設為訴訟暫止

以下是可讓信箱處於訴訟暫止使用 Exchange 系統管理中心的步驟。

1. 移至 [[https://outlook.office.com/ecp](https://outlook.office.com/ecp)並使用您的全域系統管理員帳戶登入。

2. 在左側的導覽窗格中，按一下 [**收件者 > 信箱**。

3. 選取您想要放置訴訟暫止的信箱，然後按一下 [**編輯**。

4. 在信箱內容頁面上，按一下 [**信箱功能**]。
    
5. [**訴訟暫止： 停用**，按一下 [**啟用**]，以讓信箱處於訴訟暫止狀態。
    
6. 在 [**訴訟暫止**] 頁面上，輸入下列選擇性資訊： 
    
    - **訴訟暫止持續時間 （天）** -使用此方塊來建立時間型保留，並指定當信箱處於訴訟暫止的信箱項目保留多久。 持續時間自接收或建立信箱項目的日期開始計算。 當保留期間到期時的特定項目時，則不再會保留該項目。 如果您將此方塊保留空白，項目會保留無限期或保留到移除保留為止。 請使用天數為單位來指定持續時間。
    
    - **附註**-使用此方塊告知使用者他們的信箱處於訴訟暫止狀態。 附註會出現在使用者的信箱中的 [帳戶資訊] 頁面上，如果他們使用 Outlook 2010 或更新版本。 若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。
    
    - **URL** -使用此方塊以將使用者導向至網站，使其訴訟暫止狀態的詳細資訊。 如果他們使用 Outlook 2010 或更新版本，此 URL 會顯示在使用者的信箱中的 [帳戶資訊] 頁面上。 若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。.

7. 在 [**訴訟暫止**] 頁面上，按一下 [**儲存**，然後按一下 [信箱內容] 頁面上的 [**儲存**。

### <a name="create-a-litigation-hold-using-powershell"></a>建立使用 PowerShell 訴訟暫止

您也可以建立訴訟暫止狀態，藉由[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令：

```
Set-Mailbox <username> -LitigationHoldEnabled $true
```

上述命令會無限期保留項目因為未指定保留期間。 若要建立時間型保留時，使用下列命令：

```
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

如需詳細資訊，請參閱[Set-mailbox](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/set-mailbox)。

## <a name="how-does-litigation-hold-work"></a>訴訟暫止如何運作？

在正常刪除項目工作流程中，當使用者永久刪除 (Shift+Delete) 或從 [刪除的項目] 資料夾中刪除項目時，信箱項目會移至 [可復原的項目] 資料夾中的 [刪除] 子資料夾。 當保留期間到期時，刪除原則 (也就是以刪除保留動作設定的保留標記) 也會將項目移至 [刪除] 子資料夾。 當使用者清除 [可復原的項目] 資料夾中的項目，或已刪除項目的保留期間到期時，項目會移至 [可復原的項目] 資料夾中的 [清除] 子資料夾並標示為永久刪除。 系統會在下一次受管理的資料夾助理員 (MFA) 處理信箱時，從 Exchange 清除項目。

當信箱處於訴訟暫止狀態時，[清除] 子資料夾中的項目會依訴訟暫止所指定的保留期間予以保留。保留期間是由接收或建立項目的原始日期開始計算，並定義 [清除] 子資料夾中的項目會保留多久。[清除] 子資料夾中的項目保留期間到期時，項目將標示為永久刪除，並在下一次 MFA 處理信箱時，從 Exchange清除。若信箱設為無限期保留，項目將不會從 [清除] 子資料夾中清除。

下圖顯示在 [可復原的項目] 資料夾中的子資料夾以及並保留工作流程程序。

![訴訟暫止生命週期](media/LitigationHoldLifeCycle.png)

> [!NOTE]
> 如果 eDiscovery 案例相關聯保留在信箱上，清除項目會從 [刪除] 子資料夾移到 [DiscoveryHolds] 子資料夾，並會保留直到信箱釋放 eDiscovery 保留中。
  