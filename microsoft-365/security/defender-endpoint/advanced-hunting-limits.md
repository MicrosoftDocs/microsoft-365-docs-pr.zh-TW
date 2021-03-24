---
title: Microsoft Defender ATP 中的高級搜尋限制
description: 瞭解可讓高級搜尋服務保持回應的各種服務限制
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp、搜尋、查詢、遙測、架構、kusto、CPU 限制、查詢限制、資源、最大結果
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060235"
---
# <a name="advanced-hunting-service-limits"></a>高級搜尋服務限制

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

為了讓服務具有高性能和回應能力，「高級搜尋」會為手動執行和 [自訂偵測規則](custom-detection-rules.md)，設定各種查詢限制。 請參閱下表以瞭解這些限制。

| 限制 | Size | 重新整理週期 | 描述 |
|--|--|--|--|
| 資料範圍 | 30 天 | 每個查詢 | 每個查詢都可以查詢過去30天的資料。 |
| 結果集 | 10000列 | 每個查詢 | 每個查詢最多可以傳回10000筆記錄。 |
| Timeout | 10 分鐘 | 每個查詢 | 每個查詢可長達10分鐘執行一次。 若未在10分鐘內完成，則服務會顯示錯誤。
| CPU 資源 | 根據租使用者規模 | -在每小時，然後每隔15分鐘<br>-每日12午夜 | 服務會分別強制執行每日和15分鐘的限制。 針對每個限制，當執行查詢且租使用者使用的資源超過10% 時， [門戶會顯示錯誤](advanced-hunting-errors.md) 。 如果租使用者已到達100%，直到下一天或15分鐘週期之後，才會封鎖查詢。 |

>[!NOTE] 
>一組不同的限制適用于透過 API 執行的高級搜尋查詢。 [閱讀高級搜尋 APIs](run-advanced-query-api.md)

定期執行多個查詢的客戶應追蹤工作量並套用 [優化最佳作法](advanced-hunting-best-practices.md) ，以盡可能減少超出這些限制所產生的中斷。

## <a name="related-topics"></a>相關主題

- [高級搜尋最佳作法](advanced-hunting-best-practices.md)
- [處理高級搜尋錯誤](advanced-hunting-errors.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [自訂偵測規則](custom-detection-rules.md)