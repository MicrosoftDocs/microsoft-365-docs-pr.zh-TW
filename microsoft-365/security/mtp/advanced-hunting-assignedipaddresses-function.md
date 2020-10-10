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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f0b479051c46fe35ec9aea84b23ca0c4937fbfe
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412319"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="470f0-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="470f0-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="470f0-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="470f0-105">**Applies to:**</span></span>
- <span data-ttu-id="470f0-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="470f0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="470f0-107">使用 `AssignedIPAddresses()` 您的 [高級搜尋](advanced-hunting-overview.md) 查詢中的功能，快速取得指派給裝置的最新 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="470f0-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="470f0-108">如果您指定的是 timestamp 引數，此函數會在指定的時間取得最近的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="470f0-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="470f0-109">此函數會傳回含下列各欄的資料表：</span><span class="sxs-lookup"><span data-stu-id="470f0-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="470f0-110">欄</span><span class="sxs-lookup"><span data-stu-id="470f0-110">Column</span></span> | <span data-ttu-id="470f0-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="470f0-111">Data type</span></span> | <span data-ttu-id="470f0-112">描述</span><span class="sxs-lookup"><span data-stu-id="470f0-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="470f0-113">datetime</span><span class="sxs-lookup"><span data-stu-id="470f0-113">datetime</span></span> | <span data-ttu-id="470f0-114">使用 IP 位址觀測裝置的最晚時間</span><span class="sxs-lookup"><span data-stu-id="470f0-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="470f0-115">string</span><span class="sxs-lookup"><span data-stu-id="470f0-115">string</span></span> | <span data-ttu-id="470f0-116">裝置使用的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="470f0-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="470f0-117">string</span><span class="sxs-lookup"><span data-stu-id="470f0-117">string</span></span> | <span data-ttu-id="470f0-118">指出 IP 位址是否為公用或私人位址</span><span class="sxs-lookup"><span data-stu-id="470f0-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="470f0-119">int</span><span class="sxs-lookup"><span data-stu-id="470f0-119">int</span></span> | <span data-ttu-id="470f0-120">已獲指派 IP 位址之裝置使用的網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="470f0-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="470f0-121">如需可能的值，請參閱 [this 列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="470f0-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="470f0-122">int</span><span class="sxs-lookup"><span data-stu-id="470f0-122">int</span></span> | <span data-ttu-id="470f0-123">與指派之 IP 位址的介面卡相連的網路。</span><span class="sxs-lookup"><span data-stu-id="470f0-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="470f0-124">每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述，以及表明其是否已公開連接到網際網路的旗標。</span><span class="sxs-lookup"><span data-stu-id="470f0-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="470f0-125">語法</span><span class="sxs-lookup"><span data-stu-id="470f0-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="470f0-126">引數</span><span class="sxs-lookup"><span data-stu-id="470f0-126">Arguments</span></span>

- <span data-ttu-id="470f0-127">**x** `DeviceId` 或 `DeviceName` 值，用以識別裝置</span><span class="sxs-lookup"><span data-stu-id="470f0-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="470f0-128">**y**- `Timestamp` (datetime) 值指示函數從特定時間取得最近指派的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="470f0-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="470f0-129">若未指定，該函數會傳回最新的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="470f0-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="470f0-130">範例</span><span class="sxs-lookup"><span data-stu-id="470f0-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="470f0-131">取得裝置24小時前使用的 IP 位址清單</span><span class="sxs-lookup"><span data-stu-id="470f0-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="470f0-132">取得裝置使用的 IP 位址，並尋找與其通訊的裝置</span><span class="sxs-lookup"><span data-stu-id="470f0-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="470f0-133">此查詢使用此 `AssignedIPAddresses()` 函數來取得 `example-device-name` 在特定日期 () 之前或之前的裝置 () 的指派 IP 位址 `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="470f0-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="470f0-134">然後，它會使用 IP 位址尋找其他裝置所初始化之裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="470f0-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="470f0-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="470f0-135">Related topics</span></span>
- [<span data-ttu-id="470f0-136">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="470f0-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="470f0-137">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="470f0-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="470f0-138">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="470f0-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
