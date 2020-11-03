---
title: Advanced 搜尋架構中的 DeviceNetworkInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceNetworkInfo 資料表中的網路設定資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，machinenetworkinfo，DeviceNetworkInfo，device，dhcp，adapter，隧道
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 92856d3f077d3bfe49a3b25f50965aa1c03ebdb0
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842651"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="7b6f9-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="7b6f9-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7b6f9-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="7b6f9-105">**Applies to:**</span></span>
- <span data-ttu-id="7b6f9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b6f9-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="7b6f9-107">[！附注] `DeviceNetworkInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含電腦網路設定的相關資訊，包括網路介面卡、IP 及 MAC 位址，以及連線的網路或網域。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="7b6f9-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7b6f9-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7b6f9-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="7b6f9-110">Column name</span></span> | <span data-ttu-id="7b6f9-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="7b6f9-111">Data type</span></span> | <span data-ttu-id="7b6f9-112">描述</span><span class="sxs-lookup"><span data-stu-id="7b6f9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7b6f9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7b6f9-113">datetime</span></span> | <span data-ttu-id="7b6f9-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="7b6f9-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7b6f9-115">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-115">string</span></span> | <span data-ttu-id="7b6f9-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="7b6f9-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7b6f9-117">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-117">string</span></span> | <span data-ttu-id="7b6f9-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="7b6f9-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="7b6f9-119">long</span><span class="sxs-lookup"><span data-stu-id="7b6f9-119">long</span></span> | <span data-ttu-id="7b6f9-120">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7b6f9-121">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="7b6f9-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="7b6f9-122">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-122">string</span></span> | <span data-ttu-id="7b6f9-123">網路介面卡的名稱</span><span class="sxs-lookup"><span data-stu-id="7b6f9-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="7b6f9-124">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-124">string</span></span> | <span data-ttu-id="7b6f9-125">網路介面卡的 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="7b6f9-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="7b6f9-126">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-126">string</span></span> | <span data-ttu-id="7b6f9-127">網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-127">Network adapter type.</span></span> <span data-ttu-id="7b6f9-128">如需可能的值，請參閱 [this 列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="7b6f9-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="7b6f9-129">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-129">string</span></span> | <span data-ttu-id="7b6f9-130">網路介面卡的運作狀態。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-130">Operational status of the network adapter.</span></span> <span data-ttu-id="7b6f9-131">如需可能的值，請參閱 [this 列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="7b6f9-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="7b6f9-132">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-132">string</span></span> | <span data-ttu-id="7b6f9-133">隧道通訊協定，如果此介面是用於此用途，例如6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH</span><span class="sxs-lookup"><span data-stu-id="7b6f9-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="7b6f9-134">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-134">string</span></span> | <span data-ttu-id="7b6f9-135">連接到配接器的網路。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="7b6f9-136">每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述及表明其是否已公開連接到網際網路的標誌。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="7b6f9-137">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-137">string</span></span> | <span data-ttu-id="7b6f9-138">JSON 陣列格式的 DNS 伺服器位址</span><span class="sxs-lookup"><span data-stu-id="7b6f9-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="7b6f9-139">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-139">string</span></span> | <span data-ttu-id="7b6f9-140">DHCP 伺服器的 IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="7b6f9-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="7b6f9-141">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-141">string</span></span> | <span data-ttu-id="7b6f9-142">DHCP 伺服器的 IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="7b6f9-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="7b6f9-143">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-143">string</span></span> | <span data-ttu-id="7b6f9-144">以 JSON 陣列格式的預設閘道位址</span><span class="sxs-lookup"><span data-stu-id="7b6f9-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="7b6f9-145">string</span><span class="sxs-lookup"><span data-stu-id="7b6f9-145">string</span></span> | <span data-ttu-id="7b6f9-146">包含所有指派給該配接器之 IP 位址的 JSON 陣列，以及其各自的子網前置詞和 IP 位址空間，例如 public、private 或 link 本機。</span><span class="sxs-lookup"><span data-stu-id="7b6f9-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7b6f9-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="7b6f9-147">Related topics</span></span>
- [<span data-ttu-id="7b6f9-148">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="7b6f9-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7b6f9-149">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="7b6f9-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7b6f9-150">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="7b6f9-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7b6f9-151">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="7b6f9-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7b6f9-152">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="7b6f9-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7b6f9-153">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="7b6f9-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
