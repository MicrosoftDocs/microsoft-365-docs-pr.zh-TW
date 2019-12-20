---
title: Microsoft 威脅防護進階搜捕結構描述的資料表格
description: 了解進階搜捕結構描述中的表格，以明白您可以執行威脅搜捕查詢的資料
keywords: 進階搜捕、威脅搜捕、網路威脅搜捕、搜尋、查詢、遙測、結構描述參考、kusto、表格、資料
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
ms.openlocfilehash: 631b328168003668ed06e37d76177c327794ed18
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808658"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="ced8c-104">了解進階搜捕結構描述</span><span class="sxs-lookup"><span data-stu-id="ced8c-104">Understand the advanced hunting schema</span></span>

<span data-ttu-id="ced8c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ced8c-105">**Applies to:**</span></span>
- <span data-ttu-id="ced8c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="ced8c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ced8c-107">[進階搜捕](advanced-hunting-overview.md)結構描述是由多個提供事件資訊或與電腦或實體相關資訊的表格所組成。</span><span class="sxs-lookup"><span data-stu-id="ced8c-107">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about machines and entities.</span></span> <span data-ttu-id="ced8c-108">若要有效組建跨越多個表格的查詢，您需要了解進階搜捕結構描述中的表格和欄。</span><span class="sxs-lookup"><span data-stu-id="ced8c-108">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="schema-tables"></a><span data-ttu-id="ced8c-109">結構描述表格</span><span class="sxs-lookup"><span data-stu-id="ced8c-109">Schema tables</span></span>

<span data-ttu-id="ced8c-110">以下參考列出結構描述中的所有表格。</span><span class="sxs-lookup"><span data-stu-id="ced8c-110">The following reference lists all the tables in the schema.</span></span> <span data-ttu-id="ced8c-111">每個表格名稱都會連結到描述該表格之欄名稱的頁面。</span><span class="sxs-lookup"><span data-stu-id="ced8c-111">Each table name links to a page describing the column names for that table.</span></span> <span data-ttu-id="ced8c-112">表格和欄名稱也同樣列於安全性中心，成為進階搜捕畫面上結構描述代表中的一部分。</span><span class="sxs-lookup"><span data-stu-id="ced8c-112">Table and column names are also listed in the security center as part of the the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="ced8c-113">表格名稱</span><span class="sxs-lookup"><span data-stu-id="ced8c-113">Table name</span></span> | <span data-ttu-id="ced8c-114">描述</span><span class="sxs-lookup"><span data-stu-id="ced8c-114">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="ced8c-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="ced8c-116">電腦資訊，包括作業系統資訊</span><span class="sxs-lookup"><span data-stu-id="ced8c-116">Machine information, including OS information</span></span> |
| <span data-ttu-id="ced8c-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="ced8c-118">電腦的網路摘要資訊，包括介面卡、IP 和 MAC 位址，以及已連結的網路和網域</span><span class="sxs-lookup"><span data-stu-id="ced8c-118">Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="ced8c-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="ced8c-120">程序建立與相關事件</span><span class="sxs-lookup"><span data-stu-id="ced8c-120">Process creation and related events</span></span> |
| <span data-ttu-id="ced8c-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="ced8c-122">網路連結與相關事件</span><span class="sxs-lookup"><span data-stu-id="ced8c-122">Network connection and related events</span></span> |
| <span data-ttu-id="ced8c-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="ced8c-124">檔案建立、修改及其他檔案系統事件</span><span class="sxs-lookup"><span data-stu-id="ced8c-124">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="ced8c-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="ced8c-126">登錄項目的建立及修改</span><span class="sxs-lookup"><span data-stu-id="ced8c-126">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="ced8c-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="ced8c-128">登入和其他驗證事件</span><span class="sxs-lookup"><span data-stu-id="ced8c-128">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="ced8c-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="ced8c-130">DLL 載入事件</span><span class="sxs-lookup"><span data-stu-id="ced8c-130">DLL loading events</span></span> |
| <span data-ttu-id="ced8c-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="ced8c-132">多種事件種類，包括由安全性控制項觸發的事件，例如 Windows Defender 防毒軟體和惡意探索保護</span><span class="sxs-lookup"><span data-stu-id="ced8c-132">Multiple event types, including events triggered by security controls such as Windows Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="ced8c-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span></span> | <span data-ttu-id="ced8c-134">Office 365 電子郵件事件，包括電子郵件傳送和封鎖事件</span><span class="sxs-lookup"><span data-stu-id="ced8c-134">Office 365 email events, including email delivery and blocking events</span></span> |
| <span data-ttu-id="ced8c-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span></span> | <span data-ttu-id="ced8c-136">有關已附加到 Office 365 電子郵件的檔案相關資訊</span><span class="sxs-lookup"><span data-stu-id="ced8c-136">Information about files attached to Office 365 emails</span></span> |
| <span data-ttu-id="ced8c-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span></span> | <span data-ttu-id="ced8c-138">Office 365 電子郵件上 URL 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="ced8c-138">Information about URLs on Office 365 emails</span></span> |
| <span data-ttu-id="ced8c-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span></span> | <span data-ttu-id="ced8c-140">裝置上的軟體庫存，以及這些軟體產品中的任何已知弱點</span><span class="sxs-lookup"><span data-stu-id="ced8c-140">Inventory of software on devices as well as any known vulnerabilities in these software products</span></span> |
| <span data-ttu-id="ced8c-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span></span> | <span data-ttu-id="ced8c-142">公開披露弱點的知識庫，包括是否公開提供惡意探索代碼</span><span class="sxs-lookup"><span data-stu-id="ced8c-142">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="ced8c-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span></span> | <span data-ttu-id="ced8c-144">威脅與弱點管理評定事件，可表示裝置上的各種安全性設定狀態</span><span class="sxs-lookup"><span data-stu-id="ced8c-144">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="ced8c-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ced8c-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span></span> | <span data-ttu-id="ced8c-146">由威脅與弱點管理所使用之各種安全性設定的知識庫來評定裝置，包含各種標準和效能評定的對應</span><span class="sxs-lookup"><span data-stu-id="ced8c-146">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="ced8c-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="ced8c-147">Related topics</span></span>
- [<span data-ttu-id="ced8c-148">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="ced8c-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ced8c-149">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="ced8c-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ced8c-150">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="ced8c-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ced8c-151">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="ced8c-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ced8c-152">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="ced8c-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
