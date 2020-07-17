---
title: 建立訴訟資料暫留
f1.keywords:
- NOCSH
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
description: 瞭解如何將信箱設為訴訟暫止，並在調查期間保留所有信箱內容。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 9c62dfcd9e4cf1e3cc75e029b250c7abe80de6df
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818042"
---
# <a name="create-a-litigation-hold"></a>建立訴訟資料暫留

您可以將信箱設為訴訟暫止，以保留所有信箱內容，包括已刪除的專案和已修改專案的原始版本。 當您將使用者的信箱設為訴訟暫止時，使用者封存信箱中的內容（如果已啟用）也會保留。 當您建立保留時，您可以指定保留期間（也稱為以*時間為基礎的保留*），以在指定期間內保留已刪除及已修改的專案，然後從信箱中永久刪除。 或者，您可以只保留無限期的內容（稱為*無限期*保留）或移除訴訟暫止。 如果您指定保留期間期限，它會從接收郵件或建立信箱專案的日期開始計算。 
  
以下是建立訴訟暫止時發生的情況。
  
- 使用者永久刪除的專案會保留在使用者信箱的 [可復原的專案] 資料夾中的保留期間。
    
- 從使用者的 [可復原的專案] 資料夾中清除的專案會在保留期間內保留。
    
- [可復原的專案] 資料夾的儲存配額會從 30 GB 增加為 110 GB。
    
- 保留使用者主要和封存信箱中的專案
    
## <a name="assign-an-exchange-online-plan-2-license"></a>指派 Exchange Online Plan 2 授權

- 若要將 Exchange Online 信箱設為訴訟暫止狀態，必須將其指派為 Exchange Online Plan 2 授權。 如果信箱已獲指派 Exchange Online Plan 1 授權，則必須將其指派給其另一個 Exchange Online 封存授權，以便進行暫止。
    

## <a name="place-a-mailbox-on-litigation-hold"></a>將信箱設為訴訟暫止

以下是使用 Exchange 系統管理中心，將信箱設為訴訟暫止狀態的步驟。

1. 移至 [https://outlook.office.com/ecp](https://outlook.office.com/ecp) 並使用全域系統管理員帳戶登入。

2. 按一下左導覽窗格中的 [收件者] **> 信箱**。

3. 選取您要進行訴訟暫止的信箱，然後按一下 [**編輯**]。

4. 在信箱屬性頁面上，按一下 [**信箱功能**]。
    
5. 在 [**訴訟暫止：已停用**] 下，按一下 [**啟用**]，將信箱設為訴訟暫止。
    
6. 在 [**訴訟暫**止] 頁面上，輸入下列選擇性資訊： 
    
    - **訴訟暫止持續時間（天）** -使用此方塊可建立以時間為基礎的保留，並指定當信箱處於訴訟暫止狀態時，保留信箱專案的時間長度。 持續時間自接收或建立信箱項目的日期開始計算。 特定專案的保留期間到期時，將不再保留該專案。 如果您將此方塊保留空白，則專案會無限期保留，或直到移除保留為止。 請使用天數為單位來指定持續時間。
    
    - **附注**-使用此方塊通知使用者其信箱處於訴訟暫止狀態。 如果使用者是使用 Outlook 2010 或更新版本，則附注會出現在使用者信箱中的 [帳戶資訊] 頁面上。 若要存取此頁面，使用者可以**按一下 Outlook 中的 [** 檔案]。
    
    - **URL** -使用此方塊可將使用者導向至網站，以取得訴訟暫止的詳細資訊。 如果使用者使用 Outlook 2010 或更新版本，則此 URL 會出現在使用者信箱的 [帳戶資訊] 頁面上。 若要存取此頁面，使用者可以**按一下 [** Outlook] 中的 [檔案]。

7. 按一下 [**訴訟暫**止] 頁面上的 [**儲存**]，然後按一下 [信箱屬性] 頁面上的 [**儲存**]。

### <a name="create-a-litigation-hold-using-powershell"></a>使用 PowerShell 建立訴訟暫止

您也可以在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令，以建立訴訟暫止狀態。

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

上一個命令會無限期保留專案，因為未指定保留期間。 若要建立以時間為基礎的保留，請使用下列命令：

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

如需詳細資訊，請參閱 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。

## <a name="how-does-litigation-hold-work"></a>訴訟暫止如何運作？

在正常刪除項目工作流程中，當使用者永久刪除 (Shift+Delete) 或從 [刪除的項目] 資料夾中刪除項目時，信箱項目會移至 [可復原的項目] 資料夾中的 [刪除] 子資料夾。 當保留期間到期時，刪除原則 (也就是以刪除保留動作設定的保留標記) 也會將項目移至 [刪除] 子資料夾。 當使用者清除 [可復原的項目] 資料夾中的項目，或已刪除項目的保留期間到期時，項目會移至 [可復原的項目] 資料夾中的 [清除] 子資料夾並標示為永久刪除。 系統會在下一次受管理的資料夾助理員 (MFA) 處理信箱時，從 Exchange 清除項目。

當信箱處於訴訟暫止狀態時，[清除] 子資料夾中的項目會依訴訟暫止所指定的保留期間予以保留。保留期間是由接收或建立項目的原始日期開始計算，並定義 [清除] 子資料夾中的項目會保留多久。[清除] 子資料夾中的項目保留期間到期時，項目將標示為永久刪除，並在下一次 MFA 處理信箱時，從 Exchange清除。若信箱設為無限期保留，項目將不會從 [清除] 子資料夾中清除。

下圖顯示在 [可復原的項目] 資料夾中的子資料夾以及並保留工作流程程序。

![訴訟暫止週期](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> 如果與 eDiscovery 案例相關聯的封存是放在信箱上，已清除的專案會從 [刪除] 子資料夾移至 DiscoveryHolds 子資料夾，而且會保留，直到信箱從 eDiscovery 保留中釋放為止。
  
