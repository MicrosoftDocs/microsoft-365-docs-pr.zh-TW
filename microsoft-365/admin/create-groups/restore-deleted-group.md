---
title: 還原已刪除的 Office 365 群組
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 瞭解如何還原已刪除的 Office 365 群組。
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583160"
---
# <a name="restore-a-deleted-office-365-group"></a>還原刪除的 Office 365 群組

如果您已刪除某個群組，它預設會保留30天。 這30天的期間會被視為「虛刪除」，因為您仍然可以還原群組。 30天后，就會永久刪除群組及其相關聯的內容，而且無法還原。

還原群組時，將會還原下列內容：
  
- Azure Active Directory （AD） Office 365 群組物件、屬性和成員。
    
- 群組的電子郵件地址。
    
- Exchange Online 共用收件匣和行事曆。
    
- SharePoint 線上小組網站和檔案。
    
- OneNote 筆記本
    
- Planner
    
- Teams

- Yammer 群組和群組內容（如果 Office 365 群組是由 Yammer 建立）

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>使用 Outlook 還原您擁有的群組

如果您是 Office 365 群組的擁有者，您可以遵循下列步驟，自行在 Outlook 中還原群組：

1. 在 [[刪除的群組] 頁面](https://outlook.office.com/people/group/deleted)上，選取 [**群組**] 節點底下的 [**管理群組**] 選項，然後選擇 [**刪除**]。
2. 按一下您要還原之群組旁的 [**還原**] 索引標籤。

若已刪除的群組未出現在這裡，請與系統管理員聯繫。

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心中還原群組

如果您是全域系統管理員或群組管理員，則可在 Microsoft 365 系統管理中心還原刪除的群組：

1. 移至位於 [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com) 的系統管理中心。
2. 展開 [**群組**]，然後按一下 [**刪除的群組**]。
3. 選取您要還原的群組，然後按一下 [**還原群組**]。
  
## <a name="permanently-delete-an-office-365-group"></a>永久刪除 Office 365 群組

在某些情況下，您可能想要永久清除群組，而不需等待30天的虛刪除期限到期。 若要這麼做，請啟動 PowerShell 並執行下列命令以取得該群組的物件識別碼：
  
```
Get-AzureADMSDeletedGroup
```

記下您要永久刪除之群組或群組的物件識別碼。
  
> [!CAUTION]
> 永久移除群組及其資料來清除該群組。 
  
若要清除該群組，請在 PowerShell 中執行下列命令：
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

若要確認群組已成功清除，請再次執行  *Get-AzureADMSDeletedGroup*  Cmdlet 來確認該群組已不再顯示在虛刪除群組清單中。某些情況下，最多可能需要 24 小時才能永久刪除群組及其所有資料。 
  
## <a name="got-questions-about-office-365-groups"></a>有任何關於 Office 365 群組的問題嗎？

流覽[Microsoft 技術社區](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以張貼問題，並參與 Office 365 群組的交談。 
  
## <a name="related-articles"></a>相關文章

[使用 PowerShell 管理 Office 365 群組](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[使用 Remove-UnifiedGroup Cmdlet 來刪除群組](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[管理連接群組的小組網站設定](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx) (機器翻譯)
  
[在 Outlook 中刪除群組](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx) (機器翻譯)
