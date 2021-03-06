---
title: 修正可能的郵件迴圈深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全 & 規範中心內郵件流程儀表板中的 [修正可能的郵件迴圈洞察力]，識別並修正其組織中的郵件迴圈。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204561"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>修正安全性 & 規範中心內可能的郵件迴圈洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

郵件迴圈不正確，原因如下：

- 它們會浪費系統資源。
- 它們會消耗您組織的郵件磁片區配額。
- 它們會傳送令人困惑的未傳遞回報 (也稱為 NDRs 或退回郵件) 給原始郵件寄件者。

在您的組織中偵測到郵件迴圈時，在 [安全性 & 合規性中心](https://protection.office.com)的 [[郵件流程儀表板](mail-flow-insights-v2.md)] 中，**建議** 的郵件流程儀表板區域會通知您，以 **修正可能的郵件迴圈**。

這種洞察力只會在偵測到條件之後才會出現 (如果您沒有任何郵件迴圈，您就不會看到) 的洞察力。

![修正郵件流程儀表板中為您推薦的郵件流程規則的速度](../../media/mfi-fix-possible-mail-loop.png)

當您按一下小工具上的 [ **查看詳細資料** ] 時，會出現一個快顯視窗，包含詳細資訊：

- **網域**
- **郵件數目**：您可以按一下 [ **View sample messages** ]，以查看受環路影響之郵件範例的 [郵件追蹤](message-trace-scc.md) 結果。
- **網欄位型別**"，例如「授權」或「非授權」。
- **MX 記錄**：主機 (的 **郵件伺服器**) 和網域的 MX 記錄 **優先順序** 值。
- **迴圈原因** 和 **解決方法**：我們會找出最常見的郵件迴圈案例，並提供建議的動作來修正此迴圈。

![在 [修正可能的郵件迴圈真知灼見] 上按一下 [查看詳細資料] 後出現的詳細資料浮出](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>另請參閱

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
