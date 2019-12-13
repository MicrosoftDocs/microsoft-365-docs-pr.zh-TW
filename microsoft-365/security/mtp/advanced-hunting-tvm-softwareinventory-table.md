---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareInventoryVulnerabilities 表格
description: 了解裝置中的軟體清單及其在進階搜捕結構描述之 DeviceTvmSoftwareInventoryVulnerabilities 表格中的弱點。
keywords: 進階搜捕、威脅搜捕、網路威脅搜捕、搜尋、查詢、遙測、結構描述參考、Kusto、表格、欄、資料類型、描述、威脅與弱點管理、問題管理、TVM、裝置管理、軟體、庫存、弱點、CVE 識別碼、OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f7c7ab393a956aa894a0ca8704ea0e99a82addc9
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910888"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="bedb9-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="bedb9-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="bedb9-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="bedb9-105">**Applies to:**</span></span>
- <span data-ttu-id="bedb9-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bedb9-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="bedb9-107">進階搜捕結構描述中的 `DeviceTvmSoftwareInventoryVulnerabilities` 表格包含裝置上軟體庫存的 [威脅與弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)，以及這些軟體產品中的任何已知弱點。</span><span class="sxs-lookup"><span data-stu-id="bedb9-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="bedb9-108">本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。</span><span class="sxs-lookup"><span data-stu-id="bedb9-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="bedb9-109">使用這個參照來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="bedb9-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="bedb9-110">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="bedb9-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="bedb9-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="bedb9-111">Column name</span></span> | <span data-ttu-id="bedb9-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="bedb9-112">Data type</span></span> | <span data-ttu-id="bedb9-113">描述</span><span class="sxs-lookup"><span data-stu-id="bedb9-113">Description</span></span> |
|-------------|-----------|-------------|
| `MachineId` | <span data-ttu-id="bedb9-114">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-114">string</span></span> | <span data-ttu-id="bedb9-115">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="bedb9-115">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="bedb9-116">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-116">string</span></span> | <span data-ttu-id="bedb9-117">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="bedb9-117">Fully qualified domain name (FQDN) of the pool</span></span> |
| `OSPlatform` | <span data-ttu-id="bedb9-118">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-118">string</span></span> | <span data-ttu-id="bedb9-119">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="bedb9-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="bedb9-120">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="bedb9-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="bedb9-121">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-121">string</span></span> | <span data-ttu-id="bedb9-122">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="bedb9-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="bedb9-123">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-123">string</span></span> | <span data-ttu-id="bedb9-124">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="bedb9-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="bedb9-125">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-125">string</span></span> | <span data-ttu-id="bedb9-126">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="bedb9-126">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `SoftwareName` | <span data-ttu-id="bedb9-127">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-127">string</span></span> | <span data-ttu-id="bedb9-128">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="bedb9-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="bedb9-129">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-129">string</span></span> | <span data-ttu-id="bedb9-130">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="bedb9-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="bedb9-131">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-131">string</span></span> | <span data-ttu-id="bedb9-132">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="bedb9-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="bedb9-133">字串</span><span class="sxs-lookup"><span data-stu-id="bedb9-133">string</span></span> | <span data-ttu-id="bedb9-134">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="bedb9-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="bedb9-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="bedb9-135">Related topics</span></span>

- [<span data-ttu-id="bedb9-136">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="bedb9-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bedb9-137">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="bedb9-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bedb9-138">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="bedb9-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bedb9-139">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="bedb9-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bedb9-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="bedb9-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bedb9-141">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="bedb9-141">Apply design best practices.</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="bedb9-142">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="bedb9-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
