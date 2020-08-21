---
title: 修正緩慢的郵件流程規則深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用「修正慢速」郵件流程規則深入瞭解安全性 & 合規性中心，識別並修正低效或中斷的郵件流程規則， (也稱為其組織中) 的傳輸規則。
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826878"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>修正郵件流程規則安全 & 規範中心的洞察力

電子郵件流程規則（也稱為傳輸規則) ）可能會導致組織的郵件流程延期 (。 這種洞察力可報告影響組織郵件流程的郵件流程規則。 這些規則類型的範例包括：

- 使用的條件 **是** 大型群組的成員。
- 使用複雜正則運算式 (RegEx) 模式比對的條件。
- 在附件中使用內容檢查的條件。

**修正慢速郵件流程規則**會深入瞭解安全性 & 合規性中心的 [[郵件流程] 儀表板](mail-flow-insights-v2.md)的 [**建議**] 區域，當郵件流程規則耗時過長時通知您。 這種洞察力只會在偵測到條件之後才會出現 (如果您沒有任何郵件迴圈，您就不會看到) 的洞察力。

您可以使用此通知來協助您識別及微調郵件流程規則，以協助減少郵件流程延遲。

![修正郵件流程儀表板中為您推薦的郵件流程規則的速度](../../media/mfi-fix-slow-mail-flow-rules.png)

當您按一下小工具上的 [ **查看詳細資料** ] 時，會出現一個快顯視窗，包含詳細資訊：

- **規則**：您可以將游標置於摘要上方，以查看規則的所有條件、例外狀況及動作。 您可以按一下摘要，在 Exchange 系統管理中心 (EAC) 中編輯規則。
- **評估的郵件數目**：您可以按一下 [ **View sample messages** ]，以查看受規則影響之郵件範例的 [郵件追蹤](message-trace-scc.md) 結果。
- **每封郵件所用的平均時間**
- **郵件所用的中間時間**：將上半部分的時間資料與下半部的中間值分隔。

![在修正慢速郵件流程規則真知灼見上，按一下 [查看詳細資料] 後出現的詳細資料浮出控制項](../../media/mfi-fix-slow-mail-flow-rules-details.png)

如需 Exchange Online 中郵件流程規則的條件和例外狀況的相關資訊，請參閱 [郵件流程規則條件和例外狀況) 在 Exchange online 中的 (謂語](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

## <a name="related-topics"></a>相關主題

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
