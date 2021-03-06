---
title: Microsoft 365 Defender 中的高級搜尋配額和使用參數
description: '瞭解各種配額和使用參數 (服務限制可讓高級搜尋服務保持回應的) '
keywords: 「高級搜尋」、「威脅搜尋」、「網路威脅搜尋」、「Microsoft 365 Defender」、Microsoft 365、m365、搜尋、查詢、遙測、架構、kusto、CPU 限制、查詢限制、資源、最大結果、配額、參數、配置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245597"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高級搜尋配額和使用參數

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

為了讓服務具有高性能和回應能力，「高級搜尋」會設定各種配額和使用參數 (也稱為「服務限制」 ) 。 這些配額和參數會獨立套用，以手動方式執行查詢，並使用 [自訂偵測規則](custom-detection-rules.md)執行查詢。 定期執行多個查詢的客戶應注意這些限制，並套用 [優化的最佳作法](advanced-hunting-best-practices.md) ，以盡可能減少中斷。

請參閱下表以瞭解現有的配額和使用參數。

| Quota 或參數 | Size | 重新整理週期 | 描述 |
|--|--|--|--|
| 資料範圍 | 30 天 | 每個查詢 | 每個查詢都可以查詢過去30天的資料。 |
| 結果集 | 10000列 | 每個查詢 | 每個查詢最多可以傳回10000筆記錄。 |
| Timeout | 10 分鐘 | 每個查詢 | 每個查詢可長達10分鐘執行一次。 若未在10分鐘內完成，則服務會顯示錯誤。
| CPU 資源 | 根據租使用者規模 | 每 15 分鐘 | 每當查詢執行且租使用者佔用10% 的已分配資源時， [門戶會顯示錯誤](advanced-hunting-errors.md) 。 如果租使用者到達100%，直到接下來的15分鐘週期過後，便會封鎖查詢。 |

>[!NOTE] 
>個別的配額和參數集適用于透過 API 執行的高級搜尋查詢。 [閱讀高級搜尋 APIs](./api-advanced-hunting.md)

## <a name="related-topics"></a>相關主題

- [高級搜尋最佳作法](advanced-hunting-best-practices.md)
- [處理高級搜尋錯誤](advanced-hunting-errors.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [自訂偵測概觀](custom-detections-overview.md)