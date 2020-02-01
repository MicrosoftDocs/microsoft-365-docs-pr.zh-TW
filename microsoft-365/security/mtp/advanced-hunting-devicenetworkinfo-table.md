---
title: DeviceNetworkInfo 資料表中的進階的狩獵結構描述
description: 了解 DeviceNetworkInfo 表格中的進階的狩獵結構描述的網路組態資訊
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 machinenetworkinfo，DeviceNetworkInfo，裝置]，機器、 mac、 ip、 介面卡、 dns、 dhcp、 閘道、 通道
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
ms.openlocfilehash: 25349328cd128113de7846cba5c7c9ad74631092
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600410"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="03128-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="03128-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="03128-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03128-105">**Applies to:**</span></span>
- <span data-ttu-id="03128-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="03128-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="03128-107">`DeviceNetworkInfo` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含機器，包括網路介面卡、 IP 與 MAC 位址，並已連線的網路或網域的網路組態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="03128-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="03128-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="03128-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="03128-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03128-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="03128-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="03128-110">Column name</span></span> | <span data-ttu-id="03128-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="03128-111">Data type</span></span> | <span data-ttu-id="03128-112">描述</span><span class="sxs-lookup"><span data-stu-id="03128-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="03128-113">datetime</span><span class="sxs-lookup"><span data-stu-id="03128-113">datetime</span></span> | <span data-ttu-id="03128-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="03128-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="03128-115">字串</span><span class="sxs-lookup"><span data-stu-id="03128-115">string</span></span> | <span data-ttu-id="03128-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="03128-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="03128-117">string</span><span class="sxs-lookup"><span data-stu-id="03128-117">string</span></span> | <span data-ttu-id="03128-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="03128-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="03128-119">long</span><span class="sxs-lookup"><span data-stu-id="03128-119">long</span></span> | <span data-ttu-id="03128-120">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="03128-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="03128-121">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="03128-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="03128-122">string</span><span class="sxs-lookup"><span data-stu-id="03128-122">string</span></span> | <span data-ttu-id="03128-123">網路介面卡的名稱</span><span class="sxs-lookup"><span data-stu-id="03128-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="03128-124">string</span><span class="sxs-lookup"><span data-stu-id="03128-124">string</span></span> | <span data-ttu-id="03128-125">網路介面卡的 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="03128-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="03128-126">string</span><span class="sxs-lookup"><span data-stu-id="03128-126">string</span></span> | <span data-ttu-id="03128-127">網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="03128-127">Network adapter type.</span></span> <span data-ttu-id="03128-128">可能的值，請參閱[此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="03128-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="03128-129">string</span><span class="sxs-lookup"><span data-stu-id="03128-129">string</span></span> | <span data-ttu-id="03128-130">網路介面卡的作業狀態。</span><span class="sxs-lookup"><span data-stu-id="03128-130">Operational status of the network adapter.</span></span> <span data-ttu-id="03128-131">可能的值，請參閱[此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="03128-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="03128-132">string</span><span class="sxs-lookup"><span data-stu-id="03128-132">string</span></span> | <span data-ttu-id="03128-133">通道通訊協定，如果介面可用於此目的，例如 6to4、 Teredo、 ISATAP、 PPTP、 SSTP 及 SSH</span><span class="sxs-lookup"><span data-stu-id="03128-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="03128-134">string</span><span class="sxs-lookup"><span data-stu-id="03128-134">string</span></span> | <span data-ttu-id="03128-135">網路介面卡所連接的連接。</span><span class="sxs-lookup"><span data-stu-id="03128-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="03128-136">每一個 JSON 陣列包含的網路名稱、 類別 （公用、 私用或網域）、 描述及旗標，指出是否它連線公開至網際網路</span><span class="sxs-lookup"><span data-stu-id="03128-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="03128-137">string</span><span class="sxs-lookup"><span data-stu-id="03128-137">string</span></span> | <span data-ttu-id="03128-138">DNS 伺服器位址，以 JSON 陣列格式</span><span class="sxs-lookup"><span data-stu-id="03128-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="03128-139">string</span><span class="sxs-lookup"><span data-stu-id="03128-139">string</span></span> | <span data-ttu-id="03128-140">DHCP 伺服器的 IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="03128-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="03128-141">string</span><span class="sxs-lookup"><span data-stu-id="03128-141">string</span></span> | <span data-ttu-id="03128-142">IPv6 位址的 DHCP 伺服器</span><span class="sxs-lookup"><span data-stu-id="03128-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="03128-143">string</span><span class="sxs-lookup"><span data-stu-id="03128-143">string</span></span> | <span data-ttu-id="03128-144">以 JSON 陣列格式的預設閘道地址</span><span class="sxs-lookup"><span data-stu-id="03128-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="03128-145">string</span><span class="sxs-lookup"><span data-stu-id="03128-145">string</span></span> | <span data-ttu-id="03128-146">JSON 陣列，其中包含所有指派給介面卡，以及其各自的子網路前置詞和 IP 位址空間，例如公用、 私用] 或連結-本機的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="03128-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="03128-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="03128-147">Related topics</span></span>
- [<span data-ttu-id="03128-148">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="03128-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="03128-149">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="03128-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="03128-150">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="03128-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="03128-151">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="03128-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="03128-152">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="03128-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="03128-153">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="03128-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
