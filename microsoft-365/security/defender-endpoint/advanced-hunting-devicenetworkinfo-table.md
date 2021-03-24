---
title: Advanced 搜尋架構中的 DeviceNetworkInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceNetworkInfo 資料表中的網路設定資訊
keywords: 「高級搜尋」、「威脅搜尋」、「搜尋」、「搜尋」、「查詢」、「架構參考」、「搜尋」、「表格」、「資料類型」、「描述」、「kusto」、「裝置」、「mac」、「ip」、「配接器」、「dns」
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059788"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="12f97-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="12f97-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12f97-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="12f97-105">**Applies to:**</span></span>
- [<span data-ttu-id="12f97-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="12f97-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="12f97-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="12f97-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="12f97-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="12f97-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="12f97-109">[！附注] `DeviceNetworkInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含裝置之網路設定的相關資訊，包括網路介面卡、IP 及 MAC 位址，以及連線的網路或網域。</span><span class="sxs-lookup"><span data-stu-id="12f97-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="12f97-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="12f97-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="12f97-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="12f97-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="12f97-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="12f97-112">Column name</span></span> | <span data-ttu-id="12f97-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="12f97-113">Data type</span></span> | <span data-ttu-id="12f97-114">描述</span><span class="sxs-lookup"><span data-stu-id="12f97-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="12f97-115">datetime</span><span class="sxs-lookup"><span data-stu-id="12f97-115">datetime</span></span> | <span data-ttu-id="12f97-116">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="12f97-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="12f97-117">string</span><span class="sxs-lookup"><span data-stu-id="12f97-117">string</span></span> | <span data-ttu-id="12f97-118">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="12f97-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="12f97-119">string</span><span class="sxs-lookup"><span data-stu-id="12f97-119">string</span></span> | <span data-ttu-id="12f97-120">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="12f97-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="12f97-121">long</span><span class="sxs-lookup"><span data-stu-id="12f97-121">long</span></span> | <span data-ttu-id="12f97-122">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="12f97-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="12f97-123">若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用</span><span class="sxs-lookup"><span data-stu-id="12f97-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="12f97-124">string</span><span class="sxs-lookup"><span data-stu-id="12f97-124">string</span></span> | <span data-ttu-id="12f97-125">網路介面卡的名稱</span><span class="sxs-lookup"><span data-stu-id="12f97-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="12f97-126">string</span><span class="sxs-lookup"><span data-stu-id="12f97-126">string</span></span> | <span data-ttu-id="12f97-127">網路介面卡的 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="12f97-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="12f97-128">string</span><span class="sxs-lookup"><span data-stu-id="12f97-128">string</span></span> | <span data-ttu-id="12f97-129">網路介面卡類型。</span><span class="sxs-lookup"><span data-stu-id="12f97-129">Network adapter type.</span></span> <span data-ttu-id="12f97-130">如需可能的值，請參閱 [this 列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="12f97-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="12f97-131">string</span><span class="sxs-lookup"><span data-stu-id="12f97-131">string</span></span> | <span data-ttu-id="12f97-132">網路介面卡的運作狀態。</span><span class="sxs-lookup"><span data-stu-id="12f97-132">Operational status of the network adapter.</span></span> <span data-ttu-id="12f97-133">如需可能的值，請參閱 [this 列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="12f97-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="12f97-134">string</span><span class="sxs-lookup"><span data-stu-id="12f97-134">string</span></span> | <span data-ttu-id="12f97-135">隧道通訊協定，如果此介面是用於此用途，例如6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH</span><span class="sxs-lookup"><span data-stu-id="12f97-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="12f97-136">string</span><span class="sxs-lookup"><span data-stu-id="12f97-136">string</span></span> | <span data-ttu-id="12f97-137">連接到配接器的網路。</span><span class="sxs-lookup"><span data-stu-id="12f97-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="12f97-138">每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述及表明其是否已公開連接到網際網路的標誌。</span><span class="sxs-lookup"><span data-stu-id="12f97-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="12f97-139">string</span><span class="sxs-lookup"><span data-stu-id="12f97-139">string</span></span> | <span data-ttu-id="12f97-140">JSON 陣列格式的 DNS 伺服器位址</span><span class="sxs-lookup"><span data-stu-id="12f97-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="12f97-141">string</span><span class="sxs-lookup"><span data-stu-id="12f97-141">string</span></span> | <span data-ttu-id="12f97-142">DHCP 伺服器的 IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="12f97-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="12f97-143">string</span><span class="sxs-lookup"><span data-stu-id="12f97-143">string</span></span> | <span data-ttu-id="12f97-144">DHCP 伺服器的 IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="12f97-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="12f97-145">string</span><span class="sxs-lookup"><span data-stu-id="12f97-145">string</span></span> | <span data-ttu-id="12f97-146">以 JSON 陣列格式的預設閘道位址</span><span class="sxs-lookup"><span data-stu-id="12f97-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="12f97-147">string</span><span class="sxs-lookup"><span data-stu-id="12f97-147">string</span></span> | <span data-ttu-id="12f97-148">包含所有指派給該配接器之 IP 位址的 JSON 陣列，以及其各自的子網前置詞和 IP 位址空間，例如 public、private 或 link 本機。</span><span class="sxs-lookup"><span data-stu-id="12f97-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="12f97-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="12f97-149">Related topics</span></span>
- [<span data-ttu-id="12f97-150">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="12f97-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="12f97-151">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="12f97-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="12f97-152">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="12f97-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
