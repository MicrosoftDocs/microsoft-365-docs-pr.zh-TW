---
title: 為 Office 365 中的通訊群組清單傳送電子郵件
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 了解如何在 Office 365 中以通訊群組清單的形式傳送電子郵件 (機器翻譯)。
ms.openlocfilehash: f165279cf6cfbedda4f122f453c2321c16f412d3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251594"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a>為 Office 365 中的通訊群組清單傳送電子郵件

在 Office 365 中，您可以傳送電子郵件作為通訊群組清單。 當通訊群組清單成員的人員回覆傳送給通訊群組清單的郵件時，將電子郵件會顯示從通訊群組清單，而不是由個別使用者。 本主題顯示如何進行此作業。
  
## <a name="send-email-as-a-distribution-list"></a>傳送電子郵件作為通訊群組清單

在執行這些步驟之前，請確定您已新增至 Office 365 通訊群組清單並已獲授與傳送為 」 權限在其上。
  
 **系統管理員**： 請確定您已後面的步驟主題中所[新增的 Office 365 使用者或連絡人至清單](../email/add-user-or-contact-to-distribution-list.md)和[允許傳送電子郵件做為 Office 365 群組的成員](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)，且正確的人員新增至通訊群組清單。
  
1. 開啟 outlook 網頁版並移至收件匣。 
    
2. 開啟已傳送至通訊群組清單的郵件。 
    
3. 選取 [**回覆**]。 
    
4. 在郵件的底部，選取 [**更多** \> **顯示的**。<br/> ![選取 [其他]，然後選擇 [顯示從](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. 以滑鼠右鍵按一下來源地址-例如`Ina@weewalter.me`-選擇 [**移除**。<br/> ![移除 FROM 別名](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 然後輸入通訊群組清單地址，例如 support@contoso.com，然後傳送郵件。 下次您回覆從通訊群組清單，其地址會顯示為 [**從**] 清單中的選項。<br/>![共用信箱的別名出現](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)
  

