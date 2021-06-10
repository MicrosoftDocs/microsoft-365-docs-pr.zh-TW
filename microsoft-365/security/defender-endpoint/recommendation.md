---
title: 建議方法和屬性
description: 會檢索最新的警示。
keywords: api、graph api、支援的 api、get、警示、最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771594"
---
# <a name="recommendation-resource-type"></a><span data-ttu-id="e5048-104">建議資源類型</span><span class="sxs-lookup"><span data-stu-id="e5048-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e5048-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e5048-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="e5048-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e5048-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e5048-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e5048-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="e5048-108">方法</span><span class="sxs-lookup"><span data-stu-id="e5048-108">Methods</span></span>
<span data-ttu-id="e5048-109">方法	</span><span class="sxs-lookup"><span data-stu-id="e5048-109">Method</span></span> |<span data-ttu-id="e5048-110">傳回類型</span><span class="sxs-lookup"><span data-stu-id="e5048-110">Return Type</span></span> |<span data-ttu-id="e5048-111">描述</span><span class="sxs-lookup"><span data-stu-id="e5048-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="e5048-112">列出所有建議</span><span class="sxs-lookup"><span data-stu-id="e5048-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="e5048-113">建議集合</span><span class="sxs-lookup"><span data-stu-id="e5048-113">Recommendation collection</span></span> | <span data-ttu-id="e5048-114">會檢索影響組織之所有安全性建議的清單</span><span class="sxs-lookup"><span data-stu-id="e5048-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="e5048-115">根據識別碼取得建議</span><span class="sxs-lookup"><span data-stu-id="e5048-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="e5048-116">建議</span><span class="sxs-lookup"><span data-stu-id="e5048-116">Recommendation</span></span> | <span data-ttu-id="e5048-117">依識別碼取得安全性建議</span><span class="sxs-lookup"><span data-stu-id="e5048-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="e5048-118">取得建議軟體</span><span class="sxs-lookup"><span data-stu-id="e5048-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="e5048-119">軟體</span><span class="sxs-lookup"><span data-stu-id="e5048-119">Software</span></span>](software.md) | <span data-ttu-id="e5048-120">檢索與特定軟體相關的安全性建議</span><span class="sxs-lookup"><span data-stu-id="e5048-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="e5048-121">取得建議裝置</span><span class="sxs-lookup"><span data-stu-id="e5048-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="e5048-122">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="e5048-122">MachineRef collection</span></span> | <span data-ttu-id="e5048-123">檢索與安全性建議相關聯的裝置清單</span><span class="sxs-lookup"><span data-stu-id="e5048-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="e5048-124">取得建議的弱點</span><span class="sxs-lookup"><span data-stu-id="e5048-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="e5048-125">[弱點](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="e5048-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="e5048-126">會檢索與安全性建議相關的漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="e5048-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="e5048-127">屬性</span><span class="sxs-lookup"><span data-stu-id="e5048-127">Properties</span></span>
<span data-ttu-id="e5048-128">屬性	</span><span class="sxs-lookup"><span data-stu-id="e5048-128">Property</span></span> |   <span data-ttu-id="e5048-129">類型</span><span class="sxs-lookup"><span data-stu-id="e5048-129">Type</span></span>   |   <span data-ttu-id="e5048-130">描述</span><span class="sxs-lookup"><span data-stu-id="e5048-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="e5048-131">id</span><span class="sxs-lookup"><span data-stu-id="e5048-131">id</span></span> | <span data-ttu-id="e5048-132">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-132">String</span></span> | <span data-ttu-id="e5048-133">建議識別碼</span><span class="sxs-lookup"><span data-stu-id="e5048-133">Recommendation ID</span></span>
<span data-ttu-id="e5048-134">Package.productname</span><span class="sxs-lookup"><span data-stu-id="e5048-134">productName</span></span> | <span data-ttu-id="e5048-135">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-135">String</span></span> | <span data-ttu-id="e5048-136">相關軟體名稱</span><span class="sxs-lookup"><span data-stu-id="e5048-136">Related software name</span></span>  
<span data-ttu-id="e5048-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="e5048-137">recommendationName</span></span> | <span data-ttu-id="e5048-138">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-138">String</span></span> | <span data-ttu-id="e5048-139">建議名稱</span><span class="sxs-lookup"><span data-stu-id="e5048-139">Recommendation name</span></span>
<span data-ttu-id="e5048-140">弱點</span><span class="sxs-lookup"><span data-stu-id="e5048-140">Weaknesses</span></span> | <span data-ttu-id="e5048-141">Long</span><span class="sxs-lookup"><span data-stu-id="e5048-141">Long</span></span> | <span data-ttu-id="e5048-142">發現的漏洞數目</span><span class="sxs-lookup"><span data-stu-id="e5048-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="e5048-143">廠商</span><span class="sxs-lookup"><span data-stu-id="e5048-143">Vendor</span></span> | <span data-ttu-id="e5048-144">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-144">String</span></span> | <span data-ttu-id="e5048-145">相關的供應商名稱</span><span class="sxs-lookup"><span data-stu-id="e5048-145">Related vendor name</span></span>
<span data-ttu-id="e5048-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="e5048-146">recommendedVersion</span></span> | <span data-ttu-id="e5048-147">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-147">String</span></span> | <span data-ttu-id="e5048-148">建議的版本</span><span class="sxs-lookup"><span data-stu-id="e5048-148">Recommended version</span></span>
<span data-ttu-id="e5048-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="e5048-149">recommendationCategory</span></span> | <span data-ttu-id="e5048-150">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-150">String</span></span> | <span data-ttu-id="e5048-151">建議類別。</span><span class="sxs-lookup"><span data-stu-id="e5048-151">Recommendation category.</span></span> <span data-ttu-id="e5048-152">可能的值為：「帳戶」、「應用程式」、「網路」、「OS」、「SecurityStack</span><span class="sxs-lookup"><span data-stu-id="e5048-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="e5048-153">個子</span><span class="sxs-lookup"><span data-stu-id="e5048-153">subCategory</span></span> | <span data-ttu-id="e5048-154">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-154">String</span></span> | <span data-ttu-id="e5048-155">建議子類別</span><span class="sxs-lookup"><span data-stu-id="e5048-155">Recommendation sub-category</span></span>
<span data-ttu-id="e5048-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="e5048-156">severityScore</span></span> | <span data-ttu-id="e5048-157">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="e5048-157">Double</span></span> | <span data-ttu-id="e5048-158">設定對組織之 Microsoft 安全評分的潛在影響 (1-10) </span><span class="sxs-lookup"><span data-stu-id="e5048-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="e5048-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="e5048-159">publicExploit</span></span> | <span data-ttu-id="e5048-160">布林值</span><span class="sxs-lookup"><span data-stu-id="e5048-160">Boolean</span></span> | <span data-ttu-id="e5048-161">公開利用漏洞可供使用</span><span class="sxs-lookup"><span data-stu-id="e5048-161">Public exploit is available</span></span> 
<span data-ttu-id="e5048-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="e5048-162">activeAlert</span></span> | <span data-ttu-id="e5048-163">布林值</span><span class="sxs-lookup"><span data-stu-id="e5048-163">Boolean</span></span> | <span data-ttu-id="e5048-164">主動警示與此建議相關聯</span><span class="sxs-lookup"><span data-stu-id="e5048-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="e5048-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="e5048-165">associatedThreats</span></span> | <span data-ttu-id="e5048-166">String 集合</span><span class="sxs-lookup"><span data-stu-id="e5048-166">String collection</span></span> | <span data-ttu-id="e5048-167">威脅分析報告與此建議相關聯</span><span class="sxs-lookup"><span data-stu-id="e5048-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="e5048-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="e5048-168">remediationType</span></span> | <span data-ttu-id="e5048-169">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-169">String</span></span> | <span data-ttu-id="e5048-170">修正類型。</span><span class="sxs-lookup"><span data-stu-id="e5048-170">Remediation type.</span></span> <span data-ttu-id="e5048-171">可能的值為： "ConfigurationChange"、"Update"、"Upgrade"、"Uninstall"</span><span class="sxs-lookup"><span data-stu-id="e5048-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="e5048-172">狀態</span><span class="sxs-lookup"><span data-stu-id="e5048-172">Status</span></span> | <span data-ttu-id="e5048-173">Enum</span><span class="sxs-lookup"><span data-stu-id="e5048-173">Enum</span></span> | <span data-ttu-id="e5048-174">建議例外狀況。</span><span class="sxs-lookup"><span data-stu-id="e5048-174">Recommendation exception status.</span></span> <span data-ttu-id="e5048-175">可能的值為：「Active」和「例外狀況」</span><span class="sxs-lookup"><span data-stu-id="e5048-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="e5048-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="e5048-176">configScoreImpact</span></span> | <span data-ttu-id="e5048-177">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="e5048-177">Double</span></span> | <span data-ttu-id="e5048-178">適用于裝置影響的 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="e5048-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="e5048-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="e5048-179">exposureImpacte</span></span> | <span data-ttu-id="e5048-180">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="e5048-180">Double</span></span> | <span data-ttu-id="e5048-181">曝光分數影響</span><span class="sxs-lookup"><span data-stu-id="e5048-181">Exposure score impact</span></span>
<span data-ttu-id="e5048-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="e5048-182">totalMachineCount</span></span> | <span data-ttu-id="e5048-183">Long</span><span class="sxs-lookup"><span data-stu-id="e5048-183">Long</span></span> | <span data-ttu-id="e5048-184">已安裝裝置的數目</span><span class="sxs-lookup"><span data-stu-id="e5048-184">Number of installed devices</span></span>
<span data-ttu-id="e5048-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="e5048-185">exposedMachinesCount</span></span> | <span data-ttu-id="e5048-186">Long</span><span class="sxs-lookup"><span data-stu-id="e5048-186">Long</span></span> | <span data-ttu-id="e5048-187">對漏洞公開的已安裝裝置數目</span><span class="sxs-lookup"><span data-stu-id="e5048-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="e5048-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="e5048-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="e5048-189">Long</span><span class="sxs-lookup"><span data-stu-id="e5048-189">Long</span></span> | <span data-ttu-id="e5048-190">不受影響的裝置數目</span><span class="sxs-lookup"><span data-stu-id="e5048-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="e5048-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="e5048-191">relatedComponent</span></span> | <span data-ttu-id="e5048-192">字串</span><span class="sxs-lookup"><span data-stu-id="e5048-192">String</span></span> |  <span data-ttu-id="e5048-193">相關的軟體元件</span><span class="sxs-lookup"><span data-stu-id="e5048-193">Related software component</span></span>
