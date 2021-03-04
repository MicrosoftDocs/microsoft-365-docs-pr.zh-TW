---
title: Advanced 搜尋架構中的 DeviceTvmSoftwareVulnerabilities 表格
description: 深入瞭解在裝置上找到的軟體弱點，以及可在高級搜尋架構的 DeviceTvmSoftwareVulnerabilities 資料表中處理每個弱點的可用安全性更新清單。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 漏洞管理、TVM、裝置管理、軟體、清查、弱點、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: c5a143d835120339ade006dfd2dc394ec7c542d3
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423870"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="a4d67-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="a4d67-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a4d67-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="a4d67-105">**Applies to:**</span></span>
- <span data-ttu-id="a4d67-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4d67-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="a4d67-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="a4d67-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a4d67-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a4d67-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a4d67-109">「 `DeviceTvmSoftwareVulnerabilities` 高級搜尋」架構中的表格包含已安裝軟體產品中弱點的 [威脅 & 漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 清單。</span><span class="sxs-lookup"><span data-stu-id="a4d67-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="a4d67-110">本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4d67-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="a4d67-111">例如，您可以使用此表格來搜尋有關其軟體中有嚴重弱點之裝置的事件。</span><span class="sxs-lookup"><span data-stu-id="a4d67-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="a4d67-112">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="a4d67-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="a4d67-113">`DeviceTvmSoftwareInventory`和 `DeviceTvmSoftwareVulnerabilities` tables 已取代 `DeviceTvmSoftwareInventoryVulnerabilities` 表格。</span><span class="sxs-lookup"><span data-stu-id="a4d67-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="a4d67-114">前兩個表格一起包含更多的資料行，可協助您通知 vulnerablity 管理活動或尋找易受攻擊的裝置。</span><span class="sxs-lookup"><span data-stu-id="a4d67-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="a4d67-115">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d67-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a4d67-116">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="a4d67-116">Column name</span></span> | <span data-ttu-id="a4d67-117">資料類型</span><span class="sxs-lookup"><span data-stu-id="a4d67-117">Data type</span></span> | <span data-ttu-id="a4d67-118">描述</span><span class="sxs-lookup"><span data-stu-id="a4d67-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="a4d67-119">string</span><span class="sxs-lookup"><span data-stu-id="a4d67-119">string</span></span> | <span data-ttu-id="a4d67-120">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="a4d67-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a4d67-121">string</span><span class="sxs-lookup"><span data-stu-id="a4d67-121">string</span></span> | <span data-ttu-id="a4d67-122">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a4d67-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="a4d67-123">string</span><span class="sxs-lookup"><span data-stu-id="a4d67-123">string</span></span> | <span data-ttu-id="a4d67-124">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="a4d67-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="a4d67-125">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="a4d67-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="a4d67-126">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-126">string</span></span> | <span data-ttu-id="a4d67-127">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="a4d67-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="a4d67-128">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-128">string</span></span> | <span data-ttu-id="a4d67-129">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="a4d67-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="a4d67-130">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-130">string</span></span> | <span data-ttu-id="a4d67-131">軟體廠商的名稱</span><span class="sxs-lookup"><span data-stu-id="a4d67-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="a4d67-132">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-132">string</span></span> | <span data-ttu-id="a4d67-133">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="a4d67-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="a4d67-134">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-134">string</span></span> | <span data-ttu-id="a4d67-135">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="a4d67-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="a4d67-136">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-136">string</span></span> | <span data-ttu-id="a4d67-137">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="a4d67-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="a4d67-138">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-138">string</span></span> | <span data-ttu-id="a4d67-139">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="a4d67-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="a4d67-140">字串</span><span class="sxs-lookup"><span data-stu-id="a4d67-140">string</span></span> | <span data-ttu-id="a4d67-141">軟體廠商提供的安全性更新名稱或描述，以解決此弱點</span><span class="sxs-lookup"><span data-stu-id="a4d67-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="a4d67-142">string</span><span class="sxs-lookup"><span data-stu-id="a4d67-142">string</span></span> | <span data-ttu-id="a4d67-143">對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼</span><span class="sxs-lookup"><span data-stu-id="a4d67-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="a4d67-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="a4d67-144">Related topics</span></span>

- [<span data-ttu-id="a4d67-145">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="a4d67-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a4d67-146">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="a4d67-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a4d67-147">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="a4d67-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a4d67-148">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="a4d67-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a4d67-149">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="a4d67-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a4d67-150">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="a4d67-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a4d67-151">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="a4d67-151">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
