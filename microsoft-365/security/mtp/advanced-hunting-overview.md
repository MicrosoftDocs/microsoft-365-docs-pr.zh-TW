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
ms.openlocfilehash: c4b5d58a006591da23d37aaeccf72cfccc6d1c43
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033971"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅

**適用於：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。 您可以主動檢查您網路中的事件，以找出相關的指標和實體。 可靈活存取資料有助於不受限制地同時搜捕已知和潛在的威脅。

您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。 這些規則會自動執行，以檢查和回應各種事件和系統狀態，包括可疑的入侵活動和設定不當的電腦。

在 Microsoft 365 的安全性中心，「高級搜尋」支援查詢可查看各種工作區中的資料，包括來自 Microsoft Defender ATP 的裝置、電子郵件、應用程式和身分識別的資料、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP。 若要使用進階搜捕，請[開啟 Microsoft 威脅防護](mtp-enable.md)。

## <a name="get-started-with-advanced-hunting"></a>開始使用進階搜捕

建議您透過數個步驟來利用進階搜捕快速啟動並執行。

| 學習目標 | 描述 | 資源 |
|--|--|--|
| **了解語言** | 進階搜捕是基於 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)，支援相同的語法和運算子。 執行您的第一個查詢來開始學習查詢語言。 | [查詢語言概觀](advanced-hunting-query-language.md) |
| **瞭解如何使用查詢結果** | 深入瞭解圖表和您可以查看或匯出結果的各種方式。 探索如何快速調整查詢，並深入瞭解如何取得更豐富的資訊。 | [使用查詢結果工作](advanced-hunting-query-results.md) |
| **了解結構描述** | 深入了解結構描述中的資料表和資料行。 這可協助您決定要在何處尋找資料，以及如何建構查詢。 | [結構描述參考](advanced-hunting-schema-tables.md) |
| **運用預先定義的查詢** | 探索涵蓋不同威脅搜捕案例的預先定義查詢集合。 | [使用共用查詢](advanced-hunting-shared-queries.md) |
| **最佳化查詢** | 了解如何建立可結合來自電子郵件和裝置資料的高效查詢。 | - [查詢最佳作法](advanced-hunting-shared-queries.md) <br>- [跨裝置和電子郵件進行搜尋](advanced-hunting-best-practices.md) |
| **建立自訂偵測規則** | 瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動套用回應動作。 | - [自訂偵測簡介](custom-detections-overview.md)<br>- [自訂偵測規則](custom-detection-rules.md) |

## <a name="related-topics"></a>相關主題
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](custom-detections-overview.md)