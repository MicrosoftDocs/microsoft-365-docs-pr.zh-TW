---
title: Microsoft 365 Defender 進 (尋找中的 DeviceFromIP () 函數
description: 瞭解如何使用 DeviceFromIP () 函數來取得已指派特定 IP 位址的裝置
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、裝置、devicefromIP、函數、擴充
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931299"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


在進位搜尋查詢中使用此函數快速取得特定 IP 位址在指定時間點指派 `DeviceFromIP()` 的裝置清單。 [](advanced-hunting-overview.md) 

此函數會返回具有下列資料行的表格：

| 欄 | 資料類型 | 描述 |
|------------|-------------|-------------|
| `IP` | string | IP 位址  |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |


## <a name="syntax"></a>語法

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>引數

這個函數是做為查詢的一部分來使用。

- **x**— 第一個參數通常是查詢中的資料行。 在此例中，資料行是名為 IP 位址的欄位，您想要查看已被指派的裝置 `IP` 清單。 這應該是一個本地 IP 位址。 不支援外部 IP 位址。
- **y**— 第二個選擇性參數是 ，可指示函數從特定時間取得最新 `Timestamp` 指派的裝置。 如果未指定，則函數會返回最新的可用記錄。

## <a name="example"></a>範例


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>取得已指派特定 IP 位址的最新裝置

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
