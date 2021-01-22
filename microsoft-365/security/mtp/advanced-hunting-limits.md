---
title: Microsoft 365 Defender 中的進位搜尋配額與使用參數
description: 瞭解各種配額和使用量參數 (服務限制) 進一) 服務回應
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構、kusto、CPU 限制、查詢限制、資源、最大結果、配額、參數、配置
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
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929787"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>進位搜尋配額與使用參數

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

為保持服務執行速度與回應能力，進位搜尋會設定不同的配額 (使用參數，也稱為「服務限制」) 。 這些配額和參數適用于手動執行及自訂偵測 [規則的查詢](custom-detection-rules.md)。 定期執行多個查詢的客戶應追蹤使用，並運用優化 [最佳做法，](advanced-hunting-best-practices.md) 將干擾降到最低。

請參閱下表以瞭解現有的配額和使用量參數。

| 配額或參數 | 大小 | 重新更新迴圈 | 說明 |
|--|--|--|--|
| 資料範圍 | 30 天 | 每個查詢 | 每個查詢都可以查詢過去 30 天內的資料。 |
| 結果集 | 10，000 列 | 每個查詢 | 每個查詢最多可以回回 10，000 個記錄。 |
| Timeout | 10 分鐘 | 每個查詢 | 每個查詢最多可以執行 10 分鐘。 如果 10 分鐘內無法完成，服務會顯示錯誤。
| CPU 資源 | 根據租使用者大小 | - 使用小時，然後每 15 分鐘<br>- 每天午夜 12 點 | 此服務會分別強制執行每日和 15 分鐘的配額。 針對每個配額，每當[](advanced-hunting-errors.md)查詢執行且租使用者已耗用超過 10% 的已配置資源時，入口網站會顯示錯誤。 如果租使用者已達 100%，直到下一個每日或 15 分鐘迴圈之後，查詢會封鎖。 |

>[!NOTE] 
>另一組配額和參數適用于透過 API 執行進位搜尋查詢。 [閱讀進一搜尋 API](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>相關主題

- [進位搜尋最佳作法](advanced-hunting-best-practices.md)
- [處理進位搜尋錯誤](advanced-hunting-errors.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [自訂偵測概觀](custom-detections-overview.md)