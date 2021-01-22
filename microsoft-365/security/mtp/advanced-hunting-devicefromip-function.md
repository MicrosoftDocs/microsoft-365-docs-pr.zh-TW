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
# <a name="devicefromip"></a><span data-ttu-id="b60ce-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="b60ce-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b60ce-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="b60ce-105">**Applies to:**</span></span>
- <span data-ttu-id="b60ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b60ce-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="b60ce-107">在進位搜尋查詢中使用此函數快速取得特定 IP 位址在指定時間點指派 `DeviceFromIP()` 的裝置清單。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b60ce-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="b60ce-108">此函數會返回具有下列資料行的表格：</span><span class="sxs-lookup"><span data-stu-id="b60ce-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="b60ce-109">欄</span><span class="sxs-lookup"><span data-stu-id="b60ce-109">Column</span></span> | <span data-ttu-id="b60ce-110">資料類型</span><span class="sxs-lookup"><span data-stu-id="b60ce-110">Data type</span></span> | <span data-ttu-id="b60ce-111">描述</span><span class="sxs-lookup"><span data-stu-id="b60ce-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="b60ce-112">string</span><span class="sxs-lookup"><span data-stu-id="b60ce-112">string</span></span> | <span data-ttu-id="b60ce-113">IP 位址</span><span class="sxs-lookup"><span data-stu-id="b60ce-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="b60ce-114">string</span><span class="sxs-lookup"><span data-stu-id="b60ce-114">string</span></span> | <span data-ttu-id="b60ce-115">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="b60ce-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="b60ce-116">語法</span><span class="sxs-lookup"><span data-stu-id="b60ce-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="b60ce-117">引數</span><span class="sxs-lookup"><span data-stu-id="b60ce-117">Arguments</span></span>

<span data-ttu-id="b60ce-118">這個函數是做為查詢的一部分來使用。</span><span class="sxs-lookup"><span data-stu-id="b60ce-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="b60ce-119">**x**— 第一個參數通常是查詢中的資料行。</span><span class="sxs-lookup"><span data-stu-id="b60ce-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="b60ce-120">在此例中，資料行是名為 IP 位址的欄位，您想要查看已被指派的裝置 `IP` 清單。</span><span class="sxs-lookup"><span data-stu-id="b60ce-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="b60ce-121">這應該是一個本地 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b60ce-121">It should be a local IP address.</span></span> <span data-ttu-id="b60ce-122">不支援外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b60ce-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="b60ce-123">**y**— 第二個選擇性參數是 ，可指示函數從特定時間取得最新 `Timestamp` 指派的裝置。</span><span class="sxs-lookup"><span data-stu-id="b60ce-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="b60ce-124">如果未指定，則函數會返回最新的可用記錄。</span><span class="sxs-lookup"><span data-stu-id="b60ce-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="b60ce-125">範例</span><span class="sxs-lookup"><span data-stu-id="b60ce-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="b60ce-126">取得已指派特定 IP 位址的最新裝置</span><span class="sxs-lookup"><span data-stu-id="b60ce-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="b60ce-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="b60ce-127">Related topics</span></span>
- [<span data-ttu-id="b60ce-128">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="b60ce-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b60ce-129">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="b60ce-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b60ce-130">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="b60ce-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
