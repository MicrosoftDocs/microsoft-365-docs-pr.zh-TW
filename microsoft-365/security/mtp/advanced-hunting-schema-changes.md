---
title: Microsoft 365 Defender 進位搜尋架構中的命名變更
description: 追蹤及檢查進位搜尋架構中的資料表和欄的命名變更
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料、資料、命名變更、重新命名、Microsoft 威脅防護
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
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932199"
---
# <a name="advanced-hunting-schema---naming-changes"></a>進位搜尋架構 - 命名變更

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

進 [位搜尋架構](advanced-hunting-schema-tables.md) 會定期更新，以新增資料表和欄。 在某些情況下，會重新命名或取代現有的資料行名稱，以改善使用者體驗。 請參閱這篇文章，以檢查可能會影響查詢的命名變更。

命名變更會自動適用于儲存于安全性中心的查詢，包括自訂偵測規則使用的查詢。 您不一樣需要手動更新這些查詢。 不過，您必須更新下列查詢：
- 使用 API 執行查詢
- 儲存于資訊安全中心以外位置的查詢

## <a name="december-2020"></a>2020 年 12 月

| 表格名稱 | 原始欄名稱 | 新增欄名稱 | 變更原因
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | 客戶意見回饋 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | 客戶意見回饋 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | 客戶意見回饋 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)