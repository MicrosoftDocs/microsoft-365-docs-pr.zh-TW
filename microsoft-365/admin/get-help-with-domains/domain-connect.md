---
title: 使用網域連線
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 瞭解如何使用網域連線啟用註冊機構，將您的網域新增至 Microsoft 365。
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228008"
---
# <a name="using-domain-connect"></a>使用網域連線

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。

[網域連線](https://www.domainconnect.org/)啟用型註冊機構可讓您將您的網域新增至以每三個步驟為間隔的三個步驟中 Microsoft 365。

在 [！附注] 中，我們只會確認您擁有網域，然後自動設定您的網域記錄，所以電子郵件會送出 Microsoft 365 和其他 Microsoft 365 服務，如 Teams，請與您的網域搭配使用。

> [!NOTE]
> 啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>與 Microsoft 365 整合的網域連線註冊機構

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- 使用 SecureServer DNS 主機的 SecureServer 或 WildWestDomains (GoDaddy 轉銷商) 
  - [MadDog Web 主控](https://maddogwebhosting.com/domains/)
  - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>我的電子郵件和網站會發生什麼情況？

完成設定之後，您的網域的 MX 記錄會更新，以指向 Microsoft 365，而且您網域的所有電子郵件都將開始進入 Microsoft 365。 請確認您已新增使用者，並為在您的網域中取得電子郵件的所有人設定 Microsoft 365 中的信箱！

如果您擁有商務用途的網站，該網站將會在原處繼續運作。 網域連線設定步驟不會影響您的網站。
