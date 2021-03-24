---
title: 取得實體的相關資訊以進行搜尋
description: 瞭解如何使用「移到搜尋」工具，使用高級搜尋快速查詢實體或事件的相關資訊。
keywords: 高級搜尋、事件、資料透視、實體、搜尋、相關事件、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 242c15bdd2f28f7277b93781d521c5414b9e90cf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060427"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>使用 go 搜尋快速尋找實體或事件資訊

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

使用 [ *尋找* ] [搜尋] 動作，您可以使用強大查詢的 [高級搜尋](advanced-hunting-overview.md) 功能，快速調查事件及各種實體類型。 此巨集指令會自動執行高級搜尋查詢，以尋找所選取事件或實體的相關資訊。

每當顯示事件或實體詳細資料時，就會在安全性中心的各個區段中使用「 *繼續搜尋* 」動作。 例如，您可以使用下列各節的「 *繼續搜尋* 」：

- 在 [ [事件] 頁面](investigate-incidents.md#incident-overview)中，您可以查看使用者、裝置及其他許多與事件相關聯之實體的詳細資料。 當您選取實體時，您會收到其他資訊，以及您在該 entitity 上可以採取的各種動作。 在下列範例中，會選取一個信箱，顯示信箱的詳細資料，也就是尋找該信箱的詳細資訊的選項。

    ![使用 [搜尋] 選項顯示信箱詳細資料的影像](../../media/mtp-ah/go-hunt-email.png)

- 在 [事件] 頁面中，您也可以在 [證據] 索引標籤下存取實體清單。選取其中一個實體時，會提供一個選項，以快速尋找該實體的相關資訊。

    ![在 [證據] 索引標籤中，以 [搜尋] 選項顯示選取檔案的影像](../../media/mtp-ah/go-hunt-evidence-file.png)


- 當您查看裝置的時程表時，您可以選取時程表中的事件，以查看有關該事件的其他資訊。 選取事件後，您可以在 [高級搜尋] 中取得搜尋其他相關事件的選項。

    ![顯示 [搜尋] 選項的事件詳細資料的影像](../../media/mtp-ah/go-hunt-event.png)

選取 [ **搜尋** ] 或 [ **搜尋相關的事件** ] 會傳送不同的查詢，視您是否已選取實體或事件而定。

## <a name="query-for-entity-information"></a>查詢實體資訊
當您使用「 *搜尋* 以查詢使用者、裝置或任何其他類型的實體」的相關資訊時，查詢會檢查涉及該實體之任何事件的所有相關架構資料表。 若要讓結果保持可管理，查詢的範圍會設定為與過去30天（包含實體並與該事件相關聯）的最早活動的時段。

以下是裝置的 go 搜尋查詢範例：

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>支援的實體類型
您可以在選取下列任何實體類型之後，使用 [ *搜尋* ]：

- 檔案
- 電子郵件
- 電子郵件聚簇
- 信箱
- 使用者
- 裝置
- IP 位址
- URL

## <a name="query-for-event-information"></a>事件資訊的查詢
當您使用「 *搜尋* 以查詢」時程表事件的相關資訊時，查詢會檢查所選事件時間四周其他事件的所有相關架構資料表。 例如，下列查詢會列出在相同裝置上的相同時段內發生的各種架構表格事件：

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>調整查詢
您可以使用一些 [查詢語言](advanced-hunting-query-language.md)的知識，將查詢調整為您的喜好設定。 例如，您可以調整此線，它會決定時間範圍的大小：

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

除了修改查詢以取得更相關的結果之外，您還可以：
- [以圖表形式查看結果](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [建立自訂偵測規則](custom-detection-rules.md)

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [自訂偵測規則](custom-detection-rules.md)
