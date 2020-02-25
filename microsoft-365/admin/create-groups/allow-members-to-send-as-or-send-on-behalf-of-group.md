---
title: 允許成員傳送為 」 或 「 代理群組傳送
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 了解如何讓成員為 Office 365 群組傳送電子郵件] 或 [代理 Office 365 群組傳送電子郵件。
ms.openlocfilehash: c0dca3a3bbed6617874d9dfbca06a4ec5d6b4ebc
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239246"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>允許成員傳送為 」 或 「 代理群組傳送

做為群組，或代表群組已授與**傳送為**」 或 **「 代理傳送者 」** 權限的 Office 365 群組的成員現在可以傳送電子郵件。 本主題說明如何為系統管理員可以設定這些權限。
  
例如，如果謝良屬於**訓練**的 Office 365 群組擁有 「**傳送為**權限] 群組中，如果曾經傳送一封電子郵件做為群組，它看起來像**訓練**群組傳送電子郵件。 
  
**代理傳送者 」** 權限可讓 Office 365 群組代理傳送電子郵件使用者。 例如，如果 Alex Wilber 屬於**Marketing** Office 365 群組，具有**代理傳送者 」** 權限並傳送一封電子郵件做為群組、 電子郵件看起來就由**代表行銷 Alex Wilber**所傳送。

> [!IMPORTANT]
> 您可以指定的使用者，但不能兩者同時設定**傳送為**」 或 **「 代理傳送者 」** 。 如果您設定兩者，它會預設**為**傳送。

> [!TIP]
> 簽出以從群組電子郵件中[傳送電子郵件從或是代表 Office 365 群組](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)了解如何使用 Outlook 和 outlook 網頁版傳送的步驟。
    
## <a name="allow-members-to-send-email-as-a-group"></a>允許傳送電子郵件做為群組的成員

本節說明如何允許使用者傳送電子郵件做為群組中[的 Exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)(EAC) 中 Exchange Online。
  
1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中，前往 [**收件者** \> **群組**。
    
2. 選取 [**編輯**  ![編輯群組圖示](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)上您想要允許使用者傳送為群組。 
    
3. 選取 [**群組委派**]。
    
4. 在 [以下列**傳送**] 區段中，選取 [**+** 新增您想要傳送做為群組的使用者登入。 
    
    ![選取加號，以新增您想要傳送做為 Office 365 群組的使用者](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. 輸入要搜尋或挑選清單中的使用者。 選取 [**確定**] 和 [**儲存**]。
    
    ![輸入要搜尋或挑選清單中的使用者](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>允許成員代理群組傳送電子郵件

本節說明如何允許使用者傳送代表群組的電子郵件在 Exchange 系統管理中心 (EAC) 中 Exchange Online。
  
1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中，前往 [**收件者** \> **群組**。
    
2. 選取 [**編輯**![編輯群組圖示](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)上您想要允許使用者傳送為群組。 
    
3. 選取 [**群組委派**]。
    
4. 在代理傳送者] 區段中，選取 [**+** 以新增您想要傳送做為群組的使用者登入。 
    
    ![選取加號，以新增您想要傳送做為 Office 365 群組的使用者](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. 輸入要搜尋或挑選清單中的使用者。 選取 [**確定**] 和 [**儲存**]。
    
    ![輸入要搜尋或挑選清單中的使用者](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>相關文章

[深入了解 Office 365 群組](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[Add-recipientpermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-unifiedgroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
