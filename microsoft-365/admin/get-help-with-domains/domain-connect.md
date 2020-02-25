---
title: 使用網域連線
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 了解如何使用網域連線啟用註冊機構，並將您的網域新增至 Microsoft 365。
ms.openlocfilehash: e014504116e5d19c8413549c802fd110dddfb8df
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251667"
---
# <a name="using-domain-connect"></a>使用網域連線

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。
  
[網域連線](https://www.domainconnect.org/)啟用註冊機構可讓您新增網域至 Microsoft 365 三步驟程序，在幾分鐘。 
  
在精靈中，我們只會確認您擁有該網域，然後自動設定您的網域的記錄，以便電子郵件有 Microsoft 365 及其他 Microsoft 365 服務，例如 Teams，搭配您的網域。
  
> [!NOTE]
> 啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>網域連線登錄器與 Microsoft 365 整合

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 或 WildWestDomains （GoDaddy 轉銷商使用 SecureServer DNS 主機服務）
    - [MadDog 網域](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>我的電子郵件與網站會發生什麼事？

您完成安裝之後，您的網域的 MX 記錄已經更新為指向 Microsoft 365，並為您的網域的所有電子郵件都會開始送往 Microsoft 365。 請確認您已針對在您的網域取得電子郵件的每位人員，在 Office 365 中新增使用者並設定信箱。
  
如果您擁有商務用途的網站，該網站將會在原處繼續運作。 網域連線設定步驟不會影響您的網站。