---
title: 轉寄的新網域電子郵件深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以瞭解如何使用「安全性 & 規範中心」中郵件流程儀表板中的新網域，以調查他們的使用者是否要將郵件轉寄給已永不轉寄的外部網域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f3a5f125a045176f152ccd079ebe7f7e40bc39f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203455"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心轉寄電子郵件的新網域

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

將電子郵件轉寄給特定網域中的外部收件者，有一些有效的商業原因。 不過，當組織中的使用者突然開始將郵件轉送至一個網域，而您的組織中沒有任何人曾經轉送郵件給 (新網域) 時，這是可疑的。

這種情況可能表示使用者帳戶遭到破壞。 如果您懷疑帳戶已遭破壞，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。

當您組織中的使用者將郵件轉寄給新網域時，在 [安全性 & 合規性中心](https://protection.office.com)**轉寄的新網域** 會通知您。

這種洞察力只會在偵測到問題時出現，而且會出現在 [ [轉接回報報告](view-mail-flow-reports.md#forwarding-report) ] 頁面上。

![轉寄的新網域電子郵件深入解析](../../media/mfi-new-domains-being-forwarded.png)

當您按一下該小工具時，會出現一個快顯視窗，您可以在其中找到有關轉寄郵件的詳細資訊，包括回 [轉送報告](view-mail-flow-reports.md#forwarding-report)的連結。

![在按一下要轉寄電子郵件的新網域後，出現的詳細資料浮出控制項](../../media/mfi-new-domains-being-forwarded-details.png)

您也可以在 [ (**報表** 儀表板] 或 [) ] 的 [**熱門洞察力 & 建議**] 區域中按一下 [**全部查看**] 之後，取得此詳細資料頁面 \>  <https://protection.office.com/insightdashboard> 。

若要防止自動將郵件轉送到外部網域，請設定部分或所有外部網域的遠端網域。 如需詳細資訊，請參閱 [管理 Exchange Online 中的遠端網域](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>相關主題

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。