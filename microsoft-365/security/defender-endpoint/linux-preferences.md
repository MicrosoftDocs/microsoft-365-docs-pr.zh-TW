---
title: 在 Linux 上設定 Microsoft Defender for Endpoint 的喜好設定
ms.reviewer: ''
description: 說明如何在企業中為 Linux 設定 Microsoft Defender for Endpoint。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289484"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="37e0a-104">在 Linux 上設定 Microsoft Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="37e0a-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="37e0a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="37e0a-105">**Applies to:**</span></span>
- [<span data-ttu-id="37e0a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37e0a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="37e0a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37e0a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="37e0a-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="37e0a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37e0a-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="37e0a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="37e0a-110">本主題包含如何在企業環境中設定適用于 Linux 之 Defender 的 Defender 偏好設定的指示。</span><span class="sxs-lookup"><span data-stu-id="37e0a-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="37e0a-111">如果您想要從命令列在裝置上設定產品，請參閱 [Resources](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="37e0a-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="37e0a-112">在企業環境中，可以透過設定設定檔來管理 Linux 上的 Defender。</span><span class="sxs-lookup"><span data-stu-id="37e0a-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="37e0a-113">此設定檔是從您選擇的管理工具部署。</span><span class="sxs-lookup"><span data-stu-id="37e0a-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="37e0a-114">由企業管理的喜好設定會優先于裝置上的本機設定。</span><span class="sxs-lookup"><span data-stu-id="37e0a-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="37e0a-115">換句話說，您企業中的使用者無法變更透過此設定檔設定的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="37e0a-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="37e0a-116">本文說明此設定檔的結構 (，包括可供您開始使用的建議設定檔) 及如何部署設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="37e0a-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="37e0a-117">設定設定檔結構</span><span class="sxs-lookup"><span data-stu-id="37e0a-117">Configuration profile structure</span></span>

<span data-ttu-id="37e0a-118">設定設定檔是由按鍵 (所識別的專案所組成的一個 json 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。</span><span class="sxs-lookup"><span data-stu-id="37e0a-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="37e0a-119">值可以是簡單的，例如數值或複雜，例如首選項的嵌套清單。</span><span class="sxs-lookup"><span data-stu-id="37e0a-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="37e0a-120">一般來說，您會使用設定管理工具將名稱中的檔案推入 ```mdatp_managed.json``` 該位置 ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="37e0a-121">設定設定檔的最上層包含產品的子領域首選項及專案，在下一節將詳細說明。</span><span class="sxs-lookup"><span data-stu-id="37e0a-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="37e0a-122">防病毒引擎偏好設定</span><span class="sxs-lookup"><span data-stu-id="37e0a-122">Antivirus engine preferences</span></span>

<span data-ttu-id="37e0a-123">設定設定檔的 [ *antivirusEngine* ] 區段是用來管理產品之防病毒元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="37e0a-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="37e0a-124">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-124">Description</span></span>|<span data-ttu-id="37e0a-125">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-125">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-126">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-126">**Key**</span></span>|<span data-ttu-id="37e0a-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="37e0a-127">antivirusEngine</span></span>|
|<span data-ttu-id="37e0a-128">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-128">**Data type**</span></span>|<span data-ttu-id="37e0a-129">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="37e0a-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="37e0a-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-130">**Comments**</span></span>|<span data-ttu-id="37e0a-131">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="37e0a-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="37e0a-132">啟用/停用即時保護</span><span class="sxs-lookup"><span data-stu-id="37e0a-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="37e0a-133">會決定在啟用或未啟用) 時，是否即時保護 (掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="37e0a-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="37e0a-134">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-134">Description</span></span>|<span data-ttu-id="37e0a-135">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-135">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-136">**Key**</span></span>|<span data-ttu-id="37e0a-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="37e0a-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="37e0a-138">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-138">**Data type**</span></span>|<span data-ttu-id="37e0a-139">布林值</span><span class="sxs-lookup"><span data-stu-id="37e0a-139">Boolean</span></span>|
|<span data-ttu-id="37e0a-140">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-140">**Possible values**</span></span>|<span data-ttu-id="37e0a-141">true (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-141">true (default)</span></span> <p> <span data-ttu-id="37e0a-142">假</span><span class="sxs-lookup"><span data-stu-id="37e0a-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="37e0a-143">啟用/停用被動模式</span><span class="sxs-lookup"><span data-stu-id="37e0a-143">Enable / disable passive mode</span></span>

<span data-ttu-id="37e0a-144">決定防病毒引擎是否以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="37e0a-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="37e0a-145">在被動模式：</span><span class="sxs-lookup"><span data-stu-id="37e0a-145">In passive mode:</span></span>

- <span data-ttu-id="37e0a-146">已關閉即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="37e0a-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="37e0a-147">已開啟隨選掃描。</span><span class="sxs-lookup"><span data-stu-id="37e0a-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="37e0a-148">關閉自動威脅修復功能。</span><span class="sxs-lookup"><span data-stu-id="37e0a-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="37e0a-149">已開啟安全性智慧更新。</span><span class="sxs-lookup"><span data-stu-id="37e0a-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="37e0a-150">[狀態] 功能表圖示已隱藏。</span><span class="sxs-lookup"><span data-stu-id="37e0a-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="37e0a-151">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-151">Description</span></span>|<span data-ttu-id="37e0a-152">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-152">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-153">**Key**</span></span>|<span data-ttu-id="37e0a-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="37e0a-154">passiveMode</span></span>|
|<span data-ttu-id="37e0a-155">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-155">**Data type**</span></span>|<span data-ttu-id="37e0a-156">布林值</span><span class="sxs-lookup"><span data-stu-id="37e0a-156">Boolean</span></span>|
|<span data-ttu-id="37e0a-157">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-157">**Possible values**</span></span>|<span data-ttu-id="37e0a-158">false (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-158">false (default)</span></span> <p> <span data-ttu-id="37e0a-159">真</span><span class="sxs-lookup"><span data-stu-id="37e0a-159">true</span></span>|
|<span data-ttu-id="37e0a-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-160">**Comments**</span></span>|<span data-ttu-id="37e0a-161">在100.67.60 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="37e0a-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="37e0a-162">排除合併原則</span><span class="sxs-lookup"><span data-stu-id="37e0a-162">Exclusion merge policy</span></span>

<span data-ttu-id="37e0a-163">指定排除專案的合併原則。</span><span class="sxs-lookup"><span data-stu-id="37e0a-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="37e0a-164">它可以是管理員定義和使用者定義排除的組合 (`merge`) 或只) 系統管理員定義的排除 (`admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="37e0a-165">您可以使用此設定來限制本機使用者定義自己的排除專案。</span><span class="sxs-lookup"><span data-stu-id="37e0a-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="37e0a-166">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-166">Description</span></span>|<span data-ttu-id="37e0a-167">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-167">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-168">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-168">**Key**</span></span>|<span data-ttu-id="37e0a-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="37e0a-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="37e0a-170">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-170">**Data type**</span></span>|<span data-ttu-id="37e0a-171">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-171">String</span></span>|
|<span data-ttu-id="37e0a-172">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-172">**Possible values**</span></span>|<span data-ttu-id="37e0a-173">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="37e0a-173">merge (default)</span></span> <p> <span data-ttu-id="37e0a-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="37e0a-174">admin_only</span></span>|
|<span data-ttu-id="37e0a-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-175">**Comments**</span></span>|<span data-ttu-id="37e0a-176">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="37e0a-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="37e0a-177">掃描排除</span><span class="sxs-lookup"><span data-stu-id="37e0a-177">Scan exclusions</span></span>

<span data-ttu-id="37e0a-178">已從掃描中排除的實體。</span><span class="sxs-lookup"><span data-stu-id="37e0a-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="37e0a-179">您可以使用完整路徑、副檔名或檔案名來指定排除。</span><span class="sxs-lookup"><span data-stu-id="37e0a-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="37e0a-180"> (排除專案是以專案陣列的形式指定，管理員可以根據需要依任何順序指定任意數目的元素。 ) </span><span class="sxs-lookup"><span data-stu-id="37e0a-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="37e0a-181">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-181">Description</span></span>|<span data-ttu-id="37e0a-182">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-182">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-183">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-183">**Key**</span></span>|<span data-ttu-id="37e0a-184">排除</span><span class="sxs-lookup"><span data-stu-id="37e0a-184">exclusions</span></span>|
|<span data-ttu-id="37e0a-185">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-185">**Data type**</span></span>|<span data-ttu-id="37e0a-186">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="37e0a-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="37e0a-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-187">**Comments**</span></span>|<span data-ttu-id="37e0a-188">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="37e0a-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="37e0a-189">排除的類型</span><span class="sxs-lookup"><span data-stu-id="37e0a-189">Type of exclusion</span></span>

<span data-ttu-id="37e0a-190">指定排除在掃描之外的內容類型。</span><span class="sxs-lookup"><span data-stu-id="37e0a-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="37e0a-191">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-191">Description</span></span>|<span data-ttu-id="37e0a-192">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-192">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-193">**Key**</span></span>|<span data-ttu-id="37e0a-194">$type</span><span class="sxs-lookup"><span data-stu-id="37e0a-194">$type</span></span>|
|<span data-ttu-id="37e0a-195">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-195">**Data type**</span></span>|<span data-ttu-id="37e0a-196">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-196">String</span></span>|
|<span data-ttu-id="37e0a-197">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-197">**Possible values**</span></span>|<span data-ttu-id="37e0a-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="37e0a-198">excludedPath</span></span> <p> <span data-ttu-id="37e0a-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="37e0a-199">excludedFileExtension</span></span> <p> <span data-ttu-id="37e0a-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="37e0a-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="37e0a-201">排除內容的路徑</span><span class="sxs-lookup"><span data-stu-id="37e0a-201">Path to excluded content</span></span>

<span data-ttu-id="37e0a-202">用於從掃描的完整檔案路徑中排除內容。</span><span class="sxs-lookup"><span data-stu-id="37e0a-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="37e0a-203">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-203">Description</span></span>|<span data-ttu-id="37e0a-204">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-204">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-205">**Key**</span></span>|<span data-ttu-id="37e0a-206">路徑</span><span class="sxs-lookup"><span data-stu-id="37e0a-206">path</span></span>|
|<span data-ttu-id="37e0a-207">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-207">**Data type**</span></span>|<span data-ttu-id="37e0a-208">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-208">String</span></span>|
|<span data-ttu-id="37e0a-209">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-209">**Possible values**</span></span>|<span data-ttu-id="37e0a-210">有效路徑</span><span class="sxs-lookup"><span data-stu-id="37e0a-210">valid paths</span></span>|
|<span data-ttu-id="37e0a-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-211">**Comments**</span></span>|<span data-ttu-id="37e0a-212">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="37e0a-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="37e0a-213"> (檔/目錄的路徑類型) </span><span class="sxs-lookup"><span data-stu-id="37e0a-213">Path type (file / directory)</span></span>

<span data-ttu-id="37e0a-214">會指出 *path* 屬性參照的是檔案或目錄。</span><span class="sxs-lookup"><span data-stu-id="37e0a-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="37e0a-215">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-215">Description</span></span>|<span data-ttu-id="37e0a-216">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-216">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-217">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-217">**Key**</span></span>|<span data-ttu-id="37e0a-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="37e0a-218">isDirectory</span></span>|
|<span data-ttu-id="37e0a-219">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-219">**Data type**</span></span>|<span data-ttu-id="37e0a-220">布林值</span><span class="sxs-lookup"><span data-stu-id="37e0a-220">Boolean</span></span>|
|<span data-ttu-id="37e0a-221">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-221">**Possible values**</span></span>|<span data-ttu-id="37e0a-222">false (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-222">false (default)</span></span> <p> <span data-ttu-id="37e0a-223">真</span><span class="sxs-lookup"><span data-stu-id="37e0a-223">true</span></span>|
|<span data-ttu-id="37e0a-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-224">**Comments**</span></span>|<span data-ttu-id="37e0a-225">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="37e0a-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="37e0a-226">從掃描排除的副檔名</span><span class="sxs-lookup"><span data-stu-id="37e0a-226">File extension excluded from the scan</span></span>

<span data-ttu-id="37e0a-227">用於從 [掃描者] 副檔名排除內容。</span><span class="sxs-lookup"><span data-stu-id="37e0a-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="37e0a-228">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-228">Description</span></span>|<span data-ttu-id="37e0a-229">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-229">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-230">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-230">**Key**</span></span>|<span data-ttu-id="37e0a-231">擴展</span><span class="sxs-lookup"><span data-stu-id="37e0a-231">extension</span></span>|
|<span data-ttu-id="37e0a-232">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-232">**Data type**</span></span>|<span data-ttu-id="37e0a-233">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-233">String</span></span>|
|<span data-ttu-id="37e0a-234">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-234">**Possible values**</span></span>|<span data-ttu-id="37e0a-235">有效的副檔名</span><span class="sxs-lookup"><span data-stu-id="37e0a-235">valid file extensions</span></span>|
|<span data-ttu-id="37e0a-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-236">**Comments**</span></span>|<span data-ttu-id="37e0a-237">僅適用于 *excludedFileExtension* *$type*</span><span class="sxs-lookup"><span data-stu-id="37e0a-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="37e0a-238">從掃描排除的處理常式</span><span class="sxs-lookup"><span data-stu-id="37e0a-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="37e0a-239">指定從掃描排除所有檔案活動的處理常式。</span><span class="sxs-lookup"><span data-stu-id="37e0a-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="37e0a-240">您可以透過名稱來指定程式 (例如， `cat`) 或完整路徑 (例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="37e0a-241">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-241">Description</span></span>|<span data-ttu-id="37e0a-242">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-242">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-243">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-243">**Key**</span></span>|<span data-ttu-id="37e0a-244">name</span><span class="sxs-lookup"><span data-stu-id="37e0a-244">name</span></span>|
|<span data-ttu-id="37e0a-245">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-245">**Data type**</span></span>|<span data-ttu-id="37e0a-246">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-246">String</span></span>|
|<span data-ttu-id="37e0a-247">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-247">**Possible values**</span></span>|<span data-ttu-id="37e0a-248">任何字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-248">any string</span></span>|
|<span data-ttu-id="37e0a-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-249">**Comments**</span></span>|<span data-ttu-id="37e0a-250">僅適用于 *excludedFileName* *$type*</span><span class="sxs-lookup"><span data-stu-id="37e0a-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="37e0a-251">允許的威脅</span><span class="sxs-lookup"><span data-stu-id="37e0a-251">Allowed threats</span></span>

<span data-ttu-id="37e0a-252">根據其名稱) 所識別的威脅清單，其 (未被產品封鎖，但改為允許執行。</span><span class="sxs-lookup"><span data-stu-id="37e0a-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="37e0a-253">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-253">Description</span></span>|<span data-ttu-id="37e0a-254">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-254">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-255">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-255">**Key**</span></span>|<span data-ttu-id="37e0a-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="37e0a-256">allowedThreats</span></span>|
|<span data-ttu-id="37e0a-257">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-257">**Data type**</span></span>|<span data-ttu-id="37e0a-258">字串陣列</span><span class="sxs-lookup"><span data-stu-id="37e0a-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="37e0a-259">不允許的威脅動作</span><span class="sxs-lookup"><span data-stu-id="37e0a-259">Disallowed threat actions</span></span>

<span data-ttu-id="37e0a-260">限制偵測到威脅時，裝置的本機使用者可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="37e0a-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="37e0a-261">在此清單中包含的動作不會顯示在使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="37e0a-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="37e0a-262">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-262">Description</span></span>|<span data-ttu-id="37e0a-263">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-263">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-264">**Key**</span></span>|<span data-ttu-id="37e0a-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="37e0a-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="37e0a-266">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-266">**Data type**</span></span>|<span data-ttu-id="37e0a-267">字串陣列</span><span class="sxs-lookup"><span data-stu-id="37e0a-267">Array of strings</span></span>|
|<span data-ttu-id="37e0a-268">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-268">**Possible values**</span></span>|<span data-ttu-id="37e0a-269">允許 (限制使用者允許威脅) </span><span class="sxs-lookup"><span data-stu-id="37e0a-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="37e0a-270">restore (會限制使用者從隔離區還原威脅) </span><span class="sxs-lookup"><span data-stu-id="37e0a-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="37e0a-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-271">**Comments**</span></span>|<span data-ttu-id="37e0a-272">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="37e0a-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="37e0a-273">威脅類型設定</span><span class="sxs-lookup"><span data-stu-id="37e0a-273">Threat type settings</span></span>

<span data-ttu-id="37e0a-274">防病毒引擎中的 *threatTypeSettings* 首選項是用來控制產品如何處理特定威脅類型。</span><span class="sxs-lookup"><span data-stu-id="37e0a-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="37e0a-275">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-275">Description</span></span>|<span data-ttu-id="37e0a-276">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-276">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-277">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-277">**Key**</span></span>|<span data-ttu-id="37e0a-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="37e0a-278">threatTypeSettings</span></span>|
|<span data-ttu-id="37e0a-279">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-279">**Data type**</span></span>|<span data-ttu-id="37e0a-280">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="37e0a-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="37e0a-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-281">**Comments**</span></span>|<span data-ttu-id="37e0a-282">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="37e0a-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="37e0a-283">威脅類型</span><span class="sxs-lookup"><span data-stu-id="37e0a-283">Threat type</span></span>

<span data-ttu-id="37e0a-284">設定行為的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="37e0a-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="37e0a-285">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-285">Description</span></span>|<span data-ttu-id="37e0a-286">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-286">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-287">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-287">**Key**</span></span>|<span data-ttu-id="37e0a-288">機碼</span><span class="sxs-lookup"><span data-stu-id="37e0a-288">key</span></span>|
|<span data-ttu-id="37e0a-289">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-289">**Data type**</span></span>|<span data-ttu-id="37e0a-290">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-290">String</span></span>|
|<span data-ttu-id="37e0a-291">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-291">**Possible values**</span></span>|<span data-ttu-id="37e0a-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="37e0a-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="37e0a-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="37e0a-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="37e0a-294">要採取的動作</span><span class="sxs-lookup"><span data-stu-id="37e0a-294">Action to take</span></span>

<span data-ttu-id="37e0a-295">當您在上述區段中所指定類型的威脅到來時採取的動作。</span><span class="sxs-lookup"><span data-stu-id="37e0a-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="37e0a-296">可以是：</span><span class="sxs-lookup"><span data-stu-id="37e0a-296">Can be:</span></span>

- <span data-ttu-id="37e0a-297">**Audit**：此裝置沒有針對這類威脅進行保護，但是會記錄有關威脅的專案。</span><span class="sxs-lookup"><span data-stu-id="37e0a-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="37e0a-298">**封鎖**：針對這類威脅保護裝置，並在安全性主控台中通知您。</span><span class="sxs-lookup"><span data-stu-id="37e0a-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="37e0a-299">**Off**：裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="37e0a-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="37e0a-300">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-300">Description</span></span>|<span data-ttu-id="37e0a-301">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-301">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-302">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-302">**Key**</span></span>|<span data-ttu-id="37e0a-303">數值</span><span class="sxs-lookup"><span data-stu-id="37e0a-303">value</span></span>|
|<span data-ttu-id="37e0a-304">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-304">**Data type**</span></span>|<span data-ttu-id="37e0a-305">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-305">String</span></span>|
|<span data-ttu-id="37e0a-306">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-306">**Possible values**</span></span>|<span data-ttu-id="37e0a-307">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-307">audit (default)</span></span> <p> <span data-ttu-id="37e0a-308">塊</span><span class="sxs-lookup"><span data-stu-id="37e0a-308">block</span></span> <p> <span data-ttu-id="37e0a-309">遠離</span><span class="sxs-lookup"><span data-stu-id="37e0a-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="37e0a-310">威脅類型設定合併原則</span><span class="sxs-lookup"><span data-stu-id="37e0a-310">Threat type settings merge policy</span></span>

<span data-ttu-id="37e0a-311">指定威脅類型設定的合併原則。</span><span class="sxs-lookup"><span data-stu-id="37e0a-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="37e0a-312">這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="37e0a-313">此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。</span><span class="sxs-lookup"><span data-stu-id="37e0a-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="37e0a-314">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-314">Description</span></span>|<span data-ttu-id="37e0a-315">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-315">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-316">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-316">**Key**</span></span>|<span data-ttu-id="37e0a-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="37e0a-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="37e0a-318">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-318">**Data type**</span></span>|<span data-ttu-id="37e0a-319">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-319">String</span></span>|
|<span data-ttu-id="37e0a-320">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-320">**Possible values**</span></span>|<span data-ttu-id="37e0a-321">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="37e0a-321">merge (default)</span></span> <p> <span data-ttu-id="37e0a-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="37e0a-322">admin_only</span></span>|
|<span data-ttu-id="37e0a-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-323">**Comments**</span></span>|<span data-ttu-id="37e0a-324">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="37e0a-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="37e0a-325">防病毒掃描記錄保留 (天數) </span><span class="sxs-lookup"><span data-stu-id="37e0a-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="37e0a-326">指定在裝置上的掃描歷程記錄中保留結果的天數。</span><span class="sxs-lookup"><span data-stu-id="37e0a-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="37e0a-327">舊的掃描結果會從歷史記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="37e0a-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="37e0a-328">也會從磁片中移除的舊隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="37e0a-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="37e0a-329">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-329">Description</span></span>|<span data-ttu-id="37e0a-330">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-330">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-331">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-331">**Key**</span></span>|<span data-ttu-id="37e0a-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="37e0a-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="37e0a-333">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-333">**Data type**</span></span>|<span data-ttu-id="37e0a-334">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-334">String</span></span>|
|<span data-ttu-id="37e0a-335">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-335">**Possible values**</span></span>|<span data-ttu-id="37e0a-336">90 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-336">90 (default).</span></span> <span data-ttu-id="37e0a-337">允許的值介於1天到180天。</span><span class="sxs-lookup"><span data-stu-id="37e0a-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="37e0a-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-338">**Comments**</span></span>|<span data-ttu-id="37e0a-339">在101.04.76 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="37e0a-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="37e0a-340">防病毒掃描歷程記錄中的專案數上限</span><span class="sxs-lookup"><span data-stu-id="37e0a-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="37e0a-341">指定要保留在掃描記錄中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="37e0a-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="37e0a-342">專案包括過去執行的所有按需掃描及所有防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="37e0a-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="37e0a-343">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-343">Description</span></span>|<span data-ttu-id="37e0a-344">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-344">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-345">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-345">**Key**</span></span>|<span data-ttu-id="37e0a-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="37e0a-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="37e0a-347">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-347">**Data type**</span></span>|<span data-ttu-id="37e0a-348">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-348">String</span></span>|
|<span data-ttu-id="37e0a-349">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-349">**Possible values**</span></span>|<span data-ttu-id="37e0a-350">10000 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-350">10000 (default).</span></span> <span data-ttu-id="37e0a-351">允許的值是從5000專案到15000專案。</span><span class="sxs-lookup"><span data-stu-id="37e0a-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="37e0a-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-352">**Comments**</span></span>|<span data-ttu-id="37e0a-353">在101.04.76 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="37e0a-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="37e0a-354">雲端提供的保護偏好設定</span><span class="sxs-lookup"><span data-stu-id="37e0a-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="37e0a-355">設定設定檔中的 *cloudService* 專案是用來設定產品的雲端驅動保護功能。</span><span class="sxs-lookup"><span data-stu-id="37e0a-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="37e0a-356">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-356">Description</span></span>|<span data-ttu-id="37e0a-357">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-357">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-358">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-358">**Key**</span></span>|<span data-ttu-id="37e0a-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="37e0a-359">cloudService</span></span>|
|<span data-ttu-id="37e0a-360">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-360">**Data type**</span></span>|<span data-ttu-id="37e0a-361">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="37e0a-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="37e0a-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="37e0a-362">**Comments**</span></span>|<span data-ttu-id="37e0a-363">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="37e0a-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="37e0a-364">啟用/停用雲端已傳送保護</span><span class="sxs-lookup"><span data-stu-id="37e0a-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="37e0a-365">決定是否已在裝置上啟用雲端傳送保護。</span><span class="sxs-lookup"><span data-stu-id="37e0a-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="37e0a-366">若要改善服務的安全性，建議您保持此功能開啟。</span><span class="sxs-lookup"><span data-stu-id="37e0a-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="37e0a-367">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-367">Description</span></span>|<span data-ttu-id="37e0a-368">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-368">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-369">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-369">**Key**</span></span>|<span data-ttu-id="37e0a-370">啟用</span><span class="sxs-lookup"><span data-stu-id="37e0a-370">enabled</span></span>|
|<span data-ttu-id="37e0a-371">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-371">**Data type**</span></span>|<span data-ttu-id="37e0a-372">布林值</span><span class="sxs-lookup"><span data-stu-id="37e0a-372">Boolean</span></span>|
|<span data-ttu-id="37e0a-373">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-373">**Possible values**</span></span>|<span data-ttu-id="37e0a-374">true (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-374">true (default)</span></span> <p> <span data-ttu-id="37e0a-375">假</span><span class="sxs-lookup"><span data-stu-id="37e0a-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="37e0a-376">診斷集合層級</span><span class="sxs-lookup"><span data-stu-id="37e0a-376">Diagnostic collection level</span></span>

<span data-ttu-id="37e0a-377">診斷資料是用來將 Defender 設定為安全和更新、偵測、診斷和修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="37e0a-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="37e0a-378">此設定會決定由產品所傳送給 Microsoft 的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="37e0a-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="37e0a-379">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-379">Description</span></span>|<span data-ttu-id="37e0a-380">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-380">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-381">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-381">**Key**</span></span>|<span data-ttu-id="37e0a-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="37e0a-382">diagnosticLevel</span></span>|
|<span data-ttu-id="37e0a-383">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-383">**Data type**</span></span>|<span data-ttu-id="37e0a-384">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-384">String</span></span>|
|<span data-ttu-id="37e0a-385">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-385">**Possible values**</span></span>|<span data-ttu-id="37e0a-386">選用 (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-386">optional (default)</span></span> <p> <span data-ttu-id="37e0a-387">必要</span><span class="sxs-lookup"><span data-stu-id="37e0a-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="37e0a-388">啟用/停用自動範例報送</span><span class="sxs-lookup"><span data-stu-id="37e0a-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="37e0a-389">會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。</span><span class="sxs-lookup"><span data-stu-id="37e0a-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="37e0a-390">有三個層級可用於控制範例提交：</span><span class="sxs-lookup"><span data-stu-id="37e0a-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="37e0a-391">**None**：沒有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="37e0a-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="37e0a-392">**保管庫**：系統會自動提交不含個人身分識別資訊 (PII) 的可疑範例。</span><span class="sxs-lookup"><span data-stu-id="37e0a-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="37e0a-393">此為此設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="37e0a-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="37e0a-394">**All**：將所有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="37e0a-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="37e0a-395">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-395">Description</span></span>|<span data-ttu-id="37e0a-396">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-396">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-397">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-397">**Key**</span></span>|<span data-ttu-id="37e0a-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="37e0a-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="37e0a-399">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-399">**Data type**</span></span>|<span data-ttu-id="37e0a-400">字串</span><span class="sxs-lookup"><span data-stu-id="37e0a-400">String</span></span>|
|<span data-ttu-id="37e0a-401">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-401">**Possible values**</span></span>|<span data-ttu-id="37e0a-402">無</span><span class="sxs-lookup"><span data-stu-id="37e0a-402">none</span></span> <p> <span data-ttu-id="37e0a-403">安全 (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-403">safe (default)</span></span> <p> <span data-ttu-id="37e0a-404">所有</span><span class="sxs-lookup"><span data-stu-id="37e0a-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="37e0a-405">啟用/停用自動安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="37e0a-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="37e0a-406">決定是否自動安裝安全性智慧更新：</span><span class="sxs-lookup"><span data-stu-id="37e0a-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="37e0a-407">說明</span><span class="sxs-lookup"><span data-stu-id="37e0a-407">Description</span></span>|<span data-ttu-id="37e0a-408">值</span><span class="sxs-lookup"><span data-stu-id="37e0a-408">Value</span></span>|
|---|---|
|<span data-ttu-id="37e0a-409">**Key**</span><span class="sxs-lookup"><span data-stu-id="37e0a-409">**Key**</span></span>|<span data-ttu-id="37e0a-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="37e0a-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="37e0a-411">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="37e0a-411">**Data type**</span></span>|<span data-ttu-id="37e0a-412">布林值</span><span class="sxs-lookup"><span data-stu-id="37e0a-412">Boolean</span></span>|
|<span data-ttu-id="37e0a-413">**可能值**</span><span class="sxs-lookup"><span data-stu-id="37e0a-413">**Possible values**</span></span>|<span data-ttu-id="37e0a-414">true (預設) </span><span class="sxs-lookup"><span data-stu-id="37e0a-414">true (default)</span></span> <p> <span data-ttu-id="37e0a-415">假</span><span class="sxs-lookup"><span data-stu-id="37e0a-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="37e0a-416">建議的設定設定檔</span><span class="sxs-lookup"><span data-stu-id="37e0a-416">Recommended configuration profile</span></span>

<span data-ttu-id="37e0a-417">若要開始使用，我們建議您的企業使用下列設定設定檔，以利用所有供 Endpoint 的 Defender 提供的保護功能。</span><span class="sxs-lookup"><span data-stu-id="37e0a-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="37e0a-418">下列設定檔將會：</span><span class="sxs-lookup"><span data-stu-id="37e0a-418">The following configuration profile will:</span></span>

- <span data-ttu-id="37e0a-419">啟用 (RTP) 的即時保護</span><span class="sxs-lookup"><span data-stu-id="37e0a-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="37e0a-420">指定如何處理下列威脅類型：</span><span class="sxs-lookup"><span data-stu-id="37e0a-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="37e0a-421">封鎖 **(PUA) 可能有害的應用程式**</span><span class="sxs-lookup"><span data-stu-id="37e0a-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="37e0a-422">將 bombs 具有高壓縮率) 的封存檔 (**檔案**，審核至產品記錄</span><span class="sxs-lookup"><span data-stu-id="37e0a-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="37e0a-423">啟用自動安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="37e0a-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="37e0a-424">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="37e0a-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="37e0a-425">啟用層級的自動範例提交 `safe`</span><span class="sxs-lookup"><span data-stu-id="37e0a-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="37e0a-426">範例設定檔</span><span class="sxs-lookup"><span data-stu-id="37e0a-426">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="37e0a-427">完整設定檔範例</span><span class="sxs-lookup"><span data-stu-id="37e0a-427">Full configuration profile example</span></span>

<span data-ttu-id="37e0a-428">下列設定設定檔包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要更進一步控制產品。</span><span class="sxs-lookup"><span data-stu-id="37e0a-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="37e0a-429">完整設定檔</span><span class="sxs-lookup"><span data-stu-id="37e0a-429">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="37e0a-430">設定設定檔驗證</span><span class="sxs-lookup"><span data-stu-id="37e0a-430">Configuration profile validation</span></span>

<span data-ttu-id="37e0a-431">設定設定檔必須是有效的 JSON 格式檔。</span><span class="sxs-lookup"><span data-stu-id="37e0a-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="37e0a-432">有許多工具可以用來確認這一點。</span><span class="sxs-lookup"><span data-stu-id="37e0a-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="37e0a-433">例如，如果您已 `python` 在裝置上安裝：</span><span class="sxs-lookup"><span data-stu-id="37e0a-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="37e0a-434">如果 JSON 格式正確，上述命令會將其輸出到終端，並傳回的退出程式碼 `0` 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="37e0a-435">否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。</span><span class="sxs-lookup"><span data-stu-id="37e0a-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="37e0a-436">驗證檔案上的 mdatp_managed.js是否如預期般運作</span><span class="sxs-lookup"><span data-stu-id="37e0a-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="37e0a-437">若要確認您的/etc/opt/microsoft/mdatp/managed/mdatp_managed.js開啟中是否正常運作，您應該會在下列設定旁看到「[managed]」：</span><span class="sxs-lookup"><span data-stu-id="37e0a-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="37e0a-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="37e0a-438">cloud_enabled</span></span>
- <span data-ttu-id="37e0a-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="37e0a-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="37e0a-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="37e0a-440">passive_mode_enabled</span></span>
- <span data-ttu-id="37e0a-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="37e0a-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="37e0a-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="37e0a-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="37e0a-443">為使 mdatp_managed.js生效，不需要重新開機 wdavdaemon。</span><span class="sxs-lookup"><span data-stu-id="37e0a-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="37e0a-444">設定設定檔部署</span><span class="sxs-lookup"><span data-stu-id="37e0a-444">Configuration profile deployment</span></span>

<span data-ttu-id="37e0a-445">在您為企業建立設定檔之後，您可以透過企業使用的管理工具加以部署。</span><span class="sxs-lookup"><span data-stu-id="37e0a-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="37e0a-446">Linux 上的 Defender for the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file 中讀取 managed configuration。</span><span class="sxs-lookup"><span data-stu-id="37e0a-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
