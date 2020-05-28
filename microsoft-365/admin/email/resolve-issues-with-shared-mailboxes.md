---
title: 解決共用信箱的問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您遇到共用信箱的問題，請嘗試這些解決方案。
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400013"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>解決共用信箱的問題

如果您在建立或使用共用信箱時看到錯誤訊息，請嘗試這些可能的解決方案。 

## <a name="error-when-creating-shared-mailboxes"></a>建立共用信箱時發生錯誤
<a name="bkmk_Fix"> </a>

如果您看到錯誤訊息，**表示 proxy 位址 "smtp： <共用信箱名稱 \> " 已由 "" 的 proxy 位址或 LegacyExchangeDN 使用 \<name> 。請選擇另一個 proxy 位址**，這表示您嘗試將已在使用中的名稱提供給共用信箱。 舉例來說，假設您想將共用信箱命名為 info@domain1 和 info@domain2。 方法有兩種：

  - 使用 Windows PowerShell。 如需相關指示，請參閱這篇博客文章：[在不同的網域建立具有相同別名的共用信箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 將第二個共用信箱命名為不同于「開始」以避免錯誤的地方。 然後在系統管理中心，將共用信箱重新命名為您想要的內容。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>使用共用信箱時，未具備傳送許可權的錯誤

如果您建立了共用信箱，然後嘗試從該信箱傳送郵件，您可能會收到下列訊息：

**無法傳送此郵件。您沒有代表指定使用者傳送郵件的許可權。**

當 Microsoft 365 遇到複寫延遲問題時，就會出現此訊息。 當您在所有的資料中心之間複寫新共用信箱（或新增使用者）的相關資訊時，它應該會在一小時內消失。 請等候一小時後再試一次，再傳送一封郵件。

## <a name="related-articles"></a>相關文章

[關於共用信箱](about-shared-mailboxes.md)

[建立共用信箱](create-a-shared-mailbox.md)

[設定共用信箱](configure-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)


    

