---
title: Microsoft Defender ATP 中的高級搜尋概述
description: 在 Microsoft Defender ATP 中使用威脅搜尋功能來建立查詢，以找出網路的威脅和弱點
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp、搜尋、查詢、遙測、自訂偵測、架構、kusto、時區、UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4883a4f04f06774d02aa0d942edc841867eb36b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499514"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>使用高級搜尋主動搜尋威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。 您可以主動檢查您網路中的事件，以找出威脅指示器和實體。 對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。

觀賞這段影片，快速流覽高級搜尋，以及可讓您快速入門的簡短教學課程。
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。 這些規則會自動執行，以檢查是否有可疑的破壞活動、錯誤設定的機器及其他發現的回應。

>[!TIP]
>[在 Microsoft 威脅防護中使用高級搜尋](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview)，以搜尋使用來自 Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 及 microsoft Defender 身分識別的資料的威脅。 [開啟 Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)

## <a name="get-started-with-advanced-hunting"></a>開始使用進階搜捕

請逐步執行下列步驟，以提升您的高級搜尋知識。

建議您透過數個步驟來利用進階搜捕快速啟動並執行。

| 學習目標 | 描述 | 資源 |
|--|--|--|
| **瞭解語言** | 「高級搜尋」是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。 執行您的第一個查詢來開始學習查詢語言。 | [查詢語言概觀](advanced-hunting-query-language.md) |
| **瞭解如何使用查詢結果** | 深入瞭解圖表和您可以查看或匯出結果的各種方式。 探索如何快速調整查詢，並深入瞭解如何取得更豐富的資訊。 | [使用查詢結果工作](advanced-hunting-query-results.md) |
| **了解結構描述** | 深入了解結構描述中的資料表和資料行。 瞭解在建立查詢時要尋找資料的位置。 | [結構描述參考](advanced-hunting-schema-reference.md) |
| **使用預先定義的查詢** | 探索涵蓋不同威脅搜捕案例的預先定義查詢集合。 | [共用查詢](advanced-hunting-shared-queries.md) |
| **優化查詢並處理錯誤** | 瞭解如何建立高效且無錯誤的查詢。 | - [查詢最佳作法](advanced-hunting-best-practices.md)<br>- [處理錯誤](advanced-hunting-errors.md) |
| **取得最完整的覆蓋範圍** | 使用 [審核設定] 為您的組織提供更佳的資料覆蓋率。 | - [延伸高級搜尋範圍](advanced-hunting-extend-data.md) |
| **執行快速調查** | 快速執行高級搜尋查詢，以調查可疑活動。 | - [使用 *go 搜尋* 快速尋找實體或事件資訊](advanced-hunting-go-hunt.md) |
| **包含威脅和位址受到威脅** | 隔離檔、限制應用程式執行及其他動作以回應攻擊 | - [對高級搜尋查詢結果採取動作](advanced-hunting-take-action.md) |
| **建立自訂偵測規則** | 瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動採取回應動作。 | - [自訂偵測簡介](overview-custom-detections.md)<br>- [自訂偵測規則](custom-detection-rules.md) |

## <a name="data-freshness-and-update-frequency"></a>資料新鮮度和更新頻率

「高級搜尋」資料可以分類成兩種不同的類型，每個不同的合併。

- **事件或活動資料**--填入有關警示、安全性事件、系統事件及例行評估的表格。 「高級搜尋」幾乎會在收集成功的感應器成功傳輸至端點後立即接收這類資料。
- **實體資料**—使用使用者和裝置的整合式資訊來填入資料表。 此資料來自相對靜態資料來源和動態來源，例如 Active Directory 專案和事件記錄。 若要提供全新的資料，每隔15分鐘更新一次所有新資訊的資料表，新增可能不會填滿的資料列。 每24小時都會合並資料，以插入記錄，其中包含每個實體的最新、最全面的資料集。

## <a name="time-zone"></a>時區

高級搜尋中的時間資訊目前在 UTC 時區內。

## <a name="related-topics"></a>相關主題

- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](overview-custom-detections.md)