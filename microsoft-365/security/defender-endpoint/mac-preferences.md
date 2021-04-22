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
ms.openlocfilehash: f13734392e4975738a0d60d38e618595b5175667
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934558"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1da1d-104">在 macOS 上設定 Microsoft Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="1da1d-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1da1d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1da1d-105">**Applies to:**</span></span>

- [<span data-ttu-id="1da1d-106">macOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1da1d-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="1da1d-107">本文包含如何針對企業組織中 macOS 之 Microsoft Defender for Endpoint 設定偏好設定的指示。</span><span class="sxs-lookup"><span data-stu-id="1da1d-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="1da1d-108">若要在使用命令列介面的 macOS 上設定 Microsoft Defender for Endpoint，請參閱 [Resources](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="1da1d-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="1da1d-109">摘要</span><span class="sxs-lookup"><span data-stu-id="1da1d-109">Summary</span></span>

<span data-ttu-id="1da1d-110">在企業組織中，可透過使用其中一種管理工具部署的設定檔來管理 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="1da1d-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="1da1d-111">安全作業小組所管理的喜好設定優先順序高於裝置上本機設定的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="1da1d-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="1da1d-112">變更透過設定設定檔設定的喜好設定時，需要提升許可權，且不需要系統管理許可權的使用者才能使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="1da1d-113">本文說明設定檔的結構，包含您可以用來開始使用的建議設定檔，並提供如何部署設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="1da1d-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="1da1d-114">設定設定檔結構</span><span class="sxs-lookup"><span data-stu-id="1da1d-114">Configuration profile structure</span></span>

<span data-ttu-id="1da1d-115">設定設定檔是由按鍵 (所識別之專案所識別的 *plist* 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。</span><span class="sxs-lookup"><span data-stu-id="1da1d-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="1da1d-116">值既可以是簡單的 (例如數值) 或複雜，例如首選項的嵌套清單。</span><span class="sxs-lookup"><span data-stu-id="1da1d-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="1da1d-117">設定設定檔的版面配置取決於您所使用的管理主控台。</span><span class="sxs-lookup"><span data-stu-id="1da1d-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="1da1d-118">下列各節包含 JAMF 及 Intune 之設定檔的範例。</span><span class="sxs-lookup"><span data-stu-id="1da1d-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="1da1d-119">設定設定檔的最上層包括 Microsoft Defender for Endpoint 之子領域的產品範圍偏好設定和專案，在下一節將詳細說明。</span><span class="sxs-lookup"><span data-stu-id="1da1d-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="1da1d-120">防病毒引擎偏好設定</span><span class="sxs-lookup"><span data-stu-id="1da1d-120">Antivirus engine preferences</span></span>

<span data-ttu-id="1da1d-121">設定設定檔的 [ *antivirusEngine* ] 區段是用來管理 Microsoft Defender for Endpoint 之防病毒元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="1da1d-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="1da1d-122">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-122">Section</span></span>|<span data-ttu-id="1da1d-123">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-124">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-125">**Key**</span></span> | <span data-ttu-id="1da1d-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="1da1d-126">antivirusEngine</span></span> |
| <span data-ttu-id="1da1d-127">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-127">**Data type**</span></span> | <span data-ttu-id="1da1d-128">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="1da1d-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1da1d-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-129">**Comments**</span></span> | <span data-ttu-id="1da1d-130">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="1da1d-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="1da1d-131">啟用/停用即時保護</span><span class="sxs-lookup"><span data-stu-id="1da1d-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="1da1d-132">指定是否要啟用即時保護，以在存取檔時進行掃描。</span><span class="sxs-lookup"><span data-stu-id="1da1d-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="1da1d-133">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-133">Section</span></span>|<span data-ttu-id="1da1d-134">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-135">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-136">**Key**</span></span> | <span data-ttu-id="1da1d-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="1da1d-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="1da1d-138">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-138">**Data type**</span></span> | <span data-ttu-id="1da1d-139">布林值</span><span class="sxs-lookup"><span data-stu-id="1da1d-139">Boolean</span></span> |
| <span data-ttu-id="1da1d-140">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-140">**Possible values**</span></span> | <span data-ttu-id="1da1d-141">true (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-141">true (default)</span></span> <br/> <span data-ttu-id="1da1d-142">假</span><span class="sxs-lookup"><span data-stu-id="1da1d-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="1da1d-143">啟用/停用被動模式</span><span class="sxs-lookup"><span data-stu-id="1da1d-143">Enable / disable passive mode</span></span>

<span data-ttu-id="1da1d-144">指定防病毒引擎是否以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="1da1d-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="1da1d-145">被動式模式的含義如下：</span><span class="sxs-lookup"><span data-stu-id="1da1d-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="1da1d-146">已關閉即時保護</span><span class="sxs-lookup"><span data-stu-id="1da1d-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="1da1d-147">已開啟隨選掃描</span><span class="sxs-lookup"><span data-stu-id="1da1d-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="1da1d-148">關閉自動威脅修復功能</span><span class="sxs-lookup"><span data-stu-id="1da1d-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="1da1d-149">已開啟安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="1da1d-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="1da1d-150">隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="1da1d-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="1da1d-151">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-151">Section</span></span>|<span data-ttu-id="1da1d-152">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-153">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-154">**Key**</span></span> | <span data-ttu-id="1da1d-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="1da1d-155">passiveMode</span></span> |
| <span data-ttu-id="1da1d-156">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-156">**Data type**</span></span> | <span data-ttu-id="1da1d-157">布林值</span><span class="sxs-lookup"><span data-stu-id="1da1d-157">Boolean</span></span> |
| <span data-ttu-id="1da1d-158">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-158">**Possible values**</span></span> | <span data-ttu-id="1da1d-159">false (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-159">false (default)</span></span> <br/> <span data-ttu-id="1da1d-160">真</span><span class="sxs-lookup"><span data-stu-id="1da1d-160">true</span></span> |
| <span data-ttu-id="1da1d-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-161">**Comments**</span></span> | <span data-ttu-id="1da1d-162">可在 Microsoft Defender for Endpoint 版本100.67.60 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="1da1d-163">排除合併原則</span><span class="sxs-lookup"><span data-stu-id="1da1d-163">Exclusion merge policy</span></span>

<span data-ttu-id="1da1d-164">指定排除的合併原則。</span><span class="sxs-lookup"><span data-stu-id="1da1d-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="1da1d-165">這可以是管理員定義和使用者定義排除 (的組合， `merge`) 或僅限系統管理員定義的排除 (`admin_only`) 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="1da1d-166">您可以使用此設定來限制本機使用者定義自己的排除專案。</span><span class="sxs-lookup"><span data-stu-id="1da1d-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="1da1d-167">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-167">Section</span></span>|<span data-ttu-id="1da1d-168">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-169">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-170">**Key**</span></span> | <span data-ttu-id="1da1d-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1da1d-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="1da1d-172">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-172">**Data type**</span></span> | <span data-ttu-id="1da1d-173">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-173">String</span></span> |
| <span data-ttu-id="1da1d-174">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-174">**Possible values**</span></span> | <span data-ttu-id="1da1d-175">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="1da1d-175">merge (default)</span></span> <br/> <span data-ttu-id="1da1d-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="1da1d-176">admin_only</span></span> |
| <span data-ttu-id="1da1d-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-177">**Comments**</span></span> | <span data-ttu-id="1da1d-178">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="1da1d-179">掃描排除</span><span class="sxs-lookup"><span data-stu-id="1da1d-179">Scan exclusions</span></span>

<span data-ttu-id="1da1d-180">指定排除在掃描之外的實體。</span><span class="sxs-lookup"><span data-stu-id="1da1d-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="1da1d-181">您可以使用完整路徑、副檔名或檔案名來指定排除。</span><span class="sxs-lookup"><span data-stu-id="1da1d-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="1da1d-182">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-182">Section</span></span>|<span data-ttu-id="1da1d-183">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-184">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-185">**Key**</span></span> | <span data-ttu-id="1da1d-186">排除</span><span class="sxs-lookup"><span data-stu-id="1da1d-186">exclusions</span></span> |
| <span data-ttu-id="1da1d-187">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-187">**Data type**</span></span> | <span data-ttu-id="1da1d-188">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="1da1d-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1da1d-189">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-189">**Comments**</span></span> | <span data-ttu-id="1da1d-190">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="1da1d-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="1da1d-191">排除的類型</span><span class="sxs-lookup"><span data-stu-id="1da1d-191">Type of exclusion</span></span>

<span data-ttu-id="1da1d-192">指定 [依類型掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="1da1d-193">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-193">Section</span></span>|<span data-ttu-id="1da1d-194">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-195">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-196">**Key**</span></span> | <span data-ttu-id="1da1d-197">$type</span><span class="sxs-lookup"><span data-stu-id="1da1d-197">$type</span></span> |
| <span data-ttu-id="1da1d-198">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-198">**Data type**</span></span> | <span data-ttu-id="1da1d-199">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-199">String</span></span> |
| <span data-ttu-id="1da1d-200">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-200">**Possible values**</span></span> | <span data-ttu-id="1da1d-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="1da1d-201">excludedPath</span></span> <br/> <span data-ttu-id="1da1d-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="1da1d-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="1da1d-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="1da1d-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="1da1d-204">排除內容的路徑</span><span class="sxs-lookup"><span data-stu-id="1da1d-204">Path to excluded content</span></span>

<span data-ttu-id="1da1d-205">指定以完整檔案路徑掃描排除的內容。</span><span class="sxs-lookup"><span data-stu-id="1da1d-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="1da1d-206">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-206">Section</span></span>|<span data-ttu-id="1da1d-207">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-208">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-209">**Key**</span></span> | <span data-ttu-id="1da1d-210">路徑</span><span class="sxs-lookup"><span data-stu-id="1da1d-210">path</span></span> |
| <span data-ttu-id="1da1d-211">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-211">**Data type**</span></span> | <span data-ttu-id="1da1d-212">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-212">String</span></span> |
| <span data-ttu-id="1da1d-213">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-213">**Possible values**</span></span> | <span data-ttu-id="1da1d-214">有效路徑</span><span class="sxs-lookup"><span data-stu-id="1da1d-214">valid paths</span></span> |
| <span data-ttu-id="1da1d-215">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-215">**Comments**</span></span> | <span data-ttu-id="1da1d-216">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="1da1d-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="1da1d-217"> (檔/目錄的路徑類型) </span><span class="sxs-lookup"><span data-stu-id="1da1d-217">Path type (file / directory)</span></span>

<span data-ttu-id="1da1d-218">指出 *path* 屬性參照的是檔案或目錄。</span><span class="sxs-lookup"><span data-stu-id="1da1d-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="1da1d-219">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-219">Section</span></span>|<span data-ttu-id="1da1d-220">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-221">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-222">**Key**</span></span> | <span data-ttu-id="1da1d-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="1da1d-223">isDirectory</span></span> |
| <span data-ttu-id="1da1d-224">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-224">**Data type**</span></span> | <span data-ttu-id="1da1d-225">布林值</span><span class="sxs-lookup"><span data-stu-id="1da1d-225">Boolean</span></span> |
| <span data-ttu-id="1da1d-226">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-226">**Possible values**</span></span> | <span data-ttu-id="1da1d-227">false (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-227">false (default)</span></span> <br/> <span data-ttu-id="1da1d-228">真</span><span class="sxs-lookup"><span data-stu-id="1da1d-228">true</span></span> |
| <span data-ttu-id="1da1d-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-229">**Comments**</span></span> | <span data-ttu-id="1da1d-230">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="1da1d-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="1da1d-231">從掃描排除的副檔名</span><span class="sxs-lookup"><span data-stu-id="1da1d-231">File extension excluded from the scan</span></span>

<span data-ttu-id="1da1d-232">指定 [依副檔名掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="1da1d-233">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-233">Section</span></span>|<span data-ttu-id="1da1d-234">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-235">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-236">**Key**</span></span> | <span data-ttu-id="1da1d-237">擴展</span><span class="sxs-lookup"><span data-stu-id="1da1d-237">extension</span></span> |
| <span data-ttu-id="1da1d-238">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-238">**Data type**</span></span> | <span data-ttu-id="1da1d-239">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-239">String</span></span> |
| <span data-ttu-id="1da1d-240">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-240">**Possible values**</span></span> | <span data-ttu-id="1da1d-241">有效的副檔名</span><span class="sxs-lookup"><span data-stu-id="1da1d-241">valid file extensions</span></span> |
| <span data-ttu-id="1da1d-242">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-242">**Comments**</span></span> | <span data-ttu-id="1da1d-243">僅適用于 *excludedFileExtension* *$type*</span><span class="sxs-lookup"><span data-stu-id="1da1d-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="1da1d-244">從掃描排除的處理常式</span><span class="sxs-lookup"><span data-stu-id="1da1d-244">Process excluded from the scan</span></span>

<span data-ttu-id="1da1d-245">指定從掃描排除所有檔案活動的處理常式。</span><span class="sxs-lookup"><span data-stu-id="1da1d-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="1da1d-246">您可以透過名稱指定程式 (例如 `cat`) 或完整路徑 (例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="1da1d-247">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-247">Section</span></span>|<span data-ttu-id="1da1d-248">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-249">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-250">**Key**</span></span> | <span data-ttu-id="1da1d-251">name</span><span class="sxs-lookup"><span data-stu-id="1da1d-251">name</span></span> |
| <span data-ttu-id="1da1d-252">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-252">**Data type**</span></span> | <span data-ttu-id="1da1d-253">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-253">String</span></span> |
| <span data-ttu-id="1da1d-254">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-254">**Possible values**</span></span> | <span data-ttu-id="1da1d-255">任何字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-255">any string</span></span> |
| <span data-ttu-id="1da1d-256">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-256">**Comments**</span></span> | <span data-ttu-id="1da1d-257">僅適用于 *excludedFileName* *$type*</span><span class="sxs-lookup"><span data-stu-id="1da1d-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="1da1d-258">允許的威脅</span><span class="sxs-lookup"><span data-stu-id="1da1d-258">Allowed threats</span></span>

<span data-ttu-id="1da1d-259">以 Mac 上的 Endpoint for Endpoint 未封鎖的名稱來指定威脅。</span><span class="sxs-lookup"><span data-stu-id="1da1d-259">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="1da1d-260">這些威脅都會允許執行。</span><span class="sxs-lookup"><span data-stu-id="1da1d-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="1da1d-261">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-261">Section</span></span>|<span data-ttu-id="1da1d-262">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-263">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-264">**Key**</span></span> | <span data-ttu-id="1da1d-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="1da1d-265">allowedThreats</span></span> |
| <span data-ttu-id="1da1d-266">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-266">**Data type**</span></span> | <span data-ttu-id="1da1d-267">字串陣列</span><span class="sxs-lookup"><span data-stu-id="1da1d-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="1da1d-268">不允許的威脅動作</span><span class="sxs-lookup"><span data-stu-id="1da1d-268">Disallowed threat actions</span></span>

<span data-ttu-id="1da1d-269">限制偵測到威脅時，裝置的本機使用者可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="1da1d-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="1da1d-270">在此清單中包含的動作不會顯示在使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="1da1d-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="1da1d-271">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-271">Section</span></span>|<span data-ttu-id="1da1d-272">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-273">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-274">**Key**</span></span> | <span data-ttu-id="1da1d-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="1da1d-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="1da1d-276">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-276">**Data type**</span></span> | <span data-ttu-id="1da1d-277">字串陣列</span><span class="sxs-lookup"><span data-stu-id="1da1d-277">Array of strings</span></span> |
| <span data-ttu-id="1da1d-278">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-278">**Possible values**</span></span> | <span data-ttu-id="1da1d-279">允許 (限制使用者允許威脅) </span><span class="sxs-lookup"><span data-stu-id="1da1d-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="1da1d-280">restore (會限制使用者從隔離區還原威脅) </span><span class="sxs-lookup"><span data-stu-id="1da1d-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="1da1d-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-281">**Comments**</span></span> | <span data-ttu-id="1da1d-282">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="1da1d-283">威脅類型設定</span><span class="sxs-lookup"><span data-stu-id="1da1d-283">Threat type settings</span></span>

<span data-ttu-id="1da1d-284">指定 macOS 上的 Microsoft Defender for Endpoint 處理特定威脅類型的方式。</span><span class="sxs-lookup"><span data-stu-id="1da1d-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1da1d-285">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-285">Section</span></span>|<span data-ttu-id="1da1d-286">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-287">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-288">**Key**</span></span> | <span data-ttu-id="1da1d-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="1da1d-289">threatTypeSettings</span></span> |
| <span data-ttu-id="1da1d-290">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-290">**Data type**</span></span> | <span data-ttu-id="1da1d-291">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="1da1d-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1da1d-292">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-292">**Comments**</span></span> | <span data-ttu-id="1da1d-293">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="1da1d-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="1da1d-294">威脅類型</span><span class="sxs-lookup"><span data-stu-id="1da1d-294">Threat type</span></span>

<span data-ttu-id="1da1d-295">指定威脅類型。</span><span class="sxs-lookup"><span data-stu-id="1da1d-295">Specify threat types.</span></span>

|<span data-ttu-id="1da1d-296">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-296">Section</span></span>|<span data-ttu-id="1da1d-297">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-298">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-299">**Key**</span></span> | <span data-ttu-id="1da1d-300">機碼</span><span class="sxs-lookup"><span data-stu-id="1da1d-300">key</span></span> |
| <span data-ttu-id="1da1d-301">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-301">**Data type**</span></span> | <span data-ttu-id="1da1d-302">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-302">String</span></span> |
| <span data-ttu-id="1da1d-303">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-303">**Possible values**</span></span> | <span data-ttu-id="1da1d-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="1da1d-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="1da1d-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="1da1d-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="1da1d-306">要採取的動作</span><span class="sxs-lookup"><span data-stu-id="1da1d-306">Action to take</span></span>

<span data-ttu-id="1da1d-307">指定當偵測到上述區段中所指定類型的威脅時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="1da1d-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="1da1d-308">請從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="1da1d-308">Choose from the following options:</span></span>

- <span data-ttu-id="1da1d-309">**Audit**：您的裝置不會受到這種威脅類型的保護，但是會記錄有關威脅的專案。</span><span class="sxs-lookup"><span data-stu-id="1da1d-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="1da1d-310">**封鎖**：您的裝置會受到此威脅類型的保護，而且您會收到使用者介面及安全性主控台的通知。</span><span class="sxs-lookup"><span data-stu-id="1da1d-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="1da1d-311">**Off**：您的裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="1da1d-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="1da1d-312">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-312">Section</span></span>|<span data-ttu-id="1da1d-313">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-314">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-315">**Key**</span></span> | <span data-ttu-id="1da1d-316">數值</span><span class="sxs-lookup"><span data-stu-id="1da1d-316">value</span></span> |
| <span data-ttu-id="1da1d-317">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-317">**Data type**</span></span> | <span data-ttu-id="1da1d-318">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-318">String</span></span> |
| <span data-ttu-id="1da1d-319">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-319">**Possible values**</span></span> | <span data-ttu-id="1da1d-320">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-320">audit (default)</span></span> <br/> <span data-ttu-id="1da1d-321">塊</span><span class="sxs-lookup"><span data-stu-id="1da1d-321">block</span></span> <br/> <span data-ttu-id="1da1d-322">遠離</span><span class="sxs-lookup"><span data-stu-id="1da1d-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="1da1d-323">威脅類型設定合併原則</span><span class="sxs-lookup"><span data-stu-id="1da1d-323">Threat type settings merge policy</span></span>

<span data-ttu-id="1da1d-324">指定威脅類型設定的合併原則。</span><span class="sxs-lookup"><span data-stu-id="1da1d-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="1da1d-325">這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="1da1d-326">此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。</span><span class="sxs-lookup"><span data-stu-id="1da1d-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="1da1d-327">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-327">Section</span></span>|<span data-ttu-id="1da1d-328">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-329">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-330">**Key**</span></span> | <span data-ttu-id="1da1d-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1da1d-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="1da1d-332">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-332">**Data type**</span></span> | <span data-ttu-id="1da1d-333">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-333">String</span></span> |
| <span data-ttu-id="1da1d-334">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-334">**Possible values**</span></span> | <span data-ttu-id="1da1d-335">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="1da1d-335">merge (default)</span></span> <br/> <span data-ttu-id="1da1d-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="1da1d-336">admin_only</span></span> |
| <span data-ttu-id="1da1d-337">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-337">**Comments**</span></span> | <span data-ttu-id="1da1d-338">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="1da1d-339">防病毒掃描記錄保留 (天數) </span><span class="sxs-lookup"><span data-stu-id="1da1d-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="1da1d-340">指定在裝置上的掃描歷程記錄中保留結果的天數。</span><span class="sxs-lookup"><span data-stu-id="1da1d-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="1da1d-341">舊的掃描結果會從歷史記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="1da1d-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="1da1d-342">也會從磁片中移除的舊隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="1da1d-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="1da1d-343">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-343">Section</span></span>|<span data-ttu-id="1da1d-344">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-345">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-346">**Key**</span></span> | <span data-ttu-id="1da1d-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="1da1d-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="1da1d-348">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-348">**Data type**</span></span> | <span data-ttu-id="1da1d-349">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-349">String</span></span> |
| <span data-ttu-id="1da1d-350">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-350">**Possible values**</span></span> | <span data-ttu-id="1da1d-351">90 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-351">90 (default).</span></span> <span data-ttu-id="1da1d-352">允許的值介於1天到180天。</span><span class="sxs-lookup"><span data-stu-id="1da1d-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="1da1d-353">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-353">**Comments**</span></span> | <span data-ttu-id="1da1d-354">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="1da1d-355">防病毒掃描歷程記錄中的專案數上限</span><span class="sxs-lookup"><span data-stu-id="1da1d-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="1da1d-356">指定要保留在掃描記錄中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="1da1d-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="1da1d-357">專案包括過去執行的所有按需掃描及所有防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="1da1d-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="1da1d-358">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-358">Section</span></span>|<span data-ttu-id="1da1d-359">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-360">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-361">**Key**</span></span> | <span data-ttu-id="1da1d-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="1da1d-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="1da1d-363">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-363">**Data type**</span></span> | <span data-ttu-id="1da1d-364">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-364">String</span></span> |
| <span data-ttu-id="1da1d-365">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-365">**Possible values**</span></span> | <span data-ttu-id="1da1d-366">10000 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-366">10000 (default).</span></span> <span data-ttu-id="1da1d-367">允許的值是從5000專案到15000專案。</span><span class="sxs-lookup"><span data-stu-id="1da1d-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="1da1d-368">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-368">**Comments**</span></span> | <span data-ttu-id="1da1d-369">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="1da1d-370">雲端提供的保護偏好設定</span><span class="sxs-lookup"><span data-stu-id="1da1d-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="1da1d-371">設定 macOS 上的 Microsoft Defender for Endpoint 的雲端驅動保護功能。</span><span class="sxs-lookup"><span data-stu-id="1da1d-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1da1d-372">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-372">Section</span></span>|<span data-ttu-id="1da1d-373">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-374">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-375">**Key**</span></span> | <span data-ttu-id="1da1d-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="1da1d-376">cloudService</span></span> |
| <span data-ttu-id="1da1d-377">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-377">**Data type**</span></span> | <span data-ttu-id="1da1d-378">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="1da1d-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1da1d-379">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-379">**Comments**</span></span> | <span data-ttu-id="1da1d-380">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="1da1d-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="1da1d-381">啟用/停用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="1da1d-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="1da1d-382">指定是否要對裝置啟用雲端提供保護。</span><span class="sxs-lookup"><span data-stu-id="1da1d-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="1da1d-383">若要改善服務的安全性，建議您保持此功能開啟。</span><span class="sxs-lookup"><span data-stu-id="1da1d-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="1da1d-384">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-384">Section</span></span>|<span data-ttu-id="1da1d-385">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-386">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-387">**Key**</span></span> | <span data-ttu-id="1da1d-388">啟用</span><span class="sxs-lookup"><span data-stu-id="1da1d-388">enabled</span></span> |
| <span data-ttu-id="1da1d-389">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-389">**Data type**</span></span> | <span data-ttu-id="1da1d-390">布林值</span><span class="sxs-lookup"><span data-stu-id="1da1d-390">Boolean</span></span> |
| <span data-ttu-id="1da1d-391">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-391">**Possible values**</span></span> | <span data-ttu-id="1da1d-392">true (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-392">true (default)</span></span> <br/> <span data-ttu-id="1da1d-393">假</span><span class="sxs-lookup"><span data-stu-id="1da1d-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="1da1d-394">診斷集合層級</span><span class="sxs-lookup"><span data-stu-id="1da1d-394">Diagnostic collection level</span></span>

<span data-ttu-id="1da1d-395">診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="1da1d-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="1da1d-396">此設定會決定 Microsoft Defender for Microsoft Defender 所傳送的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="1da1d-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="1da1d-397">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-397">Section</span></span>|<span data-ttu-id="1da1d-398">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-399">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-400">**Key**</span></span> | <span data-ttu-id="1da1d-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="1da1d-401">diagnosticLevel</span></span> |
| <span data-ttu-id="1da1d-402">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-402">**Data type**</span></span> | <span data-ttu-id="1da1d-403">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-403">String</span></span> |
| <span data-ttu-id="1da1d-404">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-404">**Possible values**</span></span> | <span data-ttu-id="1da1d-405">選用 (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-405">optional (default)</span></span> <br/> <span data-ttu-id="1da1d-406">必要</span><span class="sxs-lookup"><span data-stu-id="1da1d-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="1da1d-407">啟用/停用自動範例報送</span><span class="sxs-lookup"><span data-stu-id="1da1d-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="1da1d-408">會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。</span><span class="sxs-lookup"><span data-stu-id="1da1d-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="1da1d-409">如果提交的檔案可能包含個人資訊，系統會提示您。</span><span class="sxs-lookup"><span data-stu-id="1da1d-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="1da1d-410">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-410">Section</span></span>|<span data-ttu-id="1da1d-411">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-412">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-413">**Key**</span></span> | <span data-ttu-id="1da1d-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="1da1d-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="1da1d-415">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-415">**Data type**</span></span> | <span data-ttu-id="1da1d-416">布林值</span><span class="sxs-lookup"><span data-stu-id="1da1d-416">Boolean</span></span> |
| <span data-ttu-id="1da1d-417">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-417">**Possible values**</span></span> | <span data-ttu-id="1da1d-418">true (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-418">true (default)</span></span> <br/> <span data-ttu-id="1da1d-419">假</span><span class="sxs-lookup"><span data-stu-id="1da1d-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="1da1d-420">啟用/停用自動安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="1da1d-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="1da1d-421">決定是否自動安裝安全性智慧更新：</span><span class="sxs-lookup"><span data-stu-id="1da1d-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="1da1d-422">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-422">Section</span></span>|<span data-ttu-id="1da1d-423">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-424">**Key**</span></span> | <span data-ttu-id="1da1d-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="1da1d-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="1da1d-426">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-426">**Data type**</span></span> | <span data-ttu-id="1da1d-427">布林值</span><span class="sxs-lookup"><span data-stu-id="1da1d-427">Boolean</span></span> |
| <span data-ttu-id="1da1d-428">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-428">**Possible values**</span></span> | <span data-ttu-id="1da1d-429">true (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-429">true (default)</span></span> <br/> <span data-ttu-id="1da1d-430">假</span><span class="sxs-lookup"><span data-stu-id="1da1d-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="1da1d-431">使用者介面偏好設定</span><span class="sxs-lookup"><span data-stu-id="1da1d-431">User interface preferences</span></span>

<span data-ttu-id="1da1d-432">管理 macOS 上之 Microsoft Defender for Endpoint 之使用者介面的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="1da1d-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1da1d-433">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-433">Section</span></span>|<span data-ttu-id="1da1d-434">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-435">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-436">**Key**</span></span> | <span data-ttu-id="1da1d-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="1da1d-437">userInterface</span></span> |
| <span data-ttu-id="1da1d-438">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-438">**Data type**</span></span> | <span data-ttu-id="1da1d-439">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="1da1d-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1da1d-440">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-440">**Comments**</span></span> | <span data-ttu-id="1da1d-441">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="1da1d-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="1da1d-442">顯示/隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="1da1d-442">Show / hide status menu icon</span></span>

<span data-ttu-id="1da1d-443">指定是否要顯示或隱藏螢幕右上角的 [狀態] 功能表圖示。</span><span class="sxs-lookup"><span data-stu-id="1da1d-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="1da1d-444">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-444">Section</span></span>|<span data-ttu-id="1da1d-445">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-446">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-447">**Key**</span></span> | <span data-ttu-id="1da1d-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="1da1d-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="1da1d-449">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-449">**Data type**</span></span> | <span data-ttu-id="1da1d-450">布林值</span><span class="sxs-lookup"><span data-stu-id="1da1d-450">Boolean</span></span> |
| <span data-ttu-id="1da1d-451">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-451">**Possible values**</span></span> | <span data-ttu-id="1da1d-452">false (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-452">false (default)</span></span> <br/> <span data-ttu-id="1da1d-453">真</span><span class="sxs-lookup"><span data-stu-id="1da1d-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="1da1d-454">[顯示/隱藏] 選項以傳送意見反應</span><span class="sxs-lookup"><span data-stu-id="1da1d-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="1da1d-455">指定使用者是否可以前往提交對 Microsoft 的意見反應 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="1da1d-456">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-456">Section</span></span>|<span data-ttu-id="1da1d-457">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-458">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-459">**Key**</span></span> | <span data-ttu-id="1da1d-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="1da1d-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="1da1d-461">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-461">**Data type**</span></span> | <span data-ttu-id="1da1d-462">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-462">String</span></span> |
| <span data-ttu-id="1da1d-463">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-463">**Possible values**</span></span> | <span data-ttu-id="1da1d-464">已啟用 (預設) </span><span class="sxs-lookup"><span data-stu-id="1da1d-464">enabled (default)</span></span> <br/> <span data-ttu-id="1da1d-465">禁用</span><span class="sxs-lookup"><span data-stu-id="1da1d-465">disabled</span></span> |
| <span data-ttu-id="1da1d-466">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-466">**Comments**</span></span> | <span data-ttu-id="1da1d-467">可在 Microsoft Defender for Endpoint 版本101.19.61 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="1da1d-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="1da1d-468">端點偵測和回應喜好設定</span><span class="sxs-lookup"><span data-stu-id="1da1d-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="1da1d-469">管理 macOS 上之 Microsoft Defender for Endpoint 的端點偵測和回應 (EDR) 元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="1da1d-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1da1d-470">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-470">Section</span></span>|<span data-ttu-id="1da1d-471">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-472">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-473">**Key**</span></span> | <span data-ttu-id="1da1d-474">edr</span><span class="sxs-lookup"><span data-stu-id="1da1d-474">edr</span></span> |
| <span data-ttu-id="1da1d-475">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-475">**Data type**</span></span> | <span data-ttu-id="1da1d-476">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="1da1d-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1da1d-477">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-477">**Comments**</span></span> | <span data-ttu-id="1da1d-478">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="1da1d-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="1da1d-479">裝置標記</span><span class="sxs-lookup"><span data-stu-id="1da1d-479">Device tags</span></span>

<span data-ttu-id="1da1d-480">指定標記名稱及其值。</span><span class="sxs-lookup"><span data-stu-id="1da1d-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="1da1d-481">GROUP 標記，以指定的值標記裝置。</span><span class="sxs-lookup"><span data-stu-id="1da1d-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="1da1d-482">標記會反映在入口網站的 [裝置] 頁面底下，可用於篩選和群組裝置。</span><span class="sxs-lookup"><span data-stu-id="1da1d-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="1da1d-483">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-483">Section</span></span>|<span data-ttu-id="1da1d-484">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-485">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-486">**Key**</span></span> | <span data-ttu-id="1da1d-487">標籤</span><span class="sxs-lookup"><span data-stu-id="1da1d-487">tags</span></span> |
| <span data-ttu-id="1da1d-488">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-488">**Data type**</span></span> | <span data-ttu-id="1da1d-489">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="1da1d-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1da1d-490">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1da1d-490">**Comments**</span></span> | <span data-ttu-id="1da1d-491">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="1da1d-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="1da1d-492">標記類型</span><span class="sxs-lookup"><span data-stu-id="1da1d-492">Type of tag</span></span>

<span data-ttu-id="1da1d-493">會指定標記的類型</span><span class="sxs-lookup"><span data-stu-id="1da1d-493">Specifies the type of tag</span></span>

|<span data-ttu-id="1da1d-494">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-494">Section</span></span>|<span data-ttu-id="1da1d-495">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-496">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-497">**Key**</span></span> | <span data-ttu-id="1da1d-498">機碼</span><span class="sxs-lookup"><span data-stu-id="1da1d-498">key</span></span> |
| <span data-ttu-id="1da1d-499">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-499">**Data type**</span></span> | <span data-ttu-id="1da1d-500">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-500">String</span></span> |
| <span data-ttu-id="1da1d-501">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="1da1d-502">標記值</span><span class="sxs-lookup"><span data-stu-id="1da1d-502">Value of tag</span></span>

<span data-ttu-id="1da1d-503">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="1da1d-503">Specifies the value of tag</span></span>

|<span data-ttu-id="1da1d-504">區段</span><span class="sxs-lookup"><span data-stu-id="1da1d-504">Section</span></span>|<span data-ttu-id="1da1d-505">值</span><span class="sxs-lookup"><span data-stu-id="1da1d-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1da1d-506">**網域**</span><span class="sxs-lookup"><span data-stu-id="1da1d-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1da1d-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="1da1d-507">**Key**</span></span> | <span data-ttu-id="1da1d-508">數值</span><span class="sxs-lookup"><span data-stu-id="1da1d-508">value</span></span> |
| <span data-ttu-id="1da1d-509">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1da1d-509">**Data type**</span></span> | <span data-ttu-id="1da1d-510">字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-510">String</span></span> |
| <span data-ttu-id="1da1d-511">**可能值**</span><span class="sxs-lookup"><span data-stu-id="1da1d-511">**Possible values**</span></span> | <span data-ttu-id="1da1d-512">任何字串</span><span class="sxs-lookup"><span data-stu-id="1da1d-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="1da1d-513">每個 tag 類型只能設定一個值。</span><span class="sxs-lookup"><span data-stu-id="1da1d-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="1da1d-514">標記的類型是唯一的，不應該在相同的設定檔中重複。</span><span class="sxs-lookup"><span data-stu-id="1da1d-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="1da1d-515">建議的設定設定檔</span><span class="sxs-lookup"><span data-stu-id="1da1d-515">Recommended configuration profile</span></span>

<span data-ttu-id="1da1d-516">若要開始使用，我們建議您的企業進行下列設定，以利用 Microsoft Defender for Endpoint 所提供的所有保護功能。</span><span class="sxs-lookup"><span data-stu-id="1da1d-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="1da1d-517">下列設定設定檔 (，如果 JAMF，可以上傳至自訂設定設定檔的屬性清單) 會：</span><span class="sxs-lookup"><span data-stu-id="1da1d-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="1da1d-518">啟用 (RTP) 的即時保護</span><span class="sxs-lookup"><span data-stu-id="1da1d-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="1da1d-519">指定如何處理下列威脅類型：</span><span class="sxs-lookup"><span data-stu-id="1da1d-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="1da1d-520">封鎖 **(PUA) 可能有害的應用程式**</span><span class="sxs-lookup"><span data-stu-id="1da1d-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="1da1d-521">將具有高壓縮率) 的封存 **bombs (檔案** 審核至 Microsoft Defender for Endpoint 記錄檔</span><span class="sxs-lookup"><span data-stu-id="1da1d-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="1da1d-522">啟用自動安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="1da1d-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="1da1d-523">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="1da1d-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="1da1d-524">啟用自動範例提交</span><span class="sxs-lookup"><span data-stu-id="1da1d-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1da1d-525">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="1da1d-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="1da1d-526">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="1da1d-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="1da1d-527">完整設定檔範例</span><span class="sxs-lookup"><span data-stu-id="1da1d-527">Full configuration profile example</span></span>

<span data-ttu-id="1da1d-528">下列範本包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要在 macOS 上進一步控制端點的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="1da1d-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1da1d-529">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="1da1d-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="1da1d-530">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="1da1d-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="1da1d-531">屬性清單驗證</span><span class="sxs-lookup"><span data-stu-id="1da1d-531">Property list validation</span></span>

<span data-ttu-id="1da1d-532">屬性清單必須是有效的 *plist* 檔案。</span><span class="sxs-lookup"><span data-stu-id="1da1d-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="1da1d-533">您可以執行下列動作來檢查：</span><span class="sxs-lookup"><span data-stu-id="1da1d-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="1da1d-534">如果檔案的格式良好，上述命令會輸出並傳回 `OK` 的退出程式碼 `0` 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="1da1d-535">否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="1da1d-536">設定設定檔部署</span><span class="sxs-lookup"><span data-stu-id="1da1d-536">Configuration profile deployment</span></span>

<span data-ttu-id="1da1d-537">在您為企業建立設定檔之後，您可以透過企業使用的管理主控台來部署它。</span><span class="sxs-lookup"><span data-stu-id="1da1d-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="1da1d-538">下列各節提供如何使用 JAMF 和 Intune 部署此設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="1da1d-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="1da1d-539">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="1da1d-539">JAMF deployment</span></span>

<span data-ttu-id="1da1d-540">從 JAMF 主控台，開啟 [**電腦** 設定配置  >  **檔**]，流覽至您想要使用的設定設定檔，然後選取 [**自訂設定**]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="1da1d-541">建立具有 `com.microsoft.wdav` 偏好的網域的專案，並上傳先前產生的 *plist* 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="1da1d-542">您必須輸入正確的喜好網域 (`com.microsoft.wdav`) ; 否則，Microsoft Defender For Endpoint 將不會識別首選項。</span><span class="sxs-lookup"><span data-stu-id="1da1d-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="1da1d-543">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="1da1d-543">Intune deployment</span></span>

1. <span data-ttu-id="1da1d-544">開啟 [**管理**  >  **裝置** 設定]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="1da1d-545">選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="1da1d-546">選擇設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="1da1d-546">Choose a name for the profile.</span></span> <span data-ttu-id="1da1d-547">將 **平臺 = macOS** 變更為 **Profile type = Custom**。</span><span class="sxs-lookup"><span data-stu-id="1da1d-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="1da1d-548">選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-548">Select Configure.</span></span>

3. <span data-ttu-id="1da1d-549">儲存先前產生的 plist `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="1da1d-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="1da1d-550">輸入 `com.microsoft.wdav` 為 **自訂設定設定檔名稱**。</span><span class="sxs-lookup"><span data-stu-id="1da1d-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="1da1d-551">開啟設定設定檔，並上傳 `com.microsoft.wdav.xml` 檔。</span><span class="sxs-lookup"><span data-stu-id="1da1d-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="1da1d-552"> (此檔案是在步驟3中建立。 ) </span><span class="sxs-lookup"><span data-stu-id="1da1d-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="1da1d-553">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-553">Select **OK**.</span></span>

7. <span data-ttu-id="1da1d-554">選取 [**管理**  >  **指派**]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="1da1d-555">在 [ **包含** ] 索引標籤中，選取 [ **指派給所有使用者 & 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="1da1d-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="1da1d-556">您必須輸入正確的自訂設定檔名稱;否則，Microsoft Defender for Endpoint 將不會識別這些喜好設定。</span><span class="sxs-lookup"><span data-stu-id="1da1d-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="1da1d-557">資源</span><span class="sxs-lookup"><span data-stu-id="1da1d-557">Resources</span></span>

- [<span data-ttu-id="1da1d-558">組態設定檔參照 (Apple 開發人員文件)</span><span class="sxs-lookup"><span data-stu-id="1da1d-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
