---
title: EOP 一般常見問題集
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: 針對 Exchange Online Protection (EOP) 雲端主控的電子郵件篩選服務，取得最常見的一般問題的答案。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04246b7c0a241c672328febd1584a56aa11becf2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204832"
---
# <a name="eop-general-faq"></a>EOP 一般常見問題集

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
-  [Exchange Online Protection 獨立](exchange-online-protection-overview.md)

在這裡，我們會針對 Exchange Online Protection (EOP) 雲端主控的電子郵件篩選服務，回答最常見的一般問題。 如需其他常見問題集 (FAQ) 主題，請前往下列連結：

- [EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)

- [委派管理常見問題集](delegated-administration-faq.md)

- [反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)

- [隔離常見問題集](quarantine-faq.md)

- [反惡意程式碼保護常見問題集](anti-malware-protection-faq-eop.md)

- [郵件追蹤常見問題集](/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>EOP 是什麼？

EOP 是一種雲端主控的電子郵件篩選服務，可為客戶防範垃圾郵件和惡意程式碼，以及實施自訂原則規則。 EOP 包含在任何包含 Exchange Online 信箱的 Microsoft 365 訂閱中。 EOP 也以獨立的方式提供，以協助保護內部部署的電子郵件環境。

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>如何註冊 EOP 試用版或購買 EOP？

在 [Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)上，註冊 EOP 試用版或透過網頁購買 EOP。 請注意，試用期購買的功能與付費訂閱相同，但也包含 [Exchange ENTERPRISE CAL With Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) 訂閱計畫提供的其他功能。

## <a name="how-is-eop-priced"></a>EOP 的定價如何？

EOP 是由使用者授權。 如需最新的定價資訊，請參閱 [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)首頁。

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>將 EOP 投入實際執行所需的時間多久？

當您根據 [設定 EOP 服務](set-up-your-eop-service.md)中所述的步驟變更 MX 記錄，並將郵件流過 EOP 時，篩選會立即開始。 MX 記錄可能需要長達24-48 小時才能透過 DNS 傳播。 在此程式期間，您可以隨時微調保護設定。

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>我必須使用 Microsoft 365 的所有功能才能使用 EOP 嗎？ 如果我只想要 EOP 保護，該怎麼辦？

您可以使用 EOP 來保護您的內部部署信箱，而不需要使用 Microsoft 365 的任何其他功能。 這稱為獨立訂閱。 您可以在 [Exchange Online Protection 服務說明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)中找到 EOP 功能的清單。

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>為什麼在註冊透過 EOP 的電子郵件篩選時，我需要 Microsoft 365 租使用者？

Microsoft 365 是指可透過 Microsoft 365 租使用者存取的產品和服務集合所提供的名稱。 請將 Microsoft 365 租使用者想像為您可以為電子郵件篩選新增授權的起始點。

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP 是否有通訊入口網站，可從中找出已知問題和預期的解決方法？ 新功能的功能為何？

Microsoft 365 系統管理中心將會包含這項資訊。 如果您受到服務等級事件的影響，您應該會在登入 Microsoft 365 系統管理中心時，看到 (通常伴隨震鈴圖示) 的通訊警示。 建議您詳讀內容並採取適當的行動。

關於新的 EOP 功能， [Microsoft 365 for business 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) 是用來找出即將推出之新功能之相關資訊的好資源。 我們也會將有關新功能的博客文章張貼至 [Microsoft 365 博客](https://www.microsoft.com/microsoft-365/blog/) 網站。

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>服務是否能使用舊版 Exchange 版本 (例如 Exchange Server 2010) 和非 Exchange 環境？

是的，此服務是伺服器不可知的，而且可以搭配任何 SMTP 郵件傳輸代理程式使用。

## <a name="what-size-organization-can-use-the-service"></a>組織可以使用服務的規模為何？

任何大小。 EOP 網路有足夠的容量可容納您的成長，不論組織的成長速度為何。

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>我需要哪些權限才能設定 EOP？

為了設定 EOP，您必須是全域系統管理員，或 Exchange 公司管理員 (組織管理角色群組) 。

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>如何知道我的資料和私人資訊是安全的？

若要深入瞭解我們所採取的步驟，以確保資料和私人資訊的安全性，包括 (Sla) 中的服務等級協定相關資訊，請移至 [Office 365 信任中心](https://www.microsoft.com/trust-center)。

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>是否有任何應注意的限制，例如郵件大小限制？

是。 如需 EOP 中限制的相關資訊，請參閱 [Exchange Online Protection 限制](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。

## <a name="does-eop-support-powershell"></a>EOP 是否支援 PowerShell？

可以透過使用 Exchange Online 信箱的組織 PowerShell: Exchange Online PowerShell 取得完整的 EOP 功能;獨立 EOP 組織的獨立 EOP PowerShell。 如需詳細資訊，請參閱 [Exchange online PowerShell](/powershell/exchange/exchange-online-powershell) 和 [exchange online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell)。