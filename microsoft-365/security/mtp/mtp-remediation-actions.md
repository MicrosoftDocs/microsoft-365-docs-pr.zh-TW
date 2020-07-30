---
title: Microsoft 威脅防護中的自動調查遵循的修復動作
description: 深入瞭解在 Microsoft 威脅防護中遵循自動調查的修復動作
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502934"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Microsoft 威脅防護中的自動調查遵循的修復動作

適用於：****
- Microsoft 威脅防護


## <a name="remediation-actions"></a>補救動作

在 Microsoft 威脅防護中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。 對裝置（也稱為端點）採取某些類型的修復動作。 對電子郵件內容採取其他修復動作。 在採取修正動作、核准或拒絕時，自動調查會完成。

下表摘要說明 Microsoft 威脅防護目前支援的修復動作： 

|裝置（端點）修復動作  |電子郵件補救動作  |
|---------|---------|
|-收集調查套件 <br/>隔離裝置（可以復原此動作）<br/>-下架電腦 <br/>-發行程式碼執行 <br/>-從隔離區發行 <br/>-要求範例 <br/>-限制執行程式碼（可以復原此動作） <br/>-執行防病毒掃描 <br/>-停止和隔離      |-封鎖 URL （按一下時間）<br/>-虛刪除電子郵件訊息或聚簇<br/>-隔離電子郵件<br/>-隔離電子郵件附件<br/>-關閉外部郵件轉發          |

修正動作（不論是待核准或已完成），都可以在「[行動中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)」中查看。

## <a name="remediation-actions-follow-automated-investigations"></a>修正動作遵循自動調查

當自動調查完成後，會對所涉及的每個證據做出裁決，並確定修正動作。 在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。 下表列出可能的裁決和結果：

|裁決    |範圍    |結果|
|------|------|------|
|惡意    |裝置 (端點)    |自動採取修正動作|
|惡意    |電子郵件內容 (URL 或附件) | 建議的修正動作待核准|
|可疑    |裝置或電子郵件內容 |建議的修正動作待核准|
|找不到威脅    |裝置或電子郵件內容    |不需要修正動作|

[在控制中心檢閱待核准的動作](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> 如果您認為 Microsoft 威脅防護中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請告訴我們！ [報告誤報/負片](mtp-autoir-report-false-positives-negatives.md)。

## <a name="next-steps"></a>後續步驟

- [核准或拒絕動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [深入了解重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
