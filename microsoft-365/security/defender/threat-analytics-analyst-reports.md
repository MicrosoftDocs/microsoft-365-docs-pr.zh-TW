---
title: 瞭解威脅分析中的分析報告區段
ms.reviewer: ''
description: 深入瞭解每個威脅分析報告的分析報告區段。 瞭解它如何提供威脅、緩解、偵測、高級搜尋查詢等相關資訊。
keywords: 分析報告、威脅分析、偵測、高級搜尋查詢、緩解
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f916137be71dffeaed7e3718286032a17c9f8e04
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498474"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>瞭解威脅分析中的分析報告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

每個 [威脅分析報告](threat-analytics.md) 都包含動態區段，以及一個稱為「 _分析員報告_」的完整寫入章節。 若要存取此區段，開啟有關追蹤威脅的報告，然後選取 [ **分析報告** ] 索引標籤。

![威脅分析報告的分析報告區段影像](../../media/threat-analytics/ta_analystreport_mtp.png)

_威脅分析報告的分析報告區段_

## <a name="scan-the-analyst-report"></a>掃描分析報告 
分析報告的每一節都是用來提供可行動的資訊。 當報表變化時，大部分的報表會包含下表所述的區段。

| 報表區段 | 描述 |
|--|--|
| 摘要 | 威脅的概述，包括初次看到的時間、其動機、明確的事件、主要目標，以及不同的工具和技術。 您可以使用此資訊來進一步評估如何在您的行業、地理位置和網路內容中排定威脅的優先順序。 |
| 分析 | 威脅的技術資訊，包括攻擊的詳細資料，以及攻擊者可能使用新技術或攻擊面的方式 | 
| MITRE ATT&所觀察到的 CK 技術 | 觀察到的技巧如何對應至 [MITRE ATT&CK 攻擊架構](https://attack.mitre.org/) | 
| [減輕方式](#apply-additional-mitigations) | 可停止或協助降低威脅影響的建議。 本節也包含不會在威脅分析報告中動態追蹤的緩解。 |
| [偵測詳細資料](#understand-how-each-threat-can-be-detected) | Microsoft 安全性解決方案所提供的特定及一般偵測，可以呈現與威脅相關聯的活動或元件。 | 
| [進階搜捕](#find-subtle-threat-artifacts-using-advanced-hunting) | 以主動識別可能威脅活動的[高級搜尋查詢](advanced-hunting-overview.md)。 大部分的查詢都是為了補充偵測，特別是找出可能惡意的元件或無法動態評估以成為惡意的行為。 | 
| 參考 | 在建立報告期間，由分析員參考的 Microsoft 和協力廠商出版物。 威脅分析內容是以 Microsoft 研究員所驗證的資料為基礎。 公開提供的資訊，協力廠商來源會明確識別。 | 
| 變更記錄 | 報告發布的時間，以及對報表進行重大變更的時間。 |

## <a name="apply-additional-mitigations"></a>套用其他緩解
威脅分析會動態追蹤 [安全性更新和安全設定的狀態](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。 在 [ **緩解** ] 索引標籤中，此資訊是以圖表和表格的形式提供。

除了這些追蹤的緩解措施之外，「分析員」報告也會討論 _未_ 動態監視的緩解。 以下是一些不會動態追蹤之重要緩解事項的範例：

- 封鎖使用 _.lnk_ 附件或其他可疑檔案類型的電子郵件
- 隨機化本機系統管理員密碼
- 教育使用者有關網路釣魚電子郵件和其他威脅媒介的教育
- 開啟特定 [攻擊面減少規則](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

雖然您可以使用 [ **緩解** ] 索引標籤，針對威脅評估安全性狀況，但這些建議可讓您採取額外步驟，以提升安全性狀況。 請仔細閱讀分析報告中的所有緩解指導方針，並盡可能加以套用。

## <a name="understand-how-each-threat-can-be-detected"></a>瞭解每個威脅的偵測方式
分析報告也會提供 Microsoft Defender 針對端點防病毒和 _端點偵測_ (EDR) 功能的偵測。

### <a name="antivirus-detections"></a>防病毒偵測
在[Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)開啟的裝置上可以使用這些偵測。 當這些偵測發生在已架至 Microsoft Defender for Endpoint 的裝置上時，也會觸發報告中的圖表，使其變亮。

>[!NOTE]
>分析員報告也會列出 **一般性** 偵測，除了追蹤威脅特有的元件或行為之外，還可以識別範圍廣泛的威脅。 這些一般偵測不會反映在圖表中。

### <a name="endpoint-detection-and-response-edr-alerts"></a> (EDR) 警示的端點偵測和回應
[架至 Microsoft Defender for Endpoint 的裝置](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)會引發 EDR 警示。 這些警示通常會依賴 Microsoft Defender for Endpoint 感應器所收集的安全性信號，以及可充當功能強大之信號來源的其他端點功能（例如防毒軟體、網路保護、防篡改保護）。

如防病毒偵測清單，有些 EDR 警示是設計為一般標記可能不會與追蹤威脅相關聯的可疑行為。 在這種情況下，報告會將警示明確識別為「一般」，而不會影響報表中的任何圖表。

### <a name="email-related-detections-and-mitigations"></a>電子郵件相關的偵測和緩解
來自 microsoft defender for Office 365 的電子郵件相關偵測和緩解功能包含在分析報告中，除了 microsoft defender for endpoint 中已提供的端點資料之外。 

避免電子郵件嘗試資訊可讓您深入瞭解您的組織是否為分析員報告中威脅 tackled 的目標，即使在傳送或傳送至 [垃圾郵件] 資料夾之前已經有效封鎖此攻擊。

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>使用高級搜尋尋找細微威脅工件
雖然偵測可讓您自動識別及停止追蹤威脅，但許多攻擊活動都會留下需要其他檢查的細微追蹤。 有些攻擊動作會表現出也可以是正常的行為，因此會以動態方式偵測這些行為，從而導致運作雜訊或甚至是誤報。

「[高級搜尋](advanced-hunting-overview.md)」是以 Kusto 查詢語言為基礎的查詢介面，可簡化威脅活動的細微標記。 它也可讓您顯示內容資訊，並確認指示器是否連接至威脅。

分析報告中的高級搜尋查詢已由 Microsoft 分析員經，可供您在 [ [高級搜尋查詢編輯器](https://security.microsoft.com/advanced-hunting)] 中執行。 您也可以使用查詢來建立 [自訂偵測規則](custom-detection-rules.md) ，以觸發警示以供未來的相符。


>[!NOTE]
> 在 [Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)中也可以使用威脅分析。 不過，它沒有 microsoft defender Office 和 Microsoft 365 Defender 威脅分析的 microsoft defender 的資料整合。


## <a name="related-topics"></a>相關主題
- [威脅分析概觀](threat-analytics.md)
- [使用高級搜尋主動尋找威脅](advanced-hunting-overview.md) 
- [自訂偵測規則](custom-detection-rules.md)