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
ms.openlocfilehash: 29505a6e975fdfa2283efe3391c615e40e678164
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346375"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="bfbe1-104">在 Linux 上設定 Microsoft Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="bfbe1-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bfbe1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-105">**Applies to:**</span></span>
- [<span data-ttu-id="bfbe1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bfbe1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bfbe1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfbe1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bfbe1-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bfbe1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bfbe1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="bfbe1-110">本主題包含如何在企業環境中設定適用于 Linux 之 Defender 的 Defender 偏好設定的指示。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="bfbe1-111">如果您想要從命令列在裝置上設定產品，請參閱 [Resources](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="bfbe1-112">在企業環境中，可以透過設定設定檔來管理 Linux 上的 Defender。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="bfbe1-113">此設定檔是從您選擇的管理工具部署。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="bfbe1-114">由企業管理的喜好設定會優先于裝置上的本機設定。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="bfbe1-115">換句話說，您企業中的使用者無法變更透過此設定檔設定的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="bfbe1-116">本文說明此設定檔的結構 (，包括可供您開始使用的建議設定檔) 及如何部署設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="bfbe1-117">設定設定檔結構</span><span class="sxs-lookup"><span data-stu-id="bfbe1-117">Configuration profile structure</span></span>

<span data-ttu-id="bfbe1-118">設定設定檔是由按鍵 (所識別的專案所組成的一個 json 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="bfbe1-119">值可以是簡單的，例如數值或複雜，例如首選項的嵌套清單。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="bfbe1-120">一般來說，您會使用設定管理工具將名稱中的檔案推入 ```mdatp_managed.json``` 該位置 ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="bfbe1-121">設定設定檔的最上層包含產品的子領域首選項及專案，在下一節將詳細說明。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="bfbe1-122">防病毒引擎偏好設定</span><span class="sxs-lookup"><span data-stu-id="bfbe1-122">Antivirus engine preferences</span></span>

<span data-ttu-id="bfbe1-123">設定設定檔的 [ *antivirusEngine* ] 區段是用來管理產品之防病毒元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-124">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-124">**Key**</span></span> | <span data-ttu-id="bfbe1-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="bfbe1-125">antivirusEngine</span></span> |
| <span data-ttu-id="bfbe1-126">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-126">**Data type**</span></span> | <span data-ttu-id="bfbe1-127">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="bfbe1-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-128">**Comments**</span></span> | <span data-ttu-id="bfbe1-129">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="bfbe1-130">啟用/停用即時保護</span><span class="sxs-lookup"><span data-stu-id="bfbe1-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="bfbe1-131">會決定在啟用或未啟用) 時，是否即時保護 (掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-132">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-132">**Key**</span></span> | <span data-ttu-id="bfbe1-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="bfbe1-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="bfbe1-134">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-134">**Data type**</span></span> | <span data-ttu-id="bfbe1-135">布林值</span><span class="sxs-lookup"><span data-stu-id="bfbe1-135">Boolean</span></span> |
| <span data-ttu-id="bfbe1-136">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-136">**Possible values**</span></span> | <span data-ttu-id="bfbe1-137">true (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-137">true (default)</span></span> <br/> <span data-ttu-id="bfbe1-138">假</span><span class="sxs-lookup"><span data-stu-id="bfbe1-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="bfbe1-139">啟用/停用被動模式</span><span class="sxs-lookup"><span data-stu-id="bfbe1-139">Enable / disable passive mode</span></span>

<span data-ttu-id="bfbe1-140">決定防病毒引擎是否以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="bfbe1-141">在被動模式：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-141">In passive mode:</span></span>
- <span data-ttu-id="bfbe1-142">已關閉即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="bfbe1-143">已開啟隨選掃描。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="bfbe1-144">關閉自動威脅修復功能。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="bfbe1-145">已開啟安全性智慧更新。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="bfbe1-146">[狀態] 功能表圖示已隱藏。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-147">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-147">**Key**</span></span> | <span data-ttu-id="bfbe1-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="bfbe1-148">passiveMode</span></span> |
| <span data-ttu-id="bfbe1-149">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-149">**Data type**</span></span> | <span data-ttu-id="bfbe1-150">布林值</span><span class="sxs-lookup"><span data-stu-id="bfbe1-150">Boolean</span></span> |
| <span data-ttu-id="bfbe1-151">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-151">**Possible values**</span></span> | <span data-ttu-id="bfbe1-152">false (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-152">false (default)</span></span> <br/> <span data-ttu-id="bfbe1-153">真</span><span class="sxs-lookup"><span data-stu-id="bfbe1-153">true</span></span> |
| <span data-ttu-id="bfbe1-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-154">**Comments**</span></span> | <span data-ttu-id="bfbe1-155">在100.67.60 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="bfbe1-156">排除合併原則</span><span class="sxs-lookup"><span data-stu-id="bfbe1-156">Exclusion merge policy</span></span>

<span data-ttu-id="bfbe1-157">指定排除專案的合併原則。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="bfbe1-158">它可以是管理員定義和使用者定義排除的組合 (`merge`) 或只) 系統管理員定義的排除 (`admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="bfbe1-159">您可以使用此設定來限制本機使用者定義自己的排除專案。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-160">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-160">**Key**</span></span> | <span data-ttu-id="bfbe1-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="bfbe1-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="bfbe1-162">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-162">**Data type**</span></span> | <span data-ttu-id="bfbe1-163">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-163">String</span></span> |
| <span data-ttu-id="bfbe1-164">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-164">**Possible values**</span></span> | <span data-ttu-id="bfbe1-165">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-165">merge (default)</span></span> <br/> <span data-ttu-id="bfbe1-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="bfbe1-166">admin_only</span></span> |
| <span data-ttu-id="bfbe1-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-167">**Comments**</span></span> | <span data-ttu-id="bfbe1-168">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="bfbe1-169">掃描排除</span><span class="sxs-lookup"><span data-stu-id="bfbe1-169">Scan exclusions</span></span>

<span data-ttu-id="bfbe1-170">已從掃描中排除的實體。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="bfbe1-171">您可以使用完整路徑、副檔名或檔案名來指定排除。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="bfbe1-172"> (排除專案是以專案陣列的形式指定，管理員可以根據需要依任何順序指定任意數目的元素。 ) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-173">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-173">**Key**</span></span> | <span data-ttu-id="bfbe1-174">排除</span><span class="sxs-lookup"><span data-stu-id="bfbe1-174">exclusions</span></span> |
| <span data-ttu-id="bfbe1-175">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-175">**Data type**</span></span> | <span data-ttu-id="bfbe1-176">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="bfbe1-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-177">**Comments**</span></span> | <span data-ttu-id="bfbe1-178">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="bfbe1-179">**排除的類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-179">**Type of exclusion**</span></span>

<span data-ttu-id="bfbe1-180">指定排除在掃描之外的內容類型。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-181">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-181">**Key**</span></span> | <span data-ttu-id="bfbe1-182">$type</span><span class="sxs-lookup"><span data-stu-id="bfbe1-182">$type</span></span> |
| <span data-ttu-id="bfbe1-183">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-183">**Data type**</span></span> | <span data-ttu-id="bfbe1-184">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-184">String</span></span> |
| <span data-ttu-id="bfbe1-185">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-185">**Possible values**</span></span> | <span data-ttu-id="bfbe1-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="bfbe1-186">excludedPath</span></span> <br/> <span data-ttu-id="bfbe1-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="bfbe1-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="bfbe1-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="bfbe1-188">excludedFileName</span></span> |
|||

<span data-ttu-id="bfbe1-189">**排除內容的路徑**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-189">**Path to excluded content**</span></span>

<span data-ttu-id="bfbe1-190">用於從掃描的完整檔案路徑中排除內容。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-191">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-191">**Key**</span></span> | <span data-ttu-id="bfbe1-192">路徑</span><span class="sxs-lookup"><span data-stu-id="bfbe1-192">path</span></span> |
| <span data-ttu-id="bfbe1-193">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-193">**Data type**</span></span> | <span data-ttu-id="bfbe1-194">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-194">String</span></span> |
| <span data-ttu-id="bfbe1-195">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-195">**Possible values**</span></span> | <span data-ttu-id="bfbe1-196">有效路徑</span><span class="sxs-lookup"><span data-stu-id="bfbe1-196">valid paths</span></span> |
| <span data-ttu-id="bfbe1-197">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-197">**Comments**</span></span> | <span data-ttu-id="bfbe1-198">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="bfbe1-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="bfbe1-199">**(檔/目錄的路徑類型)**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="bfbe1-200">會指出 *path* 屬性參照的是檔案或目錄。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-200">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="bfbe1-201">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-201">**Key**</span></span> | <span data-ttu-id="bfbe1-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="bfbe1-202">isDirectory</span></span> |
| <span data-ttu-id="bfbe1-203">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-203">**Data type**</span></span> | <span data-ttu-id="bfbe1-204">布林值</span><span class="sxs-lookup"><span data-stu-id="bfbe1-204">Boolean</span></span> |
| <span data-ttu-id="bfbe1-205">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-205">**Possible values**</span></span> | <span data-ttu-id="bfbe1-206">false (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-206">false (default)</span></span> <br/> <span data-ttu-id="bfbe1-207">真</span><span class="sxs-lookup"><span data-stu-id="bfbe1-207">true</span></span> |
| <span data-ttu-id="bfbe1-208">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-208">**Comments**</span></span> | <span data-ttu-id="bfbe1-209">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="bfbe1-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="bfbe1-210">**從掃描排除的副檔名**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="bfbe1-211">用於從 [掃描者] 副檔名排除內容。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-212">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-212">**Key**</span></span> | <span data-ttu-id="bfbe1-213">擴展</span><span class="sxs-lookup"><span data-stu-id="bfbe1-213">extension</span></span> |
| <span data-ttu-id="bfbe1-214">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-214">**Data type**</span></span> | <span data-ttu-id="bfbe1-215">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-215">String</span></span> |
| <span data-ttu-id="bfbe1-216">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-216">**Possible values**</span></span> | <span data-ttu-id="bfbe1-217">有效的副檔名</span><span class="sxs-lookup"><span data-stu-id="bfbe1-217">valid file extensions</span></span> |
| <span data-ttu-id="bfbe1-218">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-218">**Comments**</span></span> | <span data-ttu-id="bfbe1-219">僅適用于 *excludedFileExtension* *$type*</span><span class="sxs-lookup"><span data-stu-id="bfbe1-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="bfbe1-220">**從掃描排除的處理常式**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="bfbe1-221">指定從掃描排除所有檔案活動的處理常式。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="bfbe1-222">您可以透過名稱來指定程式 (例如， `cat`) 或完整路徑 (例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-223">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-223">**Key**</span></span> | <span data-ttu-id="bfbe1-224">name</span><span class="sxs-lookup"><span data-stu-id="bfbe1-224">name</span></span> |
| <span data-ttu-id="bfbe1-225">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-225">**Data type**</span></span> | <span data-ttu-id="bfbe1-226">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-226">String</span></span> |
| <span data-ttu-id="bfbe1-227">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-227">**Possible values**</span></span> | <span data-ttu-id="bfbe1-228">任何字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-228">any string</span></span> |
| <span data-ttu-id="bfbe1-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-229">**Comments**</span></span> | <span data-ttu-id="bfbe1-230">僅適用于 *excludedFileName* *$type*</span><span class="sxs-lookup"><span data-stu-id="bfbe1-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="bfbe1-231">允許的威脅</span><span class="sxs-lookup"><span data-stu-id="bfbe1-231">Allowed threats</span></span>

<span data-ttu-id="bfbe1-232">根據其名稱) 所識別的威脅清單，其 (未被產品封鎖，但改為允許執行。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-233">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-233">**Key**</span></span> | <span data-ttu-id="bfbe1-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="bfbe1-234">allowedThreats</span></span> |
| <span data-ttu-id="bfbe1-235">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-235">**Data type**</span></span> | <span data-ttu-id="bfbe1-236">字串陣列</span><span class="sxs-lookup"><span data-stu-id="bfbe1-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="bfbe1-237">不允許的威脅動作</span><span class="sxs-lookup"><span data-stu-id="bfbe1-237">Disallowed threat actions</span></span>

<span data-ttu-id="bfbe1-238">限制偵測到威脅時，裝置的本機使用者可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="bfbe1-239">在此清單中包含的動作不會顯示在使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-240">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-240">**Key**</span></span> | <span data-ttu-id="bfbe1-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="bfbe1-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="bfbe1-242">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-242">**Data type**</span></span> | <span data-ttu-id="bfbe1-243">字串陣列</span><span class="sxs-lookup"><span data-stu-id="bfbe1-243">Array of strings</span></span> |
| <span data-ttu-id="bfbe1-244">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-244">**Possible values**</span></span> | <span data-ttu-id="bfbe1-245">允許 (限制使用者允許威脅) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="bfbe1-246">restore (會限制使用者從隔離區還原威脅) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="bfbe1-247">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-247">**Comments**</span></span> | <span data-ttu-id="bfbe1-248">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="bfbe1-249">威脅類型設定</span><span class="sxs-lookup"><span data-stu-id="bfbe1-249">Threat type settings</span></span>

<span data-ttu-id="bfbe1-250">防病毒引擎中的 *threatTypeSettings* 首選項是用來控制產品如何處理特定威脅類型。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-251">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-251">**Key**</span></span> | <span data-ttu-id="bfbe1-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="bfbe1-252">threatTypeSettings</span></span> |
| <span data-ttu-id="bfbe1-253">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-253">**Data type**</span></span> | <span data-ttu-id="bfbe1-254">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="bfbe1-255">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-255">**Comments**</span></span> | <span data-ttu-id="bfbe1-256">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="bfbe1-257">**威脅類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-257">**Threat type**</span></span>

<span data-ttu-id="bfbe1-258">設定行為的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-259">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-259">**Key**</span></span> | <span data-ttu-id="bfbe1-260">機碼</span><span class="sxs-lookup"><span data-stu-id="bfbe1-260">key</span></span> |
| <span data-ttu-id="bfbe1-261">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-261">**Data type**</span></span> | <span data-ttu-id="bfbe1-262">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-262">String</span></span> |
| <span data-ttu-id="bfbe1-263">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-263">**Possible values**</span></span> | <span data-ttu-id="bfbe1-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="bfbe1-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="bfbe1-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="bfbe1-265">archive_bomb</span></span> |
|||

<span data-ttu-id="bfbe1-266">**要採取的動作**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-266">**Action to take**</span></span>

<span data-ttu-id="bfbe1-267">當您在上述區段中所指定類型的威脅到來時採取的動作。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="bfbe1-268">可以是：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-268">Can be:</span></span>

- <span data-ttu-id="bfbe1-269">**Audit**：此裝置沒有針對這類威脅進行保護，但是會記錄有關威脅的專案。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="bfbe1-270">**封鎖**：針對這類威脅保護裝置，並在安全性主控台中通知您。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="bfbe1-271">**Off**：裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-272">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-272">**Key**</span></span> | <span data-ttu-id="bfbe1-273">數值</span><span class="sxs-lookup"><span data-stu-id="bfbe1-273">value</span></span> |
| <span data-ttu-id="bfbe1-274">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-274">**Data type**</span></span> | <span data-ttu-id="bfbe1-275">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-275">String</span></span> |
| <span data-ttu-id="bfbe1-276">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-276">**Possible values**</span></span> | <span data-ttu-id="bfbe1-277">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-277">audit (default)</span></span> <br/> <span data-ttu-id="bfbe1-278">塊</span><span class="sxs-lookup"><span data-stu-id="bfbe1-278">block</span></span> <br/> <span data-ttu-id="bfbe1-279">遠離</span><span class="sxs-lookup"><span data-stu-id="bfbe1-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="bfbe1-280">威脅類型設定合併原則</span><span class="sxs-lookup"><span data-stu-id="bfbe1-280">Threat type settings merge policy</span></span>

<span data-ttu-id="bfbe1-281">指定威脅類型設定的合併原則。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="bfbe1-282">這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="bfbe1-283">此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-284">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-284">**Key**</span></span> | <span data-ttu-id="bfbe1-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="bfbe1-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="bfbe1-286">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-286">**Data type**</span></span> | <span data-ttu-id="bfbe1-287">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-287">String</span></span> |
| <span data-ttu-id="bfbe1-288">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-288">**Possible values**</span></span> | <span data-ttu-id="bfbe1-289">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-289">merge (default)</span></span> <br/> <span data-ttu-id="bfbe1-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="bfbe1-290">admin_only</span></span> |
| <span data-ttu-id="bfbe1-291">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-291">**Comments**</span></span> | <span data-ttu-id="bfbe1-292">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="bfbe1-293">防病毒掃描記錄保留 (天數) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="bfbe1-294">指定在裝置上的掃描歷程記錄中保留結果的天數。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="bfbe1-295">舊的掃描結果會從歷史記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="bfbe1-296">也會從磁片中移除的舊隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-297">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-297">**Key**</span></span> | <span data-ttu-id="bfbe1-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="bfbe1-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="bfbe1-299">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-299">**Data type**</span></span> | <span data-ttu-id="bfbe1-300">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-300">String</span></span> |
| <span data-ttu-id="bfbe1-301">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-301">**Possible values**</span></span> | <span data-ttu-id="bfbe1-302">90 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-302">90 (default).</span></span> <span data-ttu-id="bfbe1-303">允許的值介於1天到180天。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="bfbe1-304">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-304">**Comments**</span></span> | <span data-ttu-id="bfbe1-305">在101.04.76 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="bfbe1-306">防病毒掃描歷程記錄中的專案數上限</span><span class="sxs-lookup"><span data-stu-id="bfbe1-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="bfbe1-307">指定要保留在掃描記錄中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="bfbe1-308">專案包括過去執行的所有按需掃描及所有防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-309">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-309">**Key**</span></span> | <span data-ttu-id="bfbe1-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="bfbe1-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="bfbe1-311">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-311">**Data type**</span></span> | <span data-ttu-id="bfbe1-312">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-312">String</span></span> |
| <span data-ttu-id="bfbe1-313">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-313">**Possible values**</span></span> | <span data-ttu-id="bfbe1-314">10000 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-314">10000 (default).</span></span> <span data-ttu-id="bfbe1-315">允許的值是從5000專案到15000專案。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="bfbe1-316">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-316">**Comments**</span></span> | <span data-ttu-id="bfbe1-317">在101.04.76 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="bfbe1-318">雲端提供的保護偏好設定</span><span class="sxs-lookup"><span data-stu-id="bfbe1-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="bfbe1-319">設定設定檔中的 *cloudService* 專案是用來設定產品的雲端驅動保護功能。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-320">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-320">**Key**</span></span> | <span data-ttu-id="bfbe1-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="bfbe1-321">cloudService</span></span> |
| <span data-ttu-id="bfbe1-322">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-322">**Data type**</span></span> | <span data-ttu-id="bfbe1-323">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="bfbe1-324">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-324">**Comments**</span></span> | <span data-ttu-id="bfbe1-325">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="bfbe1-326">啟用/停用雲端已傳送保護</span><span class="sxs-lookup"><span data-stu-id="bfbe1-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="bfbe1-327">決定是否已在裝置上啟用雲端傳送保護。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="bfbe1-328">若要改善服務的安全性，建議您保持此功能開啟。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-329">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-329">**Key**</span></span> | <span data-ttu-id="bfbe1-330">啟用</span><span class="sxs-lookup"><span data-stu-id="bfbe1-330">enabled</span></span> |
| <span data-ttu-id="bfbe1-331">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-331">**Data type**</span></span> | <span data-ttu-id="bfbe1-332">布林值</span><span class="sxs-lookup"><span data-stu-id="bfbe1-332">Boolean</span></span> |
| <span data-ttu-id="bfbe1-333">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-333">**Possible values**</span></span> | <span data-ttu-id="bfbe1-334">true (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-334">true (default)</span></span> <br/> <span data-ttu-id="bfbe1-335">假</span><span class="sxs-lookup"><span data-stu-id="bfbe1-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="bfbe1-336">診斷集合層級</span><span class="sxs-lookup"><span data-stu-id="bfbe1-336">Diagnostic collection level</span></span>

<span data-ttu-id="bfbe1-337">診斷資料是用來將 Defender 設定為安全和更新、偵測、診斷和修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="bfbe1-338">此設定會決定由產品所傳送給 Microsoft 的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-339">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-339">**Key**</span></span> | <span data-ttu-id="bfbe1-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="bfbe1-340">diagnosticLevel</span></span> |
| <span data-ttu-id="bfbe1-341">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-341">**Data type**</span></span> | <span data-ttu-id="bfbe1-342">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-342">String</span></span> |
| <span data-ttu-id="bfbe1-343">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-343">**Possible values**</span></span> | <span data-ttu-id="bfbe1-344">選用 (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-344">optional (default)</span></span> <br/> <span data-ttu-id="bfbe1-345">必要</span><span class="sxs-lookup"><span data-stu-id="bfbe1-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="bfbe1-346">啟用/停用自動範例報送</span><span class="sxs-lookup"><span data-stu-id="bfbe1-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="bfbe1-347">會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="bfbe1-348">有三個層級可用於控制範例提交：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="bfbe1-349">**None**：沒有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="bfbe1-350">**安全**：只有不含個人身分識別資訊 (PII) 的可疑範例會自動提交。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="bfbe1-351">此為此設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="bfbe1-352">**All**：將所有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-353">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-353">**Key**</span></span> | <span data-ttu-id="bfbe1-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="bfbe1-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="bfbe1-355">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-355">**Data type**</span></span> | <span data-ttu-id="bfbe1-356">字串</span><span class="sxs-lookup"><span data-stu-id="bfbe1-356">String</span></span> |
| <span data-ttu-id="bfbe1-357">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-357">**Possible values**</span></span> | <span data-ttu-id="bfbe1-358">無</span><span class="sxs-lookup"><span data-stu-id="bfbe1-358">none</span></span> <br/> <span data-ttu-id="bfbe1-359">安全 (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-359">safe (default)</span></span> <br/> <span data-ttu-id="bfbe1-360">所有</span><span class="sxs-lookup"><span data-stu-id="bfbe1-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="bfbe1-361">啟用/停用自動安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="bfbe1-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="bfbe1-362">決定是否自動安裝安全性智慧更新：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="bfbe1-363">**機碼**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-363">**Key**</span></span> | <span data-ttu-id="bfbe1-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="bfbe1-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="bfbe1-365">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-365">**Data type**</span></span> | <span data-ttu-id="bfbe1-366">布林值</span><span class="sxs-lookup"><span data-stu-id="bfbe1-366">Boolean</span></span> |
| <span data-ttu-id="bfbe1-367">**可能值**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-367">**Possible values**</span></span> | <span data-ttu-id="bfbe1-368">true (預設) </span><span class="sxs-lookup"><span data-stu-id="bfbe1-368">true (default)</span></span> <br/> <span data-ttu-id="bfbe1-369">假</span><span class="sxs-lookup"><span data-stu-id="bfbe1-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="bfbe1-370">建議的設定設定檔</span><span class="sxs-lookup"><span data-stu-id="bfbe1-370">Recommended configuration profile</span></span>

<span data-ttu-id="bfbe1-371">若要開始使用，我們建議您的企業使用下列設定設定檔，以利用所有供 Endpoint 的 Defender 提供的保護功能。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="bfbe1-372">下列設定檔將會：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-372">The following configuration profile will:</span></span>

- <span data-ttu-id="bfbe1-373">啟用 (RTP) 的即時保護</span><span class="sxs-lookup"><span data-stu-id="bfbe1-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="bfbe1-374">指定如何處理下列威脅類型：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="bfbe1-375">封鎖 **(PUA) 可能有害的應用程式**</span><span class="sxs-lookup"><span data-stu-id="bfbe1-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="bfbe1-376">將 bombs 具有高壓縮率) 的封存檔 (**檔案**，審核至產品記錄</span><span class="sxs-lookup"><span data-stu-id="bfbe1-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="bfbe1-377">啟用自動安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="bfbe1-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="bfbe1-378">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="bfbe1-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="bfbe1-379">啟用層級的自動範例提交 `safe`</span><span class="sxs-lookup"><span data-stu-id="bfbe1-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="bfbe1-380">範例設定檔</span><span class="sxs-lookup"><span data-stu-id="bfbe1-380">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="bfbe1-381">完整設定檔範例</span><span class="sxs-lookup"><span data-stu-id="bfbe1-381">Full configuration profile example</span></span>

<span data-ttu-id="bfbe1-382">下列設定設定檔包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要更進一步控制產品。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="bfbe1-383">完整設定檔</span><span class="sxs-lookup"><span data-stu-id="bfbe1-383">Full profile</span></span>

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
            "extension":"pdf"
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

## <a name="configuration-profile-validation"></a><span data-ttu-id="bfbe1-384">設定設定檔驗證</span><span class="sxs-lookup"><span data-stu-id="bfbe1-384">Configuration profile validation</span></span>

<span data-ttu-id="bfbe1-385">設定設定檔必須是有效的 JSON 格式檔。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="bfbe1-386">有許多工具可以用來確認這一點。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="bfbe1-387">例如，如果您已 `python` 在裝置上安裝：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="bfbe1-388">如果 JSON 格式正確，上述命令會將其輸出到終端，並傳回的退出程式碼 `0` 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="bfbe1-389">否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="bfbe1-390">驗證檔案上的 mdatp_managed.js是否如預期般運作</span><span class="sxs-lookup"><span data-stu-id="bfbe1-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="bfbe1-391">若要確認您的/etc/opt/microsoft/mdatp/managed/mdatp_managed.js開啟中是否正常運作，您應該會在下列設定旁看到「[managed]」：</span><span class="sxs-lookup"><span data-stu-id="bfbe1-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="bfbe1-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="bfbe1-392">cloud_enabled</span></span>
- <span data-ttu-id="bfbe1-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="bfbe1-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="bfbe1-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="bfbe1-394">passice_mode_enabled</span></span>
- <span data-ttu-id="bfbe1-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="bfbe1-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="bfbe1-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="bfbe1-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="bfbe1-397">為使 mdatp_managed.js生效，不需要重新開機 wdavdaemon。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="bfbe1-398">設定設定檔部署</span><span class="sxs-lookup"><span data-stu-id="bfbe1-398">Configuration profile deployment</span></span>

<span data-ttu-id="bfbe1-399">在您為企業建立設定檔之後，您可以透過企業使用的管理工具加以部署。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="bfbe1-400">Linux 上的 Defender for the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file 中讀取 managed configuration。</span><span class="sxs-lookup"><span data-stu-id="bfbe1-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
