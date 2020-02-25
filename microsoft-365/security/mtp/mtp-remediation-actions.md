---
title: 下列 Microsoft 威脅防護中的自動化的調查的修復動作
description: 取得遵循 Microsoft 威脅防護中的自動化的調查的補救動作的概觀
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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266049"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>下列 Microsoft 威脅防護中的自動化的調查的修復動作

適用於：****
- Microsoft 威脅防護


## <a name="remediation-actions"></a>補救動作

期間和之後自動進行調查，Microsoft 威脅防護中，修復動作會被識別為惡意或可疑的項目。 某些類型的補救動作所採取的裝置，也稱為端點。 在 [電子郵件內容上採取其他修復動作。 自動化調查完成後採取、 核准或拒絕修復動作。

下表摘要說明目前支援 Microsoft 威脅防護中的補救動作： 

|裝置 （端點） 修復動作  |電子郵件補救動作  |
|---------|---------|
|隔離的檔案<br/>移除登錄機碼<br/>刪除處理序 <br/>停止服務 <br/>停用驅動程式 <br/>移除排程工作      |虛刪除電子郵件訊息或群集<br/>封鎖 URL (點擊時)<br/>關閉外部郵件轉寄          |

修復動作，不論他們正在等待核准或已完成，可以檢視在[重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。

## <a name="verdicts-and-outcomes-following-automated-investigations"></a>結果和下列自動化的調查的結果

當自動調查完成後，會對所涉及的每個證據做出裁決，並確定修正動作。 在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。 下表列出可能的裁決和結果：

|裁決    |範圍   |結果|
|------|------|------|
|惡意  |裝置 (端點)    |自動採取修正動作|
|惡意  |電子郵件內容 (URL 或附件) | 建議的修正動作待核准|
|可疑 |裝置或電子郵件內容 |建議的修正動作待核准|
|無害  |裝置或電子郵件內容   |不需要修正動作|

[在控制中心檢閱待核准的動作](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> 如果您認為某個項目已未接或錯誤偵測到的自動化的調查和 Microsoft 威脅防護中的回應功能，讓我們知道 ！ [報表 positive/誤判](mtp-autoir-report-false-positives-negatives.md)。

## <a name="next-steps"></a>後續步驟

- [核准或拒絕動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [深入了解重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
