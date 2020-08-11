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
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8dca8cac2c66147975f71c86b91aee7b36c92cf9
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608330"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅

**適用於：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。 您可以主動檢查您網路中的事件，以找出相關的指標和實體。 可靈活存取資料有助於不受限制地同時搜捕已知和潛在的威脅。
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。 自動執行這些規則，以檢查各種活動和系統狀態，包括可疑的破壞活動和錯誤配置的電腦。

此功能與[Microsoft DEFENDER atp 中的高級搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)類似，不同之處在于，「microsoft 365 安全性中心」中的「高級搜尋」支援查詢可查看各種工作區中的資料，包括來自 MICROSOFT Defender ATP、OFFICE 365 ATP、Microsoft Cloud App Security 和 Azure atp 的資料。 若要使用進階搜捕，請[開啟 Microsoft 威脅防護](mtp-enable.md)。

## <a name="get-started-with-advanced-hunting"></a>開始使用進階搜捕

建議您透過數個步驟來利用進階搜捕快速啟動並執行。

| 學習目標 | 描述 | 資源 |
|--|--|--|
| **了解語言** | 「高級搜尋」是以[Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。 執行您的第一個查詢來開始學習查詢語言。 | [查詢語言概觀](advanced-hunting-query-language.md) |
| **瞭解如何使用查詢結果** | 深入瞭解圖表和您可以查看或匯出結果的各種方式。 探索您如何快速調整查詢、深入查看以取得更豐富的資訊，以及採取回應動作。 | - [使用查詢結果](advanced-hunting-query-results.md)<br>- [對查詢結果採取動作](advanced-hunting-take-action.md) |
| **了解結構描述** | 深入了解結構描述中的資料表和資料行。 這可協助您決定要在何處尋找資料，以及如何建構查詢。 | [結構描述參考](advanced-hunting-schema-tables.md) |
| **運用預先定義的查詢** | 探索涵蓋不同威脅搜捕案例的預先定義查詢集合。 | - [使用共用查詢](advanced-hunting-shared-queries.md)<br>- [開始搜尋](advanced-hunting-go-hunt.md) |
| **最佳化查詢** | 了解如何建立可結合來自電子郵件和裝置資料的高效查詢。 | - [查詢最佳作法](advanced-hunting-shared-queries.md) <br>- [跨裝置和電子郵件進行搜尋](advanced-hunting-best-practices.md) |
| **建立自訂偵測規則** | 瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動套用回應動作。 | - [自訂偵測簡介](custom-detections-overview.md)<br>- [自訂偵測規則](custom-detection-rules.md) |

## <a name="get-access"></a>取得存取權
若要使用高級搜尋或其他[Microsoft 威脅防護](microsoft-threat-protection.md)功能，您必須在 Azure AD 中獲指派適當的角色。 請注意，在 Microsoft Defender ATP 中，以角色為基礎的存取控制設定會影響對端點資料的存取。 [閱讀管理 Microsoft 威脅防護存取的相關資訊](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>資料新鮮度和更新頻率
「高級搜尋」資料可以分類成兩種不同的類型，每個不同的合併。

- **事件或活動資料**--填入有關警示、安全性事件、系統事件及例行評估的表格。 [！注意] 高級搜尋幾乎會在收集成功的感應器成功傳送至對應的雲端服務之後立即接收這類資料。 例如，您可以在工作站或網域控制站上的狀況良好感應器上開始查詢事件資料，使其能在 Microsoft Defender ATP 和 Azure ATP 上的使用中立即開始。
- **實體資料**—使用使用者和裝置的整合式資訊來填入資料表。 此資料來自相對靜態資料來源（例如 Active Directory 專案）和動態來源，例如事件記錄。 若要提供新的資料，每15分鐘更新一次表格中的任何新資訊，新增可能不會填滿的資料列。 每24小時都會合並資料，以插入記錄，其中包含每個實體的最新、最全面的資料集。

## <a name="related-topics"></a>相關主題
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [對查詢結果採取動作](advanced-hunting-take-action.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](custom-detections-overview.md)
