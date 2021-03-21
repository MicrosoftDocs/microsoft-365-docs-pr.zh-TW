---
title: Microsoft 365 Defender 中的修正動作
description: 深入瞭解 Microsoft 365 Defender 中遵循自動調查的修復動作
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928625"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的修正動作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

## <a name="remediation-actions"></a>補救動作

在 Microsoft 365 Defender 中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。 對裝置（也稱為端點）採取某些類型的修復動作。 對電子郵件內容採取其他修復動作。 在採取修正動作、核准或拒絕時，自動調查會完成。

> [!IMPORTANT]
> 是否自動採取修復動作，也取決於特定設定，例如自動化程度。 若要深入瞭解，請參閱下列文章：
> - [在 Microsoft 365 Defender 中設定您的自動化調查和回應功能](mtp-configure-auto-investigation-response.md)
> - [如何在裝置上修正威脅](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [電子郵件 & 共同作業內容的威脅和修正動作](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

下表摘要說明 Microsoft 365 Defender 目前支援的修復動作： 

|裝置 (端點) 修正動作  |電子郵件補救動作  |
|:---------|:---------|
|-收集調查套件 <br/>-隔離裝置 (此動作可復原) <br/>-下架電腦 <br/>-發行程式碼執行 <br/>-從隔離區發行 <br/>-要求範例 <br/>-限制執行程式碼執行 (此巨集指令可復原)  <br/>-執行防病毒掃描 <br/>-停止和隔離      |-)  (時，封鎖 URL<br/>-虛刪除電子郵件訊息或聚簇<br/>-隔離電子郵件<br/>-隔離電子郵件附件<br/>-關閉外部郵件轉發          |

您可以在「 [行動中心](./mtp-action-center.md)」查看修正動作（不論是待核准或已完成）。

## <a name="remediation-actions-that-follow-automated-investigations"></a>遵循自動調查的修復動作

當自動調查完成時，所涉及的每一項證據都會達到序判定。 根據判定，修正動作的識別。 在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。 這完全取決於如何 [設定自動調查和回應](mtp-configure-auto-investigation-response.md)。

下表列出可能的裁決和結果：

| 裁決    | 範圍    | 結果|
|------|------|------|
| 惡意    | 裝置 (端點)    | 如果您組織的 [裝置群組](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 會自動設定為 **完整修正威脅** ，便會自動採取修正動作 () |
| 惡意    | 電子郵件內容 (URL 或附件) | 建議的修正動作待核准|
| 可疑    | 裝置或電子郵件內容 | 建議的修正動作待核准|
| 找不到威脅    | 裝置或電子郵件內容    | 不需要修正動作|


## <a name="remediation-actions-that-are-taken-manually"></a>手動採取的修正動作

除了遵循自動調查的修復動作之外，您的安全性作業小組也可以手動採取某些修正動作。 包括下列動作：

- 手動裝置動作，例如裝置隔離或檔隔離。
- 手動電子郵件動作，例如虛刪除的電子郵件訊息。 
- 裝置或電子郵件上的[高級搜尋](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)動作。
- [Explorer](../office-365-security/threat-explorer.md) 對電子郵件內容的動作，例如將電子郵件移至垃圾郵件、虛刪除的電子郵件或實刪除的電子郵件。
- 手動 [即時回應](/windows/security/threat-protection/microsoft-defender-atp/live-response) 動作，例如刪除檔案、停止程式及移除排程的任務。
- [Microsoft Defender For Endpoint APIs](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)的即時回應動作，例如隔離裝置、執行防病毒掃描，以及取得檔案的相關資訊。 

## <a name="next-steps"></a>後續步驟

- [造訪重要訊息中心](./mtp-action-center.md)
- [查看和管理修正動作](./mtp-autoir-actions.md)
- [在自動化調查和回應功能中處理誤報/負片](mtp-autoir-report-false-positives-negatives.md)