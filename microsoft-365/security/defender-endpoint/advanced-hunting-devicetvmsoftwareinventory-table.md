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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060015"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="8dbf2-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="8dbf2-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8dbf2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8dbf2-105">**Applies to:**</span></span>
- [<span data-ttu-id="8dbf2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8dbf2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="8dbf2-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8dbf2-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8dbf2-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8dbf2-109">「 `DeviceTvmSoftwareInventory` 高級搜尋」架構中的表格包含目前安裝在網路裝置上之軟體的 [威脅 & 漏洞管理](next-gen-threat-and-vuln-mgt.md) 清單，包括支援資訊的結束。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="8dbf2-110">例如，您可以針對與目前具有漏洞軟體版本一起安裝的裝置，尋找相關事件。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="8dbf2-111">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="8dbf2-112">`DeviceTvmSoftwareInventory`和 `DeviceTvmSoftwareVulnerabilities` tables 已取代 `DeviceTvmSoftwareInventoryVulnerabilities` 表格。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="8dbf2-113">前兩個表格一起包含更多資料行，您可以用來協助通知您的漏洞管理活動。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="8dbf2-114">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="8dbf2-115">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="8dbf2-115">Column name</span></span> | <span data-ttu-id="8dbf2-116">資料類型</span><span class="sxs-lookup"><span data-stu-id="8dbf2-116">Data type</span></span> | <span data-ttu-id="8dbf2-117">描述</span><span class="sxs-lookup"><span data-stu-id="8dbf2-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="8dbf2-118">string</span><span class="sxs-lookup"><span data-stu-id="8dbf2-118">string</span></span> | <span data-ttu-id="8dbf2-119">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="8dbf2-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8dbf2-120">string</span><span class="sxs-lookup"><span data-stu-id="8dbf2-120">string</span></span> | <span data-ttu-id="8dbf2-121">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="8dbf2-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="8dbf2-122">string</span><span class="sxs-lookup"><span data-stu-id="8dbf2-122">string</span></span> | <span data-ttu-id="8dbf2-123">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8dbf2-124">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="8dbf2-125">字串</span><span class="sxs-lookup"><span data-stu-id="8dbf2-125">string</span></span> | <span data-ttu-id="8dbf2-126">裝置上所執行的作業系統版本</span><span class="sxs-lookup"><span data-stu-id="8dbf2-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="8dbf2-127">string</span><span class="sxs-lookup"><span data-stu-id="8dbf2-127">string</span></span> | <span data-ttu-id="8dbf2-128">裝置上所執行作業系統的架構</span><span class="sxs-lookup"><span data-stu-id="8dbf2-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="8dbf2-129">string</span><span class="sxs-lookup"><span data-stu-id="8dbf2-129">string</span></span> | <span data-ttu-id="8dbf2-130">軟體廠商的名稱</span><span class="sxs-lookup"><span data-stu-id="8dbf2-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="8dbf2-131">字串</span><span class="sxs-lookup"><span data-stu-id="8dbf2-131">string</span></span> | <span data-ttu-id="8dbf2-132">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="8dbf2-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="8dbf2-133">字串</span><span class="sxs-lookup"><span data-stu-id="8dbf2-133">string</span></span> | <span data-ttu-id="8dbf2-134">軟體產品的版本號碼</span><span class="sxs-lookup"><span data-stu-id="8dbf2-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="8dbf2-135">字串</span><span class="sxs-lookup"><span data-stu-id="8dbf2-135">string</span></span> | <span data-ttu-id="8dbf2-136">會指出軟體產品的生命週期階段相對於其指定的支援終止 (EOS) 或生命週期 (EOL) 日期</span><span class="sxs-lookup"><span data-stu-id="8dbf2-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="8dbf2-137">string</span><span class="sxs-lookup"><span data-stu-id="8dbf2-137">string</span></span> | <span data-ttu-id="8dbf2-138">支援終止 (EOS) 或使用壽命結束 (EOL) 軟體產品的日期</span><span class="sxs-lookup"><span data-stu-id="8dbf2-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="8dbf2-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="8dbf2-139">Related topics</span></span>

- [<span data-ttu-id="8dbf2-140">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="8dbf2-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8dbf2-141">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="8dbf2-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8dbf2-142">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="8dbf2-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="8dbf2-143">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="8dbf2-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

