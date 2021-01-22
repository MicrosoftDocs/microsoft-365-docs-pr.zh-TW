---
title: AssignedIPAddresses () 函數在 Microsoft 365 Defender 進步搜尋中
description: 瞭解如何使用 AssignedIPAddresses () 函數，以取得指派給裝置的最新 IP 位址
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、FileProfile、檔案設定檔、函數、擴充
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
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933015"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="3941b-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="3941b-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3941b-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="3941b-105">**Applies to:**</span></span>
- <span data-ttu-id="3941b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3941b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3941b-107">在 `AssignedIPAddresses()` 進位搜尋 [查詢中使用此](advanced-hunting-overview.md) 函數來快速取得已指派給裝置的最新 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3941b-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="3941b-108">如果您指定時間戳記引數，此函數會于指定時間取得最新的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3941b-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="3941b-109">此函數會返回具有下列資料行的表格：</span><span class="sxs-lookup"><span data-stu-id="3941b-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="3941b-110">欄</span><span class="sxs-lookup"><span data-stu-id="3941b-110">Column</span></span> | <span data-ttu-id="3941b-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="3941b-111">Data type</span></span> | <span data-ttu-id="3941b-112">描述</span><span class="sxs-lookup"><span data-stu-id="3941b-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="3941b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="3941b-113">datetime</span></span> | <span data-ttu-id="3941b-114">裝置使用 IP 位址觀察的最近時間</span><span class="sxs-lookup"><span data-stu-id="3941b-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="3941b-115">string</span><span class="sxs-lookup"><span data-stu-id="3941b-115">string</span></span> | <span data-ttu-id="3941b-116">裝置使用的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="3941b-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="3941b-117">string</span><span class="sxs-lookup"><span data-stu-id="3941b-117">string</span></span> | <span data-ttu-id="3941b-118">指出 IP 位址是公用還是私人位址</span><span class="sxs-lookup"><span data-stu-id="3941b-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="3941b-119">int</span><span class="sxs-lookup"><span data-stu-id="3941b-119">int</span></span> | <span data-ttu-id="3941b-120">已指派 IP 位址之裝置使用的網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="3941b-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="3941b-121">有關可能的值，請參閱 [此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="3941b-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="3941b-122">int</span><span class="sxs-lookup"><span data-stu-id="3941b-122">int</span></span> | <span data-ttu-id="3941b-123">具有已指派 IP 位址的介面卡所連接的網路。</span><span class="sxs-lookup"><span data-stu-id="3941b-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="3941b-124">每個 JSON 陣列都包含網路名稱、類別 (公用、私人或網域) 、描述及旗標，指出該陣列是否公開連接至網際網路</span><span class="sxs-lookup"><span data-stu-id="3941b-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="3941b-125">語法</span><span class="sxs-lookup"><span data-stu-id="3941b-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="3941b-126">引數</span><span class="sxs-lookup"><span data-stu-id="3941b-126">Arguments</span></span>

- <span data-ttu-id="3941b-127">**x** `DeviceId` — `DeviceName` 或識別裝置的值</span><span class="sxs-lookup"><span data-stu-id="3941b-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="3941b-128">**y**— (時間) 值，指示函數從特定時間取得最近指派的 `Timestamp` IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3941b-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="3941b-129">如果未指定，函數會回電最新的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3941b-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="3941b-130">範例</span><span class="sxs-lookup"><span data-stu-id="3941b-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="3941b-131">取得裝置 24 小時前使用的 IP 位址清單</span><span class="sxs-lookup"><span data-stu-id="3941b-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="3941b-132">取得裝置使用的 IP 位址，並尋找與裝置通訊的裝置</span><span class="sxs-lookup"><span data-stu-id="3941b-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="3941b-133">此查詢會使用函數，取得特定日期或 () 裝置所指派的 IP `AssignedIPAddresses()` `example-device-name` `example-date` 位址 () 。</span><span class="sxs-lookup"><span data-stu-id="3941b-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="3941b-134">接著，它會使用 IP 位址尋找由其他裝置啟動之裝置的連接。</span><span class="sxs-lookup"><span data-stu-id="3941b-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="3941b-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="3941b-135">Related topics</span></span>
- [<span data-ttu-id="3941b-136">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="3941b-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3941b-137">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="3941b-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3941b-138">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="3941b-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
