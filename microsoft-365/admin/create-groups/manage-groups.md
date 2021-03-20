---
title: 管理系統管理中心中的群組
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: 瞭解如何管理 Microsoft 365 群組，包括新增移除群組成員、編輯電子郵件地址、組名或描述，以及自訂群組的運作方式。
ms.openlocfilehash: 3ba3dd36ed3929e956ce6359e678d6b684f64bb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908707"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心中管理群組

[建立 Microsoft 365 群組](create-groups.md)並新增群組成員之後，您可以設定群組。 您可以編輯群組名稱或描述、管理擁有者或成員，並指定外部寄件者是否可以寄出群組，以及是否要將群組交談的複本傳送給成員。

移至 Microsoft 365 系統管理中心，網址為 [https://admin.microsoft.com](https://admin.microsoft.com) 。

## <a name="edit-the-group-name-or-description"></a>編輯群組名稱或描述

1. 在系統管理中心中，展開 [ **群組**]，然後按一下 [ **群組**]。

2. 選取您要編輯的群組，然後按一下 [ **編輯名稱與描述**]。

3. 更新 [名稱] 和 [描述]，然後選取 [ **儲存**]。

## <a name="manage-group-owners-and-members"></a>管理群組擁有者和成員

1. 在系統管理中心中，展開 [ **群組**]，然後按一下 [ **群組**]。

2. 按一下您要管理的群組名稱，以開啟 [設定] 窗格。

3. 在 [ **成員** ] 索引標籤上，選擇您是否要管理擁有者或成員。

4. 選擇 [ **新增** ] 以新增人員，或按一下 **X** 以移除某人。

5. 按一下 [關閉 **]**。

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>將交談複本傳送至群組成員的收件匣
  
當您使用系統管理中心建立群組時，使用者預設不會取得群組電子郵件和會議邀請傳送至其收件匣的副本。 他們必須前往群組，才能看到交談和會議。 您可以在系統管理中心變更此設定。

當您開啟此設定時，群組成員將會取得組電子郵件和會議邀請傳送至其 Outlook 收件匣的副本。 群組成員可以閱讀和刪除此電子郵件複本，且不會影響任何其他人。 電子郵件複本仍會存在群組收件匣中。

群組成員可以選擇停止關注 Outlook 中的群組，以選擇不接收這些電子郵件。

1. 在系統管理中心中，展開 [ **群組**]，然後按一下 [ **群組**]。

2. 按一下您要管理的群組名稱，以開啟 [設定] 窗格。

3. 在 [ **設定** ] 索引標籤上，如果您想要讓成員在自己的收件匣接收群組郵件和行事曆專案的副本，請選取 [ **將群組交談和事件的副本傳送至群組成員** ]

4. 選取 [儲存]。

## <a name="let-people-outside-the-organization-email-the-group"></a>讓組織外部的人員以電子郵件傳送群組

如果您想要有公司的電子郵件地址（例如 info@contoso.com），則此選項非常好。
 
1. 在系統管理中心中，展開 [ **群組**]，然後按一下 [ **群組**]。

2. 按一下您要管理的群組名稱，以開啟 [設定] 窗格。

3. 在 [系統管理中心群組] 清單中，選取您要變更之群組的名稱，然後在 [ **設定** ] 索引標籤上，選取 [ **允許外部寄件者以電子郵件傳送此群組**]。
    
4. 選取 [儲存]。

## <a name="permanently-delete-a-microsoft-365-group"></a>永久刪除 Microsoft 365 群組

在某些情況下，您可能想要永久清除群組，而不需等待30天的虛刪除期限到期。 若要這麼做，請啟動 PowerShell 並執行下列命令以取得該群組的物件識別碼：
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

記下您要永久刪除之群組或群組的物件識別碼。
  
> [!CAUTION]
> 永久移除群組及其資料來清除該群組。 
  
若要清除該群組，請在 PowerShell 中執行下列命令：

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

若要確認群組已成功清除，請再次執行  *Get-AzureADMSDeletedGroup*  Cmdlet 來確認該群組已不再顯示在虛刪除群組清單中。某些情況下，最多可能需要 24 小時才能永久刪除群組及其所有資料。 
  
## <a name="related-articles"></a>相關文章

[建立 Microsoft 365 群組](create-groups.md)

[管理 Microsoft 365 群組的來賓存取權](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[選擇建立 Microsoft 365 群組時要使用的網域](../../solutions/choose-domain-to-create-groups.md)

[允許成員以 Microsoft 365 群組的身分傳送或傳送](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[將通訊群組清單升級至 Microsoft 365 群組](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Microsoft 365 群組](../../enterprise/manage-microsoft-365-groups-with-powershell.md)