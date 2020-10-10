---
title: 概覽-高級搜尋
description: 了解 Microsoft 365 中的進階搜捕查詢，以及如何使用該功能主動找出您的網路中的威脅和弱點
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，schema，kusto，microsoft 365，Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d231e1d2f05a2ff7c5abc86a74c6301043268f6e
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412667"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 威脅防護

進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。 您可以主動檢查您網路中的事件，以找出威脅指示器和實體。 對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。 這些規則會自動執行，以檢查是否有可疑的破壞活動、錯誤設定的機器及其他發現的回應。

這項功能類似于 [Microsoft DEFENDER ATP 中的高級搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。 可在 Microsoft 365 的安全性中心使用此功能，可支援從下列專案中檢查更廣泛資料集的查詢：

- Microsoft Defender 進階威脅防護
- Office 365 進階威脅防護
- Microsoft Cloud App Security
- Azure 進階威脅防護

若要使用進階搜捕，請[開啟 Microsoft 威脅防護](mtp-enable.md)。

## <a name="get-started-with-advanced-hunting"></a>開始使用進階搜捕

我們建議您逐步完成一些步驟，快速開始使用高級搜尋。

| 學習目標 | 描述 | 資源 |
|--|--|--|
| **瞭解語言** | 「高級搜尋」是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。 執行您的第一個查詢來開始學習查詢語言。 | [查詢語言概觀](advanced-hunting-query-language.md) |
| **瞭解如何使用查詢結果** | 深入瞭解圖表和您可以查看或匯出結果的各種方式。 探索您如何快速調整查詢、深入查看以取得更豐富的資訊，以及採取回應動作。 | - [使用查詢結果](advanced-hunting-query-results.md)<br>- [對查詢結果採取動作](advanced-hunting-take-action.md) |
| **了解結構描述** | 深入了解結構描述中的資料表和資料行。 瞭解在建立查詢時要尋找資料的位置。 | - [架構參考](advanced-hunting-schema-tables.md)<br>- [從 Microsoft Defender ATP 轉換](advanced-hunting-migrate-from-mdatp.md) |
| **取得專家秘訣和範例** | 透過 Microsoft 專家的指南訓練。 探索涵蓋不同威脅搜捕案例的預先定義查詢集合。 | - [取得專家訓練](advanced-hunting-expert-training.md)<br>- [使用共用查詢](advanced-hunting-shared-queries.md)<br>- [開始搜尋](advanced-hunting-go-hunt.md)<br>- [尋找跨裝置、電子郵件、應用程式和身分識別的威脅](advanced-hunting-query-emails-devices.md) |
| **優化查詢並處理錯誤** | 瞭解如何建立高效且無錯誤的查詢。 | - [查詢最佳作法](advanced-hunting-best-practices.md)<br>- [處理錯誤](advanced-hunting-errors.md) |
| **建立自訂偵測規則** | 瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動採取回應動作。 | - [自訂偵測簡介](custom-detections-overview.md)<br>- [自訂偵測規則](custom-detection-rules.md) |

## <a name="get-access"></a>取得存取權
若要使用高級搜尋或其他 [Microsoft 威脅防護](microsoft-threat-protection.md) 功能，您在 Azure Active Directory 中需要有適當的角色。 此外，您可以使用 Microsoft Defender ATP 中的角色型存取控制 (RBAC) 設定所決定的端點資料存取。 [閱讀管理 Microsoft 威脅防護存取的相關資訊](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>資料新鮮度和更新頻率
「高級搜尋」資料可以分類成兩種不同的類型，每個不同的合併。

- **事件或活動資料**--填入有關警示、安全性事件、系統事件及例行評估的表格。 [！注意] 高級搜尋幾乎會在收集成功的感應器成功傳送至對應的雲端服務之後立即接收這類資料。 例如，您可以在工作站或網域控制站上的狀況良好感應器上查詢事件資料，使其在 Microsoft Defender ATP 和 Azure ATP 上可用之後幾乎可以立即查詢。
- **實體資料**—以使用者和裝置的相關資訊填入資料表。 此資料來自相對靜態資料來源和動態來源，例如 Active Directory 專案和事件記錄。 若要提供全新的資料，每隔15分鐘更新一次所有新資訊的資料表，新增可能不會填滿的資料列。 每24小時都會合並資料，以插入記錄，其中包含每個實體的最新、最全面的資料集。

## <a name="time-zone"></a>時區
「高級搜尋」中的時間資訊是在 UTC 時區。

## <a name="related-topics"></a>相關主題
- [了解查詢語言](advanced-hunting-query-language.md)
- [取得專家訓練](advanced-hunting-expert-training.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](custom-detections-overview.md)

