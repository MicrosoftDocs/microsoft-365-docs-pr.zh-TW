---
title: Advanced 搜尋架構中的 DeviceNetworkInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceNetworkInfo 資料表中的網路設定資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，machinenetworkinfo，DeviceNetworkInfo，device，dhcp，adapter，隧道
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
ms.openlocfilehash: 3e3b657d1c33e411f38a8f583adb96139cc85207
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907393"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="178de-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="178de-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="178de-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="178de-105">**Applies to:**</span></span>
- <span data-ttu-id="178de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="178de-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="178de-107">[！附注] `DeviceNetworkInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含電腦網路設定的相關資訊，包括網路介面卡、IP 及 MAC 位址，以及連線的網路或網域。</span><span class="sxs-lookup"><span data-stu-id="178de-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="178de-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="178de-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="178de-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="178de-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="178de-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="178de-110">Column name</span></span> | <span data-ttu-id="178de-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="178de-111">Data type</span></span> | <span data-ttu-id="178de-112">描述</span><span class="sxs-lookup"><span data-stu-id="178de-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="178de-113">datetime</span><span class="sxs-lookup"><span data-stu-id="178de-113">datetime</span></span> | <span data-ttu-id="178de-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="178de-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="178de-115">string</span><span class="sxs-lookup"><span data-stu-id="178de-115">string</span></span> | <span data-ttu-id="178de-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="178de-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="178de-117">string</span><span class="sxs-lookup"><span data-stu-id="178de-117">string</span></span> | <span data-ttu-id="178de-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="178de-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="178de-119">long</span><span class="sxs-lookup"><span data-stu-id="178de-119">long</span></span> | <span data-ttu-id="178de-120">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="178de-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="178de-121">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="178de-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="178de-122">string</span><span class="sxs-lookup"><span data-stu-id="178de-122">string</span></span> | <span data-ttu-id="178de-123">網路介面卡的名稱</span><span class="sxs-lookup"><span data-stu-id="178de-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="178de-124">string</span><span class="sxs-lookup"><span data-stu-id="178de-124">string</span></span> | <span data-ttu-id="178de-125">網路介面卡的 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="178de-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="178de-126">string</span><span class="sxs-lookup"><span data-stu-id="178de-126">string</span></span> | <span data-ttu-id="178de-127">網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="178de-127">Network adapter type.</span></span> <span data-ttu-id="178de-128">如需可能的值，請參閱 [this 列舉](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="178de-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="178de-129">string</span><span class="sxs-lookup"><span data-stu-id="178de-129">string</span></span> | <span data-ttu-id="178de-130">網路介面卡的運作狀態。</span><span class="sxs-lookup"><span data-stu-id="178de-130">Operational status of the network adapter.</span></span> <span data-ttu-id="178de-131">如需可能的值，請參閱 [this 列舉](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="178de-131">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="178de-132">string</span><span class="sxs-lookup"><span data-stu-id="178de-132">string</span></span> | <span data-ttu-id="178de-133">隧道通訊協定，如果此介面是用於此用途，例如6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH</span><span class="sxs-lookup"><span data-stu-id="178de-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="178de-134">string</span><span class="sxs-lookup"><span data-stu-id="178de-134">string</span></span> | <span data-ttu-id="178de-135">連接到配接器的網路。</span><span class="sxs-lookup"><span data-stu-id="178de-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="178de-136">每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述及表明其是否已公開連接到網際網路的標誌。</span><span class="sxs-lookup"><span data-stu-id="178de-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="178de-137">string</span><span class="sxs-lookup"><span data-stu-id="178de-137">string</span></span> | <span data-ttu-id="178de-138">JSON 陣列格式的 DNS 伺服器位址</span><span class="sxs-lookup"><span data-stu-id="178de-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="178de-139">string</span><span class="sxs-lookup"><span data-stu-id="178de-139">string</span></span> | <span data-ttu-id="178de-140">DHCP 伺服器的 IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="178de-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="178de-141">string</span><span class="sxs-lookup"><span data-stu-id="178de-141">string</span></span> | <span data-ttu-id="178de-142">DHCP 伺服器的 IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="178de-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="178de-143">string</span><span class="sxs-lookup"><span data-stu-id="178de-143">string</span></span> | <span data-ttu-id="178de-144">以 JSON 陣列格式的預設閘道位址</span><span class="sxs-lookup"><span data-stu-id="178de-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="178de-145">string</span><span class="sxs-lookup"><span data-stu-id="178de-145">string</span></span> | <span data-ttu-id="178de-146">包含所有指派給該配接器之 IP 位址的 JSON 陣列，以及其各自的子網前置詞和 IP 位址空間，例如 public、private 或 link 本機。</span><span class="sxs-lookup"><span data-stu-id="178de-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="178de-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="178de-147">Related topics</span></span>
- [<span data-ttu-id="178de-148">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="178de-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="178de-149">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="178de-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="178de-150">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="178de-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="178de-151">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="178de-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="178de-152">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="178de-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="178de-153">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="178de-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)