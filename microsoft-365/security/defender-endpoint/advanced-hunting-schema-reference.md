---
title: 高級搜尋架構參考
description: 深入瞭解 advanced 搜尋架構中的表格，以瞭解您可以在其上執行威脅搜尋查詢的資料。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、microsoft defender for endpoint、wdatp search、query、遙測、schema reference、kusto、table、data
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: fcc7d96f51121824550128e89186074e1ebc3ce0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228876"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3ef5b-104">瞭解 Microsoft Defender for Endpoint 中的高級搜尋架構</span><span class="sxs-lookup"><span data-stu-id="3ef5b-104">Understand the advanced hunting schema in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ef5b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ef5b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3ef5b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="3ef5b-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3ef5b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3ef5b-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3ef5b-109">[！附注] [高級搜尋](advanced-hunting-overview.md) 架構是由多個表格組成，可提供事件資訊或裝置及其他實體的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-109">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about devices and other entities.</span></span> <span data-ttu-id="3ef5b-110">若要有效組建跨越多個表格的查詢，您需要了解進階搜捕結構描述中的表格和欄。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-110">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="get-schema-information-in-the-security-center"></a><span data-ttu-id="3ef5b-111">在安全性中心取得架構資訊</span><span class="sxs-lookup"><span data-stu-id="3ef5b-111">Get schema information in the security center</span></span>
<span data-ttu-id="3ef5b-112">建立查詢時，請使用內建架構參考，快速取得架構中每個資料表的下列相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3ef5b-112">While constructing queries, use the built-in schema reference to quickly get the following information about each table in the schema:</span></span>

- <span data-ttu-id="3ef5b-113">**資料表描述**—資料表中包含的資料類型和該資料的來源。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-113">**Tables description**—type of data contained in the table and the source of that data.</span></span>
- <span data-ttu-id="3ef5b-114">**欄**-表格中的所有欄。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-114">**Columns**—all the columns in the table.</span></span>
- <span data-ttu-id="3ef5b-115">**動作類型**—欄中的可能值， `ActionType` 代表資料表支援的事件種類。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-115">**Action types**—possible values in the `ActionType` column representing the event types supported by the table.</span></span> <span data-ttu-id="3ef5b-116">這只是針對包含事件資訊的資料表提供。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-116">This is provided only for tables that contain event information.</span></span>
- <span data-ttu-id="3ef5b-117">**範例查詢**--可用於功能如何使用表格的範例查詢。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-117">**Sample query**—example queries that feature how the table can be utilized.</span></span>

### <a name="access-the-schema-reference"></a><span data-ttu-id="3ef5b-118">存取架構參考</span><span class="sxs-lookup"><span data-stu-id="3ef5b-118">Access the schema reference</span></span>
<span data-ttu-id="3ef5b-119">若要快速存取架構參照，請選取架構表示中的資料表名稱旁邊的 **View reference** 動作。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-119">To quickly access the schema reference, select the **View reference** action next to the table name in the schema representation.</span></span> <span data-ttu-id="3ef5b-120">您也可以選取 [ **架構參考** ]，以搜尋表格。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-120">You can also select **Schema reference** to search for a table.</span></span>

