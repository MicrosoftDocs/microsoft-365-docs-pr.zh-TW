---
title: Microsoft 365 Defender 中的補救動作
description: 取得 Microsoft 365 Defender 中遵循自動化調查的補救動作概觀
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932847"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的補救動作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

## <a name="remediation-actions"></a>補救動作

在 Microsoft 365 Defender 的自動化調查期間和之後，會針對惡意或可疑專案識別補救動作。 某些類型的補救動作會針對裝置進行，也稱為端點。 對電子郵件內容採取其他補救動作。 在採取、核准或拒絕補救動作之後，自動化調查即完成。

> [!IMPORTANT]
> 要自動採取補救動作，或僅根據核准才進行修復動作，取決於某些設定，例如自動化層級的方式。 若要深入瞭解，請參閱下列文章：
> - [在 Microsoft 365 Defender 中設定您的自動化調查及回應功能](mtp-configure-auto-investigation-response.md)
> - [如何在裝置上補救威脅](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [電子郵件和共同處理內容上的威脅&補救動作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

下表摘要列出 Microsoft 365 Defender 目前支援的補救動作： 

|裝置 (修復) 動作  |電子郵件補救動作  |
|---------|---------|
|- 收集調查套件 <br/>- 隔離裝置 (此動作可以復原) <br/>- Offboard 電腦 <br/>- 發行代碼執行 <br/>- 從隔離中釋出 <br/>- 要求範例 <br/>- 限制程式碼 (此動作可以復原)  <br/>- 執行防毒軟體掃描 <br/>- 停止和隔離      |- 封鎖 (按一下滑鼠的網址) <br/>- 柔式刪除電子郵件訊息或郵件組<br/>- 隔離電子郵件<br/>- 隔離電子郵件附件<br/>- 關閉外部郵件轉寄功能          |

您可以在控制中心中查看待核准或已完成的補救 [動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。

## <a name="remediation-actions-that-follow-automated-investigations"></a>追蹤自動化調查的補救動作

完成自動化調查時，會針對每一個涉及的證明進行調查。 根據補救方式，識別補救動作。 在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。 這完全取決於您如何進行 [自動化調查與回應](mtp-configure-auto-investigation-response.md)。

下表列出可能的裁決和結果：

| 裁決    | 範圍    | 結果|
|------|------|------|
| 惡意    | 裝置 (端點)    | 假設貴組織的裝置 (設定為完整 **-** 自動修復威脅 [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)，就會自動採取補救) |
| 惡意    | 電子郵件內容 (URL 或附件) | 建議的修正動作待核准|
| 可疑    | 裝置或電子郵件內容 | 建議的修正動作待核准|
| 找不到任何威脅    | 裝置或電子郵件內容    | 不需要修正動作|


## <a name="remediation-actions-that-are-taken-manually"></a>手動採取的補救動作

除了遵循自動化調查的補救動作，您的安全性作業小組可以手動採取特定的補救動作。 這些動作包括下列動作：

- 手動裝置動作，例如裝置隔離或檔案隔離。
- 手動電子郵件動作，例如手動刪除電子郵件訊息。 
- [裝置或](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) 電子郵件上的進一步搜尋動作。
- [在](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 電子郵件內容上執行 Explorer 動作，例如將電子郵件移動至垃圾郵件、使用柔式刪除電子郵件，或硬式刪除電子郵件。
- 手動 [即時回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 動作，例如刪除檔案、停止程式，以及移除已排程的工作。
- 使用 Microsoft [Defender 端點](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)API 執行即時回應動作，例如隔離裝置、執行防毒掃描，以及取得檔案相關資訊。 

## <a name="next-steps"></a>後續步驟

- [造訪重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [核准或拒絕擱置動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [在自動化調查與回應功能中處理誤對/負數](mtp-autoir-report-false-positives-negatives.md)
