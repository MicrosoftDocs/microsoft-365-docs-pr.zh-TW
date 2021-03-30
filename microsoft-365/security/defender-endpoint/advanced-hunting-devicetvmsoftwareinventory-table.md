---
title: Advanced 搜尋架構中的 DeviceTvmSoftwareInventory 表格
description: 深入瞭解在高級搜尋架構的 DeviceTvmSoftwareInventory 資料表中，裝置中的軟體清單。
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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408620"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="1c7f8-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="1c7f8-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c7f8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1c7f8-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c7f8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1c7f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="1c7f8-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1c7f8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1c7f8-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1c7f8-109">「 `DeviceTvmSoftwareInventory` 高級搜尋」架構中的表格包含目前安裝在網路裝置上的軟體 [威脅和弱點管理](next-gen-threat-and-vuln-mgt.md) 清單，包括支援資訊的結束。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="1c7f8-110">例如，您可以針對與目前具有漏洞軟體版本一起安裝的裝置，尋找相關事件。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="1c7f8-111">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="1c7f8-112">DeviceTVMSoftwareInventory 包含威脅和弱點管理可以比對通用平臺列舉 (CPE) –不論是否有影響的軟體。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="1c7f8-113">`DeviceTvmSoftwareInventory`和 `DeviceTvmSoftwareVulnerabilities` tables 已取代 `DeviceTvmSoftwareInventoryVulnerabilities` 表格。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="1c7f8-114">前兩個表格一起包含更多資料行，您可以用來協助通知您的漏洞管理活動。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="1c7f8-115">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="1c7f8-116">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="1c7f8-116">Column name</span></span> | <span data-ttu-id="1c7f8-117">資料類型</span><span class="sxs-lookup"><span data-stu-id="1c7f8-117">Data type</span></span> | <span data-ttu-id="1c7f8-118">描述</span><span class="sxs-lookup"><span data-stu-id="1c7f8-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="1c7f8-119">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-119">string</span></span> | <span data-ttu-id="1c7f8-120">服務中裝置的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="1c7f8-121">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-121">string</span></span> | <span data-ttu-id="1c7f8-122">裝置 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="1c7f8-123">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-123">string</span></span> | <span data-ttu-id="1c7f8-124">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="1c7f8-125">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="1c7f8-126">字串</span><span class="sxs-lookup"><span data-stu-id="1c7f8-126">string</span></span> | <span data-ttu-id="1c7f8-127">裝置上所執行作業系統的版本。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="1c7f8-128">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-128">string</span></span> | <span data-ttu-id="1c7f8-129">裝置上所執行作業系統的架構。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="1c7f8-130">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-130">string</span></span> | <span data-ttu-id="1c7f8-131">軟體廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="1c7f8-132">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-132">string</span></span> | <span data-ttu-id="1c7f8-133">軟體產品的名稱。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="1c7f8-134">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-134">string</span></span> | <span data-ttu-id="1c7f8-135">軟體產品的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="1c7f8-136">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-136">string</span></span> | <span data-ttu-id="1c7f8-137">會指出軟體產品的生命週期階段相對於其指定的支援終止 (EOS) 或生命週期 (EOL) 日期。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="1c7f8-138">string</span><span class="sxs-lookup"><span data-stu-id="1c7f8-138">string</span></span> | <span data-ttu-id="1c7f8-139">支援終止 (EOS) 或壽命週期 (EOL) 軟體產品的日期。</span><span class="sxs-lookup"><span data-stu-id="1c7f8-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1c7f8-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="1c7f8-140">Related topics</span></span>

- [<span data-ttu-id="1c7f8-141">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="1c7f8-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1c7f8-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="1c7f8-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1c7f8-143">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="1c7f8-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="1c7f8-144">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="1c7f8-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
