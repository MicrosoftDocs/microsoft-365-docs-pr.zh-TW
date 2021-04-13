---
title: 設定 Mac 版 Microsoft Defender ATP 的喜好設定
description: 在企業組織中設定適用于 Mac 的 Microsoft Defender ATP。
keywords: microsoft，defender，atp，mac，management，喜好設定，enterprise，intune，jamf，macos，catalina，mojave，高塞拉里昂
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
ms.openlocfilehash: 951c51c767ba09ebc6056481b4fac45da09c5671
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688546"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="52556-104">在 macOS 上設定 Microsoft Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="52556-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="52556-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="52556-105">**Applies to:**</span></span>

- [<span data-ttu-id="52556-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="52556-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="52556-107">本文包含如何針對企業組織中 macOS 之 Microsoft Defender for Endpoint 設定偏好設定的指示。</span><span class="sxs-lookup"><span data-stu-id="52556-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="52556-108">若要在使用命令列介面的 macOS 上設定 Microsoft Defender for Endpoint，請參閱 [Resources](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="52556-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="52556-109">摘要</span><span class="sxs-lookup"><span data-stu-id="52556-109">Summary</span></span>

<span data-ttu-id="52556-110">在企業組織中，可透過使用其中一種管理工具部署的設定檔來管理 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="52556-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="52556-111">安全作業小組所管理的喜好設定優先順序高於裝置上本機設定的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="52556-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="52556-112">變更透過設定設定檔設定的喜好設定時，需要提升許可權，且不需要系統管理許可權的使用者才能使用。</span><span class="sxs-lookup"><span data-stu-id="52556-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="52556-113">本文說明設定檔的結構，包含您可以用來開始使用的建議設定檔，並提供如何部署設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="52556-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="52556-114">設定設定檔結構</span><span class="sxs-lookup"><span data-stu-id="52556-114">Configuration profile structure</span></span>

<span data-ttu-id="52556-115">設定設定檔是由按鍵 (所識別之專案所識別的 *plist* 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。</span><span class="sxs-lookup"><span data-stu-id="52556-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="52556-116">值既可以是簡單的 (例如數值) 或複雜，例如首選項的嵌套清單。</span><span class="sxs-lookup"><span data-stu-id="52556-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="52556-117">設定設定檔的版面配置取決於您所使用的管理主控台。</span><span class="sxs-lookup"><span data-stu-id="52556-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="52556-118">下列各節包含 JAMF 及 Intune 之設定檔的範例。</span><span class="sxs-lookup"><span data-stu-id="52556-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="52556-119">設定設定檔的最上層包括 Microsoft Defender for Endpoint 之子領域的產品範圍偏好設定和專案，在下一節將詳細說明。</span><span class="sxs-lookup"><span data-stu-id="52556-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="52556-120">防病毒引擎偏好設定</span><span class="sxs-lookup"><span data-stu-id="52556-120">Antivirus engine preferences</span></span>

<span data-ttu-id="52556-121">設定設定檔的 [ *antivirusEngine* ] 區段是用來管理 Microsoft Defender for Endpoint 之防病毒元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="52556-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="52556-122">區段</span><span class="sxs-lookup"><span data-stu-id="52556-122">Section</span></span>|<span data-ttu-id="52556-123">值</span><span class="sxs-lookup"><span data-stu-id="52556-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-124">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-125">**Key**</span></span> | <span data-ttu-id="52556-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="52556-126">antivirusEngine</span></span> |
| <span data-ttu-id="52556-127">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-127">**Data type**</span></span> | <span data-ttu-id="52556-128">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="52556-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="52556-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-129">**Comments**</span></span> | <span data-ttu-id="52556-130">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="52556-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="52556-131">啟用/停用即時保護</span><span class="sxs-lookup"><span data-stu-id="52556-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="52556-132">指定是否要啟用即時保護，以在存取檔時進行掃描。</span><span class="sxs-lookup"><span data-stu-id="52556-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="52556-133">區段</span><span class="sxs-lookup"><span data-stu-id="52556-133">Section</span></span>|<span data-ttu-id="52556-134">值</span><span class="sxs-lookup"><span data-stu-id="52556-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-135">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-136">**Key**</span></span> | <span data-ttu-id="52556-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="52556-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="52556-138">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-138">**Data type**</span></span> | <span data-ttu-id="52556-139">布林值</span><span class="sxs-lookup"><span data-stu-id="52556-139">Boolean</span></span> |
| <span data-ttu-id="52556-140">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-140">**Possible values**</span></span> | <span data-ttu-id="52556-141">true (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-141">true (default)</span></span> <br/> <span data-ttu-id="52556-142">假</span><span class="sxs-lookup"><span data-stu-id="52556-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="52556-143">啟用/停用被動模式</span><span class="sxs-lookup"><span data-stu-id="52556-143">Enable / disable passive mode</span></span>

<span data-ttu-id="52556-144">指定防病毒引擎是否以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="52556-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="52556-145">被動式模式的含義如下：</span><span class="sxs-lookup"><span data-stu-id="52556-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="52556-146">已關閉即時保護</span><span class="sxs-lookup"><span data-stu-id="52556-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="52556-147">已開啟隨選掃描</span><span class="sxs-lookup"><span data-stu-id="52556-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="52556-148">關閉自動威脅修復功能</span><span class="sxs-lookup"><span data-stu-id="52556-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="52556-149">已開啟安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="52556-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="52556-150">隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="52556-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="52556-151">區段</span><span class="sxs-lookup"><span data-stu-id="52556-151">Section</span></span>|<span data-ttu-id="52556-152">值</span><span class="sxs-lookup"><span data-stu-id="52556-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-153">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-154">**Key**</span></span> | <span data-ttu-id="52556-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="52556-155">passiveMode</span></span> |
| <span data-ttu-id="52556-156">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-156">**Data type**</span></span> | <span data-ttu-id="52556-157">布林值</span><span class="sxs-lookup"><span data-stu-id="52556-157">Boolean</span></span> |
| <span data-ttu-id="52556-158">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-158">**Possible values**</span></span> | <span data-ttu-id="52556-159">false (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-159">false (default)</span></span> <br/> <span data-ttu-id="52556-160">真</span><span class="sxs-lookup"><span data-stu-id="52556-160">true</span></span> |
| <span data-ttu-id="52556-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-161">**Comments**</span></span> | <span data-ttu-id="52556-162">可在 Microsoft Defender for Endpoint 版本100.67.60 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="52556-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="52556-163">排除合併原則</span><span class="sxs-lookup"><span data-stu-id="52556-163">Exclusion merge policy</span></span>

<span data-ttu-id="52556-164">指定排除的合併原則。</span><span class="sxs-lookup"><span data-stu-id="52556-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="52556-165">這可以是管理員定義和使用者定義排除 (的組合， `merge`) 或僅限系統管理員定義的排除 (`admin_only`) 。</span><span class="sxs-lookup"><span data-stu-id="52556-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="52556-166">您可以使用此設定來限制本機使用者定義自己的排除專案。</span><span class="sxs-lookup"><span data-stu-id="52556-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="52556-167">區段</span><span class="sxs-lookup"><span data-stu-id="52556-167">Section</span></span>|<span data-ttu-id="52556-168">值</span><span class="sxs-lookup"><span data-stu-id="52556-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-169">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-170">**Key**</span></span> | <span data-ttu-id="52556-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="52556-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="52556-172">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-172">**Data type**</span></span> | <span data-ttu-id="52556-173">字串</span><span class="sxs-lookup"><span data-stu-id="52556-173">String</span></span> |
| <span data-ttu-id="52556-174">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-174">**Possible values**</span></span> | <span data-ttu-id="52556-175">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="52556-175">merge (default)</span></span> <br/> <span data-ttu-id="52556-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="52556-176">admin_only</span></span> |
| <span data-ttu-id="52556-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-177">**Comments**</span></span> | <span data-ttu-id="52556-178">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="52556-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="52556-179">掃描排除</span><span class="sxs-lookup"><span data-stu-id="52556-179">Scan exclusions</span></span>

<span data-ttu-id="52556-180">指定排除在掃描之外的實體。</span><span class="sxs-lookup"><span data-stu-id="52556-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="52556-181">您可以使用完整路徑、副檔名或檔案名來指定排除。</span><span class="sxs-lookup"><span data-stu-id="52556-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="52556-182">區段</span><span class="sxs-lookup"><span data-stu-id="52556-182">Section</span></span>|<span data-ttu-id="52556-183">值</span><span class="sxs-lookup"><span data-stu-id="52556-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-184">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-185">**Key**</span></span> | <span data-ttu-id="52556-186">排除</span><span class="sxs-lookup"><span data-stu-id="52556-186">exclusions</span></span> |
| <span data-ttu-id="52556-187">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-187">**Data type**</span></span> | <span data-ttu-id="52556-188">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="52556-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="52556-189">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-189">**Comments**</span></span> | <span data-ttu-id="52556-190">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="52556-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="52556-191">排除的類型</span><span class="sxs-lookup"><span data-stu-id="52556-191">Type of exclusion</span></span>

<span data-ttu-id="52556-192">指定 [依類型掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="52556-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="52556-193">區段</span><span class="sxs-lookup"><span data-stu-id="52556-193">Section</span></span>|<span data-ttu-id="52556-194">值</span><span class="sxs-lookup"><span data-stu-id="52556-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-195">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-196">**Key**</span></span> | <span data-ttu-id="52556-197">$type</span><span class="sxs-lookup"><span data-stu-id="52556-197">$type</span></span> |
| <span data-ttu-id="52556-198">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-198">**Data type**</span></span> | <span data-ttu-id="52556-199">字串</span><span class="sxs-lookup"><span data-stu-id="52556-199">String</span></span> |
| <span data-ttu-id="52556-200">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-200">**Possible values**</span></span> | <span data-ttu-id="52556-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="52556-201">excludedPath</span></span> <br/> <span data-ttu-id="52556-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="52556-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="52556-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="52556-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="52556-204">排除內容的路徑</span><span class="sxs-lookup"><span data-stu-id="52556-204">Path to excluded content</span></span>

<span data-ttu-id="52556-205">指定以完整檔案路徑掃描排除的內容。</span><span class="sxs-lookup"><span data-stu-id="52556-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="52556-206">區段</span><span class="sxs-lookup"><span data-stu-id="52556-206">Section</span></span>|<span data-ttu-id="52556-207">值</span><span class="sxs-lookup"><span data-stu-id="52556-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-208">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-209">**Key**</span></span> | <span data-ttu-id="52556-210">路徑</span><span class="sxs-lookup"><span data-stu-id="52556-210">path</span></span> |
| <span data-ttu-id="52556-211">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-211">**Data type**</span></span> | <span data-ttu-id="52556-212">字串</span><span class="sxs-lookup"><span data-stu-id="52556-212">String</span></span> |
| <span data-ttu-id="52556-213">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-213">**Possible values**</span></span> | <span data-ttu-id="52556-214">有效路徑</span><span class="sxs-lookup"><span data-stu-id="52556-214">valid paths</span></span> |
| <span data-ttu-id="52556-215">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-215">**Comments**</span></span> | <span data-ttu-id="52556-216">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="52556-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="52556-217"> (檔/目錄的路徑類型) </span><span class="sxs-lookup"><span data-stu-id="52556-217">Path type (file / directory)</span></span>

<span data-ttu-id="52556-218">指出 *path* 屬性參照的是檔案或目錄。</span><span class="sxs-lookup"><span data-stu-id="52556-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="52556-219">區段</span><span class="sxs-lookup"><span data-stu-id="52556-219">Section</span></span>|<span data-ttu-id="52556-220">值</span><span class="sxs-lookup"><span data-stu-id="52556-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-221">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-222">**Key**</span></span> | <span data-ttu-id="52556-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="52556-223">isDirectory</span></span> |
| <span data-ttu-id="52556-224">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-224">**Data type**</span></span> | <span data-ttu-id="52556-225">布林值</span><span class="sxs-lookup"><span data-stu-id="52556-225">Boolean</span></span> |
| <span data-ttu-id="52556-226">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-226">**Possible values**</span></span> | <span data-ttu-id="52556-227">false (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-227">false (default)</span></span> <br/> <span data-ttu-id="52556-228">真</span><span class="sxs-lookup"><span data-stu-id="52556-228">true</span></span> |
| <span data-ttu-id="52556-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-229">**Comments**</span></span> | <span data-ttu-id="52556-230">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="52556-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="52556-231">從掃描排除的副檔名</span><span class="sxs-lookup"><span data-stu-id="52556-231">File extension excluded from the scan</span></span>

<span data-ttu-id="52556-232">指定 [依副檔名掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="52556-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="52556-233">區段</span><span class="sxs-lookup"><span data-stu-id="52556-233">Section</span></span>|<span data-ttu-id="52556-234">值</span><span class="sxs-lookup"><span data-stu-id="52556-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-235">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-236">**Key**</span></span> | <span data-ttu-id="52556-237">擴展</span><span class="sxs-lookup"><span data-stu-id="52556-237">extension</span></span> |
| <span data-ttu-id="52556-238">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-238">**Data type**</span></span> | <span data-ttu-id="52556-239">字串</span><span class="sxs-lookup"><span data-stu-id="52556-239">String</span></span> |
| <span data-ttu-id="52556-240">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-240">**Possible values**</span></span> | <span data-ttu-id="52556-241">有效的副檔名</span><span class="sxs-lookup"><span data-stu-id="52556-241">valid file extensions</span></span> |
| <span data-ttu-id="52556-242">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-242">**Comments**</span></span> | <span data-ttu-id="52556-243">僅適用于 *excludedFileExtension* *$type*</span><span class="sxs-lookup"><span data-stu-id="52556-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="52556-244">從掃描排除的處理常式</span><span class="sxs-lookup"><span data-stu-id="52556-244">Process excluded from the scan</span></span>

<span data-ttu-id="52556-245">指定從掃描排除所有檔案活動的處理常式。</span><span class="sxs-lookup"><span data-stu-id="52556-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="52556-246">您可以透過名稱指定程式 (例如 `cat`) 或完整路徑 (例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="52556-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="52556-247">區段</span><span class="sxs-lookup"><span data-stu-id="52556-247">Section</span></span>|<span data-ttu-id="52556-248">值</span><span class="sxs-lookup"><span data-stu-id="52556-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-249">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-250">**Key**</span></span> | <span data-ttu-id="52556-251">name</span><span class="sxs-lookup"><span data-stu-id="52556-251">name</span></span> |
| <span data-ttu-id="52556-252">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-252">**Data type**</span></span> | <span data-ttu-id="52556-253">字串</span><span class="sxs-lookup"><span data-stu-id="52556-253">String</span></span> |
| <span data-ttu-id="52556-254">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-254">**Possible values**</span></span> | <span data-ttu-id="52556-255">任何字串</span><span class="sxs-lookup"><span data-stu-id="52556-255">any string</span></span> |
| <span data-ttu-id="52556-256">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-256">**Comments**</span></span> | <span data-ttu-id="52556-257">僅適用于 *excludedFileName* *$type*</span><span class="sxs-lookup"><span data-stu-id="52556-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="52556-258">允許的威脅</span><span class="sxs-lookup"><span data-stu-id="52556-258">Allowed threats</span></span>

<span data-ttu-id="52556-259">依名稱指定不會被 Defender for Mac 的 Endpoint 封鎖的威脅。</span><span class="sxs-lookup"><span data-stu-id="52556-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="52556-260">這些威脅都會允許執行。</span><span class="sxs-lookup"><span data-stu-id="52556-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="52556-261">區段</span><span class="sxs-lookup"><span data-stu-id="52556-261">Section</span></span>|<span data-ttu-id="52556-262">值</span><span class="sxs-lookup"><span data-stu-id="52556-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-263">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-264">**Key**</span></span> | <span data-ttu-id="52556-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="52556-265">allowedThreats</span></span> |
| <span data-ttu-id="52556-266">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-266">**Data type**</span></span> | <span data-ttu-id="52556-267">字串陣列</span><span class="sxs-lookup"><span data-stu-id="52556-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="52556-268">不允許的威脅動作</span><span class="sxs-lookup"><span data-stu-id="52556-268">Disallowed threat actions</span></span>

<span data-ttu-id="52556-269">限制偵測到威脅時，裝置的本機使用者可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="52556-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="52556-270">在此清單中包含的動作不會顯示在使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="52556-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="52556-271">區段</span><span class="sxs-lookup"><span data-stu-id="52556-271">Section</span></span>|<span data-ttu-id="52556-272">值</span><span class="sxs-lookup"><span data-stu-id="52556-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-273">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-274">**Key**</span></span> | <span data-ttu-id="52556-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="52556-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="52556-276">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-276">**Data type**</span></span> | <span data-ttu-id="52556-277">字串陣列</span><span class="sxs-lookup"><span data-stu-id="52556-277">Array of strings</span></span> |
| <span data-ttu-id="52556-278">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-278">**Possible values**</span></span> | <span data-ttu-id="52556-279">允許 (限制使用者允許威脅) </span><span class="sxs-lookup"><span data-stu-id="52556-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="52556-280">restore (會限制使用者從隔離區還原威脅) </span><span class="sxs-lookup"><span data-stu-id="52556-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="52556-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-281">**Comments**</span></span> | <span data-ttu-id="52556-282">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="52556-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="52556-283">威脅類型設定</span><span class="sxs-lookup"><span data-stu-id="52556-283">Threat type settings</span></span>

<span data-ttu-id="52556-284">指定 macOS 上的 Microsoft Defender for Endpoint 處理特定威脅類型的方式。</span><span class="sxs-lookup"><span data-stu-id="52556-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="52556-285">區段</span><span class="sxs-lookup"><span data-stu-id="52556-285">Section</span></span>|<span data-ttu-id="52556-286">值</span><span class="sxs-lookup"><span data-stu-id="52556-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-287">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-288">**Key**</span></span> | <span data-ttu-id="52556-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="52556-289">threatTypeSettings</span></span> |
| <span data-ttu-id="52556-290">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-290">**Data type**</span></span> | <span data-ttu-id="52556-291">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="52556-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="52556-292">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-292">**Comments**</span></span> | <span data-ttu-id="52556-293">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="52556-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="52556-294">威脅類型</span><span class="sxs-lookup"><span data-stu-id="52556-294">Threat type</span></span>

<span data-ttu-id="52556-295">指定威脅類型。</span><span class="sxs-lookup"><span data-stu-id="52556-295">Specify threat types.</span></span>

|<span data-ttu-id="52556-296">區段</span><span class="sxs-lookup"><span data-stu-id="52556-296">Section</span></span>|<span data-ttu-id="52556-297">值</span><span class="sxs-lookup"><span data-stu-id="52556-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-298">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-299">**Key**</span></span> | <span data-ttu-id="52556-300">機碼</span><span class="sxs-lookup"><span data-stu-id="52556-300">key</span></span> |
| <span data-ttu-id="52556-301">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-301">**Data type**</span></span> | <span data-ttu-id="52556-302">字串</span><span class="sxs-lookup"><span data-stu-id="52556-302">String</span></span> |
| <span data-ttu-id="52556-303">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-303">**Possible values**</span></span> | <span data-ttu-id="52556-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="52556-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="52556-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="52556-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="52556-306">要採取的動作</span><span class="sxs-lookup"><span data-stu-id="52556-306">Action to take</span></span>

<span data-ttu-id="52556-307">指定當偵測到上述區段中所指定類型的威脅時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="52556-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="52556-308">請從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="52556-308">Choose from the following options:</span></span>

- <span data-ttu-id="52556-309">**Audit**：您的裝置不會受到這種威脅類型的保護，但是會記錄有關威脅的專案。</span><span class="sxs-lookup"><span data-stu-id="52556-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="52556-310">**封鎖**：您的裝置會受到此威脅類型的保護，而且您會收到使用者介面及安全性主控台的通知。</span><span class="sxs-lookup"><span data-stu-id="52556-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="52556-311">**Off**：您的裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="52556-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="52556-312">區段</span><span class="sxs-lookup"><span data-stu-id="52556-312">Section</span></span>|<span data-ttu-id="52556-313">值</span><span class="sxs-lookup"><span data-stu-id="52556-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-314">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-315">**Key**</span></span> | <span data-ttu-id="52556-316">數值</span><span class="sxs-lookup"><span data-stu-id="52556-316">value</span></span> |
| <span data-ttu-id="52556-317">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-317">**Data type**</span></span> | <span data-ttu-id="52556-318">字串</span><span class="sxs-lookup"><span data-stu-id="52556-318">String</span></span> |
| <span data-ttu-id="52556-319">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-319">**Possible values**</span></span> | <span data-ttu-id="52556-320">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-320">audit (default)</span></span> <br/> <span data-ttu-id="52556-321">塊</span><span class="sxs-lookup"><span data-stu-id="52556-321">block</span></span> <br/> <span data-ttu-id="52556-322">遠離</span><span class="sxs-lookup"><span data-stu-id="52556-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="52556-323">威脅類型設定合併原則</span><span class="sxs-lookup"><span data-stu-id="52556-323">Threat type settings merge policy</span></span>

<span data-ttu-id="52556-324">指定威脅類型設定的合併原則。</span><span class="sxs-lookup"><span data-stu-id="52556-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="52556-325">這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="52556-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="52556-326">此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。</span><span class="sxs-lookup"><span data-stu-id="52556-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="52556-327">區段</span><span class="sxs-lookup"><span data-stu-id="52556-327">Section</span></span>|<span data-ttu-id="52556-328">值</span><span class="sxs-lookup"><span data-stu-id="52556-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-329">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-330">**Key**</span></span> | <span data-ttu-id="52556-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="52556-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="52556-332">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-332">**Data type**</span></span> | <span data-ttu-id="52556-333">字串</span><span class="sxs-lookup"><span data-stu-id="52556-333">String</span></span> |
| <span data-ttu-id="52556-334">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-334">**Possible values**</span></span> | <span data-ttu-id="52556-335">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="52556-335">merge (default)</span></span> <br/> <span data-ttu-id="52556-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="52556-336">admin_only</span></span> |
| <span data-ttu-id="52556-337">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-337">**Comments**</span></span> | <span data-ttu-id="52556-338">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="52556-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="52556-339">防病毒掃描記錄保留 (天數) </span><span class="sxs-lookup"><span data-stu-id="52556-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="52556-340">指定在裝置上的掃描歷程記錄中保留結果的天數。</span><span class="sxs-lookup"><span data-stu-id="52556-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="52556-341">舊的掃描結果會從歷史記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="52556-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="52556-342">也會從磁片中移除的舊隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="52556-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="52556-343">區段</span><span class="sxs-lookup"><span data-stu-id="52556-343">Section</span></span>|<span data-ttu-id="52556-344">值</span><span class="sxs-lookup"><span data-stu-id="52556-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-345">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-346">**Key**</span></span> | <span data-ttu-id="52556-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="52556-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="52556-348">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-348">**Data type**</span></span> | <span data-ttu-id="52556-349">字串</span><span class="sxs-lookup"><span data-stu-id="52556-349">String</span></span> |
| <span data-ttu-id="52556-350">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-350">**Possible values**</span></span> | <span data-ttu-id="52556-351">90 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="52556-351">90 (default).</span></span> <span data-ttu-id="52556-352">允許的值介於1天到180天。</span><span class="sxs-lookup"><span data-stu-id="52556-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="52556-353">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-353">**Comments**</span></span> | <span data-ttu-id="52556-354">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="52556-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="52556-355">防病毒掃描歷程記錄中的專案數上限</span><span class="sxs-lookup"><span data-stu-id="52556-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="52556-356">指定要保留在掃描記錄中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="52556-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="52556-357">專案包括過去執行的所有按需掃描及所有防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="52556-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="52556-358">區段</span><span class="sxs-lookup"><span data-stu-id="52556-358">Section</span></span>|<span data-ttu-id="52556-359">值</span><span class="sxs-lookup"><span data-stu-id="52556-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-360">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-361">**Key**</span></span> | <span data-ttu-id="52556-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="52556-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="52556-363">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-363">**Data type**</span></span> | <span data-ttu-id="52556-364">字串</span><span class="sxs-lookup"><span data-stu-id="52556-364">String</span></span> |
| <span data-ttu-id="52556-365">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-365">**Possible values**</span></span> | <span data-ttu-id="52556-366">10000 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="52556-366">10000 (default).</span></span> <span data-ttu-id="52556-367">允許的值是從5000專案到15000專案。</span><span class="sxs-lookup"><span data-stu-id="52556-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="52556-368">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-368">**Comments**</span></span> | <span data-ttu-id="52556-369">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="52556-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="52556-370">雲端提供的保護偏好設定</span><span class="sxs-lookup"><span data-stu-id="52556-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="52556-371">設定 macOS 上的 Microsoft Defender for Endpoint 的雲端驅動保護功能。</span><span class="sxs-lookup"><span data-stu-id="52556-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="52556-372">區段</span><span class="sxs-lookup"><span data-stu-id="52556-372">Section</span></span>|<span data-ttu-id="52556-373">值</span><span class="sxs-lookup"><span data-stu-id="52556-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-374">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-375">**Key**</span></span> | <span data-ttu-id="52556-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="52556-376">cloudService</span></span> |
| <span data-ttu-id="52556-377">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-377">**Data type**</span></span> | <span data-ttu-id="52556-378">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="52556-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="52556-379">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-379">**Comments**</span></span> | <span data-ttu-id="52556-380">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="52556-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="52556-381">啟用/停用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="52556-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="52556-382">指定是否要對裝置啟用雲端提供保護。</span><span class="sxs-lookup"><span data-stu-id="52556-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="52556-383">若要改善服務的安全性，建議您保持此功能開啟。</span><span class="sxs-lookup"><span data-stu-id="52556-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="52556-384">區段</span><span class="sxs-lookup"><span data-stu-id="52556-384">Section</span></span>|<span data-ttu-id="52556-385">值</span><span class="sxs-lookup"><span data-stu-id="52556-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-386">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-387">**Key**</span></span> | <span data-ttu-id="52556-388">啟用</span><span class="sxs-lookup"><span data-stu-id="52556-388">enabled</span></span> |
| <span data-ttu-id="52556-389">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-389">**Data type**</span></span> | <span data-ttu-id="52556-390">布林值</span><span class="sxs-lookup"><span data-stu-id="52556-390">Boolean</span></span> |
| <span data-ttu-id="52556-391">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-391">**Possible values**</span></span> | <span data-ttu-id="52556-392">true (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-392">true (default)</span></span> <br/> <span data-ttu-id="52556-393">假</span><span class="sxs-lookup"><span data-stu-id="52556-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="52556-394">診斷集合層級</span><span class="sxs-lookup"><span data-stu-id="52556-394">Diagnostic collection level</span></span>

<span data-ttu-id="52556-395">診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="52556-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="52556-396">此設定會決定 Microsoft Defender for Microsoft Defender 所傳送的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="52556-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="52556-397">區段</span><span class="sxs-lookup"><span data-stu-id="52556-397">Section</span></span>|<span data-ttu-id="52556-398">值</span><span class="sxs-lookup"><span data-stu-id="52556-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-399">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-400">**Key**</span></span> | <span data-ttu-id="52556-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="52556-401">diagnosticLevel</span></span> |
| <span data-ttu-id="52556-402">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-402">**Data type**</span></span> | <span data-ttu-id="52556-403">字串</span><span class="sxs-lookup"><span data-stu-id="52556-403">String</span></span> |
| <span data-ttu-id="52556-404">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-404">**Possible values**</span></span> | <span data-ttu-id="52556-405">選用 (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-405">optional (default)</span></span> <br/> <span data-ttu-id="52556-406">必要</span><span class="sxs-lookup"><span data-stu-id="52556-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="52556-407">啟用/停用自動範例報送</span><span class="sxs-lookup"><span data-stu-id="52556-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="52556-408">會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。</span><span class="sxs-lookup"><span data-stu-id="52556-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="52556-409">如果提交的檔案可能包含個人資訊，系統會提示您。</span><span class="sxs-lookup"><span data-stu-id="52556-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="52556-410">區段</span><span class="sxs-lookup"><span data-stu-id="52556-410">Section</span></span>|<span data-ttu-id="52556-411">值</span><span class="sxs-lookup"><span data-stu-id="52556-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-412">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-413">**Key**</span></span> | <span data-ttu-id="52556-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="52556-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="52556-415">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-415">**Data type**</span></span> | <span data-ttu-id="52556-416">布林值</span><span class="sxs-lookup"><span data-stu-id="52556-416">Boolean</span></span> |
| <span data-ttu-id="52556-417">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-417">**Possible values**</span></span> | <span data-ttu-id="52556-418">true (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-418">true (default)</span></span> <br/> <span data-ttu-id="52556-419">假</span><span class="sxs-lookup"><span data-stu-id="52556-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="52556-420">啟用/停用自動安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="52556-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="52556-421">決定是否自動安裝安全性智慧更新：</span><span class="sxs-lookup"><span data-stu-id="52556-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="52556-422">區段</span><span class="sxs-lookup"><span data-stu-id="52556-422">Section</span></span>|<span data-ttu-id="52556-423">值</span><span class="sxs-lookup"><span data-stu-id="52556-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-424">**Key**</span></span> | <span data-ttu-id="52556-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="52556-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="52556-426">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-426">**Data type**</span></span> | <span data-ttu-id="52556-427">布林值</span><span class="sxs-lookup"><span data-stu-id="52556-427">Boolean</span></span> |
| <span data-ttu-id="52556-428">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-428">**Possible values**</span></span> | <span data-ttu-id="52556-429">true (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-429">true (default)</span></span> <br/> <span data-ttu-id="52556-430">假</span><span class="sxs-lookup"><span data-stu-id="52556-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="52556-431">使用者介面偏好設定</span><span class="sxs-lookup"><span data-stu-id="52556-431">User interface preferences</span></span>

<span data-ttu-id="52556-432">管理 macOS 上之 Microsoft Defender for Endpoint 之使用者介面的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="52556-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="52556-433">區段</span><span class="sxs-lookup"><span data-stu-id="52556-433">Section</span></span>|<span data-ttu-id="52556-434">值</span><span class="sxs-lookup"><span data-stu-id="52556-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-435">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-436">**Key**</span></span> | <span data-ttu-id="52556-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="52556-437">userInterface</span></span> |
| <span data-ttu-id="52556-438">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-438">**Data type**</span></span> | <span data-ttu-id="52556-439">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="52556-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="52556-440">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-440">**Comments**</span></span> | <span data-ttu-id="52556-441">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="52556-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="52556-442">顯示/隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="52556-442">Show / hide status menu icon</span></span>

<span data-ttu-id="52556-443">指定是否要顯示或隱藏螢幕右上角的 [狀態] 功能表圖示。</span><span class="sxs-lookup"><span data-stu-id="52556-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="52556-444">區段</span><span class="sxs-lookup"><span data-stu-id="52556-444">Section</span></span>|<span data-ttu-id="52556-445">值</span><span class="sxs-lookup"><span data-stu-id="52556-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-446">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-447">**Key**</span></span> | <span data-ttu-id="52556-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="52556-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="52556-449">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-449">**Data type**</span></span> | <span data-ttu-id="52556-450">布林值</span><span class="sxs-lookup"><span data-stu-id="52556-450">Boolean</span></span> |
| <span data-ttu-id="52556-451">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-451">**Possible values**</span></span> | <span data-ttu-id="52556-452">false (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-452">false (default)</span></span> <br/> <span data-ttu-id="52556-453">真</span><span class="sxs-lookup"><span data-stu-id="52556-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="52556-454">[顯示/隱藏] 選項以傳送意見反應</span><span class="sxs-lookup"><span data-stu-id="52556-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="52556-455">指定使用者是否可以前往提交對 Microsoft 的意見反應 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="52556-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="52556-456">區段</span><span class="sxs-lookup"><span data-stu-id="52556-456">Section</span></span>|<span data-ttu-id="52556-457">值</span><span class="sxs-lookup"><span data-stu-id="52556-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-458">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-459">**Key**</span></span> | <span data-ttu-id="52556-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="52556-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="52556-461">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-461">**Data type**</span></span> | <span data-ttu-id="52556-462">字串</span><span class="sxs-lookup"><span data-stu-id="52556-462">String</span></span> |
| <span data-ttu-id="52556-463">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-463">**Possible values**</span></span> | <span data-ttu-id="52556-464">已啟用 (預設) </span><span class="sxs-lookup"><span data-stu-id="52556-464">enabled (default)</span></span> <br/> <span data-ttu-id="52556-465">禁用</span><span class="sxs-lookup"><span data-stu-id="52556-465">disabled</span></span> |
| <span data-ttu-id="52556-466">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-466">**Comments**</span></span> | <span data-ttu-id="52556-467">可在 Microsoft Defender for Endpoint 版本101.19.61 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="52556-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="52556-468">端點偵測和回應喜好設定</span><span class="sxs-lookup"><span data-stu-id="52556-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="52556-469">管理 macOS 上之 Microsoft Defender for Endpoint 的端點偵測和回應 (EDR) 元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="52556-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="52556-470">區段</span><span class="sxs-lookup"><span data-stu-id="52556-470">Section</span></span>|<span data-ttu-id="52556-471">值</span><span class="sxs-lookup"><span data-stu-id="52556-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-472">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-473">**Key**</span></span> | <span data-ttu-id="52556-474">edr</span><span class="sxs-lookup"><span data-stu-id="52556-474">edr</span></span> |
| <span data-ttu-id="52556-475">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-475">**Data type**</span></span> | <span data-ttu-id="52556-476">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="52556-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="52556-477">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-477">**Comments**</span></span> | <span data-ttu-id="52556-478">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="52556-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="52556-479">裝置標記</span><span class="sxs-lookup"><span data-stu-id="52556-479">Device tags</span></span>

<span data-ttu-id="52556-480">指定標記名稱及其值。</span><span class="sxs-lookup"><span data-stu-id="52556-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="52556-481">GROUP 標記，以指定的值標記裝置。</span><span class="sxs-lookup"><span data-stu-id="52556-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="52556-482">標記會反映在入口網站的 [裝置] 頁面底下，可用於篩選和群組裝置。</span><span class="sxs-lookup"><span data-stu-id="52556-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="52556-483">區段</span><span class="sxs-lookup"><span data-stu-id="52556-483">Section</span></span>|<span data-ttu-id="52556-484">值</span><span class="sxs-lookup"><span data-stu-id="52556-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-485">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-486">**Key**</span></span> | <span data-ttu-id="52556-487">標籤</span><span class="sxs-lookup"><span data-stu-id="52556-487">tags</span></span> |
| <span data-ttu-id="52556-488">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-488">**Data type**</span></span> | <span data-ttu-id="52556-489">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="52556-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="52556-490">**Comments**</span><span class="sxs-lookup"><span data-stu-id="52556-490">**Comments**</span></span> | <span data-ttu-id="52556-491">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="52556-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="52556-492">標記類型</span><span class="sxs-lookup"><span data-stu-id="52556-492">Type of tag</span></span>

<span data-ttu-id="52556-493">會指定標記的類型</span><span class="sxs-lookup"><span data-stu-id="52556-493">Specifies the type of tag</span></span>

|<span data-ttu-id="52556-494">區段</span><span class="sxs-lookup"><span data-stu-id="52556-494">Section</span></span>|<span data-ttu-id="52556-495">值</span><span class="sxs-lookup"><span data-stu-id="52556-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-496">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-497">**Key**</span></span> | <span data-ttu-id="52556-498">機碼</span><span class="sxs-lookup"><span data-stu-id="52556-498">key</span></span> |
| <span data-ttu-id="52556-499">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-499">**Data type**</span></span> | <span data-ttu-id="52556-500">字串</span><span class="sxs-lookup"><span data-stu-id="52556-500">String</span></span> |
| <span data-ttu-id="52556-501">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="52556-502">標記值</span><span class="sxs-lookup"><span data-stu-id="52556-502">Value of tag</span></span>

<span data-ttu-id="52556-503">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="52556-503">Specifies the value of tag</span></span>

|<span data-ttu-id="52556-504">區段</span><span class="sxs-lookup"><span data-stu-id="52556-504">Section</span></span>|<span data-ttu-id="52556-505">值</span><span class="sxs-lookup"><span data-stu-id="52556-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="52556-506">**網域**</span><span class="sxs-lookup"><span data-stu-id="52556-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="52556-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="52556-507">**Key**</span></span> | <span data-ttu-id="52556-508">數值</span><span class="sxs-lookup"><span data-stu-id="52556-508">value</span></span> |
| <span data-ttu-id="52556-509">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="52556-509">**Data type**</span></span> | <span data-ttu-id="52556-510">字串</span><span class="sxs-lookup"><span data-stu-id="52556-510">String</span></span> |
| <span data-ttu-id="52556-511">**可能值**</span><span class="sxs-lookup"><span data-stu-id="52556-511">**Possible values**</span></span> | <span data-ttu-id="52556-512">任何字串</span><span class="sxs-lookup"><span data-stu-id="52556-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="52556-513">每個 tag 類型只能設定一個值。</span><span class="sxs-lookup"><span data-stu-id="52556-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="52556-514">標記的類型是唯一的，不應該在相同的設定檔中重複。</span><span class="sxs-lookup"><span data-stu-id="52556-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="52556-515">建議的設定設定檔</span><span class="sxs-lookup"><span data-stu-id="52556-515">Recommended configuration profile</span></span>

<span data-ttu-id="52556-516">若要開始使用，我們建議您的企業進行下列設定，以利用 Microsoft Defender for Endpoint 所提供的所有保護功能。</span><span class="sxs-lookup"><span data-stu-id="52556-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="52556-517">下列設定設定檔 (，如果 JAMF，可以上傳至自訂設定設定檔的屬性清單) 會：</span><span class="sxs-lookup"><span data-stu-id="52556-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="52556-518">啟用 (RTP) 的即時保護</span><span class="sxs-lookup"><span data-stu-id="52556-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="52556-519">指定如何處理下列威脅類型：</span><span class="sxs-lookup"><span data-stu-id="52556-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="52556-520">封鎖 **(PUA) 可能有害的應用程式**</span><span class="sxs-lookup"><span data-stu-id="52556-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="52556-521">將具有高壓縮率) 的封存 **bombs (檔案** 審核至 Microsoft Defender for Endpoint 記錄檔</span><span class="sxs-lookup"><span data-stu-id="52556-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="52556-522">啟用自動安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="52556-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="52556-523">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="52556-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="52556-524">啟用自動範例提交</span><span class="sxs-lookup"><span data-stu-id="52556-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="52556-525">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="52556-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="52556-526">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="52556-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="52556-527">完整設定檔範例</span><span class="sxs-lookup"><span data-stu-id="52556-527">Full configuration profile example</span></span>

<span data-ttu-id="52556-528">下列範本包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要在 macOS 上進一步控制端點的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="52556-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="52556-529">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="52556-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="52556-530">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="52556-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="52556-531">屬性清單驗證</span><span class="sxs-lookup"><span data-stu-id="52556-531">Property list validation</span></span>

<span data-ttu-id="52556-532">屬性清單必須是有效的 *plist* 檔案。</span><span class="sxs-lookup"><span data-stu-id="52556-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="52556-533">您可以執行下列動作來檢查：</span><span class="sxs-lookup"><span data-stu-id="52556-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="52556-534">如果檔案的格式良好，上述命令會輸出並傳回 `OK` 的退出程式碼 `0` 。</span><span class="sxs-lookup"><span data-stu-id="52556-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="52556-535">否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。</span><span class="sxs-lookup"><span data-stu-id="52556-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="52556-536">設定設定檔部署</span><span class="sxs-lookup"><span data-stu-id="52556-536">Configuration profile deployment</span></span>

<span data-ttu-id="52556-537">在您為企業建立設定檔之後，您可以透過企業使用的管理主控台來部署它。</span><span class="sxs-lookup"><span data-stu-id="52556-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="52556-538">下列各節提供如何使用 JAMF 和 Intune 部署此設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="52556-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="52556-539">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="52556-539">JAMF deployment</span></span>

<span data-ttu-id="52556-540">從 JAMF 主控台，開啟 [**電腦** 設定配置  >  **檔**]，流覽至您想要使用的設定設定檔，然後選取 [**自訂設定**]。</span><span class="sxs-lookup"><span data-stu-id="52556-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="52556-541">建立具有 `com.microsoft.wdav` 偏好的網域的專案，並上傳先前產生的 *plist* 。</span><span class="sxs-lookup"><span data-stu-id="52556-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="52556-542">您必須輸入正確的喜好網域 (`com.microsoft.wdav`) ; 否則，Microsoft Defender For Endpoint 將不會識別首選項。</span><span class="sxs-lookup"><span data-stu-id="52556-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="52556-543">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="52556-543">Intune deployment</span></span>

1. <span data-ttu-id="52556-544">開啟 [**管理**  >  **裝置** 設定]。</span><span class="sxs-lookup"><span data-stu-id="52556-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="52556-545">選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="52556-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="52556-546">選擇設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="52556-546">Choose a name for the profile.</span></span> <span data-ttu-id="52556-547">將 **平臺 = macOS** 變更為 **Profile type = Custom**。</span><span class="sxs-lookup"><span data-stu-id="52556-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="52556-548">選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="52556-548">Select Configure.</span></span>

3. <span data-ttu-id="52556-549">儲存先前產生的 plist `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="52556-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="52556-550">輸入 `com.microsoft.wdav` 為 **自訂設定設定檔名稱**。</span><span class="sxs-lookup"><span data-stu-id="52556-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="52556-551">開啟設定設定檔，並上傳 `com.microsoft.wdav.xml` 檔。</span><span class="sxs-lookup"><span data-stu-id="52556-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="52556-552"> (此檔案是在步驟3中建立。 ) </span><span class="sxs-lookup"><span data-stu-id="52556-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="52556-553">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="52556-553">Select **OK**.</span></span>

7. <span data-ttu-id="52556-554">選取 [**管理**  >  **指派**]。</span><span class="sxs-lookup"><span data-stu-id="52556-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="52556-555">在 [ **包含** ] 索引標籤中，選取 [ **指派給所有使用者 & 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="52556-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="52556-556">您必須輸入正確的自訂設定檔名稱;否則，Microsoft Defender for Endpoint 將不會識別這些喜好設定。</span><span class="sxs-lookup"><span data-stu-id="52556-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="52556-557">資源</span><span class="sxs-lookup"><span data-stu-id="52556-557">Resources</span></span>

- [<span data-ttu-id="52556-558">組態設定檔參照 (Apple 開發人員文件)</span><span class="sxs-lookup"><span data-stu-id="52556-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
