---
title: 解決共用信箱的問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您遇到問題的共用信箱，請嘗試這些解決方案。
ms.openlocfilehash: b45c2eefa8cb4fb5fa34808223efbc1f0023161d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251673"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>解決共用信箱的問題

如果您看到錯誤訊息建立或使用共用的信箱時，請嘗試這些可能的解決方案。 

## <a name="error-when-creating-shared-mailboxes"></a>建立共用信箱時發生錯誤
<a name="bkmk_Fix"> </a>

如果您看到錯誤訊息、 **proxy 位址"smtp: <共用的信箱名稱\>」 已經正在使用的 proxy 位址或 LegacyExchangeDN 「\<命名> 」。請選擇其他 proxy 位址**，就表示您想要提供共用的信箱已在使用的名稱。 舉例來說，假設您想將共用信箱命名為 info@domain1 和 info@domain2。 方法有兩種：

  - 使用 Windows PowerShell。 如需相關指示，請參閱此部落格文章：[在 Office 365 中建立別名相同但網域不同的共用信箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 指定的名稱，第二個共用的信箱不同從開始到避開這個錯誤。 然後在系統管理中心中，請重新共用的信箱命名為您想要。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>關於使用共用的信箱時不會察覺傳送權限錯誤

如果您建立共用的信箱，然後再嘗試從它來傳送郵件，您可能收到這：

**無法傳送此郵件。您沒有代表指定使用者將郵件傳送的權限。**

Office 365 遇到的複寫延遲問題時，就會出現此訊息。 它應移至離開一小時或，當您新的共用的信箱 （或新增的使用者） 的資訊複製所有我們的資料中心。 請稍候一小時，然後再試一次傳送訊息。

## <a name="related-articles"></a>相關文章

[關於共用信箱](about-shared-mailboxes.md)

[建立共用信箱](create-a-shared-mailbox.md)

[設定共用信箱](configure-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)


    

