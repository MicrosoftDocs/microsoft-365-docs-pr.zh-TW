---
title: Advanced 搜尋架構中的 DeviceTvmSoftwareInventory 表格
description: 深入瞭解在高級搜尋架構的 DeviceTvmSoftwareInventory 資料表中，裝置中的軟體清單。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，資料類型，描述，威脅 & 弱點管理，TVM，裝置管理，軟體，清查，漏洞，CVE ID，作業系統 DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024226"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="49b9f-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="49b9f-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="49b9f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="49b9f-105">**Applies to:**</span></span>
- <span data-ttu-id="49b9f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49b9f-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="49b9f-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="49b9f-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="49b9f-108">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="49b9f-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="49b9f-109">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="49b9f-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="49b9f-110">「 `DeviceTvmSoftwareInventory` 高級搜尋」架構中的表格包含目前安裝在網路裝置上之軟體的 [威脅 & 漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 清單，包括支援資訊的結束。</span><span class="sxs-lookup"><span data-stu-id="49b9f-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="49b9f-111">例如，您可以針對與目前具有漏洞軟體版本一起安裝的裝置，尋找相關事件。</span><span class="sxs-lookup"><span data-stu-id="49b9f-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="49b9f-112">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="49b9f-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="49b9f-113">`DeviceTvmSoftwareInventory`和 `DeviceTvmSoftwareVulnerabilities` tables 已取代 `DeviceTvmSoftwareInventoryVulnerabilities` 表格。</span><span class="sxs-lookup"><span data-stu-id="49b9f-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="49b9f-114">前兩個表格一起包含更多的資料行，可協助您通知 vulnerablity 管理活動或尋找易受攻擊的裝置。</span><span class="sxs-lookup"><span data-stu-id="49b9f-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="49b9f-115">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="49b9f-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="49b9f-116">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="49b9f-116">Column name</span></span> | <span data-ttu-id="49b9f-117">資料類型</span><span class="sxs-lookup"><span data-stu-id="49b9f-117">Data type</span></span> | <span data-ttu-id="49b9f-118">描述</span><span class="sxs-lookup"><span data-stu-id="49b9f-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="49b9f-119">string</span><span class="sxs-lookup"><span data-stu-id="49b9f-119">string</span></span> | <span data-ttu-id="49b9f-120">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="49b9f-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="49b9f-121">string</span><span class="sxs-lookup"><span data-stu-id="49b9f-121">string</span></span> | <span data-ttu-id="49b9f-122">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="49b9f-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="49b9f-123">string</span><span class="sxs-lookup"><span data-stu-id="49b9f-123">string</span></span> | <span data-ttu-id="49b9f-124">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="49b9f-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="49b9f-125">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="49b9f-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="49b9f-126">字串</span><span class="sxs-lookup"><span data-stu-id="49b9f-126">string</span></span> | <span data-ttu-id="49b9f-127">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="49b9f-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="49b9f-128">字串</span><span class="sxs-lookup"><span data-stu-id="49b9f-128">string</span></span> | <span data-ttu-id="49b9f-129">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="49b9f-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="49b9f-130">字串</span><span class="sxs-lookup"><span data-stu-id="49b9f-130">string</span></span> | <span data-ttu-id="49b9f-131">軟體廠商的名稱</span><span class="sxs-lookup"><span data-stu-id="49b9f-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="49b9f-132">字串</span><span class="sxs-lookup"><span data-stu-id="49b9f-132">string</span></span> | <span data-ttu-id="49b9f-133">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="49b9f-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="49b9f-134">字串</span><span class="sxs-lookup"><span data-stu-id="49b9f-134">string</span></span> | <span data-ttu-id="49b9f-135">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="49b9f-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="49b9f-136">字串</span><span class="sxs-lookup"><span data-stu-id="49b9f-136">string</span></span> | <span data-ttu-id="49b9f-137">會指出軟體產品的生命週期階段相對於其指定的支援終止 (EOS) 或生命週期 (EOL) 日期</span><span class="sxs-lookup"><span data-stu-id="49b9f-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="49b9f-138">string</span><span class="sxs-lookup"><span data-stu-id="49b9f-138">string</span></span> | <span data-ttu-id="49b9f-139">支援終止 (EOS) 或使用壽命結束 (EOL) 軟體產品的日期</span><span class="sxs-lookup"><span data-stu-id="49b9f-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="49b9f-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="49b9f-140">Related topics</span></span>

- [<span data-ttu-id="49b9f-141">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="49b9f-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="49b9f-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="49b9f-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="49b9f-143">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="49b9f-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="49b9f-144">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="49b9f-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="49b9f-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="49b9f-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="49b9f-146">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="49b9f-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="49b9f-147">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="49b9f-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)