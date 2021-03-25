---
title: 設定 Microsoft Defender ATP 的首選項（適用于 Linux）
ms.reviewer: ''
description: 說明如何在企業中為 Linux 設定 Microsoft Defender ATP。
keywords: microsoft，defender，atp，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
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
ms.openlocfilehash: ed28d3b5b7bafaea2d72b7a8c45f66bf69033bc2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187790"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4b0a9-104">為 Linux 設定 Microsoft Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="4b0a9-104">Set preferences for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4b0a9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-105">**Applies to:**</span></span>
- [<span data-ttu-id="4b0a9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4b0a9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4b0a9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b0a9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4b0a9-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4b0a9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4b0a9-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="4b0a9-110">本主題包含如何在企業環境中設定適用于 Linux 之 Defender 的 Defender 偏好設定的指示。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="4b0a9-111">如果您想要從命令列在裝置上設定產品，請參閱 [Resources](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="4b0a9-112">在企業環境中，可透過設定設定檔管理適用于 Linux 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="4b0a9-113">此設定檔是從您選擇的管理工具部署。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="4b0a9-114">由企業管理的喜好設定會優先于裝置上的本機設定。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="4b0a9-115">換句話說，您企業中的使用者無法變更透過此設定檔設定的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="4b0a9-116">本文說明此設定檔的結構 (，包括可供您開始使用的建議設定檔) 及如何部署設定檔的指示。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="4b0a9-117">設定設定檔結構</span><span class="sxs-lookup"><span data-stu-id="4b0a9-117">Configuration profile structure</span></span>

<span data-ttu-id="4b0a9-118">設定設定檔是由按鍵 (所識別的專案所組成的一個 json 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="4b0a9-119">值可以是簡單的，例如數值或複雜，例如首選項的嵌套清單。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="4b0a9-120">一般來說，您會使用設定管理工具將名稱中的檔案推入 ```mdatp_managed.json``` 該位置 ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="4b0a9-121">設定設定檔的最上層包含產品的子領域首選項及專案，在下一節將詳細說明。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="4b0a9-122">防病毒引擎偏好設定</span><span class="sxs-lookup"><span data-stu-id="4b0a9-122">Antivirus engine preferences</span></span>

<span data-ttu-id="4b0a9-123">設定設定檔的 [ *antivirusEngine* ] 區段是用來管理產品之防病毒元件的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-124">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-124">**Key**</span></span> | <span data-ttu-id="4b0a9-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="4b0a9-125">antivirusEngine</span></span> |
| <span data-ttu-id="4b0a9-126">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-126">**Data type**</span></span> | <span data-ttu-id="4b0a9-127">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="4b0a9-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-128">**Comments**</span></span> | <span data-ttu-id="4b0a9-129">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-129">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="4b0a9-130">啟用/停用即時保護</span><span class="sxs-lookup"><span data-stu-id="4b0a9-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="4b0a9-131">會決定在啟用或未啟用) 時，是否即時保護 (掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-132">**Key**</span></span> | <span data-ttu-id="4b0a9-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="4b0a9-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="4b0a9-134">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-134">**Data type**</span></span> | <span data-ttu-id="4b0a9-135">布林值</span><span class="sxs-lookup"><span data-stu-id="4b0a9-135">Boolean</span></span> |
| <span data-ttu-id="4b0a9-136">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-136">**Possible values**</span></span> | <span data-ttu-id="4b0a9-137">true (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-137">true (default)</span></span> <br/> <span data-ttu-id="4b0a9-138">假</span><span class="sxs-lookup"><span data-stu-id="4b0a9-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="4b0a9-139">啟用/停用被動模式</span><span class="sxs-lookup"><span data-stu-id="4b0a9-139">Enable / disable passive mode</span></span>

<span data-ttu-id="4b0a9-140">決定防病毒引擎是否以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="4b0a9-141">在被動模式：</span><span class="sxs-lookup"><span data-stu-id="4b0a9-141">In passive mode:</span></span>
- <span data-ttu-id="4b0a9-142">已關閉即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="4b0a9-143">已開啟隨選掃描。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="4b0a9-144">關閉自動威脅修復功能。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="4b0a9-145">已開啟安全性智慧更新。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="4b0a9-146">[狀態] 功能表圖示已隱藏。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-147">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-147">**Key**</span></span> | <span data-ttu-id="4b0a9-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="4b0a9-148">passiveMode</span></span> |
| <span data-ttu-id="4b0a9-149">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-149">**Data type**</span></span> | <span data-ttu-id="4b0a9-150">布林值</span><span class="sxs-lookup"><span data-stu-id="4b0a9-150">Boolean</span></span> |
| <span data-ttu-id="4b0a9-151">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-151">**Possible values**</span></span> | <span data-ttu-id="4b0a9-152">false (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-152">false (default)</span></span> <br/> <span data-ttu-id="4b0a9-153">真</span><span class="sxs-lookup"><span data-stu-id="4b0a9-153">true</span></span> |
| <span data-ttu-id="4b0a9-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-154">**Comments**</span></span> | <span data-ttu-id="4b0a9-155">在100.67.60 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="4b0a9-156">排除合併原則</span><span class="sxs-lookup"><span data-stu-id="4b0a9-156">Exclusion merge policy</span></span>

<span data-ttu-id="4b0a9-157">指定排除專案的合併原則。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="4b0a9-158">它可以是管理員定義和使用者定義排除的組合 (`merge`) 或只) 系統管理員定義的排除 (`admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="4b0a9-159">您可以使用此設定來限制本機使用者定義自己的排除專案。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-160">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-160">**Key**</span></span> | <span data-ttu-id="4b0a9-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="4b0a9-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="4b0a9-162">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-162">**Data type**</span></span> | <span data-ttu-id="4b0a9-163">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-163">String</span></span> |
| <span data-ttu-id="4b0a9-164">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-164">**Possible values**</span></span> | <span data-ttu-id="4b0a9-165">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-165">merge (default)</span></span> <br/> <span data-ttu-id="4b0a9-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="4b0a9-166">admin_only</span></span> |
| <span data-ttu-id="4b0a9-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-167">**Comments**</span></span> | <span data-ttu-id="4b0a9-168">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="4b0a9-169">掃描排除</span><span class="sxs-lookup"><span data-stu-id="4b0a9-169">Scan exclusions</span></span>

<span data-ttu-id="4b0a9-170">已從掃描中排除的實體。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="4b0a9-171">您可以使用完整路徑、副檔名或檔案名來指定排除。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-172">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-172">**Key**</span></span> | <span data-ttu-id="4b0a9-173">排除</span><span class="sxs-lookup"><span data-stu-id="4b0a9-173">exclusions</span></span> |
| <span data-ttu-id="4b0a9-174">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-174">**Data type**</span></span> | <span data-ttu-id="4b0a9-175">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="4b0a9-176">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-176">**Comments**</span></span> | <span data-ttu-id="4b0a9-177">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-177">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="4b0a9-178">**排除的類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-178">**Type of exclusion**</span></span>

<span data-ttu-id="4b0a9-179">指定排除在掃描之外的內容類型。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-180">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-180">**Key**</span></span> | <span data-ttu-id="4b0a9-181">$type</span><span class="sxs-lookup"><span data-stu-id="4b0a9-181">$type</span></span> |
| <span data-ttu-id="4b0a9-182">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-182">**Data type**</span></span> | <span data-ttu-id="4b0a9-183">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-183">String</span></span> |
| <span data-ttu-id="4b0a9-184">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-184">**Possible values**</span></span> | <span data-ttu-id="4b0a9-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="4b0a9-185">excludedPath</span></span> <br/> <span data-ttu-id="4b0a9-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="4b0a9-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="4b0a9-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="4b0a9-187">excludedFileName</span></span> |

<span data-ttu-id="4b0a9-188">**排除內容的路徑**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-188">**Path to excluded content**</span></span>

<span data-ttu-id="4b0a9-189">用於從掃描的完整檔案路徑中排除內容。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-190">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-190">**Key**</span></span> | <span data-ttu-id="4b0a9-191">路徑</span><span class="sxs-lookup"><span data-stu-id="4b0a9-191">path</span></span> |
| <span data-ttu-id="4b0a9-192">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-192">**Data type**</span></span> | <span data-ttu-id="4b0a9-193">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-193">String</span></span> |
| <span data-ttu-id="4b0a9-194">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-194">**Possible values**</span></span> | <span data-ttu-id="4b0a9-195">有效路徑</span><span class="sxs-lookup"><span data-stu-id="4b0a9-195">valid paths</span></span> |
| <span data-ttu-id="4b0a9-196">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-196">**Comments**</span></span> | <span data-ttu-id="4b0a9-197">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="4b0a9-197">Applicable only if *$type* is *excludedPath*</span></span> |

<span data-ttu-id="4b0a9-198">**(檔/目錄的路徑類型)**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="4b0a9-199">會指出 *path* 屬性參照的是檔案或目錄。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="4b0a9-200">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-200">**Key**</span></span> | <span data-ttu-id="4b0a9-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="4b0a9-201">isDirectory</span></span> |
| <span data-ttu-id="4b0a9-202">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-202">**Data type**</span></span> | <span data-ttu-id="4b0a9-203">布林值</span><span class="sxs-lookup"><span data-stu-id="4b0a9-203">Boolean</span></span> |
| <span data-ttu-id="4b0a9-204">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-204">**Possible values**</span></span> | <span data-ttu-id="4b0a9-205">false (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-205">false (default)</span></span> <br/> <span data-ttu-id="4b0a9-206">真</span><span class="sxs-lookup"><span data-stu-id="4b0a9-206">true</span></span> |
| <span data-ttu-id="4b0a9-207">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-207">**Comments**</span></span> | <span data-ttu-id="4b0a9-208">僅適用于 *excludedPath* *$type*</span><span class="sxs-lookup"><span data-stu-id="4b0a9-208">Applicable only if *$type* is *excludedPath*</span></span> |

<span data-ttu-id="4b0a9-209">**從掃描排除的副檔名**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="4b0a9-210">用於從 [掃描者] 副檔名排除內容。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-211">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-211">**Key**</span></span> | <span data-ttu-id="4b0a9-212">擴展</span><span class="sxs-lookup"><span data-stu-id="4b0a9-212">extension</span></span> |
| <span data-ttu-id="4b0a9-213">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-213">**Data type**</span></span> | <span data-ttu-id="4b0a9-214">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-214">String</span></span> |
| <span data-ttu-id="4b0a9-215">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-215">**Possible values**</span></span> | <span data-ttu-id="4b0a9-216">有效的副檔名</span><span class="sxs-lookup"><span data-stu-id="4b0a9-216">valid file extensions</span></span> |
| <span data-ttu-id="4b0a9-217">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-217">**Comments**</span></span> | <span data-ttu-id="4b0a9-218">僅適用于 *excludedFileExtension* *$type*</span><span class="sxs-lookup"><span data-stu-id="4b0a9-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |

<span data-ttu-id="4b0a9-219">**從掃描排除的處理常式**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="4b0a9-220">指定從掃描排除所有檔案活動的處理常式。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="4b0a9-221">您可以透過名稱來指定程式 (例如， `cat`) 或完整路徑 (例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-222">**Key**</span></span> | <span data-ttu-id="4b0a9-223">name</span><span class="sxs-lookup"><span data-stu-id="4b0a9-223">name</span></span> |
| <span data-ttu-id="4b0a9-224">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-224">**Data type**</span></span> | <span data-ttu-id="4b0a9-225">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-225">String</span></span> |
| <span data-ttu-id="4b0a9-226">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-226">**Possible values**</span></span> | <span data-ttu-id="4b0a9-227">任何字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-227">any string</span></span> |
| <span data-ttu-id="4b0a9-228">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-228">**Comments**</span></span> | <span data-ttu-id="4b0a9-229">僅適用于 *excludedFileName* *$type*</span><span class="sxs-lookup"><span data-stu-id="4b0a9-229">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="4b0a9-230">允許的威脅</span><span class="sxs-lookup"><span data-stu-id="4b0a9-230">Allowed threats</span></span>

<span data-ttu-id="4b0a9-231">根據其名稱) 所識別的威脅清單，其 (未被產品封鎖，但改為允許執行。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-232">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-232">**Key**</span></span> | <span data-ttu-id="4b0a9-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="4b0a9-233">allowedThreats</span></span> |
| <span data-ttu-id="4b0a9-234">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-234">**Data type**</span></span> | <span data-ttu-id="4b0a9-235">字串陣列</span><span class="sxs-lookup"><span data-stu-id="4b0a9-235">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="4b0a9-236">不允許的威脅動作</span><span class="sxs-lookup"><span data-stu-id="4b0a9-236">Disallowed threat actions</span></span>

<span data-ttu-id="4b0a9-237">限制偵測到威脅時，裝置的本機使用者可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="4b0a9-238">在此清單中包含的動作不會顯示在使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-239">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-239">**Key**</span></span> | <span data-ttu-id="4b0a9-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="4b0a9-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="4b0a9-241">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-241">**Data type**</span></span> | <span data-ttu-id="4b0a9-242">字串陣列</span><span class="sxs-lookup"><span data-stu-id="4b0a9-242">Array of strings</span></span> |
| <span data-ttu-id="4b0a9-243">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-243">**Possible values**</span></span> | <span data-ttu-id="4b0a9-244">允許 (限制使用者允許威脅) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="4b0a9-245">restore (會限制使用者從隔離區還原威脅) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="4b0a9-246">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-246">**Comments**</span></span> | <span data-ttu-id="4b0a9-247">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="4b0a9-248">威脅類型設定</span><span class="sxs-lookup"><span data-stu-id="4b0a9-248">Threat type settings</span></span>

<span data-ttu-id="4b0a9-249">防病毒引擎中的 *threatTypeSettings* 首選項是用來控制產品如何處理特定威脅類型。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-250">**Key**</span></span> | <span data-ttu-id="4b0a9-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="4b0a9-251">threatTypeSettings</span></span> |
| <span data-ttu-id="4b0a9-252">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-252">**Data type**</span></span> | <span data-ttu-id="4b0a9-253">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="4b0a9-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-254">**Comments**</span></span> | <span data-ttu-id="4b0a9-255">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-255">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="4b0a9-256">**威脅類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-256">**Threat type**</span></span>

<span data-ttu-id="4b0a9-257">設定行為的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-258">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-258">**Key**</span></span> | <span data-ttu-id="4b0a9-259">機碼</span><span class="sxs-lookup"><span data-stu-id="4b0a9-259">key</span></span> |
| <span data-ttu-id="4b0a9-260">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-260">**Data type**</span></span> | <span data-ttu-id="4b0a9-261">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-261">String</span></span> |
| <span data-ttu-id="4b0a9-262">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-262">**Possible values**</span></span> | <span data-ttu-id="4b0a9-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="4b0a9-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="4b0a9-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="4b0a9-264">archive_bomb</span></span> |

<span data-ttu-id="4b0a9-265">**要採取的動作**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-265">**Action to take**</span></span>

<span data-ttu-id="4b0a9-266">當您在上述區段中所指定類型的威脅到來時採取的動作。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="4b0a9-267">可以是：</span><span class="sxs-lookup"><span data-stu-id="4b0a9-267">Can be:</span></span>

- <span data-ttu-id="4b0a9-268">**Audit**：此裝置沒有針對這類威脅進行保護，但是會記錄有關威脅的專案。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="4b0a9-269">**封鎖**：針對這類威脅保護裝置，並在安全性主控台中通知您。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="4b0a9-270">**Off**：裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-271">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-271">**Key**</span></span> | <span data-ttu-id="4b0a9-272">數值</span><span class="sxs-lookup"><span data-stu-id="4b0a9-272">value</span></span> |
| <span data-ttu-id="4b0a9-273">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-273">**Data type**</span></span> | <span data-ttu-id="4b0a9-274">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-274">String</span></span> |
| <span data-ttu-id="4b0a9-275">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-275">**Possible values**</span></span> | <span data-ttu-id="4b0a9-276">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-276">audit (default)</span></span> <br/> <span data-ttu-id="4b0a9-277">塊</span><span class="sxs-lookup"><span data-stu-id="4b0a9-277">block</span></span> <br/> <span data-ttu-id="4b0a9-278">遠離</span><span class="sxs-lookup"><span data-stu-id="4b0a9-278">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="4b0a9-279">威脅類型設定合併原則</span><span class="sxs-lookup"><span data-stu-id="4b0a9-279">Threat type settings merge policy</span></span>

<span data-ttu-id="4b0a9-280">指定威脅類型設定的合併原則。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="4b0a9-281">這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="4b0a9-282">此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-283">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-283">**Key**</span></span> | <span data-ttu-id="4b0a9-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="4b0a9-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="4b0a9-285">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-285">**Data type**</span></span> | <span data-ttu-id="4b0a9-286">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-286">String</span></span> |
| <span data-ttu-id="4b0a9-287">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-287">**Possible values**</span></span> | <span data-ttu-id="4b0a9-288">merge (預設值) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-288">merge (default)</span></span> <br/> <span data-ttu-id="4b0a9-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="4b0a9-289">admin_only</span></span> |
| <span data-ttu-id="4b0a9-290">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-290">**Comments**</span></span> | <span data-ttu-id="4b0a9-291">在100.83.73 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="4b0a9-292">防病毒掃描記錄保留 (天數) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="4b0a9-293">指定在裝置上的掃描歷程記錄中保留結果的天數。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="4b0a9-294">舊的掃描結果會從歷史記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="4b0a9-295">也會從磁片中移除的舊隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-296">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-296">**Key**</span></span> | <span data-ttu-id="4b0a9-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="4b0a9-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="4b0a9-298">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-298">**Data type**</span></span> | <span data-ttu-id="4b0a9-299">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-299">String</span></span> |
| <span data-ttu-id="4b0a9-300">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-300">**Possible values**</span></span> | <span data-ttu-id="4b0a9-301">90 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-301">90 (default).</span></span> <span data-ttu-id="4b0a9-302">允許的值介於1天到180天。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="4b0a9-303">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-303">**Comments**</span></span> | <span data-ttu-id="4b0a9-304">在101.04.76 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="4b0a9-305">防病毒掃描歷程記錄中的專案數上限</span><span class="sxs-lookup"><span data-stu-id="4b0a9-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="4b0a9-306">指定要保留在掃描記錄中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="4b0a9-307">專案包括過去執行的所有按需掃描及所有防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-308">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-308">**Key**</span></span> | <span data-ttu-id="4b0a9-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="4b0a9-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="4b0a9-310">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-310">**Data type**</span></span> | <span data-ttu-id="4b0a9-311">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-311">String</span></span> |
| <span data-ttu-id="4b0a9-312">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-312">**Possible values**</span></span> | <span data-ttu-id="4b0a9-313">10000 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-313">10000 (default).</span></span> <span data-ttu-id="4b0a9-314">允許的值是從5000專案到15000專案。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="4b0a9-315">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-315">**Comments**</span></span> | <span data-ttu-id="4b0a9-316">在101.04.76 或更高版本的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="4b0a9-317">雲端提供的保護偏好設定</span><span class="sxs-lookup"><span data-stu-id="4b0a9-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="4b0a9-318">設定設定檔中的 *cloudService* 專案是用來設定產品的雲端驅動保護功能。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-319">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-319">**Key**</span></span> | <span data-ttu-id="4b0a9-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="4b0a9-320">cloudService</span></span> |
| <span data-ttu-id="4b0a9-321">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-321">**Data type**</span></span> | <span data-ttu-id="4b0a9-322">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="4b0a9-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-323">**Comments**</span></span> | <span data-ttu-id="4b0a9-324">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-324">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="4b0a9-325">啟用/停用雲端已傳送保護</span><span class="sxs-lookup"><span data-stu-id="4b0a9-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="4b0a9-326">決定是否已在裝置上啟用雲端傳送保護。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="4b0a9-327">若要改善服務的安全性，建議您保持此功能開啟。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-328">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-328">**Key**</span></span> | <span data-ttu-id="4b0a9-329">啟用</span><span class="sxs-lookup"><span data-stu-id="4b0a9-329">enabled</span></span> |
| <span data-ttu-id="4b0a9-330">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-330">**Data type**</span></span> | <span data-ttu-id="4b0a9-331">布林值</span><span class="sxs-lookup"><span data-stu-id="4b0a9-331">Boolean</span></span> |
| <span data-ttu-id="4b0a9-332">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-332">**Possible values**</span></span> | <span data-ttu-id="4b0a9-333">true (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-333">true (default)</span></span> <br/> <span data-ttu-id="4b0a9-334">假</span><span class="sxs-lookup"><span data-stu-id="4b0a9-334">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="4b0a9-335">診斷集合層級</span><span class="sxs-lookup"><span data-stu-id="4b0a9-335">Diagnostic collection level</span></span>

<span data-ttu-id="4b0a9-336">診斷資料是用來將 Defender 設定為安全和更新、偵測、診斷和修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="4b0a9-337">此設定會決定由產品所傳送給 Microsoft 的診斷層級。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-338">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-338">**Key**</span></span> | <span data-ttu-id="4b0a9-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="4b0a9-339">diagnosticLevel</span></span> |
| <span data-ttu-id="4b0a9-340">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-340">**Data type**</span></span> | <span data-ttu-id="4b0a9-341">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-341">String</span></span> |
| <span data-ttu-id="4b0a9-342">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-342">**Possible values**</span></span> | <span data-ttu-id="4b0a9-343">選用 (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-343">optional (default)</span></span> <br/> <span data-ttu-id="4b0a9-344">必要</span><span class="sxs-lookup"><span data-stu-id="4b0a9-344">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="4b0a9-345">啟用/停用自動範例報送</span><span class="sxs-lookup"><span data-stu-id="4b0a9-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="4b0a9-346">會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="4b0a9-347">有三個層級可用於控制範例提交：</span><span class="sxs-lookup"><span data-stu-id="4b0a9-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="4b0a9-348">**None**：沒有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="4b0a9-349">**安全**：只有不含個人身分識別資訊 (PII) 的可疑範例會自動提交。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="4b0a9-350">此為此設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="4b0a9-351">**All**：將所有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-352">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-352">**Key**</span></span> | <span data-ttu-id="4b0a9-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="4b0a9-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="4b0a9-354">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-354">**Data type**</span></span> | <span data-ttu-id="4b0a9-355">字串</span><span class="sxs-lookup"><span data-stu-id="4b0a9-355">String</span></span> |
| <span data-ttu-id="4b0a9-356">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-356">**Possible values**</span></span> | <span data-ttu-id="4b0a9-357">無</span><span class="sxs-lookup"><span data-stu-id="4b0a9-357">none</span></span> <br/> <span data-ttu-id="4b0a9-358">安全 (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-358">safe (default)</span></span> <br/> <span data-ttu-id="4b0a9-359">所有</span><span class="sxs-lookup"><span data-stu-id="4b0a9-359">all</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="4b0a9-360">啟用/停用自動安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="4b0a9-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="4b0a9-361">決定是否自動安裝安全性智慧更新：</span><span class="sxs-lookup"><span data-stu-id="4b0a9-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="4b0a9-362">**Key**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-362">**Key**</span></span> | <span data-ttu-id="4b0a9-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="4b0a9-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="4b0a9-364">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-364">**Data type**</span></span> | <span data-ttu-id="4b0a9-365">布林值</span><span class="sxs-lookup"><span data-stu-id="4b0a9-365">Boolean</span></span> |
| <span data-ttu-id="4b0a9-366">**可能值**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-366">**Possible values**</span></span> | <span data-ttu-id="4b0a9-367">true (預設) </span><span class="sxs-lookup"><span data-stu-id="4b0a9-367">true (default)</span></span> <br/> <span data-ttu-id="4b0a9-368">假</span><span class="sxs-lookup"><span data-stu-id="4b0a9-368">false</span></span> |

## <a name="recommended-configuration-profile"></a><span data-ttu-id="4b0a9-369">建議的設定設定檔</span><span class="sxs-lookup"><span data-stu-id="4b0a9-369">Recommended configuration profile</span></span>

<span data-ttu-id="4b0a9-370">若要開始使用，我們建議您的企業使用下列設定設定檔，以利用所有供 Endpoint 的 Defender 提供的保護功能。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="4b0a9-371">下列設定檔將會：</span><span class="sxs-lookup"><span data-stu-id="4b0a9-371">The following configuration profile will:</span></span>

- <span data-ttu-id="4b0a9-372">啟用 (RTP) 的即時保護</span><span class="sxs-lookup"><span data-stu-id="4b0a9-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="4b0a9-373">指定如何處理下列威脅類型：</span><span class="sxs-lookup"><span data-stu-id="4b0a9-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="4b0a9-374">封鎖 **(PUA) 可能有害的應用程式**</span><span class="sxs-lookup"><span data-stu-id="4b0a9-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="4b0a9-375">將 bombs 具有高壓縮率) 的封存檔 (**檔案**，審核至產品記錄</span><span class="sxs-lookup"><span data-stu-id="4b0a9-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="4b0a9-376">啟用自動安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="4b0a9-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="4b0a9-377">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="4b0a9-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="4b0a9-378">啟用層級的自動範例提交 `safe`</span><span class="sxs-lookup"><span data-stu-id="4b0a9-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="4b0a9-379">範例設定檔</span><span class="sxs-lookup"><span data-stu-id="4b0a9-379">Sample profile</span></span>

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
      "enabled":true
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="4b0a9-380">完整設定檔範例</span><span class="sxs-lookup"><span data-stu-id="4b0a9-380">Full configuration profile example</span></span>

<span data-ttu-id="4b0a9-381">下列設定設定檔包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要更進一步控制產品。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="4b0a9-382">完整設定檔</span><span class="sxs-lookup"><span data-stu-id="4b0a9-382">Full profile</span></span>

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
            "path":"/home"
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
      "automaticDefinitionUpdateEnabled":true
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="4b0a9-383">設定設定檔驗證</span><span class="sxs-lookup"><span data-stu-id="4b0a9-383">Configuration profile validation</span></span>

<span data-ttu-id="4b0a9-384">設定設定檔必須是有效的 JSON 格式檔。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="4b0a9-385">有許多工具可以用來確認這一點。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="4b0a9-386">例如，如果您已 `python` 在裝置上安裝：</span><span class="sxs-lookup"><span data-stu-id="4b0a9-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="4b0a9-387">如果 JSON 格式正確，上述命令會將其輸出到終端，並傳回的退出程式碼 `0` 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="4b0a9-388">否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="4b0a9-389">設定設定檔部署</span><span class="sxs-lookup"><span data-stu-id="4b0a9-389">Configuration profile deployment</span></span>

<span data-ttu-id="4b0a9-390">在您為企業建立設定檔之後，您可以透過企業使用的管理工具加以部署。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-390">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="4b0a9-391">/Etc/opt/microsoft/mdatp/managed/版的 Defender for Linux 會從檔案上的 *mdatp_managed.js* 讀取 managed 設定。</span><span class="sxs-lookup"><span data-stu-id="4b0a9-391">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
