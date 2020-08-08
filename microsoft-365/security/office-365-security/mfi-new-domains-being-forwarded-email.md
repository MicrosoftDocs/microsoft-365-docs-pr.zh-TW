---
title: 轉寄電子郵件的新網域深入瞭解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以瞭解如何使用現代 Exchange 系統管理中心中已轉寄的電子郵件功能，調查組織中的使用者將郵件轉寄給已永不轉寄的外部網域。
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578368"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心轉寄電子郵件的新網域

雖然您可以將電子郵件轉寄至特定網域中的外部收件者，但在組織中的使用者突然開始將郵件轉送至外部網域，而組織中的使用者卻沒有任何人轉寄郵件給這些網域，但在 (新的網域) 之前，這是可疑的業務原因。 這種情況可能表示使用者帳戶遭到破壞。 如果您懷疑帳戶已遭破壞，請參閱[回應遭到破壞的電子郵件帳戶](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)。

當您組織中的使用者將郵件轉送至新網域時，**正轉送的新網域**會告訴您。

這種洞察力只會在偵測到問題時出現，而且會出現在 [[轉接回報報告](view-mail-flow-reports.md#forwarding-report)] 頁面上。

![轉寄電子郵件的新網域深入瞭解](../../media/mfi-new-domains-being-forwarded.png)

當您按一下該小工具時，會出現一個快顯視窗，您可以在其中找到有關轉寄郵件的詳細資訊，包括回[轉送報告](view-mail-flow-reports.md#forwarding-report)的連結。

![在按一下要轉寄電子郵件的新網域後，出現的詳細資料浮出控制項](../../media/mfi-new-domains-being-forwarded-details.png)

您也可以在 [ (**報表**儀表板] 或 [) ] 的 [**熱門洞察力 & 建議**] 區域中按一下 [**全部查看**] 之後，取得此詳細資料頁面 \> **Dashboard** <https://protection.office.com/insightdashboard> 。

若要防止自動將郵件轉送到外部網域，請設定部分或所有外部網域的遠端網域。 如需詳細資訊，請參閱[管理 Exchange Online 中的遠端網域](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>相關主題

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱[Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。