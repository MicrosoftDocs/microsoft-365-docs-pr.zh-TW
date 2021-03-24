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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060708"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="57a8b-104">設定 Mac 的 Microsoft Defender 端點偏好設定</span><span class="sxs-lookup"><span data-stu-id="57a8b-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="57a8b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="57a8b-105">**Applies to:**</span></span>

- [<span data-ttu-id="57a8b-106">Mac 版端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="57a8b-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="57a8b-107">本文包含如何針對企業組織中的 Mac 設定 Microsoft Defender for Mac 的首選項的指示。</span><span class="sxs-lookup"><span data-stu-id="57a8b-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="57a8b-108">若要使用命令列介面設定 Microsoft Defender for Mac 的端點，請參閱 [Resources](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="57a8b-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="57a8b-109">摘要</span><span class="sxs-lookup"><span data-stu-id="57a8b-109">Summary</span></span>

<span data-ttu-id="57a8b-110">在企業組織中，可透過使用其中一種管理工具部署的設定檔來管理 Microsoft Defender for Mac 的端點。</span><span class="sxs-lookup"><span data-stu-id="57a8b-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="57a8b-111">安全作業小組所管理的喜好設定優先順序高於裝置上本機設定的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="57a8b-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="57a8b-112">變更透過設定設定檔設定的喜好設定時，需要提升許可權，且不需要系統管理許可權的使用者才能使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="57a8b-113">本文說明設定檔的結構，包含您可以用來開始使用的建議設定檔，並提供如何部署設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="57a8b-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="57a8b-114">設定設定檔結構</span><span class="sxs-lookup"><span data-stu-id="57a8b-114">Configuration profile structure</span></span>

<span data-ttu-id="57a8b-115">設定設定檔是由按鍵 (所識別之專案所識別的 *plist* 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。</span><span class="sxs-lookup"><span data-stu-id="57a8b-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="57a8b-116">值既可以是簡單的 (例如數值) 或複雜，例如首選項的嵌套清單。</span><span class="sxs-lookup"><span data-stu-id="57a8b-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="57a8b-117">設定設定檔的版面配置取決於您所使用的管理主控台。</span><span class="sxs-lookup"><span data-stu-id="57a8b-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="57a8b-118">下列各節包含 JAMF 及 Intune 之設定檔的範例。</span><span class="sxs-lookup"><span data-stu-id="57a8b-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="57a8b-119">設定設定檔的最上層包括 Microsoft Defender for Endpoint 之子領域的產品範圍偏好設定和專案，在下一節將詳細說明。</span><span class="sxs-lookup"><span data-stu-id="57a8b-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="57a8b-120">防病毒引擎偏好設定</span><span class="sxs-lookup"><span data-stu-id="57a8b-120">Antivirus engine preferences</span></span>

<span data-ttu-id="57a8b-121">設定設定檔的 [ *antivirusEngine* ] 區段是用來管理 Microsoft Defender for Endpoint 之防病毒元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="57a8b-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-122">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-123">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-123">**Key**</span></span> | <span data-ttu-id="57a8b-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="57a8b-124">antivirusEngine</span></span> |
| <span data-ttu-id="57a8b-125">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-125">**Data type**</span></span> | <span data-ttu-id="57a8b-126">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="57a8b-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="57a8b-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-127">**Comments**</span></span> | <span data-ttu-id="57a8b-128">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="57a8b-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="57a8b-129">啟用/停用即時保護</span><span class="sxs-lookup"><span data-stu-id="57a8b-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="57a8b-130">指定是否要啟用即時保護，以在存取檔時進行掃描。</span><span class="sxs-lookup"><span data-stu-id="57a8b-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-131">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-132">**Key**</span></span> | <span data-ttu-id="57a8b-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="57a8b-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="57a8b-134">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-134">**Data type**</span></span> | <span data-ttu-id="57a8b-135">布林值</span><span class="sxs-lookup"><span data-stu-id="57a8b-135">Boolean</span></span> |
| <span data-ttu-id="57a8b-136">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-136">**Possible values**</span></span> | <span data-ttu-id="57a8b-137">true (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-137">true (default)</span></span> <br/> <span data-ttu-id="57a8b-138">假</span><span class="sxs-lookup"><span data-stu-id="57a8b-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="57a8b-139">啟用/停用被動模式</span><span class="sxs-lookup"><span data-stu-id="57a8b-139">Enable / disable passive mode</span></span>

<span data-ttu-id="57a8b-140">指定防病毒引擎是否以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="57a8b-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="57a8b-141">被動式模式的含義如下：</span><span class="sxs-lookup"><span data-stu-id="57a8b-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="57a8b-142">已關閉即時保護</span><span class="sxs-lookup"><span data-stu-id="57a8b-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="57a8b-143">已開啟隨選掃描</span><span class="sxs-lookup"><span data-stu-id="57a8b-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="57a8b-144">關閉自動威脅修復功能</span><span class="sxs-lookup"><span data-stu-id="57a8b-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="57a8b-145">已開啟安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="57a8b-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="57a8b-146">隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="57a8b-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-147">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-148">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-148">**Key**</span></span> | <span data-ttu-id="57a8b-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="57a8b-149">passiveMode</span></span> |
| <span data-ttu-id="57a8b-150">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-150">**Data type**</span></span> | <span data-ttu-id="57a8b-151">布林值</span><span class="sxs-lookup"><span data-stu-id="57a8b-151">Boolean</span></span> |
| <span data-ttu-id="57a8b-152">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-152">**Possible values**</span></span> | <span data-ttu-id="57a8b-153">false (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-153">false (default)</span></span> <br/> <span data-ttu-id="57a8b-154">真</span><span class="sxs-lookup"><span data-stu-id="57a8b-154">true</span></span> |
| <span data-ttu-id="57a8b-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-155">**Comments**</span></span> | <span data-ttu-id="57a8b-156">可在 Microsoft Defender for Endpoint 版本100.67.60 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="57a8b-157">排除合併原則</span><span class="sxs-lookup"><span data-stu-id="57a8b-157">Exclusion merge policy</span></span>

<span data-ttu-id="57a8b-158">指定排除的合併原則。</span><span class="sxs-lookup"><span data-stu-id="57a8b-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="57a8b-159">這可以是管理員定義和使用者定義排除 (的組合， `merge`) 或僅限系統管理員定義的排除 (`admin_only`) 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="57a8b-160">您可以使用此設定來限制本機使用者定義自己的排除專案。</span><span class="sxs-lookup"><span data-stu-id="57a8b-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-161">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-162">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-162">**Key**</span></span> | <span data-ttu-id="57a8b-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="57a8b-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="57a8b-164">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-164">**Data type**</span></span> | <span data-ttu-id="57a8b-165">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-165">String</span></span> |
| <span data-ttu-id="57a8b-166">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-166">**Possible values**</span></span> | <span data-ttu-id="57a8b-167">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="57a8b-167">merge (default)</span></span> <br/> <span data-ttu-id="57a8b-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="57a8b-168">admin_only</span></span> |
| <span data-ttu-id="57a8b-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-169">**Comments**</span></span> | <span data-ttu-id="57a8b-170">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="57a8b-171">掃描排除</span><span class="sxs-lookup"><span data-stu-id="57a8b-171">Scan exclusions</span></span>

<span data-ttu-id="57a8b-172">指定排除在掃描之外的實體。</span><span class="sxs-lookup"><span data-stu-id="57a8b-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="57a8b-173">您可以使用完整路徑、副檔名或檔案名來指定排除。</span><span class="sxs-lookup"><span data-stu-id="57a8b-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-174">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-175">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-175">**Key**</span></span> | <span data-ttu-id="57a8b-176">排除</span><span class="sxs-lookup"><span data-stu-id="57a8b-176">exclusions</span></span> |
| <span data-ttu-id="57a8b-177">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-177">**Data type**</span></span> | <span data-ttu-id="57a8b-178">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="57a8b-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="57a8b-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-179">**Comments**</span></span> | <span data-ttu-id="57a8b-180">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="57a8b-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="57a8b-181">排除的類型</span><span class="sxs-lookup"><span data-stu-id="57a8b-181">Type of exclusion</span></span>

<span data-ttu-id="57a8b-182">指定 [依類型掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-183">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-184">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-184">**Key**</span></span> | <span data-ttu-id="57a8b-185">$type</span><span class="sxs-lookup"><span data-stu-id="57a8b-185">$type</span></span> |
| <span data-ttu-id="57a8b-186">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-186">**Data type**</span></span> | <span data-ttu-id="57a8b-187">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-187">String</span></span> |
| <span data-ttu-id="57a8b-188">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-188">**Possible values**</span></span> | <span data-ttu-id="57a8b-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="57a8b-189">excludedPath</span></span> <br/> <span data-ttu-id="57a8b-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="57a8b-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="57a8b-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="57a8b-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="57a8b-192">排除內容的路徑</span><span class="sxs-lookup"><span data-stu-id="57a8b-192">Path to excluded content</span></span>

<span data-ttu-id="57a8b-193">指定以完整檔案路徑掃描排除的內容。</span><span class="sxs-lookup"><span data-stu-id="57a8b-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-194">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-195">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-195">**Key**</span></span> | <span data-ttu-id="57a8b-196">路徑</span><span class="sxs-lookup"><span data-stu-id="57a8b-196">path</span></span> |
| <span data-ttu-id="57a8b-197">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-197">**Data type**</span></span> | <span data-ttu-id="57a8b-198">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-198">String</span></span> |
| <span data-ttu-id="57a8b-199">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-199">**Possible values**</span></span> | <span data-ttu-id="57a8b-200">有效路徑</span><span class="sxs-lookup"><span data-stu-id="57a8b-200">valid paths</span></span> |
| <span data-ttu-id="57a8b-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-201">**Comments**</span></span> | <span data-ttu-id="57a8b-202">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="57a8b-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="57a8b-203"> (檔/目錄的路徑類型) </span><span class="sxs-lookup"><span data-stu-id="57a8b-203">Path type (file / directory)</span></span>

<span data-ttu-id="57a8b-204">指出 *path* 屬性參照的是檔案或目錄。</span><span class="sxs-lookup"><span data-stu-id="57a8b-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="57a8b-205">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-206">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-206">**Key**</span></span> | <span data-ttu-id="57a8b-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="57a8b-207">isDirectory</span></span> |
| <span data-ttu-id="57a8b-208">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-208">**Data type**</span></span> | <span data-ttu-id="57a8b-209">布林值</span><span class="sxs-lookup"><span data-stu-id="57a8b-209">Boolean</span></span> |
| <span data-ttu-id="57a8b-210">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-210">**Possible values**</span></span> | <span data-ttu-id="57a8b-211">false (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-211">false (default)</span></span> <br/> <span data-ttu-id="57a8b-212">真</span><span class="sxs-lookup"><span data-stu-id="57a8b-212">true</span></span> |
| <span data-ttu-id="57a8b-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-213">**Comments**</span></span> | <span data-ttu-id="57a8b-214">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="57a8b-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="57a8b-215">從掃描排除的副檔名</span><span class="sxs-lookup"><span data-stu-id="57a8b-215">File extension excluded from the scan</span></span>

<span data-ttu-id="57a8b-216">指定 [依副檔名掃描排除的內容]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-217">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-218">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-218">**Key**</span></span> | <span data-ttu-id="57a8b-219">擴展</span><span class="sxs-lookup"><span data-stu-id="57a8b-219">extension</span></span> |
| <span data-ttu-id="57a8b-220">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-220">**Data type**</span></span> | <span data-ttu-id="57a8b-221">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-221">String</span></span> |
| <span data-ttu-id="57a8b-222">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-222">**Possible values**</span></span> | <span data-ttu-id="57a8b-223">有效的副檔名</span><span class="sxs-lookup"><span data-stu-id="57a8b-223">valid file extensions</span></span> |
| <span data-ttu-id="57a8b-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-224">**Comments**</span></span> | <span data-ttu-id="57a8b-225">僅適用于 *excludedFileExtension* *$type*</span><span class="sxs-lookup"><span data-stu-id="57a8b-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="57a8b-226">從掃描排除的處理常式</span><span class="sxs-lookup"><span data-stu-id="57a8b-226">Process excluded from the scan</span></span>

<span data-ttu-id="57a8b-227">指定從掃描排除所有檔案活動的處理常式。</span><span class="sxs-lookup"><span data-stu-id="57a8b-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="57a8b-228">您可以透過名稱指定程式 (例如 `cat`) 或完整路徑 (例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-229">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-230">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-230">**Key**</span></span> | <span data-ttu-id="57a8b-231">name</span><span class="sxs-lookup"><span data-stu-id="57a8b-231">name</span></span> |
| <span data-ttu-id="57a8b-232">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-232">**Data type**</span></span> | <span data-ttu-id="57a8b-233">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-233">String</span></span> |
| <span data-ttu-id="57a8b-234">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-234">**Possible values**</span></span> | <span data-ttu-id="57a8b-235">任何字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-235">any string</span></span> |
| <span data-ttu-id="57a8b-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-236">**Comments**</span></span> | <span data-ttu-id="57a8b-237">僅適用于 *excludedFileName* *$type*</span><span class="sxs-lookup"><span data-stu-id="57a8b-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="57a8b-238">允許的威脅</span><span class="sxs-lookup"><span data-stu-id="57a8b-238">Allowed threats</span></span>

<span data-ttu-id="57a8b-239">依名稱指定不會被 Defender for Mac 的 Endpoint 封鎖的威脅。</span><span class="sxs-lookup"><span data-stu-id="57a8b-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="57a8b-240">這些威脅都會允許執行。</span><span class="sxs-lookup"><span data-stu-id="57a8b-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-241">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-242">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-242">**Key**</span></span> | <span data-ttu-id="57a8b-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="57a8b-243">allowedThreats</span></span> |
| <span data-ttu-id="57a8b-244">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-244">**Data type**</span></span> | <span data-ttu-id="57a8b-245">字串陣列</span><span class="sxs-lookup"><span data-stu-id="57a8b-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="57a8b-246">不允許的威脅動作</span><span class="sxs-lookup"><span data-stu-id="57a8b-246">Disallowed threat actions</span></span>

<span data-ttu-id="57a8b-247">限制偵測到威脅時，裝置的本機使用者可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="57a8b-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="57a8b-248">在此清單中包含的動作不會顯示在使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="57a8b-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-249">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-250">**Key**</span></span> | <span data-ttu-id="57a8b-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="57a8b-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="57a8b-252">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-252">**Data type**</span></span> | <span data-ttu-id="57a8b-253">字串陣列</span><span class="sxs-lookup"><span data-stu-id="57a8b-253">Array of strings</span></span> |
| <span data-ttu-id="57a8b-254">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-254">**Possible values**</span></span> | <span data-ttu-id="57a8b-255">允許 (限制使用者允許威脅) </span><span class="sxs-lookup"><span data-stu-id="57a8b-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="57a8b-256">restore (會限制使用者從隔離區還原威脅) </span><span class="sxs-lookup"><span data-stu-id="57a8b-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="57a8b-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-257">**Comments**</span></span> | <span data-ttu-id="57a8b-258">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="57a8b-259">威脅類型設定</span><span class="sxs-lookup"><span data-stu-id="57a8b-259">Threat type settings</span></span>

<span data-ttu-id="57a8b-260">指定 Microsoft Defender for Mac 的終結點處理特定威脅類型的方式。</span><span class="sxs-lookup"><span data-stu-id="57a8b-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-261">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-262">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-262">**Key**</span></span> | <span data-ttu-id="57a8b-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="57a8b-263">threatTypeSettings</span></span> |
| <span data-ttu-id="57a8b-264">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-264">**Data type**</span></span> | <span data-ttu-id="57a8b-265">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="57a8b-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="57a8b-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-266">**Comments**</span></span> | <span data-ttu-id="57a8b-267">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="57a8b-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="57a8b-268">威脅類型</span><span class="sxs-lookup"><span data-stu-id="57a8b-268">Threat type</span></span>

<span data-ttu-id="57a8b-269">指定威脅類型。</span><span class="sxs-lookup"><span data-stu-id="57a8b-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-270">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-271">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-271">**Key**</span></span> | <span data-ttu-id="57a8b-272">機碼</span><span class="sxs-lookup"><span data-stu-id="57a8b-272">key</span></span> |
| <span data-ttu-id="57a8b-273">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-273">**Data type**</span></span> | <span data-ttu-id="57a8b-274">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-274">String</span></span> |
| <span data-ttu-id="57a8b-275">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-275">**Possible values**</span></span> | <span data-ttu-id="57a8b-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="57a8b-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="57a8b-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="57a8b-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="57a8b-278">要採取的動作</span><span class="sxs-lookup"><span data-stu-id="57a8b-278">Action to take</span></span>

<span data-ttu-id="57a8b-279">指定當偵測到上述區段中所指定類型的威脅時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="57a8b-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="57a8b-280">請從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="57a8b-280">Choose from the following options:</span></span>

- <span data-ttu-id="57a8b-281">**Audit**：您的裝置不會受到這種威脅類型的保護，但是會記錄有關威脅的專案。</span><span class="sxs-lookup"><span data-stu-id="57a8b-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="57a8b-282">**封鎖**：您的裝置會受到此威脅類型的保護，而且您會收到使用者介面及安全性主控台的通知。</span><span class="sxs-lookup"><span data-stu-id="57a8b-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="57a8b-283">**Off**：您的裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="57a8b-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-284">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-285">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-285">**Key**</span></span> | <span data-ttu-id="57a8b-286">數值</span><span class="sxs-lookup"><span data-stu-id="57a8b-286">value</span></span> |
| <span data-ttu-id="57a8b-287">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-287">**Data type**</span></span> | <span data-ttu-id="57a8b-288">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-288">String</span></span> |
| <span data-ttu-id="57a8b-289">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-289">**Possible values**</span></span> | <span data-ttu-id="57a8b-290">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-290">audit (default)</span></span> <br/> <span data-ttu-id="57a8b-291">塊</span><span class="sxs-lookup"><span data-stu-id="57a8b-291">block</span></span> <br/> <span data-ttu-id="57a8b-292">遠離</span><span class="sxs-lookup"><span data-stu-id="57a8b-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="57a8b-293">威脅類型設定合併原則</span><span class="sxs-lookup"><span data-stu-id="57a8b-293">Threat type settings merge policy</span></span>

<span data-ttu-id="57a8b-294">指定威脅類型設定的合併原則。</span><span class="sxs-lookup"><span data-stu-id="57a8b-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="57a8b-295">這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="57a8b-296">此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。</span><span class="sxs-lookup"><span data-stu-id="57a8b-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-297">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-298">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-298">**Key**</span></span> | <span data-ttu-id="57a8b-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="57a8b-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="57a8b-300">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-300">**Data type**</span></span> | <span data-ttu-id="57a8b-301">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-301">String</span></span> |
| <span data-ttu-id="57a8b-302">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-302">**Possible values**</span></span> | <span data-ttu-id="57a8b-303">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="57a8b-303">merge (default)</span></span> <br/> <span data-ttu-id="57a8b-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="57a8b-304">admin_only</span></span> |
| <span data-ttu-id="57a8b-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-305">**Comments**</span></span> | <span data-ttu-id="57a8b-306">可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="57a8b-307">防病毒掃描記錄保留 (天數) </span><span class="sxs-lookup"><span data-stu-id="57a8b-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="57a8b-308">指定在裝置上的掃描歷程記錄中保留結果的天數。</span><span class="sxs-lookup"><span data-stu-id="57a8b-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="57a8b-309">舊的掃描結果會從歷史記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="57a8b-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="57a8b-310">也會從磁片中移除的舊隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="57a8b-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-311">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-312">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-312">**Key**</span></span> | <span data-ttu-id="57a8b-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="57a8b-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="57a8b-314">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-314">**Data type**</span></span> | <span data-ttu-id="57a8b-315">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-315">String</span></span> |
| <span data-ttu-id="57a8b-316">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-316">**Possible values**</span></span> | <span data-ttu-id="57a8b-317">90 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-317">90 (default).</span></span> <span data-ttu-id="57a8b-318">允許的值介於1天到180天。</span><span class="sxs-lookup"><span data-stu-id="57a8b-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="57a8b-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-319">**Comments**</span></span> | <span data-ttu-id="57a8b-320">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="57a8b-321">防病毒掃描歷程記錄中的專案數上限</span><span class="sxs-lookup"><span data-stu-id="57a8b-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="57a8b-322">指定要保留在掃描記錄中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="57a8b-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="57a8b-323">專案包括過去執行的所有按需掃描及所有防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="57a8b-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-324">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-325">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-325">**Key**</span></span> | <span data-ttu-id="57a8b-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="57a8b-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="57a8b-327">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-327">**Data type**</span></span> | <span data-ttu-id="57a8b-328">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-328">String</span></span> |
| <span data-ttu-id="57a8b-329">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-329">**Possible values**</span></span> | <span data-ttu-id="57a8b-330">10000 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-330">10000 (default).</span></span> <span data-ttu-id="57a8b-331">允許的值是從5000專案到15000專案。</span><span class="sxs-lookup"><span data-stu-id="57a8b-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="57a8b-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-332">**Comments**</span></span> | <span data-ttu-id="57a8b-333">可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="57a8b-334">雲端提供的保護偏好設定</span><span class="sxs-lookup"><span data-stu-id="57a8b-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="57a8b-335">為 Mac 設定 Microsoft Defender for Endpoint 的雲端驅動保護功能。</span><span class="sxs-lookup"><span data-stu-id="57a8b-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-336">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-337">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-337">**Key**</span></span> | <span data-ttu-id="57a8b-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="57a8b-338">cloudService</span></span> |
| <span data-ttu-id="57a8b-339">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-339">**Data type**</span></span> | <span data-ttu-id="57a8b-340">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="57a8b-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="57a8b-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-341">**Comments**</span></span> | <span data-ttu-id="57a8b-342">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="57a8b-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="57a8b-343">啟用/停用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="57a8b-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="57a8b-344">指定是否要對裝置啟用雲端提供保護。</span><span class="sxs-lookup"><span data-stu-id="57a8b-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="57a8b-345">若要改善服務的安全性，建議您保持此功能開啟。</span><span class="sxs-lookup"><span data-stu-id="57a8b-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-346">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-347">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-347">**Key**</span></span> | <span data-ttu-id="57a8b-348">啟用</span><span class="sxs-lookup"><span data-stu-id="57a8b-348">enabled</span></span> |
| <span data-ttu-id="57a8b-349">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-349">**Data type**</span></span> | <span data-ttu-id="57a8b-350">布林值</span><span class="sxs-lookup"><span data-stu-id="57a8b-350">Boolean</span></span> |
| <span data-ttu-id="57a8b-351">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-351">**Possible values**</span></span> | <span data-ttu-id="57a8b-352">true (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-352">true (default)</span></span> <br/> <span data-ttu-id="57a8b-353">假</span><span class="sxs-lookup"><span data-stu-id="57a8b-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="57a8b-354">診斷集合層級</span><span class="sxs-lookup"><span data-stu-id="57a8b-354">Diagnostic collection level</span></span>

<span data-ttu-id="57a8b-355">診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="57a8b-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="57a8b-356">此設定會決定 Microsoft Defender for Microsoft Defender 所傳送的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="57a8b-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-357">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-358">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-358">**Key**</span></span> | <span data-ttu-id="57a8b-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="57a8b-359">diagnosticLevel</span></span> |
| <span data-ttu-id="57a8b-360">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-360">**Data type**</span></span> | <span data-ttu-id="57a8b-361">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-361">String</span></span> |
| <span data-ttu-id="57a8b-362">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-362">**Possible values**</span></span> | <span data-ttu-id="57a8b-363">選用 (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-363">optional (default)</span></span> <br/> <span data-ttu-id="57a8b-364">必要</span><span class="sxs-lookup"><span data-stu-id="57a8b-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="57a8b-365">啟用/停用自動範例報送</span><span class="sxs-lookup"><span data-stu-id="57a8b-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="57a8b-366">會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。</span><span class="sxs-lookup"><span data-stu-id="57a8b-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="57a8b-367">如果提交的檔案可能包含個人資訊，系統會提示您。</span><span class="sxs-lookup"><span data-stu-id="57a8b-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-368">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-369">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-369">**Key**</span></span> | <span data-ttu-id="57a8b-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="57a8b-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="57a8b-371">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-371">**Data type**</span></span> | <span data-ttu-id="57a8b-372">布林值</span><span class="sxs-lookup"><span data-stu-id="57a8b-372">Boolean</span></span> |
| <span data-ttu-id="57a8b-373">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-373">**Possible values**</span></span> | <span data-ttu-id="57a8b-374">true (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-374">true (default)</span></span> <br/> <span data-ttu-id="57a8b-375">假</span><span class="sxs-lookup"><span data-stu-id="57a8b-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="57a8b-376">啟用/停用自動安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="57a8b-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="57a8b-377">決定是否自動安裝安全性智慧更新：</span><span class="sxs-lookup"><span data-stu-id="57a8b-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-378">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-378">**Key**</span></span> | <span data-ttu-id="57a8b-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="57a8b-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="57a8b-380">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-380">**Data type**</span></span> | <span data-ttu-id="57a8b-381">布林值</span><span class="sxs-lookup"><span data-stu-id="57a8b-381">Boolean</span></span> |
| <span data-ttu-id="57a8b-382">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-382">**Possible values**</span></span> | <span data-ttu-id="57a8b-383">true (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-383">true (default)</span></span> <br/> <span data-ttu-id="57a8b-384">假</span><span class="sxs-lookup"><span data-stu-id="57a8b-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="57a8b-385">使用者介面偏好設定</span><span class="sxs-lookup"><span data-stu-id="57a8b-385">User interface preferences</span></span>

<span data-ttu-id="57a8b-386">管理 Microsoft Defender for Mac 之使用者介面的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="57a8b-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-387">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-388">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-388">**Key**</span></span> | <span data-ttu-id="57a8b-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="57a8b-389">userInterface</span></span> |
| <span data-ttu-id="57a8b-390">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-390">**Data type**</span></span> | <span data-ttu-id="57a8b-391">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="57a8b-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="57a8b-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-392">**Comments**</span></span> | <span data-ttu-id="57a8b-393">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="57a8b-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="57a8b-394">顯示/隱藏狀態功能表圖示</span><span class="sxs-lookup"><span data-stu-id="57a8b-394">Show / hide status menu icon</span></span>

<span data-ttu-id="57a8b-395">指定是否要顯示或隱藏螢幕右上角的 [狀態] 功能表圖示。</span><span class="sxs-lookup"><span data-stu-id="57a8b-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-396">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-397">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-397">**Key**</span></span> | <span data-ttu-id="57a8b-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="57a8b-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="57a8b-399">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-399">**Data type**</span></span> | <span data-ttu-id="57a8b-400">布林值</span><span class="sxs-lookup"><span data-stu-id="57a8b-400">Boolean</span></span> |
| <span data-ttu-id="57a8b-401">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-401">**Possible values**</span></span> | <span data-ttu-id="57a8b-402">false (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-402">false (default)</span></span> <br/> <span data-ttu-id="57a8b-403">真</span><span class="sxs-lookup"><span data-stu-id="57a8b-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="57a8b-404">[顯示/隱藏] 選項以傳送意見反應</span><span class="sxs-lookup"><span data-stu-id="57a8b-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="57a8b-405">指定使用者是否可以前往提交對 Microsoft 的意見反應 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-406">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-407">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-407">**Key**</span></span> | <span data-ttu-id="57a8b-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="57a8b-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="57a8b-409">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-409">**Data type**</span></span> | <span data-ttu-id="57a8b-410">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-410">String</span></span> |
| <span data-ttu-id="57a8b-411">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-411">**Possible values**</span></span> | <span data-ttu-id="57a8b-412">已啟用 (預設) </span><span class="sxs-lookup"><span data-stu-id="57a8b-412">enabled (default)</span></span> <br/> <span data-ttu-id="57a8b-413">禁用</span><span class="sxs-lookup"><span data-stu-id="57a8b-413">disabled</span></span> |
| <span data-ttu-id="57a8b-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-414">**Comments**</span></span> | <span data-ttu-id="57a8b-415">可在 Microsoft Defender for Endpoint 版本101.19.61 或更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="57a8b-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="57a8b-416">端點偵測和回應喜好設定</span><span class="sxs-lookup"><span data-stu-id="57a8b-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="57a8b-417">管理 Mac 之 Microsoft Defender for Endpoint 的端點偵測和回應 (EDR) 元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="57a8b-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-418">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-419">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-419">**Key**</span></span> | <span data-ttu-id="57a8b-420">edr</span><span class="sxs-lookup"><span data-stu-id="57a8b-420">edr</span></span> |
| <span data-ttu-id="57a8b-421">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-421">**Data type**</span></span> | <span data-ttu-id="57a8b-422">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="57a8b-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="57a8b-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-423">**Comments**</span></span> | <span data-ttu-id="57a8b-424">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="57a8b-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="57a8b-425">裝置標記</span><span class="sxs-lookup"><span data-stu-id="57a8b-425">Device tags</span></span>

<span data-ttu-id="57a8b-426">指定標記名稱及其值。</span><span class="sxs-lookup"><span data-stu-id="57a8b-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="57a8b-427">GROUP 標記，以指定的值標記裝置。</span><span class="sxs-lookup"><span data-stu-id="57a8b-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="57a8b-428">標記會反映在入口網站的 [裝置] 頁面底下，可用於篩選和群組裝置。</span><span class="sxs-lookup"><span data-stu-id="57a8b-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-429">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-430">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-430">**Key**</span></span> | <span data-ttu-id="57a8b-431">標籤</span><span class="sxs-lookup"><span data-stu-id="57a8b-431">tags</span></span> |
| <span data-ttu-id="57a8b-432">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-432">**Data type**</span></span> | <span data-ttu-id="57a8b-433">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="57a8b-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="57a8b-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="57a8b-434">**Comments**</span></span> | <span data-ttu-id="57a8b-435">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="57a8b-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="57a8b-436">標記類型</span><span class="sxs-lookup"><span data-stu-id="57a8b-436">Type of tag</span></span>

<span data-ttu-id="57a8b-437">會指定標記的類型</span><span class="sxs-lookup"><span data-stu-id="57a8b-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-438">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-439">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-439">**Key**</span></span> | <span data-ttu-id="57a8b-440">機碼</span><span class="sxs-lookup"><span data-stu-id="57a8b-440">key</span></span> |
| <span data-ttu-id="57a8b-441">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-441">**Data type**</span></span> | <span data-ttu-id="57a8b-442">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-442">String</span></span> |
| <span data-ttu-id="57a8b-443">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="57a8b-444">標記值</span><span class="sxs-lookup"><span data-stu-id="57a8b-444">Value of tag</span></span>

<span data-ttu-id="57a8b-445">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="57a8b-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="57a8b-446">**網域**</span><span class="sxs-lookup"><span data-stu-id="57a8b-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="57a8b-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="57a8b-447">**Key**</span></span> | <span data-ttu-id="57a8b-448">數值</span><span class="sxs-lookup"><span data-stu-id="57a8b-448">value</span></span> |
| <span data-ttu-id="57a8b-449">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="57a8b-449">**Data type**</span></span> | <span data-ttu-id="57a8b-450">字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-450">String</span></span> |
| <span data-ttu-id="57a8b-451">**可能值**</span><span class="sxs-lookup"><span data-stu-id="57a8b-451">**Possible values**</span></span> | <span data-ttu-id="57a8b-452">任何字串</span><span class="sxs-lookup"><span data-stu-id="57a8b-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="57a8b-453">每個 tag 類型只能設定一個值。</span><span class="sxs-lookup"><span data-stu-id="57a8b-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="57a8b-454">標記的類型是唯一的，不應該在相同的設定檔中重複。</span><span class="sxs-lookup"><span data-stu-id="57a8b-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="57a8b-455">建議的設定設定檔</span><span class="sxs-lookup"><span data-stu-id="57a8b-455">Recommended configuration profile</span></span>

<span data-ttu-id="57a8b-456">若要開始使用，我們建議您的企業進行下列設定，以利用 Microsoft Defender for Endpoint 所提供的所有保護功能。</span><span class="sxs-lookup"><span data-stu-id="57a8b-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="57a8b-457">下列設定設定檔 (，如果 JAMF，可以上傳至自訂設定設定檔的屬性清單) 會：</span><span class="sxs-lookup"><span data-stu-id="57a8b-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="57a8b-458">啟用 (RTP) 的即時保護</span><span class="sxs-lookup"><span data-stu-id="57a8b-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="57a8b-459">指定如何處理下列威脅類型：</span><span class="sxs-lookup"><span data-stu-id="57a8b-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="57a8b-460">封鎖 **(PUA) 可能有害的應用程式**</span><span class="sxs-lookup"><span data-stu-id="57a8b-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="57a8b-461">將具有高壓縮率) 的封存 **bombs (檔案** 審核至 Microsoft Defender for Endpoint 記錄檔</span><span class="sxs-lookup"><span data-stu-id="57a8b-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="57a8b-462">啟用自動安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="57a8b-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="57a8b-463">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="57a8b-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="57a8b-464">啟用自動範例提交</span><span class="sxs-lookup"><span data-stu-id="57a8b-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="57a8b-465">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="57a8b-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="57a8b-466">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="57a8b-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="57a8b-467">完整設定檔範例</span><span class="sxs-lookup"><span data-stu-id="57a8b-467">Full configuration profile example</span></span>

<span data-ttu-id="57a8b-468">下列範本包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要更進一步控制 Mac 的 Microsoft Defender 端點。</span><span class="sxs-lookup"><span data-stu-id="57a8b-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="57a8b-469">JAMF 設定檔的屬性清單</span><span class="sxs-lookup"><span data-stu-id="57a8b-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="57a8b-470">Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="57a8b-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="57a8b-471">屬性清單驗證</span><span class="sxs-lookup"><span data-stu-id="57a8b-471">Property list validation</span></span>

<span data-ttu-id="57a8b-472">屬性清單必須是有效的 *plist* 檔案。</span><span class="sxs-lookup"><span data-stu-id="57a8b-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="57a8b-473">您可以執行下列動作來檢查：</span><span class="sxs-lookup"><span data-stu-id="57a8b-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="57a8b-474">如果檔案的格式良好，上述命令會輸出並傳回 `OK` 的退出程式碼 `0` 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="57a8b-475">否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="57a8b-476">設定設定檔部署</span><span class="sxs-lookup"><span data-stu-id="57a8b-476">Configuration profile deployment</span></span>

<span data-ttu-id="57a8b-477">在您為企業建立設定檔之後，您可以透過企業使用的管理主控台來部署它。</span><span class="sxs-lookup"><span data-stu-id="57a8b-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="57a8b-478">下列各節提供如何使用 JAMF 和 Intune 部署此設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="57a8b-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="57a8b-479">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="57a8b-479">JAMF deployment</span></span>

<span data-ttu-id="57a8b-480">從 JAMF 主控台，開啟 [**電腦** 設定配置  >  **檔**]，流覽至您想要使用的設定設定檔，然後選取 [**自訂設定**]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="57a8b-481">建立具有 `com.microsoft.wdav` 偏好的網域的專案，並上傳先前產生的 *plist* 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="57a8b-482">您必須輸入正確的喜好網域 (`com.microsoft.wdav`) ; 否則，Microsoft Defender For Endpoint 將不會識別首選項。</span><span class="sxs-lookup"><span data-stu-id="57a8b-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="57a8b-483">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="57a8b-483">Intune deployment</span></span>

1. <span data-ttu-id="57a8b-484">開啟 [**管理**  >  **裝置** 設定]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="57a8b-485">選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="57a8b-486">選擇設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="57a8b-486">Choose a name for the profile.</span></span> <span data-ttu-id="57a8b-487">將 **平臺 = macOS** 變更為 **Profile type = Custom**。</span><span class="sxs-lookup"><span data-stu-id="57a8b-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="57a8b-488">選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-488">Select Configure.</span></span>

3. <span data-ttu-id="57a8b-489">儲存先前產生的 plist `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="57a8b-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="57a8b-490">輸入 `com.microsoft.wdav` 為 **自訂設定設定檔名稱**。</span><span class="sxs-lookup"><span data-stu-id="57a8b-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="57a8b-491">開啟設定設定檔，並上傳 `com.microsoft.wdav.xml` 檔。</span><span class="sxs-lookup"><span data-stu-id="57a8b-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="57a8b-492"> (此檔案是在步驟3中建立。 ) </span><span class="sxs-lookup"><span data-stu-id="57a8b-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="57a8b-493">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-493">Select **OK**.</span></span>

7. <span data-ttu-id="57a8b-494">選取 [**管理**  >  **指派**]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="57a8b-495">在 [ **包含** ] 索引標籤中，選取 [ **指派給所有使用者 & 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="57a8b-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="57a8b-496">您必須輸入正確的自訂設定檔名稱;否則，Microsoft Defender for Endpoint 將不會識別這些喜好設定。</span><span class="sxs-lookup"><span data-stu-id="57a8b-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="57a8b-497">資源</span><span class="sxs-lookup"><span data-stu-id="57a8b-497">Resources</span></span>

- [<span data-ttu-id="57a8b-498">組態設定檔參照 (Apple 開發人員文件)</span><span class="sxs-lookup"><span data-stu-id="57a8b-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
