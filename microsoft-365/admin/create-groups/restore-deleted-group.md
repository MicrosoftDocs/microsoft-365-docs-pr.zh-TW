---
title: 還原已刪除的 Microsoft 365 群組
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 已刪除的群組會保留30天，您仍可還原此群組。 30天后，就會永久刪除群組及其內容。
ms.openlocfilehash: 285796ec45b1e6d77d46d7a0c39706f566bb8cf6
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582677"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>還原已刪除的 Microsoft 365 群組

如果您已刪除某個群組，它預設會保留30天。 這30天的期間會被視為「虛刪除」，因為您仍然可以還原群組。 30天后，就會永久刪除群組及其相關聯的內容，而且無法還原。

還原群組時，將會還原下列內容：
  
- Azure Active Directory (AD) Microsoft 365 Groups 物件、屬性和成員。
    
- 群組的電子郵件地址。
    
- Exchange Online 共用收件匣和行事曆。
    
- SharePoint線上小組網站和檔案。
    
- OneNote 筆記本
    
- Planner
    
- Teams

- Yammer 群組和群組內容 (如果 Microsoft 365 群組是從 Yammer 建立的) 

> [!NOTE]
> 本文說明只還原 Microsoft 365 的群組。 所有其他群組一經刪除，便無法還原。

## <a name="restore-a-group"></a>還原群組

# <a name="outlook"></a>[Outlook](#tab/outlook)

如果您是 Microsoft 365 群組的擁有者，您可以遵循下列步驟，在網頁上 Outlook 中，自行還原群組：

1. 在 [[刪除的群組] 頁面](https://outlook.office.com/people/group/deleted)上，選取 [**群組**] 節點底下的 [**管理群組**] 選項，然後選擇 [**刪除**]。

2. 按一下您要還原之群組旁的 [ **還原** ] 索引標籤。

若已刪除的群組未出現在這裡，請與系統管理員聯繫。

# <a name="admin-center"></a>[系統管理中心](#tab/admin-center)

如果您是全域系統管理員或群組管理員，您可以在 Microsoft 365 系統管理中心還原已刪除的群組：

1. 移至 [[系統管理中心]](https://admin.microsoft.com)。
2. 展開 [ **群組**]，然後按一下 [ **刪除的群組**]。
3. 選取您要還原的群組，然後按一下 [ **還原群組**]。

> [!NOTE]
> 在某些情況下，您可能需要24小時的時間才能還原群組及其所有資料。 

---

## <a name="got-questions-about-microsoft-365-groups"></a>有 Microsoft 365 群組的相關問題嗎？

流覽[Microsoft 技術 Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以張貼問題，並參與有關 Microsoft 365 群組的交談。 
  
## <a name="related-content"></a>相關內容

[使用 PowerShell (文章管理 Microsoft 365 群組](../../enterprise/manage-microsoft-365-groups-with-powershell.md)) 
  
[使用 Remove-UnifiedGroup Cmdlet 刪除群組](/powershell/module/exchange/remove-unifiedgroup) (文章) 
  
[管理群組連線的小組網站設定](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (文章) 
  
[在 Outlook (文章中刪除群組](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)) 