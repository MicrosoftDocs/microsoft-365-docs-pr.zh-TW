---
title: 傳輸中資料的加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 在本文中，會找到 Microsoft 如何在傳輸中加密 Microsoft 365 客戶資料的簡短說明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ee869308549398a9df00ed42975b4aeedb666a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033601"
---
# <a name="encryption-for-data-in-transit"></a>傳輸中資料的加密

除了保護靜態客戶資料之外，Microsoft 還使用加密技術來保護傳輸中的客戶資料。 

資料正在傳輸中：

- 當用戶端電腦與 Microsoft 伺服器通訊時;
- 當 Microsoft 伺服器與另一部 Microsoft 伺服器通訊時，和
- 當 Microsoft 伺服器與非 Microsoft 伺服器通訊時（例如，Exchange Online 將電子郵件傳遞至協力廠商電子郵件伺服器）。

Microsoft 伺服器之間的資料中心通訊會透過 TLS 或 IPsec 進行，而且所有客戶對向伺服器都使用 TLS 與用戶端電腦協商安全會話（例如，Exchange Online 使用 TLS 1.2 搭配256位密碼強度（FIPS 140-2 層級2驗證）。 （如需有關 Office 365 支援之 TLS 密碼套件清單的[加密技術參考詳細資料](technical-reference-details-about-encryption.md)，請參閱。）這適用于用戶端（例如 Outlook、商務用 Skype、Microsoft 小組和 Outlook 網頁版）所使用的通訊協定（例如 HTTP、POP3 等）。

公用憑證是由 Microsoft IT SSL 使用 SSLAdmin （內部 Microsoft 工具）發行，以保護傳輸資訊的機密性。 所有由 Microsoft 所發行的憑證，其長度最低為2048位，且 Webtrust 合規性需要 SSLAdmin，以確保只將憑證發行給 Microsoft 所擁有的公用 IP 位址。 任何無法符合此準則的 IP 位址，都是透過例外狀況流程進行路由傳送。

所有的執行詳細資料（如使用的 TLS 版本）、是否已啟用轉寄保密（FS）、密碼套件等順序皆可公開使用。 查看這些詳細資料的一種方式是使用協力廠商網站，例如[QUALYS SSL 實驗](https://www.ssllabs.com)。 以下是 Qualys 中的自動測試頁面連結，可顯示下列服務的資訊：

- [Office 365 入口網站](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [商務用 Skype （SIP）](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [商務用 Skype （Web）](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

針對 Exchange Online Protection，URLs 會因租使用者名稱而異;不過，所有客戶都可以使用**microsoft-com.mail.protection.outlook.com**測試 Microsoft 365。
