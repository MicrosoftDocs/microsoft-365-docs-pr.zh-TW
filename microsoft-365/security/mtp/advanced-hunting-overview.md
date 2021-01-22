---
title: 概觀 - 進位搜尋
description: 了解 Microsoft 365 中的進階搜捕查詢，以及如何使用該功能主動找出您的網路中的威脅和弱點
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、自訂偵測、架構、kusto、microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932271"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>使用 Microsoft 365 Defender 中的進位搜尋主動搜尋威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。
>

進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。 您可以主動檢查您網路中的事件，以找出威脅標記和實體。 彈性的資料存取可讓系統針對已知和潛在威脅進行快速搜尋。
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。 這些規則會自動執行，以檢查並回應可疑的外泄活動、錯誤的電腦和其他發現。

此功能類似于 Microsoft [Defender for Endpoint 中的進位搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。 此功能可在 Microsoft 365 資訊安全中心使用，支援可檢查更多資料集的查詢：

- 適用於端點的 Microsoft Defender
- 適用於 Office 365 的 Microsoft Defender
- Microsoft Cloud App Security
- 適用於身分識別的 Microsoft Defender

若要使用進位搜尋[，請開啟 Microsoft 365 Defender。](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>開始使用進階搜捕

我們建議您執行數個步驟，以快速開始進一步搜尋。

| 學習目標 | 描述 | 資源 |
|--|--|--|
| **瞭解語言** | 進位搜尋是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。 執行您的第一個查詢來開始學習查詢語言。 | [查詢語言概觀](advanced-hunting-query-language.md) |
| **瞭解如何使用查詢結果** | 瞭解圖表以及您可以視圖或匯出結果的各種方式。 探索如何快速調整查詢、向下切入以取得更豐富的資訊，以及採取回應動作。 | - [使用查詢結果](advanced-hunting-query-results.md)<br>- [對查詢結果採取行動](advanced-hunting-take-action.md) |
| **了解結構描述** | 深入了解結構描述中的資料表和資料行。 瞭解在建構查詢時要在哪裡尋找資料。 | - [架構參照](advanced-hunting-schema-tables.md)<br>- [從 Microsoft Defender for Endpoint 轉換](advanced-hunting-migrate-from-mdatp.md) |
| **取得專家秘訣和範例** | 使用 Microsoft 專家的指南免費訓練。 探索涵蓋不同威脅搜捕案例的預先定義查詢集合。 | - [取得專家訓練](advanced-hunting-expert-training.md)<br>- [使用共用查詢](advanced-hunting-shared-queries.md)<br>- [前往搜尋](advanced-hunting-go-hunt.md)<br>- [跨裝置、電子郵件、應用程式和身分身分尋找威脅](advanced-hunting-query-emails-devices.md) |
| **優化查詢並處理錯誤** | 瞭解如何建立有效率且無錯誤的查詢。 | - [查詢最佳做法](advanced-hunting-best-practices.md)<br>- [處理錯誤](advanced-hunting-errors.md) |
| **建立自訂偵測規則** | 瞭解如何使用進位搜尋查詢來觸發警示，並自動採取回應動作。 | - [自訂偵測概觀](custom-detections-overview.md)<br>- [自訂偵測規則](custom-detection-rules.md) |

## <a name="get-access"></a>取得存取權
若要使用進位搜尋或其他 [Microsoft 365 Defender](microsoft-threat-protection.md) 功能，您需要在 Azure Active Directory 中擔任適當的角色。 此外，端點資料的存取權是由 Microsoft Defender for Endpoint (RBAC) 角色型存取控制決定。 [閱讀有關管理 Microsoft 365 Defender 存取權](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>資料更新和更新頻率
進位搜尋資料可以分類為兩種不同的類型，每個合併方式不同。

- **事件或活動資料**— 填入有關警示、安全性事件、系統事件和例行評定的資料表。 進位搜尋幾乎會立即在收集它們成功傳送至對應雲端服務的感應器之後接收這些資料。 例如，您可以查詢工作站或網網域控制站上健康感應器的事件資料，它們幾乎可在 Microsoft Defender for Endpoint 和 Microsoft Defender 的識別功能上使用後立即查詢。
- **實體資料**— 將資料表填入使用者和裝置相關資訊。 此資料來自相對靜態的資料來源和動態來源，例如 Active Directory 專案及事件記錄。 為了提供最新的資料，表格每 15 分鐘會以任何新資訊更新，並新增可能尚未完全填進的列。 每 24 小時會合並一次資料，以插入包含每個實體最新、最全面資料集的記錄。

## <a name="time-zone"></a>時區
進位搜尋的時間資訊為 UTC 時區。

## <a name="related-topics"></a>相關主題
- [了解查詢語言](advanced-hunting-query-language.md)
- [取得專家訓練](advanced-hunting-expert-training.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](custom-detections-overview.md)

