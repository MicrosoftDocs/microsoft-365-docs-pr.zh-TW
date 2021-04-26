---
title: Advanced 搜尋架構中的 DeviceNetworkInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceNetworkInfo 資料表中的網路設定資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，machinenetworkinfo，DeviceNetworkInfo，device，machine，mac，隧道，adapter，dns，dhcp，閘道，隧道
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
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023186"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="f346a-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="f346a-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f346a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f346a-105">**Applies to:**</span></span>
- <span data-ttu-id="f346a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f346a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="f346a-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f346a-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="f346a-108">[！附注] `DeviceNetworkInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含電腦網路設定的相關資訊，包括網路介面卡、IP 及 MAC 位址，以及連線的網路或網域。</span><span class="sxs-lookup"><span data-stu-id="f346a-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="f346a-109">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="f346a-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f346a-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f346a-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f346a-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="f346a-111">Column name</span></span> | <span data-ttu-id="f346a-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="f346a-112">Data type</span></span> | <span data-ttu-id="f346a-113">描述</span><span class="sxs-lookup"><span data-stu-id="f346a-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f346a-114">datetime</span><span class="sxs-lookup"><span data-stu-id="f346a-114">datetime</span></span> | <span data-ttu-id="f346a-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="f346a-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f346a-116">string</span><span class="sxs-lookup"><span data-stu-id="f346a-116">string</span></span> | <span data-ttu-id="f346a-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f346a-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f346a-118">string</span><span class="sxs-lookup"><span data-stu-id="f346a-118">string</span></span> | <span data-ttu-id="f346a-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f346a-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="f346a-120">string</span><span class="sxs-lookup"><span data-stu-id="f346a-120">string</span></span> | <span data-ttu-id="f346a-121">網路介面卡的名稱</span><span class="sxs-lookup"><span data-stu-id="f346a-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="f346a-122">string</span><span class="sxs-lookup"><span data-stu-id="f346a-122">string</span></span> | <span data-ttu-id="f346a-123">網路介面卡的 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="f346a-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f346a-124">string</span><span class="sxs-lookup"><span data-stu-id="f346a-124">string</span></span> | <span data-ttu-id="f346a-125">網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="f346a-125">Network adapter type.</span></span> <span data-ttu-id="f346a-126">如需可能的值，請參閱 [this 列舉](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="f346a-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="f346a-127">string</span><span class="sxs-lookup"><span data-stu-id="f346a-127">string</span></span> | <span data-ttu-id="f346a-128">網路介面卡的運作狀態。</span><span class="sxs-lookup"><span data-stu-id="f346a-128">Operational status of the network adapter.</span></span> <span data-ttu-id="f346a-129">如需可能的值，請參閱 [this 列舉](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="f346a-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="f346a-130">string</span><span class="sxs-lookup"><span data-stu-id="f346a-130">string</span></span> | <span data-ttu-id="f346a-131">隧道通訊協定，如果此介面是用於此用途，例如6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH</span><span class="sxs-lookup"><span data-stu-id="f346a-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f346a-132">string</span><span class="sxs-lookup"><span data-stu-id="f346a-132">string</span></span> | <span data-ttu-id="f346a-133">連接到配接器的網路。</span><span class="sxs-lookup"><span data-stu-id="f346a-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="f346a-134">每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述及表明其是否已公開連接到網際網路的標誌。</span><span class="sxs-lookup"><span data-stu-id="f346a-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="f346a-135">string</span><span class="sxs-lookup"><span data-stu-id="f346a-135">string</span></span> | <span data-ttu-id="f346a-136">JSON 陣列格式的 DNS 伺服器位址</span><span class="sxs-lookup"><span data-stu-id="f346a-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="f346a-137">string</span><span class="sxs-lookup"><span data-stu-id="f346a-137">string</span></span> | <span data-ttu-id="f346a-138">DHCP 伺服器的 IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="f346a-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="f346a-139">string</span><span class="sxs-lookup"><span data-stu-id="f346a-139">string</span></span> | <span data-ttu-id="f346a-140">DHCP 伺服器的 IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="f346a-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="f346a-141">string</span><span class="sxs-lookup"><span data-stu-id="f346a-141">string</span></span> | <span data-ttu-id="f346a-142">以 JSON 陣列格式的預設閘道位址</span><span class="sxs-lookup"><span data-stu-id="f346a-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="f346a-143">string</span><span class="sxs-lookup"><span data-stu-id="f346a-143">string</span></span> | <span data-ttu-id="f346a-144">包含所有指派給該配接器之 IP 位址的 JSON 陣列，以及其各自的子網前置詞和 IP 位址空間，例如 public、private 或 link 本機。</span><span class="sxs-lookup"><span data-stu-id="f346a-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="f346a-145">long</span><span class="sxs-lookup"><span data-stu-id="f346a-145">long</span></span> | <span data-ttu-id="f346a-146">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="f346a-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f346a-147">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="f346a-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f346a-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="f346a-148">Related topics</span></span>
- [<span data-ttu-id="f346a-149">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="f346a-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f346a-150">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="f346a-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f346a-151">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="f346a-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f346a-152">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="f346a-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f346a-153">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="f346a-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f346a-154">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="f346a-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)