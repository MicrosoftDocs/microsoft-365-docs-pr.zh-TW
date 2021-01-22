---
title: 進位搜尋架構中的 DeviceNetworkInfo 資料表
description: 在進位搜尋架構的 DeviceNetworkInfo 資料表中瞭解網路組式資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、machinenetworkinfo、DeviceNetworkInfo、裝置、電腦、mac、ip、配卡、dns、dhcp、閘道、裝置
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931203"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="39641-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="39641-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="39641-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="39641-105">**Applies to:**</span></span>
- <span data-ttu-id="39641-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39641-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="39641-107">進位搜尋架構中的表格包含機器網路設定的資訊，包括網路介面卡、IP 和 MAC 位址， `DeviceNetworkInfo` 以及已連接的網路或網域。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="39641-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="39641-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="39641-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="39641-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="39641-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="39641-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="39641-110">Column name</span></span> | <span data-ttu-id="39641-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="39641-111">Data type</span></span> | <span data-ttu-id="39641-112">描述</span><span class="sxs-lookup"><span data-stu-id="39641-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="39641-113">datetime</span><span class="sxs-lookup"><span data-stu-id="39641-113">datetime</span></span> | <span data-ttu-id="39641-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="39641-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="39641-115">string</span><span class="sxs-lookup"><span data-stu-id="39641-115">string</span></span> | <span data-ttu-id="39641-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="39641-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="39641-117">string</span><span class="sxs-lookup"><span data-stu-id="39641-117">string</span></span> | <span data-ttu-id="39641-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="39641-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="39641-119">long</span><span class="sxs-lookup"><span data-stu-id="39641-119">long</span></span> | <span data-ttu-id="39641-120">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="39641-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="39641-121">若要識別唯一事件，此欄必須與 DeviceName 和時間戳記欄一起使用</span><span class="sxs-lookup"><span data-stu-id="39641-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="39641-122">string</span><span class="sxs-lookup"><span data-stu-id="39641-122">string</span></span> | <span data-ttu-id="39641-123">網路介面卡的名稱</span><span class="sxs-lookup"><span data-stu-id="39641-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="39641-124">string</span><span class="sxs-lookup"><span data-stu-id="39641-124">string</span></span> | <span data-ttu-id="39641-125">網路介面卡的 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="39641-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="39641-126">string</span><span class="sxs-lookup"><span data-stu-id="39641-126">string</span></span> | <span data-ttu-id="39641-127">網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="39641-127">Network adapter type.</span></span> <span data-ttu-id="39641-128">有關可能的值，請參閱 [此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="39641-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="39641-129">string</span><span class="sxs-lookup"><span data-stu-id="39641-129">string</span></span> | <span data-ttu-id="39641-130">網路介面卡的營運狀態。</span><span class="sxs-lookup"><span data-stu-id="39641-130">Operational status of the network adapter.</span></span> <span data-ttu-id="39641-131">有關可能的值，請參閱 [此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="39641-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="39641-132">string</span><span class="sxs-lookup"><span data-stu-id="39641-132">string</span></span> | <span data-ttu-id="39641-133">如果介面用於此目的 ，例如 6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH，則建立通訊協定</span><span class="sxs-lookup"><span data-stu-id="39641-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="39641-134">string</span><span class="sxs-lookup"><span data-stu-id="39641-134">string</span></span> | <span data-ttu-id="39641-135">介面卡所連接的網路。</span><span class="sxs-lookup"><span data-stu-id="39641-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="39641-136">每個 JSON 陣列都包含網路名稱、類別 (公用、私人或網域) 、描述，以及指出該陣列是否公開連接至網際網路的標標。</span><span class="sxs-lookup"><span data-stu-id="39641-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="39641-137">string</span><span class="sxs-lookup"><span data-stu-id="39641-137">string</span></span> | <span data-ttu-id="39641-138">JSON 陣列格式的 DNS 伺服器位址</span><span class="sxs-lookup"><span data-stu-id="39641-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="39641-139">string</span><span class="sxs-lookup"><span data-stu-id="39641-139">string</span></span> | <span data-ttu-id="39641-140">DHCP 伺服器的 IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="39641-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="39641-141">string</span><span class="sxs-lookup"><span data-stu-id="39641-141">string</span></span> | <span data-ttu-id="39641-142">DHCP 伺服器的 IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="39641-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="39641-143">string</span><span class="sxs-lookup"><span data-stu-id="39641-143">string</span></span> | <span data-ttu-id="39641-144">JSON 陣列格式的預設閘道位址</span><span class="sxs-lookup"><span data-stu-id="39641-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="39641-145">string</span><span class="sxs-lookup"><span data-stu-id="39641-145">string</span></span> | <span data-ttu-id="39641-146">JSON 陣列，其中包含指派給配卡的所有 IP 位址，以及各自的子網首碼和 IP 位址空間，例如公用、私人或 link-local</span><span class="sxs-lookup"><span data-stu-id="39641-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="39641-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="39641-147">Related topics</span></span>
- [<span data-ttu-id="39641-148">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="39641-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="39641-149">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="39641-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="39641-150">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="39641-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="39641-151">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="39641-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="39641-152">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="39641-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="39641-153">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="39641-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
