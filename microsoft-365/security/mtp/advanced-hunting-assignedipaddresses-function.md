---
title: 'AssignedIPAddresses Microsoft 威脅防護的高級搜尋中的 ( # A1 函數'
description: '瞭解如何使用 AssignedIPAddresses ( # A1 函數來取得指派給裝置的最新 IP 位址'
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，FileProfile，file profile，function，豐富
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
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794228"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="2375c-104">AssignedIPAddresses ( # A1</span><span class="sxs-lookup"><span data-stu-id="2375c-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="2375c-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2375c-105">**Applies to:**</span></span>
- <span data-ttu-id="2375c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="2375c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2375c-107">使用此 `AssignedIPAddresses()` 功能可快速取得從指定時間點指派給裝置或最近的 ip 位址的最新 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="2375c-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="2375c-108">此函數會傳回含下列各欄的資料表：</span><span class="sxs-lookup"><span data-stu-id="2375c-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="2375c-109">欄</span><span class="sxs-lookup"><span data-stu-id="2375c-109">Column</span></span> | <span data-ttu-id="2375c-110">資料類型</span><span class="sxs-lookup"><span data-stu-id="2375c-110">Data type</span></span> | <span data-ttu-id="2375c-111">描述</span><span class="sxs-lookup"><span data-stu-id="2375c-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="2375c-112">時間 戳</span><span class="sxs-lookup"><span data-stu-id="2375c-112">Timestamp</span></span> | <span data-ttu-id="2375c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="2375c-113">datetime</span></span> | <span data-ttu-id="2375c-114">使用 IP 位址觀測裝置的最晚時間</span><span class="sxs-lookup"><span data-stu-id="2375c-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="2375c-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="2375c-115">IPAddress</span></span> | <span data-ttu-id="2375c-116">string</span><span class="sxs-lookup"><span data-stu-id="2375c-116">string</span></span> | <span data-ttu-id="2375c-117">裝置使用的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="2375c-117">IP address used by the device</span></span> |
| <span data-ttu-id="2375c-118">IPType</span><span class="sxs-lookup"><span data-stu-id="2375c-118">IPType</span></span> | <span data-ttu-id="2375c-119">string</span><span class="sxs-lookup"><span data-stu-id="2375c-119">string</span></span> | <span data-ttu-id="2375c-120">指出 IP 位址是否為公用或私人位址</span><span class="sxs-lookup"><span data-stu-id="2375c-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="2375c-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="2375c-121">NetworkAdapterType</span></span> | <span data-ttu-id="2375c-122">int</span><span class="sxs-lookup"><span data-stu-id="2375c-122">int</span></span> | <span data-ttu-id="2375c-123">已獲指派 IP 位址之裝置使用的網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="2375c-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="2375c-124">如需可能的值，請參閱 [this 列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="2375c-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="2375c-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="2375c-125">ConnectedNetworks</span></span> | <span data-ttu-id="2375c-126">int</span><span class="sxs-lookup"><span data-stu-id="2375c-126">int</span></span> | <span data-ttu-id="2375c-127">與指派之 IP 位址的介面卡相連的網路。</span><span class="sxs-lookup"><span data-stu-id="2375c-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="2375c-128">每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述及表明其是否已公開連接到網際網路的標誌。</span><span class="sxs-lookup"><span data-stu-id="2375c-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="2375c-129">語法</span><span class="sxs-lookup"><span data-stu-id="2375c-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="2375c-130">引數</span><span class="sxs-lookup"><span data-stu-id="2375c-130">Arguments</span></span>

- <span data-ttu-id="2375c-131">**x** `DeviceId` 或 `DeviceName` 值，用以識別裝置</span><span class="sxs-lookup"><span data-stu-id="2375c-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="2375c-132">**y** - `Timestamp` (datetime) 值，表示取得最近的 IP 位址的特定時間點。</span><span class="sxs-lookup"><span data-stu-id="2375c-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="2375c-133">若未指定，該函數會傳回最新的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2375c-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="2375c-134">範例</span><span class="sxs-lookup"><span data-stu-id="2375c-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="2375c-135">取得裝置在24小時前所使用的 IP 位址清單</span><span class="sxs-lookup"><span data-stu-id="2375c-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="2375c-136">取得裝置使用的 IP 位址，並尋找與其通訊的裝置</span><span class="sxs-lookup"><span data-stu-id="2375c-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="2375c-137">此查詢使用此 `AssignedIPAddresses()` 函數來取得 `example-device-name` 在特定日期 () 之前或之前的裝置 () 的指派 IP 位址 `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="2375c-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="2375c-138">然後，它會使用 IP 位址尋找其他裝置所初始化之裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="2375c-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="2375c-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="2375c-139">Related topics</span></span>
- [<span data-ttu-id="2375c-140">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="2375c-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2375c-141">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="2375c-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2375c-142">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="2375c-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)