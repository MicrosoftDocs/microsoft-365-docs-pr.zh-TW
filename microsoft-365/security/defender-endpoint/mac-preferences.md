---
title: 設定 Mac 上的 Microsoft Defender for Endpoint 的喜好設定
description: 在企業組織中設定 Mac 上端點的 MMicrosoft Defender。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，management，喜好設定，enterprise，intune，jamf，macos，catalina，mojave，high 塞拉里昂
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346399"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3dadc-104">在 macOS 上設定 Microsoft Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="3dadc-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3dadc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3dadc-105">**Applies to:**</span></span>

- [<span data-ttu-id="3dadc-106">macOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3dadc-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="3dadc-107">本文包含如何針對企業組織中 macOS 之 Microsoft Defender for Endpoint 設定偏好設定的指示。</span><span class="sxs-lookup"><span data-stu-id="3dadc-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="3dadc-108">若要在使用命令列介面的 macOS 上設定 Microsoft Defender for Endpoint，請參閱 [Resources](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="3dadc-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="3dadc-109">摘要</span><span class="sxs-lookup"><span data-stu-id="3dadc-109">Summary</span></span>

<span data-ttu-id="3dadc-110">在企業組織中，可透過使用其中一種管理工具部署的設定檔來管理 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="3dadc-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="3dadc-111">安全作業小組所管理的喜好設定優先順序高於裝置上本機設定的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="3dadc-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="3dadc-112">變更透過設定設定檔設定的喜好設定時，需要提升許可權，且不需要系統管理許可權的使用者才能使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="3dadc-113">本文說明設定檔的結構，包含您可以用來開始使用的建議設定檔，並提供如何部署設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="3dadc-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="3dadc-114">設定設定檔結構</span><span class="sxs-lookup"><span data-stu-id="3dadc-114">Configuration profile structure</span></span>

<span data-ttu-id="3dadc-115">設定設定檔是由按鍵 (所識別之專案所識別的 *plist* 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。</span><span class="sxs-lookup"><span data-stu-id="3dadc-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="3dadc-116">值既可以是簡單的 (例如數值) 或複雜，例如首選項的嵌套清單。</span><span class="sxs-lookup"><span data-stu-id="3dadc-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="3dadc-117">設定設定檔的版面配置取決於您所使用的管理主控台。</span><span class="sxs-lookup"><span data-stu-id="3dadc-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="3dadc-118">下列各節包含 JAMF 及 Intune 之設定檔的範例。</span><span class="sxs-lookup"><span data-stu-id="3dadc-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="3dadc-119">設定設定檔的最上層包括 Microsoft Defender for Endpoint 之子領域的產品範圍偏好設定和專案，在下一節將詳細說明。</span><span class="sxs-lookup"><span data-stu-id="3dadc-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="3dadc-120">防病毒引擎偏好設定</span><span class="sxs-lookup"><span data-stu-id="3dadc-120">Antivirus engine preferences</span></span>

<span data-ttu-id="3dadc-121">設定設定檔的 [ *antivirusEngine* ] 區段是用來管理 Microsoft Defender for Endpoint 之防病毒元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="3dadc-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="3dadc-122">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-122">Section</span></span>|<span data-ttu-id="3dadc-123">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-124">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-125">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-125">**Key**</span></span> | <span data-ttu-id="3dadc-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="3dadc-126">antivirusEngine</span></span> |
| <span data-ttu-id="3dadc-127">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-127">**Data type**</span></span> | <span data-ttu-id="3dadc-128">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="3dadc-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3dadc-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-129">**Comments**</span></span> | <span data-ttu-id="3dadc-130">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="3dadc-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="3dadc-131">啟用/停用即時保護</span><span class="sxs-lookup"><span data-stu-id="3dadc-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="3dadc-132">指定是否要啟用即時保護，以在存取檔時進行掃描。</span><span class="sxs-lookup"><span data-stu-id="3dadc-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="3dadc-133">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-133">Section</span></span>|<span data-ttu-id="3dadc-134">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-135">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-136">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-136">**Key**</span></span> | <span data-ttu-id="3dadc-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="3dadc-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="3dadc-138">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-138">**Data type**</span></span> | <span data-ttu-id="3dadc-139">布林值</span><span class="sxs-lookup"><span data-stu-id="3dadc-139">Boolean</span></span> |
| <span data-ttu-id="3dadc-140">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-140">**Possible values**</span></span> | <span data-ttu-id="3dadc-141">true (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-141">true (default)</span></span> <br/> <span data-ttu-id="3dadc-142">假</span><span class="sxs-lookup"><span data-stu-id="3dadc-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="3dadc-143">啟用/停用被動模式</span><span class="sxs-lookup"><span data-stu-id="3dadc-143">Enable / disable passive mode</span></span>

<span data-ttu-id="3dadc-144">指定防病毒引擎是否以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="3dadc-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="3dadc-145">被動式模式的含義如下：</span><span class="sxs-lookup"><span data-stu-id="3dadc-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="3dadc-146">已關閉即時保護</span><span class="sxs-lookup"><span data-stu-id="3dadc-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="3dadc-147">已開啟隨選掃描</span><span class="sxs-lookup"><span data-stu-id="3dadc-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="3dadc-148">關閉自動威脅修復功能</span><span class="sxs-lookup"><span data-stu-id="3dadc-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="3dadc-149">已開啟安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="3dadc-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="3dadc-150">隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="3dadc-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="3dadc-151">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-151">Section</span></span>|<span data-ttu-id="3dadc-152">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-153">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-154">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-154">**Key**</span></span> | <span data-ttu-id="3dadc-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="3dadc-155">passiveMode</span></span> |
| <span data-ttu-id="3dadc-156">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-156">**Data type**</span></span> | <span data-ttu-id="3dadc-157">布林值</span><span class="sxs-lookup"><span data-stu-id="3dadc-157">Boolean</span></span> |
| <span data-ttu-id="3dadc-158">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-158">**Possible values**</span></span> | <span data-ttu-id="3dadc-159">false (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-159">false (default)</span></span> <br/> <span data-ttu-id="3dadc-160">真</span><span class="sxs-lookup"><span data-stu-id="3dadc-160">true</span></span> |
| <span data-ttu-id="3dadc-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-161">**Comments**</span></span> | <span data-ttu-id="3dadc-162">可在 Microsoft Defender for Endpoint 版本100.67.60 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="3dadc-163">排除合併原則</span><span class="sxs-lookup"><span data-stu-id="3dadc-163">Exclusion merge policy</span></span>

<span data-ttu-id="3dadc-164">指定排除的合併原則。</span><span class="sxs-lookup"><span data-stu-id="3dadc-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="3dadc-165">這可以是管理員定義和使用者定義排除 (的組合， `merge`) 或僅限系統管理員定義的排除 (`admin_only`) 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="3dadc-166">您可以使用此設定來限制本機使用者定義自己的排除專案。</span><span class="sxs-lookup"><span data-stu-id="3dadc-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="3dadc-167">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-167">Section</span></span>|<span data-ttu-id="3dadc-168">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-169">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-170">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-170">**Key**</span></span> | <span data-ttu-id="3dadc-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3dadc-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="3dadc-172">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-172">**Data type**</span></span> | <span data-ttu-id="3dadc-173">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-173">String</span></span> |
| <span data-ttu-id="3dadc-174">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-174">**Possible values**</span></span> | <span data-ttu-id="3dadc-175">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="3dadc-175">merge (default)</span></span> <br/> <span data-ttu-id="3dadc-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="3dadc-176">admin_only</span></span> |
| <span data-ttu-id="3dadc-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-177">**Comments**</span></span> | <span data-ttu-id="3dadc-178">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="3dadc-179">掃描排除</span><span class="sxs-lookup"><span data-stu-id="3dadc-179">Scan exclusions</span></span>

<span data-ttu-id="3dadc-180">指定排除在掃描之外的實體。</span><span class="sxs-lookup"><span data-stu-id="3dadc-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="3dadc-181">您可以使用完整路徑、副檔名或檔案名來指定排除。</span><span class="sxs-lookup"><span data-stu-id="3dadc-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="3dadc-182"> (排除專案是以專案陣列的形式指定，管理員可以根據需要依任何順序指定任意數目的元素。 ) </span><span class="sxs-lookup"><span data-stu-id="3dadc-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="3dadc-183">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-183">Section</span></span>|<span data-ttu-id="3dadc-184">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-185">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-186">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-186">**Key**</span></span> | <span data-ttu-id="3dadc-187">排除</span><span class="sxs-lookup"><span data-stu-id="3dadc-187">exclusions</span></span> |
| <span data-ttu-id="3dadc-188">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-188">**Data type**</span></span> | <span data-ttu-id="3dadc-189">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="3dadc-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3dadc-190">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-190">**Comments**</span></span> | <span data-ttu-id="3dadc-191">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="3dadc-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="3dadc-192">排除的類型</span><span class="sxs-lookup"><span data-stu-id="3dadc-192">Type of exclusion</span></span>

<span data-ttu-id="3dadc-193">指定 [依類型掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="3dadc-194">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-194">Section</span></span>|<span data-ttu-id="3dadc-195">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-196">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-197">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-197">**Key**</span></span> | <span data-ttu-id="3dadc-198">$type</span><span class="sxs-lookup"><span data-stu-id="3dadc-198">$type</span></span> |
| <span data-ttu-id="3dadc-199">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-199">**Data type**</span></span> | <span data-ttu-id="3dadc-200">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-200">String</span></span> |
| <span data-ttu-id="3dadc-201">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-201">**Possible values**</span></span> | <span data-ttu-id="3dadc-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="3dadc-202">excludedPath</span></span> <br/> <span data-ttu-id="3dadc-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="3dadc-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="3dadc-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="3dadc-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="3dadc-205">排除內容的路徑</span><span class="sxs-lookup"><span data-stu-id="3dadc-205">Path to excluded content</span></span>

<span data-ttu-id="3dadc-206">指定以完整檔案路徑掃描排除的內容。</span><span class="sxs-lookup"><span data-stu-id="3dadc-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="3dadc-207">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-207">Section</span></span>|<span data-ttu-id="3dadc-208">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-209">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-210">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-210">**Key**</span></span> | <span data-ttu-id="3dadc-211">路徑</span><span class="sxs-lookup"><span data-stu-id="3dadc-211">path</span></span> |
| <span data-ttu-id="3dadc-212">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-212">**Data type**</span></span> | <span data-ttu-id="3dadc-213">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-213">String</span></span> |
| <span data-ttu-id="3dadc-214">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-214">**Possible values**</span></span> | <span data-ttu-id="3dadc-215">有效路徑</span><span class="sxs-lookup"><span data-stu-id="3dadc-215">valid paths</span></span> |
| <span data-ttu-id="3dadc-216">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-216">**Comments**</span></span> | <span data-ttu-id="3dadc-217">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="3dadc-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="3dadc-218">支援的排除類型</span><span class="sxs-lookup"><span data-stu-id="3dadc-218">Supported exclusion types</span></span>

<span data-ttu-id="3dadc-219">下表顯示 Mac 上的 Defender for Endpoint 所支援的排除類型。</span><span class="sxs-lookup"><span data-stu-id="3dadc-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="3dadc-220">排除</span><span class="sxs-lookup"><span data-stu-id="3dadc-220">Exclusion</span></span> | <span data-ttu-id="3dadc-221">定義</span><span class="sxs-lookup"><span data-stu-id="3dadc-221">Definition</span></span> | <span data-ttu-id="3dadc-222">範例</span><span class="sxs-lookup"><span data-stu-id="3dadc-222">Examples</span></span>
---|---|---
<span data-ttu-id="3dadc-223">副檔名</span><span class="sxs-lookup"><span data-stu-id="3dadc-223">File extension</span></span> | <span data-ttu-id="3dadc-224">在裝置上的任何位置具有分機的所有檔案</span><span class="sxs-lookup"><span data-stu-id="3dadc-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="3dadc-225">檔案</span><span class="sxs-lookup"><span data-stu-id="3dadc-225">File</span></span> | <span data-ttu-id="3dadc-226">完整路徑所識別的特定檔案</span><span class="sxs-lookup"><span data-stu-id="3dadc-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="3dadc-227">資料夾</span><span class="sxs-lookup"><span data-stu-id="3dadc-227">Folder</span></span> | <span data-ttu-id="3dadc-228">指定資料夾底下的所有檔案 (以遞迴方式) </span><span class="sxs-lookup"><span data-stu-id="3dadc-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="3dadc-229">程序</span><span class="sxs-lookup"><span data-stu-id="3dadc-229">Process</span></span> | <span data-ttu-id="3dadc-230">指定的程式 (會以完整路徑或檔案名指定，也可以是由它所開啟的所有檔案) </span><span class="sxs-lookup"><span data-stu-id="3dadc-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="3dadc-231">以上的路徑必須是硬連結，而不是符號連結，才可成功排除。</span><span class="sxs-lookup"><span data-stu-id="3dadc-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="3dadc-232">您可以執行，檢查路徑是否為符號連結 `file <path-name>` 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="3dadc-233">檔案、資料夾及處理常式排除支援下列萬用字元：</span><span class="sxs-lookup"><span data-stu-id="3dadc-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="3dadc-234">萬用字元</span><span class="sxs-lookup"><span data-stu-id="3dadc-234">Wildcard</span></span> | <span data-ttu-id="3dadc-235">描述</span><span class="sxs-lookup"><span data-stu-id="3dadc-235">Description</span></span> | <span data-ttu-id="3dadc-236">範例</span><span class="sxs-lookup"><span data-stu-id="3dadc-236">Example</span></span> | <span data-ttu-id="3dadc-237">比賽</span><span class="sxs-lookup"><span data-stu-id="3dadc-237">Matches</span></span> | <span data-ttu-id="3dadc-238">不符合</span><span class="sxs-lookup"><span data-stu-id="3dadc-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="3dadc-239">符合任何數目的任何字元，包含無 (請注意，當路徑內使用此萬用字元時，它只會取代一個資料夾) </span><span class="sxs-lookup"><span data-stu-id="3dadc-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="3dadc-240">?</span><span class="sxs-lookup"><span data-stu-id="3dadc-240">?</span></span> | <span data-ttu-id="3dadc-241">符合任何單一字元</span><span class="sxs-lookup"><span data-stu-id="3dadc-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="3dadc-242"> (檔/目錄的路徑類型) </span><span class="sxs-lookup"><span data-stu-id="3dadc-242">Path type (file / directory)</span></span>

<span data-ttu-id="3dadc-243">指出 *path* 屬性參照的是檔案或目錄。</span><span class="sxs-lookup"><span data-stu-id="3dadc-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="3dadc-244">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-244">Section</span></span>|<span data-ttu-id="3dadc-245">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-246">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-247">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-247">**Key**</span></span> | <span data-ttu-id="3dadc-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="3dadc-248">isDirectory</span></span> |
| <span data-ttu-id="3dadc-249">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-249">**Data type**</span></span> | <span data-ttu-id="3dadc-250">布林值</span><span class="sxs-lookup"><span data-stu-id="3dadc-250">Boolean</span></span> |
| <span data-ttu-id="3dadc-251">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-251">**Possible values**</span></span> | <span data-ttu-id="3dadc-252">false (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-252">false (default)</span></span> <br/> <span data-ttu-id="3dadc-253">真</span><span class="sxs-lookup"><span data-stu-id="3dadc-253">true</span></span> |
| <span data-ttu-id="3dadc-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-254">**Comments**</span></span> | <span data-ttu-id="3dadc-255">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="3dadc-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="3dadc-256">從掃描排除的副檔名</span><span class="sxs-lookup"><span data-stu-id="3dadc-256">File extension excluded from the scan</span></span>

<span data-ttu-id="3dadc-257">指定 [依副檔名掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="3dadc-258">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-258">Section</span></span>|<span data-ttu-id="3dadc-259">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-260">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-261">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-261">**Key**</span></span> | <span data-ttu-id="3dadc-262">擴展</span><span class="sxs-lookup"><span data-stu-id="3dadc-262">extension</span></span> |
| <span data-ttu-id="3dadc-263">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-263">**Data type**</span></span> | <span data-ttu-id="3dadc-264">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-264">String</span></span> |
| <span data-ttu-id="3dadc-265">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-265">**Possible values**</span></span> | <span data-ttu-id="3dadc-266">有效的副檔名</span><span class="sxs-lookup"><span data-stu-id="3dadc-266">valid file extensions</span></span> |
| <span data-ttu-id="3dadc-267">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-267">**Comments**</span></span> | <span data-ttu-id="3dadc-268">僅適用于 *excludedFileExtension* *$type*</span><span class="sxs-lookup"><span data-stu-id="3dadc-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="3dadc-269">從掃描排除的處理常式</span><span class="sxs-lookup"><span data-stu-id="3dadc-269">Process excluded from the scan</span></span>

<span data-ttu-id="3dadc-270">指定從掃描排除所有檔案活動的處理常式。</span><span class="sxs-lookup"><span data-stu-id="3dadc-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="3dadc-271">您可以透過名稱指定程式 (例如 `cat`) 或完整路徑 (例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="3dadc-272">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-272">Section</span></span>|<span data-ttu-id="3dadc-273">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-274">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-275">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-275">**Key**</span></span> | <span data-ttu-id="3dadc-276">name</span><span class="sxs-lookup"><span data-stu-id="3dadc-276">name</span></span> |
| <span data-ttu-id="3dadc-277">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-277">**Data type**</span></span> | <span data-ttu-id="3dadc-278">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-278">String</span></span> |
| <span data-ttu-id="3dadc-279">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-279">**Possible values**</span></span> | <span data-ttu-id="3dadc-280">任何字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-280">any string</span></span> |
| <span data-ttu-id="3dadc-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-281">**Comments**</span></span> | <span data-ttu-id="3dadc-282">僅適用于 *excludedFileName* *$type*</span><span class="sxs-lookup"><span data-stu-id="3dadc-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="3dadc-283">允許的威脅</span><span class="sxs-lookup"><span data-stu-id="3dadc-283">Allowed threats</span></span>

<span data-ttu-id="3dadc-284">以 Mac 上的 Endpoint for Endpoint 未封鎖的名稱來指定威脅。</span><span class="sxs-lookup"><span data-stu-id="3dadc-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="3dadc-285">這些威脅都會允許執行。</span><span class="sxs-lookup"><span data-stu-id="3dadc-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="3dadc-286">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-286">Section</span></span>|<span data-ttu-id="3dadc-287">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-288">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-289">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-289">**Key**</span></span> | <span data-ttu-id="3dadc-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="3dadc-290">allowedThreats</span></span> |
| <span data-ttu-id="3dadc-291">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-291">**Data type**</span></span> | <span data-ttu-id="3dadc-292">字串陣列</span><span class="sxs-lookup"><span data-stu-id="3dadc-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="3dadc-293">不允許的威脅動作</span><span class="sxs-lookup"><span data-stu-id="3dadc-293">Disallowed threat actions</span></span>

<span data-ttu-id="3dadc-294">限制偵測到威脅時，裝置的本機使用者可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3dadc-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="3dadc-295">在此清單中包含的動作不會顯示在使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="3dadc-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="3dadc-296">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-296">Section</span></span>|<span data-ttu-id="3dadc-297">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-298">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-299">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-299">**Key**</span></span> | <span data-ttu-id="3dadc-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="3dadc-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="3dadc-301">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-301">**Data type**</span></span> | <span data-ttu-id="3dadc-302">字串陣列</span><span class="sxs-lookup"><span data-stu-id="3dadc-302">Array of strings</span></span> |
| <span data-ttu-id="3dadc-303">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-303">**Possible values**</span></span> | <span data-ttu-id="3dadc-304">允許 (限制使用者允許威脅) </span><span class="sxs-lookup"><span data-stu-id="3dadc-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="3dadc-305">restore (會限制使用者從隔離區還原威脅) </span><span class="sxs-lookup"><span data-stu-id="3dadc-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="3dadc-306">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-306">**Comments**</span></span> | <span data-ttu-id="3dadc-307">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="3dadc-308">威脅類型設定</span><span class="sxs-lookup"><span data-stu-id="3dadc-308">Threat type settings</span></span>

<span data-ttu-id="3dadc-309">指定 macOS 上的 Microsoft Defender for Endpoint 處理特定威脅類型的方式。</span><span class="sxs-lookup"><span data-stu-id="3dadc-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3dadc-310">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-310">Section</span></span>|<span data-ttu-id="3dadc-311">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-312">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-313">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-313">**Key**</span></span> | <span data-ttu-id="3dadc-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="3dadc-314">threatTypeSettings</span></span> |
| <span data-ttu-id="3dadc-315">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-315">**Data type**</span></span> | <span data-ttu-id="3dadc-316">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="3dadc-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3dadc-317">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-317">**Comments**</span></span> | <span data-ttu-id="3dadc-318">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="3dadc-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="3dadc-319">威脅類型</span><span class="sxs-lookup"><span data-stu-id="3dadc-319">Threat type</span></span>

<span data-ttu-id="3dadc-320">指定威脅類型。</span><span class="sxs-lookup"><span data-stu-id="3dadc-320">Specify threat types.</span></span>

|<span data-ttu-id="3dadc-321">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-321">Section</span></span>|<span data-ttu-id="3dadc-322">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-323">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-324">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-324">**Key**</span></span> | <span data-ttu-id="3dadc-325">機碼</span><span class="sxs-lookup"><span data-stu-id="3dadc-325">key</span></span> |
| <span data-ttu-id="3dadc-326">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-326">**Data type**</span></span> | <span data-ttu-id="3dadc-327">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-327">String</span></span> |
| <span data-ttu-id="3dadc-328">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-328">**Possible values**</span></span> | <span data-ttu-id="3dadc-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="3dadc-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="3dadc-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="3dadc-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="3dadc-331">要採取的動作</span><span class="sxs-lookup"><span data-stu-id="3dadc-331">Action to take</span></span>

<span data-ttu-id="3dadc-332">指定當偵測到上述區段中所指定類型的威脅時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3dadc-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="3dadc-333">請從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="3dadc-333">Choose from the following options:</span></span>

- <span data-ttu-id="3dadc-334">**Audit**：您的裝置不會受到這種威脅類型的保護，但是會記錄有關威脅的專案。</span><span class="sxs-lookup"><span data-stu-id="3dadc-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="3dadc-335">**封鎖**：您的裝置會受到此威脅類型的保護，而且您會收到使用者介面及安全性主控台的通知。</span><span class="sxs-lookup"><span data-stu-id="3dadc-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="3dadc-336">**Off**：您的裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="3dadc-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="3dadc-337">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-337">Section</span></span>|<span data-ttu-id="3dadc-338">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-339">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-340">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-340">**Key**</span></span> | <span data-ttu-id="3dadc-341">數值</span><span class="sxs-lookup"><span data-stu-id="3dadc-341">value</span></span> |
| <span data-ttu-id="3dadc-342">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-342">**Data type**</span></span> | <span data-ttu-id="3dadc-343">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-343">String</span></span> |
| <span data-ttu-id="3dadc-344">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-344">**Possible values**</span></span> | <span data-ttu-id="3dadc-345">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-345">audit (default)</span></span> <br/> <span data-ttu-id="3dadc-346">塊</span><span class="sxs-lookup"><span data-stu-id="3dadc-346">block</span></span> <br/> <span data-ttu-id="3dadc-347">遠離</span><span class="sxs-lookup"><span data-stu-id="3dadc-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="3dadc-348">威脅類型設定合併原則</span><span class="sxs-lookup"><span data-stu-id="3dadc-348">Threat type settings merge policy</span></span>

<span data-ttu-id="3dadc-349">指定威脅類型設定的合併原則。</span><span class="sxs-lookup"><span data-stu-id="3dadc-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="3dadc-350">這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="3dadc-351">此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。</span><span class="sxs-lookup"><span data-stu-id="3dadc-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="3dadc-352">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-352">Section</span></span>|<span data-ttu-id="3dadc-353">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-354">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-355">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-355">**Key**</span></span> | <span data-ttu-id="3dadc-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3dadc-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="3dadc-357">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-357">**Data type**</span></span> | <span data-ttu-id="3dadc-358">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-358">String</span></span> |
| <span data-ttu-id="3dadc-359">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-359">**Possible values**</span></span> | <span data-ttu-id="3dadc-360">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="3dadc-360">merge (default)</span></span> <br/> <span data-ttu-id="3dadc-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="3dadc-361">admin_only</span></span> |
| <span data-ttu-id="3dadc-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-362">**Comments**</span></span> | <span data-ttu-id="3dadc-363">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="3dadc-364">防病毒掃描記錄保留 (天數) </span><span class="sxs-lookup"><span data-stu-id="3dadc-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="3dadc-365">指定在裝置上的掃描歷程記錄中保留結果的天數。</span><span class="sxs-lookup"><span data-stu-id="3dadc-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="3dadc-366">舊的掃描結果會從歷史記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="3dadc-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="3dadc-367">也會從磁片中移除的舊隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="3dadc-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="3dadc-368">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-368">Section</span></span>|<span data-ttu-id="3dadc-369">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-370">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-371">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-371">**Key**</span></span> | <span data-ttu-id="3dadc-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="3dadc-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="3dadc-373">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-373">**Data type**</span></span> | <span data-ttu-id="3dadc-374">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-374">String</span></span> |
| <span data-ttu-id="3dadc-375">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-375">**Possible values**</span></span> | <span data-ttu-id="3dadc-376">90 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-376">90 (default).</span></span> <span data-ttu-id="3dadc-377">允許的值介於1天到180天。</span><span class="sxs-lookup"><span data-stu-id="3dadc-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="3dadc-378">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-378">**Comments**</span></span> | <span data-ttu-id="3dadc-379">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="3dadc-380">防病毒掃描歷程記錄中的專案數上限</span><span class="sxs-lookup"><span data-stu-id="3dadc-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="3dadc-381">指定要保留在掃描記錄中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="3dadc-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="3dadc-382">專案包括過去執行的所有按需掃描及所有防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="3dadc-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="3dadc-383">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-383">Section</span></span>|<span data-ttu-id="3dadc-384">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-385">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-386">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-386">**Key**</span></span> | <span data-ttu-id="3dadc-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="3dadc-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="3dadc-388">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-388">**Data type**</span></span> | <span data-ttu-id="3dadc-389">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-389">String</span></span> |
| <span data-ttu-id="3dadc-390">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-390">**Possible values**</span></span> | <span data-ttu-id="3dadc-391">10000 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-391">10000 (default).</span></span> <span data-ttu-id="3dadc-392">允許的值是從5000專案到15000專案。</span><span class="sxs-lookup"><span data-stu-id="3dadc-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="3dadc-393">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-393">**Comments**</span></span> | <span data-ttu-id="3dadc-394">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="3dadc-395">雲端提供的保護偏好設定</span><span class="sxs-lookup"><span data-stu-id="3dadc-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="3dadc-396">設定 macOS 上的 Microsoft Defender for Endpoint 的雲端驅動保護功能。</span><span class="sxs-lookup"><span data-stu-id="3dadc-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3dadc-397">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-397">Section</span></span>|<span data-ttu-id="3dadc-398">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-399">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-400">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-400">**Key**</span></span> | <span data-ttu-id="3dadc-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="3dadc-401">cloudService</span></span> |
| <span data-ttu-id="3dadc-402">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-402">**Data type**</span></span> | <span data-ttu-id="3dadc-403">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="3dadc-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3dadc-404">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-404">**Comments**</span></span> | <span data-ttu-id="3dadc-405">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="3dadc-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="3dadc-406">啟用/停用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="3dadc-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="3dadc-407">指定是否要對裝置啟用雲端提供保護。</span><span class="sxs-lookup"><span data-stu-id="3dadc-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="3dadc-408">若要改善服務的安全性，建議您保持此功能開啟。</span><span class="sxs-lookup"><span data-stu-id="3dadc-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="3dadc-409">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-409">Section</span></span>|<span data-ttu-id="3dadc-410">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-411">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-412">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-412">**Key**</span></span> | <span data-ttu-id="3dadc-413">啟用</span><span class="sxs-lookup"><span data-stu-id="3dadc-413">enabled</span></span> |
| <span data-ttu-id="3dadc-414">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-414">**Data type**</span></span> | <span data-ttu-id="3dadc-415">布林值</span><span class="sxs-lookup"><span data-stu-id="3dadc-415">Boolean</span></span> |
| <span data-ttu-id="3dadc-416">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-416">**Possible values**</span></span> | <span data-ttu-id="3dadc-417">true (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-417">true (default)</span></span> <br/> <span data-ttu-id="3dadc-418">假</span><span class="sxs-lookup"><span data-stu-id="3dadc-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="3dadc-419">診斷集合層級</span><span class="sxs-lookup"><span data-stu-id="3dadc-419">Diagnostic collection level</span></span>

<span data-ttu-id="3dadc-420">診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="3dadc-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="3dadc-421">此設定會決定 Microsoft Defender for Microsoft Defender 所傳送的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="3dadc-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="3dadc-422">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-422">Section</span></span>|<span data-ttu-id="3dadc-423">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-424">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-425">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-425">**Key**</span></span> | <span data-ttu-id="3dadc-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="3dadc-426">diagnosticLevel</span></span> |
| <span data-ttu-id="3dadc-427">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-427">**Data type**</span></span> | <span data-ttu-id="3dadc-428">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-428">String</span></span> |
| <span data-ttu-id="3dadc-429">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-429">**Possible values**</span></span> | <span data-ttu-id="3dadc-430">選用 (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-430">optional (default)</span></span> <br/> <span data-ttu-id="3dadc-431">必要</span><span class="sxs-lookup"><span data-stu-id="3dadc-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="3dadc-432">啟用/停用自動範例報送</span><span class="sxs-lookup"><span data-stu-id="3dadc-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="3dadc-433">會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。</span><span class="sxs-lookup"><span data-stu-id="3dadc-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="3dadc-434">如果提交的檔案可能包含個人資訊，系統會提示您。</span><span class="sxs-lookup"><span data-stu-id="3dadc-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="3dadc-435">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-435">Section</span></span>|<span data-ttu-id="3dadc-436">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-437">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-438">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-438">**Key**</span></span> | <span data-ttu-id="3dadc-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="3dadc-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="3dadc-440">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-440">**Data type**</span></span> | <span data-ttu-id="3dadc-441">布林值</span><span class="sxs-lookup"><span data-stu-id="3dadc-441">Boolean</span></span> |
| <span data-ttu-id="3dadc-442">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-442">**Possible values**</span></span> | <span data-ttu-id="3dadc-443">true (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-443">true (default)</span></span> <br/> <span data-ttu-id="3dadc-444">假</span><span class="sxs-lookup"><span data-stu-id="3dadc-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="3dadc-445">啟用/停用自動安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="3dadc-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="3dadc-446">決定是否自動安裝安全性智慧更新：</span><span class="sxs-lookup"><span data-stu-id="3dadc-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="3dadc-447">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-447">Section</span></span>|<span data-ttu-id="3dadc-448">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-449">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-449">**Key**</span></span> | <span data-ttu-id="3dadc-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="3dadc-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="3dadc-451">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-451">**Data type**</span></span> | <span data-ttu-id="3dadc-452">布林值</span><span class="sxs-lookup"><span data-stu-id="3dadc-452">Boolean</span></span> |
| <span data-ttu-id="3dadc-453">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-453">**Possible values**</span></span> | <span data-ttu-id="3dadc-454">true (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-454">true (default)</span></span> <br/> <span data-ttu-id="3dadc-455">假</span><span class="sxs-lookup"><span data-stu-id="3dadc-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="3dadc-456">使用者介面偏好設定</span><span class="sxs-lookup"><span data-stu-id="3dadc-456">User interface preferences</span></span>

<span data-ttu-id="3dadc-457">管理 macOS 上之 Microsoft Defender for Endpoint 之使用者介面的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="3dadc-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3dadc-458">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-458">Section</span></span>|<span data-ttu-id="3dadc-459">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-460">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-461">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-461">**Key**</span></span> | <span data-ttu-id="3dadc-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="3dadc-462">userInterface</span></span> |
| <span data-ttu-id="3dadc-463">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-463">**Data type**</span></span> | <span data-ttu-id="3dadc-464">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="3dadc-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3dadc-465">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-465">**Comments**</span></span> | <span data-ttu-id="3dadc-466">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="3dadc-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="3dadc-467">顯示/隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="3dadc-467">Show / hide status menu icon</span></span>

<span data-ttu-id="3dadc-468">指定是否要顯示或隱藏螢幕右上角的 [狀態] 功能表圖示。</span><span class="sxs-lookup"><span data-stu-id="3dadc-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="3dadc-469">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-469">Section</span></span>|<span data-ttu-id="3dadc-470">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-471">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-472">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-472">**Key**</span></span> | <span data-ttu-id="3dadc-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="3dadc-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="3dadc-474">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-474">**Data type**</span></span> | <span data-ttu-id="3dadc-475">布林值</span><span class="sxs-lookup"><span data-stu-id="3dadc-475">Boolean</span></span> |
| <span data-ttu-id="3dadc-476">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-476">**Possible values**</span></span> | <span data-ttu-id="3dadc-477">false (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-477">false (default)</span></span> <br/> <span data-ttu-id="3dadc-478">真</span><span class="sxs-lookup"><span data-stu-id="3dadc-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="3dadc-479">[顯示/隱藏] 選項以傳送意見反應</span><span class="sxs-lookup"><span data-stu-id="3dadc-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="3dadc-480">指定使用者是否可以前往提交對 Microsoft 的意見反應 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="3dadc-481">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-481">Section</span></span>|<span data-ttu-id="3dadc-482">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-483">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-484">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-484">**Key**</span></span> | <span data-ttu-id="3dadc-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="3dadc-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="3dadc-486">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-486">**Data type**</span></span> | <span data-ttu-id="3dadc-487">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-487">String</span></span> |
| <span data-ttu-id="3dadc-488">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-488">**Possible values**</span></span> | <span data-ttu-id="3dadc-489">已啟用 (預設) </span><span class="sxs-lookup"><span data-stu-id="3dadc-489">enabled (default)</span></span> <br/> <span data-ttu-id="3dadc-490">禁用</span><span class="sxs-lookup"><span data-stu-id="3dadc-490">disabled</span></span> |
| <span data-ttu-id="3dadc-491">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-491">**Comments**</span></span> | <span data-ttu-id="3dadc-492">可在 Microsoft Defender for Endpoint 版本101.19.61 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="3dadc-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="3dadc-493">端點偵測和回應喜好設定</span><span class="sxs-lookup"><span data-stu-id="3dadc-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="3dadc-494">在 macOS 上管理之 Microsoft Defender for endpoint 的端點偵測和回應 (EDR) 元件。</span><span class="sxs-lookup"><span data-stu-id="3dadc-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3dadc-495">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-495">Section</span></span>|<span data-ttu-id="3dadc-496">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-497">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-498">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-498">**Key**</span></span> | <span data-ttu-id="3dadc-499">edr</span><span class="sxs-lookup"><span data-stu-id="3dadc-499">edr</span></span> |
| <span data-ttu-id="3dadc-500">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-500">**Data type**</span></span> | <span data-ttu-id="3dadc-501">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="3dadc-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3dadc-502">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-502">**Comments**</span></span> | <span data-ttu-id="3dadc-503">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="3dadc-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="3dadc-504">裝置標記</span><span class="sxs-lookup"><span data-stu-id="3dadc-504">Device tags</span></span>

<span data-ttu-id="3dadc-505">指定標記名稱及其值。</span><span class="sxs-lookup"><span data-stu-id="3dadc-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="3dadc-506">GROUP 標記，以指定的值標記裝置。</span><span class="sxs-lookup"><span data-stu-id="3dadc-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="3dadc-507">標記會反映在入口網站的 [裝置] 頁面底下，可用於篩選和群組裝置。</span><span class="sxs-lookup"><span data-stu-id="3dadc-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="3dadc-508">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-508">Section</span></span>|<span data-ttu-id="3dadc-509">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-510">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-511">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-511">**Key**</span></span> | <span data-ttu-id="3dadc-512">標籤</span><span class="sxs-lookup"><span data-stu-id="3dadc-512">tags</span></span> |
| <span data-ttu-id="3dadc-513">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-513">**Data type**</span></span> | <span data-ttu-id="3dadc-514">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="3dadc-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3dadc-515">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3dadc-515">**Comments**</span></span> | <span data-ttu-id="3dadc-516">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="3dadc-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="3dadc-517">標記類型</span><span class="sxs-lookup"><span data-stu-id="3dadc-517">Type of tag</span></span>

<span data-ttu-id="3dadc-518">會指定標記的類型</span><span class="sxs-lookup"><span data-stu-id="3dadc-518">Specifies the type of tag</span></span>

|<span data-ttu-id="3dadc-519">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-519">Section</span></span>|<span data-ttu-id="3dadc-520">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-521">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-522">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-522">**Key**</span></span> | <span data-ttu-id="3dadc-523">機碼</span><span class="sxs-lookup"><span data-stu-id="3dadc-523">key</span></span> |
| <span data-ttu-id="3dadc-524">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-524">**Data type**</span></span> | <span data-ttu-id="3dadc-525">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-525">String</span></span> |
| <span data-ttu-id="3dadc-526">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="3dadc-527">標記值</span><span class="sxs-lookup"><span data-stu-id="3dadc-527">Value of tag</span></span>

<span data-ttu-id="3dadc-528">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="3dadc-528">Specifies the value of tag</span></span>

|<span data-ttu-id="3dadc-529">區段</span><span class="sxs-lookup"><span data-stu-id="3dadc-529">Section</span></span>|<span data-ttu-id="3dadc-530">值</span><span class="sxs-lookup"><span data-stu-id="3dadc-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3dadc-531">**網域**</span><span class="sxs-lookup"><span data-stu-id="3dadc-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3dadc-532">**索引鍵**</span><span class="sxs-lookup"><span data-stu-id="3dadc-532">**Key**</span></span> | <span data-ttu-id="3dadc-533">數值</span><span class="sxs-lookup"><span data-stu-id="3dadc-533">value</span></span> |
| <span data-ttu-id="3dadc-534">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3dadc-534">**Data type**</span></span> | <span data-ttu-id="3dadc-535">字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-535">String</span></span> |
| <span data-ttu-id="3dadc-536">**可能值**</span><span class="sxs-lookup"><span data-stu-id="3dadc-536">**Possible values**</span></span> | <span data-ttu-id="3dadc-537">任何字串</span><span class="sxs-lookup"><span data-stu-id="3dadc-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="3dadc-538">每個 tag 類型只能設定一個值。</span><span class="sxs-lookup"><span data-stu-id="3dadc-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="3dadc-539">標記的類型是唯一的，不應該在相同的設定檔中重複。</span><span class="sxs-lookup"><span data-stu-id="3dadc-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="3dadc-540">建議的設定設定檔</span><span class="sxs-lookup"><span data-stu-id="3dadc-540">Recommended configuration profile</span></span>

<span data-ttu-id="3dadc-541">若要開始使用，我們建議您的企業進行下列設定，以利用 Microsoft Defender for Endpoint 所提供的所有保護功能。</span><span class="sxs-lookup"><span data-stu-id="3dadc-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="3dadc-542">下列設定設定檔 (，如果 JAMF，可以上傳至自訂設定設定檔的屬性清單) 會：</span><span class="sxs-lookup"><span data-stu-id="3dadc-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="3dadc-543">啟用 (RTP) 的即時保護</span><span class="sxs-lookup"><span data-stu-id="3dadc-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="3dadc-544">指定如何處理下列威脅類型：</span><span class="sxs-lookup"><span data-stu-id="3dadc-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="3dadc-545">封鎖 **(PUA) 可能有害的應用程式**</span><span class="sxs-lookup"><span data-stu-id="3dadc-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="3dadc-546">將具有高壓縮率) 的封存 **bombs (檔案** 審核至 Microsoft Defender for Endpoint 記錄檔</span><span class="sxs-lookup"><span data-stu-id="3dadc-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="3dadc-547">啟用自動安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="3dadc-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="3dadc-548">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="3dadc-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="3dadc-549">啟用自動範例提交</span><span class="sxs-lookup"><span data-stu-id="3dadc-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="3dadc-550">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="3dadc-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="3dadc-551">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="3dadc-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="3dadc-552">完整設定檔範例</span><span class="sxs-lookup"><span data-stu-id="3dadc-552">Full configuration profile example</span></span>

<span data-ttu-id="3dadc-553">下列範本包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要在 macOS 上進一步控制端點的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="3dadc-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="3dadc-554">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="3dadc-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="3dadc-555">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="3dadc-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="3dadc-556">屬性清單驗證</span><span class="sxs-lookup"><span data-stu-id="3dadc-556">Property list validation</span></span>

<span data-ttu-id="3dadc-557">屬性清單必須是有效的 *plist* 檔案。</span><span class="sxs-lookup"><span data-stu-id="3dadc-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="3dadc-558">您可以執行下列動作來檢查：</span><span class="sxs-lookup"><span data-stu-id="3dadc-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="3dadc-559">如果檔案的格式良好，上述命令會輸出並傳回 `OK` 的退出程式碼 `0` 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="3dadc-560">否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="3dadc-561">設定設定檔部署</span><span class="sxs-lookup"><span data-stu-id="3dadc-561">Configuration profile deployment</span></span>

<span data-ttu-id="3dadc-562">在您為企業建立設定檔之後，您可以透過企業使用的管理主控台來部署它。</span><span class="sxs-lookup"><span data-stu-id="3dadc-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="3dadc-563">下列各節提供如何使用 JAMF 和 Intune 部署此設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="3dadc-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="3dadc-564">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="3dadc-564">JAMF deployment</span></span>

<span data-ttu-id="3dadc-565">從 JAMF 主控台，開啟 [**電腦** 設定配置  >  **檔**]，流覽至您想要使用的設定設定檔，然後選取 [**自訂設定**]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="3dadc-566">建立具有 `com.microsoft.wdav` 偏好的網域的專案，並上傳先前產生的 *plist* 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="3dadc-567">您必須輸入正確的喜好網域 (`com.microsoft.wdav`) ; 否則，Microsoft Defender For Endpoint 將不會識別首選項。</span><span class="sxs-lookup"><span data-stu-id="3dadc-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="3dadc-568">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="3dadc-568">Intune deployment</span></span>

1. <span data-ttu-id="3dadc-569">開啟 [**管理**  >  **裝置** 設定]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="3dadc-570">選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="3dadc-571">選擇設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="3dadc-571">Choose a name for the profile.</span></span> <span data-ttu-id="3dadc-572">將 **平臺 = macOS** 變更為 **Profile type = Custom**。</span><span class="sxs-lookup"><span data-stu-id="3dadc-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="3dadc-573">選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-573">Select Configure.</span></span>

3. <span data-ttu-id="3dadc-574">儲存先前產生的 plist `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="3dadc-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="3dadc-575">輸入 `com.microsoft.wdav` 為 **自訂設定設定檔名稱**。</span><span class="sxs-lookup"><span data-stu-id="3dadc-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="3dadc-576">開啟設定設定檔，並上傳 `com.microsoft.wdav.xml` 檔。</span><span class="sxs-lookup"><span data-stu-id="3dadc-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="3dadc-577"> (此檔案是在步驟3中建立。 ) </span><span class="sxs-lookup"><span data-stu-id="3dadc-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="3dadc-578">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3dadc-578">Select **OK**.</span></span>

7. <span data-ttu-id="3dadc-579">選取 [**管理**  >  **指派**]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="3dadc-580">在 [ **包含** ] 索引標籤中，選取 [ **指派給所有使用者 & 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="3dadc-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="3dadc-581">您必須輸入正確的自訂設定檔名稱;否則，Microsoft Defender for Endpoint 將不會識別這些喜好設定。</span><span class="sxs-lookup"><span data-stu-id="3dadc-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="3dadc-582">資源</span><span class="sxs-lookup"><span data-stu-id="3dadc-582">Resources</span></span>

- [<span data-ttu-id="3dadc-583">組態設定檔參照 (Apple 開發人員文件)</span><span class="sxs-lookup"><span data-stu-id="3dadc-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
