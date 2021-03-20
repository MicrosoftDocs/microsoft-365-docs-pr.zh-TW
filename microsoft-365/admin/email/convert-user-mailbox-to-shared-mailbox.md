---
title: 將使用者信箱轉換為共用信箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '瞭解如何將私人信箱轉換為可供多位使用者存取的共用信箱。 '
ms.openlocfilehash: d5b33731908d2d555a8dd12d5d7fbbd462bd83ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915863"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>將使用者信箱轉換為共用信箱

當您將使用者的信箱轉換成共用信箱時，所有的現有電子郵件和行事曆都會保留。 只是在共用信箱中，有好幾個人可以存取，而不是一個人。 在以後的日期，您可以將共用信箱轉換回使用者 (私人) 信箱。

**以下是您必須知道的一些重要事項：**

- 您要轉換的使用者信箱必須已獲指派授權，才可將其轉換成共用信箱。 否則，您將看不到轉換信箱的選項。 如果您已移除授權，請將其新增回來，以便轉換信箱。 將信箱轉換成共用信箱之後，您可以從使用者的帳戶中移除授權。

- 共用信箱最多可以有 50 GB 的資料，而不會獲指派授權。 若要保留超過該數目的資料，您必須指派授權給它。 您可能需要刪除大量的電子郵件 (說，其中包含附件的附件) 從共用信箱壓縮，這樣您就可以移除授權。

- 不要刪除舊的使用者帳戶。 鎖定共用信箱所需。 如果您已刪除使用者帳戶，請參閱 [轉換已刪除之使用者的信箱](#convert-the-mailbox-of-a-deleted-user)。

- 在信箱轉換成共用信箱之後，這些規則會完好無損。

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>使用 Exchange 系統管理中心來轉換信箱
 
1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。

2. 選取 **[** 收件者] \> **信箱**。

3. 選取使用者信箱。 在 [ **轉換為共用信箱**] 底下，選取 [ **轉換**]。

4. 如果信箱小於 50 GB，您可以移除 [使用者的授權](../manage/remove-licenses-from-users.md)，然後停止支付。 請勿刪除使用者的帳戶。 共用信箱需要以錨定。 如果您要轉換的是離開組織之員工的信箱，您應該採取額外的步驟，確定他們無法再登入。 請參閱 [從 Microsoft 365 移除前任員工](../add-users/remove-former-employee.md)。
    
> [!NOTE]
> 在信箱轉換期間，不需要重設使用者的密碼。 不過，如果沒有重設密碼， **則原始的使用者名稱和密碼** 會在信箱轉換完成之後繼續運作。

如需有關共用信箱的其他資訊，請參閱 [關於共用](about-shared-mailboxes.md) 信箱及 [建立共用信箱](create-a-shared-mailbox.md)。

> [!NOTE]
> 共用信箱不需要個別授權。 但是，如果您想啟用「就地封存」，或在共用信箱中使用「就地保留」或「訴訟資料暫留」，必須指派具有 Exchange Online 封存功能的 Exchange Online Plan 1 或 Exchange Online Plan 2 授權至信箱。


## <a name="convert-the-mailbox-of-a-deleted-user"></a>轉換已刪除使用者的信箱

假設您已刪除使用者帳戶，而現在您想要將其舊的信箱轉換成共用信箱。 以下是您需要執行的動作：

1. [還原使用者的帳戶](../add-users/restore-user.md)。

2. 請確定已將 Microsoft 365 授權指派給它。

3. 重設使用者的密碼。
    
4. 請等候20-30 分鐘，以重新建立其信箱。
    
5. 現在遵循此頁面上的指示，將其信箱轉換成共用信箱。
    
6. 完成後，您可以從使用者的信箱中移除授權。 不要刪除使用者的舊信箱。 共用信箱需要以錨定。
    
7. 新增成員至共用信箱。


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>將共用信箱轉換回使用者的 (私人) 信箱

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。
   
2. 選取 **[** 共用收件者] \> ****。

3. 選取共用信箱。 在 [ **轉換為一般信箱**] 底下，選取 [ **轉換**]。

4. 請回到系統管理中心。 在 [ **使用者**] 底下，選擇與舊共用信箱相關聯的使用者帳戶。 指派授權給帳戶，然後重設密碼。

   信箱需要幾分鐘的時間才能設定，但是在該之後，將使用該帳戶的人員可以前往。 登入時，他們會看到使用於共用信箱中的電子郵件和行事曆專案。

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>轉換使用者在混合式環境中的信箱

如需將使用者信箱轉換成 Exchange 混合式環境中共用信箱的詳細資訊，請參閱：

 - [在內部部署 Exchange 環境中建立或修改遠端共用信箱的 Cmdlet](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [在 Exchange 混合式部署中執行目錄同步作業後，共用信箱意外轉換為使用者信箱](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> 如果您是「組織管理」或「收件者管理」角色群組的成員，您可以使用 Exchange 管理命令介面，將使用者信箱變更為內部部署的共用信箱。 例如，`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`。

## <a name="related-articles"></a>相關文章

[關於共用信箱](about-shared-mailboxes.md)

[建立共用信箱](create-a-shared-mailbox.md)

[設定共用信箱](configure-a-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)

[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md)