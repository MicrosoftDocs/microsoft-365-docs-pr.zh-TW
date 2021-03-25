---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareInventoryVulnerabilities 表格
description: 了解裝置中的軟體清單及其在進階搜捕結構描述之 DeviceTvmSoftwareInventoryVulnerabilities 表格中的弱點。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、table、column、data type、description、威脅 & 漏洞管理、TVM、裝置管理、軟體、清查、弱點、CVE 識別碼、OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163456"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="06025-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="06025-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="06025-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="06025-105">**Applies to:**</span></span>

- [<span data-ttu-id="06025-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="06025-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="06025-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="06025-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="06025-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="06025-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="06025-109">進階搜捕結構描述中的 `DeviceTvmSoftwareInventoryVulnerabilities` 表格包含裝置上軟體庫存的 [威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)，以及這些軟體產品中的任何已知弱點。</span><span class="sxs-lookup"><span data-stu-id="06025-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="06025-110">本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。</span><span class="sxs-lookup"><span data-stu-id="06025-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="06025-111">使用這個參照來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="06025-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="06025-112">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="06025-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="06025-113">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="06025-113">Column name</span></span> | <span data-ttu-id="06025-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="06025-114">Data type</span></span> | <span data-ttu-id="06025-115">描述</span><span class="sxs-lookup"><span data-stu-id="06025-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="06025-116">string</span><span class="sxs-lookup"><span data-stu-id="06025-116">string</span></span> | <span data-ttu-id="06025-117">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="06025-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="06025-118">string</span><span class="sxs-lookup"><span data-stu-id="06025-118">string</span></span> | <span data-ttu-id="06025-119">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="06025-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="06025-120">string</span><span class="sxs-lookup"><span data-stu-id="06025-120">string</span></span> | <span data-ttu-id="06025-121">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="06025-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="06025-122">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="06025-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="06025-123">字串</span><span class="sxs-lookup"><span data-stu-id="06025-123">string</span></span> | <span data-ttu-id="06025-124">裝置上所執行的作業系統版本</span><span class="sxs-lookup"><span data-stu-id="06025-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="06025-125">string</span><span class="sxs-lookup"><span data-stu-id="06025-125">string</span></span> | <span data-ttu-id="06025-126">裝置上所執行作業系統的架構</span><span class="sxs-lookup"><span data-stu-id="06025-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="06025-127">string</span><span class="sxs-lookup"><span data-stu-id="06025-127">string</span></span> | <span data-ttu-id="06025-128">軟體廠商的名稱</span><span class="sxs-lookup"><span data-stu-id="06025-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="06025-129">字串</span><span class="sxs-lookup"><span data-stu-id="06025-129">string</span></span> | <span data-ttu-id="06025-130">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="06025-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="06025-131">字串</span><span class="sxs-lookup"><span data-stu-id="06025-131">string</span></span> | <span data-ttu-id="06025-132">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="06025-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="06025-133">字串</span><span class="sxs-lookup"><span data-stu-id="06025-133">string</span></span> | <span data-ttu-id="06025-134">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="06025-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="06025-135">字串</span><span class="sxs-lookup"><span data-stu-id="06025-135">string</span></span> | <span data-ttu-id="06025-136">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="06025-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="06025-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="06025-137">Related topics</span></span>

- [<span data-ttu-id="06025-138">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="06025-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06025-139">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="06025-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06025-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="06025-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="06025-141">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="06025-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
