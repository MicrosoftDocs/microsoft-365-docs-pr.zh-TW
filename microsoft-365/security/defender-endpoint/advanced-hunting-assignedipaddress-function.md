---
title: AssignedIPAddresses for Microsoft Defender for Endpoint 中的高級搜尋中的 () 功能
description: 瞭解如何使用 AssignedIPAddresses () 函數來取得指派給裝置的最新 IP 位址
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，mdatp，Microsoft Defender ATP，Microsoft Defender for Endpoint，Windows Defender，Windows Defender ATP，Windows Defender Advanced 威脅防護，搜尋，查詢，遙測，schema reference，kusto，FileProfile，file profile，豐富
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 5dcc41302d797b4084c36d020908ba59131c90d4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499277"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="8ffbc-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="8ffbc-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="8ffbc-105">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8ffbc-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8ffbc-106">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="8ffbc-107">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8ffbc-107">**Applies to:**</span></span>
- [<span data-ttu-id="8ffbc-108">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ffbc-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="8ffbc-109">使用 `AssignedIPAddresses()` 您的高級搜尋查詢中的功能，快速取得指派給裝置的最新 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="8ffbc-110">如果您指定的是 timestamp 引數，此函數會在指定的時間取得最近的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="8ffbc-111">此函數會傳回含下列各欄的資料表：</span><span class="sxs-lookup"><span data-stu-id="8ffbc-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="8ffbc-112">欄</span><span class="sxs-lookup"><span data-stu-id="8ffbc-112">Column</span></span> | <span data-ttu-id="8ffbc-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="8ffbc-113">Data type</span></span> | <span data-ttu-id="8ffbc-114">描述</span><span class="sxs-lookup"><span data-stu-id="8ffbc-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="8ffbc-115">datetime</span><span class="sxs-lookup"><span data-stu-id="8ffbc-115">datetime</span></span> | <span data-ttu-id="8ffbc-116">使用 IP 位址觀測裝置的最晚時間</span><span class="sxs-lookup"><span data-stu-id="8ffbc-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="8ffbc-117">string</span><span class="sxs-lookup"><span data-stu-id="8ffbc-117">string</span></span> | <span data-ttu-id="8ffbc-118">裝置使用的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8ffbc-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="8ffbc-119">string</span><span class="sxs-lookup"><span data-stu-id="8ffbc-119">string</span></span> | <span data-ttu-id="8ffbc-120">指出 IP 位址是否為公用或私人位址</span><span class="sxs-lookup"><span data-stu-id="8ffbc-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="8ffbc-121">int</span><span class="sxs-lookup"><span data-stu-id="8ffbc-121">int</span></span> | <span data-ttu-id="8ffbc-122">已獲指派 IP 位址之裝置使用的網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="8ffbc-123">如需可能的值，請參閱 [this 列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="8ffbc-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="8ffbc-124">int</span><span class="sxs-lookup"><span data-stu-id="8ffbc-124">int</span></span> | <span data-ttu-id="8ffbc-125">與指派之 IP 位址的介面卡相連的網路。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="8ffbc-126">每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述，以及表明其是否已公開連接到網際網路的旗標。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="8ffbc-127">語法</span><span class="sxs-lookup"><span data-stu-id="8ffbc-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="8ffbc-128">引數</span><span class="sxs-lookup"><span data-stu-id="8ffbc-128">Arguments</span></span>

- <span data-ttu-id="8ffbc-129">**x** `DeviceId` 或 `DeviceName` 值，用以識別裝置</span><span class="sxs-lookup"><span data-stu-id="8ffbc-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="8ffbc-130">**y**- `Timestamp` (datetime) 值指示函數從特定時間取得最近指派的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="8ffbc-131">若未指定，該函數會傳回最新的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="8ffbc-132">範例</span><span class="sxs-lookup"><span data-stu-id="8ffbc-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="8ffbc-133">取得裝置24小時前使用的 IP 位址清單</span><span class="sxs-lookup"><span data-stu-id="8ffbc-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="8ffbc-134">取得裝置使用的 IP 位址，並尋找與其通訊的裝置</span><span class="sxs-lookup"><span data-stu-id="8ffbc-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="8ffbc-135">此查詢使用此 `AssignedIPAddresses()` 函數來取得 `example-device-name` 在特定日期 () 之前或之前的裝置 () 的指派 IP 位址 `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="8ffbc-136">然後，它會使用 IP 位址尋找其他裝置所初始化之裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="8ffbc-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="8ffbc-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="8ffbc-137">Related topics</span></span>

- [<span data-ttu-id="8ffbc-138">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="8ffbc-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8ffbc-139">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="8ffbc-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8ffbc-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="8ffbc-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
