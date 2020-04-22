---
title: EOP 一般常見問題集
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 在這裡，我們將回答有關於 Microsoft Exchange Online Protection (EOP) 雲端電子郵件篩選服務的最常見一般問題。如需其他常見問題集 (FAQ) 主題，請前往下列連結：
ms.openlocfilehash: 899109a768399f53674b97fc8df2f71aa822316d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636249"
---
# <a name="eop-general-faq"></a>EOP 一般常見問題集

在這裡，我們將回答有關於 Microsoft Exchange Online Protection (EOP) 雲端電子郵件篩選服務的最常見一般問題。如需其他常見問題集 (FAQ) 主題，請前往下列連結：

- [EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)

- [委派管理常見問題集](delegated-administration-faq.md)

- [反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)

- [隔離常見問題集](quarantine-faq.md)

- [反惡意程式碼保護常見問題集](anti-malware-protection-faq-eop.md)

- [郵件追蹤常見問題集](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

**問：EOP 是什麼？**

答：EOP 是雲端電子郵件篩選服務，專門用來保護客戶遠離垃圾郵件與惡意程式碼，以及執行自訂原則規則。

**問：如何註冊 EOP 試用版或購買 EOP？**

答：可透過以下網址註冊 EOP 試用版或購買 EOP：[Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)。請注意，試用購買的功能與付費訂閱版相同，但另外包含 [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) 訂閱方案提供的其他功能。

**問：EOP 如何定價？**

答：EOP 是依使用者授權。如需最新定價資訊，請參閱 [Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)。

**問：將 EOP 放入實際執行環境需時多久？**

答：當您依照[設定 EOP 服務](set-up-your-eop-service.md)中所述步驟變更 MX 記錄，以及透過 EOP 變更郵件流程，就會立即開始進行篩選。MX 記錄可能需要 24-48 個小時，以透過 DNS 進行傳播。在處理過程中，您隨時可以在 Exchange 系統管理中心 (EAC) 中微調您的保護設定。

**問：我是否需要使用 Microsoft 365 的所有功能才能使用 EOP？如果我只想要 EOP 保護，該怎麼辦？**

答： 您可以使用 EOP 來保護您的內部部署信箱，而不需要使用 Microsoft 365 的任何其他功能。 這稱為獨立訂閱。 您可以在[Exchange Online Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)中找到 EOP 功能的清單。

**問：在註冊透過 EOP 的電子郵件篩選時，為什麼需要 Microsoft 365 租使用者？**

答： Microsoft 365 是指可透過 Microsoft 365 租使用者存取的產品和服務集合所提供的名稱。 請將 Microsoft 365 租使用者想像為您可以為電子郵件篩選新增授權的起始點。

**問：EOP 是否有通訊入口網站可讓我了解已知問題和預期的解決方案？有哪些新功能？**

答： Microsoft 365 系統管理中心將會包含這項資訊。 如果您受到服務等級事件的影響，您應該會在登入 Microsoft 365 系統管理中心後，看到一則通訊警示（通常伴隨鈴聲圖示）。 建議您詳讀內容並採取適當的行動。

關於新的 EOP 功能， [Microsoft 365 for business 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是用來找出即將推出之新功能之相關資訊的好資源。 我們也會將有關新功能的博客文章張貼至[Microsoft 365 博客](https://www.microsoft.com/microsoft-365/blog/)網站。

**問：此服務可與舊版 Exchange (例如 Exchange Server 2010) 和非 Exchange 環境搭配使用嗎？**

答：可以，此服務與伺服器無關，可與任何 SMTP 郵件傳輸代理程式共用。

**問：哪種組織規模可以使用此項服務？**

問：所有規模都可以。無論您組織的成長速度多快，EOP 網路都有足夠容量可容納成長。

**我需要哪些權限才能設定 EOP？**

為了設定 EOP，您必須是全域管理員或 Exchange 公司管理員（組織管理角色群組）。

**問：我如何確定我的資料和私人資訊是安全的？**

答：若想深入了解我們為了確保您的資料和私人資訊之安全所採取的措施，包括服務等級協定 (SLA) 的相關資訊，請前往 [Office 365 信任中心](https://www.microsoft.com/trust-center)。

**問：是否有我應該知道的任何限制，例如郵件大小限制？**

答：是。如需 EOP 限制的詳細資訊，請參閱＜[Exchange Online Protection 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)＞。

**問： EOP 是否支援 PowerShell？**

答： 是的，可透過 PowerShell 取得完整的 EOP 功能。 如需詳細資訊，請參閱 [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)。
