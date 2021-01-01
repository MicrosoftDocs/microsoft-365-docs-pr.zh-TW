---
title: 'DeviceFromIP Microsoft 365 Defender 的高級搜尋中的 ( # A1 函數'
description: '瞭解如何使用 DeviceFromIP ( # A1 函數，以取得指派特定 IP 位址的裝置'
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，device，devicefromIP，function，豐富
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741103"
---
# <a name="devicefromip"></a><span data-ttu-id="9564e-104">DeviceFromIP ( # A1</span><span class="sxs-lookup"><span data-stu-id="9564e-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9564e-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="9564e-105">**Applies to:**</span></span>
- <span data-ttu-id="9564e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9564e-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="9564e-107">使用 `DeviceFromIP()` 您的 [高級搜尋](advanced-hunting-overview.md) 查詢中的功能，快速取得在指定時間點指派給特定 IP 位址的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="9564e-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="9564e-108">此函數會傳回含下列各欄的資料表：</span><span class="sxs-lookup"><span data-stu-id="9564e-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="9564e-109">欄</span><span class="sxs-lookup"><span data-stu-id="9564e-109">Column</span></span> | <span data-ttu-id="9564e-110">資料類型</span><span class="sxs-lookup"><span data-stu-id="9564e-110">Data type</span></span> | <span data-ttu-id="9564e-111">描述</span><span class="sxs-lookup"><span data-stu-id="9564e-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="9564e-112">string</span><span class="sxs-lookup"><span data-stu-id="9564e-112">string</span></span> | <span data-ttu-id="9564e-113">IP 位址</span><span class="sxs-lookup"><span data-stu-id="9564e-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="9564e-114">string</span><span class="sxs-lookup"><span data-stu-id="9564e-114">string</span></span> | <span data-ttu-id="9564e-115">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9564e-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="9564e-116">語法</span><span class="sxs-lookup"><span data-stu-id="9564e-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="9564e-117">引數</span><span class="sxs-lookup"><span data-stu-id="9564e-117">Arguments</span></span>

<span data-ttu-id="9564e-118">這項功能會在查詢中稱為「是」。</span><span class="sxs-lookup"><span data-stu-id="9564e-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="9564e-119">**x**-第一個參數通常已經是查詢中的一欄。</span><span class="sxs-lookup"><span data-stu-id="9564e-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="9564e-120">在此情況下，其為 `IP` 您想要查看指派給它之裝置清單的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9564e-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="9564e-121">它應該是本機 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9564e-121">It should be a local IP address.</span></span> <span data-ttu-id="9564e-122">不支援外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9564e-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="9564e-123">**y**-第二個選擇性參數是 `Timestamp` ，它會指示函數從特定時間取得最近指派的裝置。</span><span class="sxs-lookup"><span data-stu-id="9564e-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="9564e-124">若未指定，函數會傳回最新的可用記錄。</span><span class="sxs-lookup"><span data-stu-id="9564e-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="9564e-125">範例</span><span class="sxs-lookup"><span data-stu-id="9564e-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="9564e-126">取得指派特定 IP 位址的最新裝置</span><span class="sxs-lookup"><span data-stu-id="9564e-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="9564e-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="9564e-127">Related topics</span></span>
- [<span data-ttu-id="9564e-128">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="9564e-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9564e-129">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="9564e-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9564e-130">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="9564e-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
