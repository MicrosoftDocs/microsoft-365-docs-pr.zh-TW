---
title: 以通訊群組清單傳送電子郵件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 在 Microsoft 365 中以通訊群組清單形式傳送電子郵件，這樣當成員回復郵件時，就會從通訊群組清單中回復。
ms.openlocfilehash: 01bff7e1d2515670c5a6faa199355e7de591f1fb
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624534"
---
# <a name="send-email-as-a-distribution-list"></a>以通訊群組清單傳送電子郵件

在 Microsoft 365 中，您可以傳送電子郵件做為通訊群組清單。 當通訊群組清單的成員回復傳送至通訊群組清單的郵件時，電子郵件看似來自通訊群組清單，而不是來自個別使用者。 本主題說明如何執行這項操作。
  
## <a name="before-you-begin"></a>開始之前

在執行這些步驟之前，請確定您已新增至 Microsoft 365 通訊群組清單，且已被授與您的「傳送為」許可權。
  
 系統 **管理員**：請確定您已遵循 [新增 Microsoft 365 使用者或連絡人清單](../email/add-user-or-contact-to-distribution-list.md)中的步驟，並 [允許成員將電子郵件當做 Microsoft 365 群組主題傳送](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)，並將正確的人員新增至通訊群組清單。
  
## <a name="outlook-on-the-web"></a>Outlook 網頁版

1. 開啟網頁上的 Outlook，然後移至您的收件匣。 
    
2. 開啟傳送至通訊群組清單的郵件。 
    
3. 選取 [ **回復**]。 
    
4. 在郵件的底部，選取 [ **其他** \> **顯示來源**]。<br/> ![選取 [其他]，然後選擇 [顯示來源]](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. 在 [寄件者位址--] 上按一下滑鼠右鍵 `Ina@weewalter.me` ，然後選擇 [ **移除**]。<br/> ![移除寄件者別名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 然後輸入通訊群組清單位址（如 support@contoso.com），然後傳送郵件。 當您下次從通訊群組清單回復時，其位址會顯示為 [ **發件** 人] 清單中的選項。<br/>![共用信箱的別名會出現](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)

## <a name="outlook"></a>Outlook

1. 開啟 Outlook 桌面用戶端。

2. 撰寫新的電子郵件。 按一下 [ **寄件者** ] 欄位，然後選取 [ **其他電子郵件地址**]。 如果您沒有看到 [寄件者] 欄位，請流覽至 [ **選項** ]，然後在 [顯示欄位] 區段中選取 [ **從** ]。

3. 從全域通訊清單中選取 **通訊群組清單** 位址。

4. 傳送電子郵件。

## <a name="related-content"></a>相關內容

[在 Microsoft 365 系統管理中心建立、編輯或刪除安全性群組](../email/create-edit-or-delete-a-security-group.md) (文章) \
[電子郵件](../email/email-collaboration.md) 共同作業 (文章) \
[新增使用者或連絡人至通訊群組](../email/add-user-or-contact-to-distribution-list.md)