![顯示如何存取入口網站架構參考的影像](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a><span data-ttu-id="3ef5b-122">瞭解架構表格</span><span class="sxs-lookup"><span data-stu-id="3ef5b-122">Learn the schema tables</span></span>

<span data-ttu-id="3ef5b-123">下列參考會列出高級搜尋架構中的所有表格。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-123">The following reference lists all the tables in the advanced hunting schema.</span></span> <span data-ttu-id="3ef5b-124">每個表格名稱都會連結到描述該表格之欄名稱的頁面。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-124">Each table name links to a page describing the column names for that table.</span></span>

<span data-ttu-id="3ef5b-125">資料表和欄名稱也會列在「高級搜尋」畫面的 [架構標記法] 的 Microsoft Defender 資訊安全中心中。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-125">Table and column names are also listed within the Microsoft Defender Security Center, in the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="3ef5b-126">表格名稱</span><span class="sxs-lookup"><span data-stu-id="3ef5b-126">Table name</span></span> | <span data-ttu-id="3ef5b-127">描述</span><span class="sxs-lookup"><span data-stu-id="3ef5b-127">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="3ef5b-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-129">Microsoft Defender 資訊安全中心的警示</span><span class="sxs-lookup"><span data-stu-id="3ef5b-129">Alerts on Microsoft Defender Security Center</span></span> |
| <span data-ttu-id="3ef5b-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="3ef5b-131">裝置資訊，包括作業系統資訊</span><span class="sxs-lookup"><span data-stu-id="3ef5b-131">Device information, including OS information</span></span> |
| <span data-ttu-id="3ef5b-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="3ef5b-133">裝置的網路內容，包括配接器、IP 和 MAC 位址，以及連線的網路和網域</span><span class="sxs-lookup"><span data-stu-id="3ef5b-133">Network properties of devices, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="3ef5b-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-135">程序建立與相關事件</span><span class="sxs-lookup"><span data-stu-id="3ef5b-135">Process creation and related events</span></span> |
| <span data-ttu-id="3ef5b-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-137">網路連結與相關事件</span><span class="sxs-lookup"><span data-stu-id="3ef5b-137">Network connection and related events</span></span> |
| <span data-ttu-id="3ef5b-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-139">檔案建立、修改及其他檔案系統事件</span><span class="sxs-lookup"><span data-stu-id="3ef5b-139">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="3ef5b-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-141">登錄項目的建立及修改</span><span class="sxs-lookup"><span data-stu-id="3ef5b-141">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="3ef5b-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-143">登入和其他驗證事件</span><span class="sxs-lookup"><span data-stu-id="3ef5b-143">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="3ef5b-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-145">DLL 載入事件</span><span class="sxs-lookup"><span data-stu-id="3ef5b-145">DLL loading events</span></span> |
| <span data-ttu-id="3ef5b-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="3ef5b-147">多種事件種類，包括安全性控制所觸發的事件，例如 Microsoft Defender 防毒軟體和 exploit protection</span><span class="sxs-lookup"><span data-stu-id="3ef5b-147">Multiple event types, including events triggered by security controls such as Microsoft Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="3ef5b-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span></span> | <span data-ttu-id="3ef5b-149">從端點上的憑證驗證事件取得的簽署檔憑證資訊</span><span class="sxs-lookup"><span data-stu-id="3ef5b-149">Certificate information of signed files obtained from certificate verification events on endpoints</span></span> |
| <span data-ttu-id="3ef5b-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span></span> | <span data-ttu-id="3ef5b-151">安裝在裝置上的軟體清單，包括其版本資訊和支援終止狀態</span><span class="sxs-lookup"><span data-stu-id="3ef5b-151">Inventory of software installed on devices, including their version information and end-of-support status</span></span> |
| <span data-ttu-id="3ef5b-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span></span> | <span data-ttu-id="3ef5b-153">裝置上的軟體弱點，以及解決每個弱點的可用安全性更新清單</span><span class="sxs-lookup"><span data-stu-id="3ef5b-153">Software vulnerabilities found on devices and the list of available security updates that address each vulnerability</span></span> |
| <span data-ttu-id="3ef5b-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span></span> | <span data-ttu-id="3ef5b-155">公開披露弱點的知識庫，包括是否公開提供惡意探索代碼</span><span class="sxs-lookup"><span data-stu-id="3ef5b-155">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="3ef5b-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span></span> | <span data-ttu-id="3ef5b-157">威脅與弱點管理評定事件，可表示裝置上的各種安全性設定狀態</span><span class="sxs-lookup"><span data-stu-id="3ef5b-157">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="3ef5b-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span></span> | <span data-ttu-id="3ef5b-159">由威脅與弱點管理所使用之各種安全性設定的知識庫來評定裝置，包含各種標準和效能評定的對應</span><span class="sxs-lookup"><span data-stu-id="3ef5b-159">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span> |

>[!TIP]
><span data-ttu-id="3ef5b-160">使用[Microsoft 365 Defender 中的高級搜尋](/microsoft-365/security/defender/advanced-hunting-overview)來尋找威脅，使用來自 Defender for Endpoint 的資料，microsoft defender 用於 Office 365、Microsoft Cloud App Security 和 Microsoft defender 身分識別。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-160">Use [advanced hunting in Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) to hunt for threats using data from Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> [<span data-ttu-id="3ef5b-161">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ef5b-161">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-enable)<br><br>
<span data-ttu-id="3ef5b-162">深入瞭解如何將您的高級搜尋工作流程從 microsoft defender for endpoint 移至 Microsoft 365 Defender 以[從 microsoft defender for endpoint 遷移高級搜尋查詢](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)。</span><span class="sxs-lookup"><span data-stu-id="3ef5b-162">Learn more about how to move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ef5b-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="3ef5b-163">Related topics</span></span>
- [<span data-ttu-id="3ef5b-164">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="3ef5b-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3ef5b-165">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="3ef5b-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3ef5b-166">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="3ef5b-166">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3ef5b-167">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="3ef5b-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3ef5b-168">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="3ef5b-168">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="3ef5b-169">高級搜尋資料架構變更</span><span class="sxs-lookup"><span data-stu-id="3ef5b-169">Advanced hunting data schema changes</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
