---
title: Advanced 搜尋架構中的 DeviceTvmSoftwareVulnerabilities 表格
description: 深入瞭解在裝置上找到的軟體弱點，以及可在高級搜尋架構的 DeviceTvmSoftwareVulnerabilities 資料表中處理每個弱點的可用安全性更新清單。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、table、column、data type、description、威脅 & 漏洞管理、TVM、裝置管理、軟體、清查、弱點、CVE 識別碼、OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060260"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="37033-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="37033-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37033-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="37033-105">**Applies to:**</span></span>
- [<span data-ttu-id="37033-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37033-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="37033-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="37033-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37033-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="37033-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="37033-109">「 `DeviceTvmSoftwareVulnerabilities` 高級搜尋」架構中的表格包含已安裝軟體產品中弱點的 [威脅 & 漏洞管理](next-gen-threat-and-vuln-mgt.md) 清單。</span><span class="sxs-lookup"><span data-stu-id="37033-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="37033-110">本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。</span><span class="sxs-lookup"><span data-stu-id="37033-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="37033-111">例如，您可以使用此表格來搜尋有關其軟體中有嚴重弱點之裝置的事件。</span><span class="sxs-lookup"><span data-stu-id="37033-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="37033-112">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="37033-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="37033-113">`DeviceTvmSoftwareInventory`和 `DeviceTvmSoftwareVulnerabilities` tables 已取代 `DeviceTvmSoftwareInventoryVulnerabilities` 表格。</span><span class="sxs-lookup"><span data-stu-id="37033-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="37033-114">前兩個表格一起包含更多資料行，您可以用來協助通知您的漏洞管理活動。</span><span class="sxs-lookup"><span data-stu-id="37033-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="37033-115">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="37033-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="37033-116">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="37033-116">Column name</span></span> | <span data-ttu-id="37033-117">資料類型</span><span class="sxs-lookup"><span data-stu-id="37033-117">Data type</span></span> | <span data-ttu-id="37033-118">描述</span><span class="sxs-lookup"><span data-stu-id="37033-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="37033-119">string</span><span class="sxs-lookup"><span data-stu-id="37033-119">string</span></span> | <span data-ttu-id="37033-120">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="37033-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="37033-121">string</span><span class="sxs-lookup"><span data-stu-id="37033-121">string</span></span> | <span data-ttu-id="37033-122">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="37033-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="37033-123">string</span><span class="sxs-lookup"><span data-stu-id="37033-123">string</span></span> | <span data-ttu-id="37033-124">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="37033-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="37033-125">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="37033-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="37033-126">字串</span><span class="sxs-lookup"><span data-stu-id="37033-126">string</span></span> | <span data-ttu-id="37033-127">裝置上所執行的作業系統版本</span><span class="sxs-lookup"><span data-stu-id="37033-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="37033-128">string</span><span class="sxs-lookup"><span data-stu-id="37033-128">string</span></span> | <span data-ttu-id="37033-129">裝置上所執行作業系統的架構</span><span class="sxs-lookup"><span data-stu-id="37033-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="37033-130">string</span><span class="sxs-lookup"><span data-stu-id="37033-130">string</span></span> | <span data-ttu-id="37033-131">軟體廠商的名稱</span><span class="sxs-lookup"><span data-stu-id="37033-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="37033-132">字串</span><span class="sxs-lookup"><span data-stu-id="37033-132">string</span></span> | <span data-ttu-id="37033-133">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="37033-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="37033-134">字串</span><span class="sxs-lookup"><span data-stu-id="37033-134">string</span></span> | <span data-ttu-id="37033-135">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="37033-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="37033-136">字串</span><span class="sxs-lookup"><span data-stu-id="37033-136">string</span></span> | <span data-ttu-id="37033-137">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="37033-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="37033-138">字串</span><span class="sxs-lookup"><span data-stu-id="37033-138">string</span></span> | <span data-ttu-id="37033-139">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="37033-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="37033-140">字串</span><span class="sxs-lookup"><span data-stu-id="37033-140">string</span></span> | <span data-ttu-id="37033-141">軟體廠商提供的安全性更新名稱或描述，以解決此弱點</span><span class="sxs-lookup"><span data-stu-id="37033-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="37033-142">string</span><span class="sxs-lookup"><span data-stu-id="37033-142">string</span></span> | <span data-ttu-id="37033-143">對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼</span><span class="sxs-lookup"><span data-stu-id="37033-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="37033-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="37033-144">Related topics</span></span>

- [<span data-ttu-id="37033-145">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="37033-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="37033-146">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="37033-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="37033-147">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="37033-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="37033-148">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="37033-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
