---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareInventoryVulnerabilities 表格
description: 了解裝置中的軟體清單及其在進階搜捕結構描述之 DeviceTvmSoftwareInventoryVulnerabilities 表格中的弱點。
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 弱點管理、TVM、裝置管理、軟體、庫存、弱點、CVE ID、OS DevicePvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 517f974657032a1a4b7fee5888b0c681ec8063d7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931071"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="2b547-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="2b547-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2b547-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="2b547-105">**Applies to:**</span></span>
- <span data-ttu-id="2b547-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b547-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="2b547-107">進階搜捕結構描述中的 `DeviceTvmSoftwareInventoryVulnerabilities` 表格包含裝置上軟體庫存的 [威脅與弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)，以及這些軟體產品中的任何已知弱點。</span><span class="sxs-lookup"><span data-stu-id="2b547-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="2b547-108">本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。</span><span class="sxs-lookup"><span data-stu-id="2b547-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="2b547-109">使用這個參照來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="2b547-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="2b547-110">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="2b547-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2b547-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="2b547-111">Column name</span></span> | <span data-ttu-id="2b547-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="2b547-112">Data type</span></span> | <span data-ttu-id="2b547-113">描述</span><span class="sxs-lookup"><span data-stu-id="2b547-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2b547-114">string</span><span class="sxs-lookup"><span data-stu-id="2b547-114">string</span></span> | <span data-ttu-id="2b547-115">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="2b547-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2b547-116">string</span><span class="sxs-lookup"><span data-stu-id="2b547-116">string</span></span> | <span data-ttu-id="2b547-117">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2b547-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="2b547-118">string</span><span class="sxs-lookup"><span data-stu-id="2b547-118">string</span></span> | <span data-ttu-id="2b547-119">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="2b547-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="2b547-120">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="2b547-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="2b547-121">字串</span><span class="sxs-lookup"><span data-stu-id="2b547-121">string</span></span> | <span data-ttu-id="2b547-122">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="2b547-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="2b547-123">字串</span><span class="sxs-lookup"><span data-stu-id="2b547-123">string</span></span> | <span data-ttu-id="2b547-124">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="2b547-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="2b547-125">字串</span><span class="sxs-lookup"><span data-stu-id="2b547-125">string</span></span> | <span data-ttu-id="2b547-126">軟體廠商名稱</span><span class="sxs-lookup"><span data-stu-id="2b547-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="2b547-127">字串</span><span class="sxs-lookup"><span data-stu-id="2b547-127">string</span></span> | <span data-ttu-id="2b547-128">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="2b547-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="2b547-129">字串</span><span class="sxs-lookup"><span data-stu-id="2b547-129">string</span></span> | <span data-ttu-id="2b547-130">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="2b547-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="2b547-131">字串</span><span class="sxs-lookup"><span data-stu-id="2b547-131">string</span></span> | <span data-ttu-id="2b547-132">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="2b547-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="2b547-133">字串</span><span class="sxs-lookup"><span data-stu-id="2b547-133">string</span></span> | <span data-ttu-id="2b547-134">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="2b547-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="2b547-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="2b547-135">Related topics</span></span>

- [<span data-ttu-id="2b547-136">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="2b547-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2b547-137">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="2b547-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2b547-138">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="2b547-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2b547-139">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="2b547-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2b547-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="2b547-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2b547-141">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="2b547-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2b547-142">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="2b547-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
