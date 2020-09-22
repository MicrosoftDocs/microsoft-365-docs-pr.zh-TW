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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 232d19cb0bcb6a2f91c1bdad15d842ec7396499c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201048"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Microsoft 威脅防護中的自動調查遵循的修復動作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護


## <a name="remediation-actions"></a>補救動作

在 Microsoft 威脅防護中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。 對裝置（也稱為端點）採取某些類型的修復動作。 對電子郵件內容採取其他修復動作。 在採取修正動作、核准或拒絕時，自動調查會完成。

下表摘要說明 Microsoft 威脅防護目前支援的修復動作： 

|裝置 (端點) 修正動作  |電子郵件補救動作  |
|---------|---------|
|-收集調查套件 <br/>-隔離裝置 (此動作可復原) <br/>-下架電腦 <br/>-發行程式碼執行 <br/>-從隔離區發行 <br/>-要求範例 <br/>-限制執行程式碼執行 (此巨集指令可復原)  <br/>-執行防病毒掃描 <br/>-停止和隔離      |-)  (時，封鎖 URL<br/>-虛刪除電子郵件訊息或聚簇<br/>-隔離電子郵件<br/>-隔離電子郵件附件<br/>-關閉外部郵件轉發          |

您可以在「 [行動中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)」查看修正動作（不論是待核准或已完成）。

## <a name="remediation-actions-follow-automated-investigations"></a>修正動作遵循自動調查

當自動調查完成時，所涉及的每一項證據都會達到序判定。 根據判定，修正動作的識別。 在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。 這完全取決於如何 [設定自動調查和回應](mtp-configure-auto-investigation-response.md)。

下表列出可能的裁決和結果：

|裁決    |範圍    |結果|
|------|------|------|
|惡意    |裝置 (端點)    |如果您組織的 [裝置群組](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 會自動設定為 **完整修正威脅** ，便會自動採取修正動作 () |
|惡意    |電子郵件內容 (URL 或附件) | 建議的修正動作待核准|
|可疑    |裝置或電子郵件內容 |建議的修正動作待核准|
|找不到威脅    |裝置或電子郵件內容    |不需要修正動作|

> [!IMPORTANT]
> 是否自動採取修復動作，也取決於特定設定，例如組織的裝置群組原則。 若要深入瞭解，請參閱下列文章：
> - [在 Microsoft 威脅防護中設定自動化調查和回應功能](mtp-configure-auto-investigation-response.md)
> - [如何在裝置上修正威脅](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>後續步驟

- [造訪重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [核准或拒絕擱置動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [在自動化調查和回應功能中處理誤報/負片](mtp-autoir-report-false-positives-negatives.md)
