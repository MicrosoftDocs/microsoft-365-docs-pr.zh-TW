---
title: Microsoft 365 Defender 的高級搜尋中的 DeviceFromIP () 功能
description: 瞭解如何使用 DeviceFromIP () 函數來取得指派特定 IP 位址的裝置
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，device，devicefromIP，function，豐富
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933178"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


使用 `DeviceFromIP()` 您的 [高級搜尋](advanced-hunting-overview.md) 查詢中的功能，快速取得在指定時間點指派給特定 IP 位址的裝置清單。 

此函數會傳回含下列各欄的資料表：

| 欄 | 資料類型 | 描述 |
|------------|-------------|-------------|
| `IP` | string | IP 位址  |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |


## <a name="syntax"></a>語法

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>引數

這項功能會在查詢中稱為「是」。

- **x**-第一個參數通常已經是查詢中的一欄。 在此情況下，其為 `IP` 您想要查看指派給它之裝置清單的 IP 位址。 它應該是本機 IP 位址。 不支援外部 IP 位址。
- **y**-第二個選擇性參數是 `Timestamp` ，它會指示函數從特定時間取得最近指派的裝置。 若未指定，函數會傳回最新的可用記錄。

## <a name="example"></a>範例


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>取得指派特定 IP 位址的最新裝置

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
