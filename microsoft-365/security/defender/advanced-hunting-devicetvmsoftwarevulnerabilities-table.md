---
title: Advanced 搜尋架構中的 DeviceTvmSoftwareVulnerabilities 表格
description: 深入瞭解在裝置上找到的軟體弱點，以及可在高級搜尋架構的 DeviceTvmSoftwareVulnerabilities 資料表中處理每個弱點的可用安全性更新清單。
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023806"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="3df72-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="3df72-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3df72-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3df72-105">**Applies to:**</span></span>
- <span data-ttu-id="3df72-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3df72-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="3df72-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3df72-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3df72-108">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="3df72-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3df72-109">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="3df72-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3df72-110">「 `DeviceTvmSoftwareVulnerabilities` 高級搜尋」架構中的表格包含已安裝軟體產品中弱點的 [威脅 & 漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 清單。</span><span class="sxs-lookup"><span data-stu-id="3df72-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="3df72-111">本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。</span><span class="sxs-lookup"><span data-stu-id="3df72-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="3df72-112">例如，您可以使用此表格來搜尋有關其軟體中有嚴重弱點之裝置的事件。</span><span class="sxs-lookup"><span data-stu-id="3df72-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="3df72-113">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="3df72-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="3df72-114">`DeviceTvmSoftwareInventory`和 `DeviceTvmSoftwareVulnerabilities` tables 已取代 `DeviceTvmSoftwareInventoryVulnerabilities` 表格。</span><span class="sxs-lookup"><span data-stu-id="3df72-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="3df72-115">前兩個表格一起包含更多的資料行，可協助您通知 vulnerablity 管理活動或尋找易受攻擊的裝置。</span><span class="sxs-lookup"><span data-stu-id="3df72-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="3df72-116">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="3df72-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3df72-117">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="3df72-117">Column name</span></span> | <span data-ttu-id="3df72-118">資料類型</span><span class="sxs-lookup"><span data-stu-id="3df72-118">Data type</span></span> | <span data-ttu-id="3df72-119">描述</span><span class="sxs-lookup"><span data-stu-id="3df72-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="3df72-120">string</span><span class="sxs-lookup"><span data-stu-id="3df72-120">string</span></span> | <span data-ttu-id="3df72-121">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="3df72-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3df72-122">string</span><span class="sxs-lookup"><span data-stu-id="3df72-122">string</span></span> | <span data-ttu-id="3df72-123">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="3df72-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="3df72-124">string</span><span class="sxs-lookup"><span data-stu-id="3df72-124">string</span></span> | <span data-ttu-id="3df72-125">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="3df72-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="3df72-126">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="3df72-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="3df72-127">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-127">string</span></span> | <span data-ttu-id="3df72-128">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="3df72-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="3df72-129">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-129">string</span></span> | <span data-ttu-id="3df72-130">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="3df72-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="3df72-131">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-131">string</span></span> | <span data-ttu-id="3df72-132">軟體廠商的名稱</span><span class="sxs-lookup"><span data-stu-id="3df72-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="3df72-133">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-133">string</span></span> | <span data-ttu-id="3df72-134">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="3df72-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="3df72-135">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-135">string</span></span> | <span data-ttu-id="3df72-136">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="3df72-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="3df72-137">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-137">string</span></span> | <span data-ttu-id="3df72-138">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="3df72-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="3df72-139">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-139">string</span></span> | <span data-ttu-id="3df72-140">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="3df72-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="3df72-141">字串</span><span class="sxs-lookup"><span data-stu-id="3df72-141">string</span></span> | <span data-ttu-id="3df72-142">軟體廠商提供的安全性更新名稱或描述，以解決此弱點</span><span class="sxs-lookup"><span data-stu-id="3df72-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="3df72-143">string</span><span class="sxs-lookup"><span data-stu-id="3df72-143">string</span></span> | <span data-ttu-id="3df72-144">對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼</span><span class="sxs-lookup"><span data-stu-id="3df72-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="3df72-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="3df72-145">Related topics</span></span>

- [<span data-ttu-id="3df72-146">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="3df72-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3df72-147">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="3df72-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3df72-148">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="3df72-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3df72-149">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="3df72-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3df72-150">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="3df72-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3df72-151">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="3df72-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3df72-152">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="3df72-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)