---
title: 解決共用信箱的問題
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您在使用共用信箱時遇到問題，請嘗試這些解決方案。
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926483"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>解決共用信箱的問題

如果您在建立或使用共用信箱時看到錯誤訊息，請嘗試這些可能的解決方案。 

## <a name="error-when-creating-shared-mailboxes"></a>建立共用信箱時發生錯誤
<a name="bkmk_Fix"> </a>

如果您看到錯誤訊息，表示 Proxy 位址 "smtp：<共用信箱名稱" 已由 " "的 Proxy 位址 **\> 或 LegacyExchangeDN \<name> 使用。請選擇另一個 Proxy 位址**，這表示您嘗試為共用信箱提供已在使用中的名稱。 舉例來說，假設您想將共用信箱命名為 info@domain1 和 info@domain2。 方法有兩種：

  - 使用 Windows PowerShell。 請參閱此部落格文章以參閱指示：在不同的網域建立別名 [相同的共用信箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 將第二個共用信箱命名為與一開始不同的名稱以擺脫錯誤。 然後在系統管理中心，將共用信箱重新命名為您想要的名稱。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>使用共用信箱時沒有傳送許可權的錯誤

如果您建立了共用信箱，然後嘗試從共用信箱傳送郵件，您可能會收到以下訊息：

**無法送出此郵件。您沒有代表指定使用者傳送郵件的許可權。**

當 Microsoft 365 發生複寫延遲問題時，會出現這則訊息。 當您的新共用信箱資訊已複製 (或新增的使用者) 複製至我們所有資料中心時，一小時左右應該會消失。 請等候一個小時，然後再試一次以傳送郵件。

## <a name="related-articles"></a>相關文章

[關於共用信箱](about-shared-mailboxes.md)

[建立共用信箱](create-a-shared-mailbox.md)

[設定共用信箱](configure-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)


    

