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
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198230"
---
# <a name="recommendation-resource-type"></a><span data-ttu-id="267ff-104">建議資源類型</span><span class="sxs-lookup"><span data-stu-id="267ff-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="267ff-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="267ff-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="267ff-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="267ff-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="267ff-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="267ff-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="267ff-108">方法</span><span class="sxs-lookup"><span data-stu-id="267ff-108">Methods</span></span>
<span data-ttu-id="267ff-109">方法	</span><span class="sxs-lookup"><span data-stu-id="267ff-109">Method</span></span> |<span data-ttu-id="267ff-110">傳回類型</span><span class="sxs-lookup"><span data-stu-id="267ff-110">Return Type</span></span> |<span data-ttu-id="267ff-111">描述</span><span class="sxs-lookup"><span data-stu-id="267ff-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="267ff-112">列出所有建議</span><span class="sxs-lookup"><span data-stu-id="267ff-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="267ff-113">建議集合</span><span class="sxs-lookup"><span data-stu-id="267ff-113">Recommendation collection</span></span> | <span data-ttu-id="267ff-114">會檢索影響組織之所有安全性建議的清單</span><span class="sxs-lookup"><span data-stu-id="267ff-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="267ff-115">依識別碼取得建議</span><span class="sxs-lookup"><span data-stu-id="267ff-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="267ff-116">建議</span><span class="sxs-lookup"><span data-stu-id="267ff-116">Recommendation</span></span> | <span data-ttu-id="267ff-117">依識別碼取得安全性建議</span><span class="sxs-lookup"><span data-stu-id="267ff-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="267ff-118">取得建議軟體</span><span class="sxs-lookup"><span data-stu-id="267ff-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="267ff-119">軟體</span><span class="sxs-lookup"><span data-stu-id="267ff-119">Software</span></span>](software.md) | <span data-ttu-id="267ff-120">檢索與特定軟體相關的安全性建議</span><span class="sxs-lookup"><span data-stu-id="267ff-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="267ff-121">取得建議裝置</span><span class="sxs-lookup"><span data-stu-id="267ff-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="267ff-122">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="267ff-122">MachineRef collection</span></span> | <span data-ttu-id="267ff-123">檢索與安全性建議相關聯的裝置清單</span><span class="sxs-lookup"><span data-stu-id="267ff-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="267ff-124">取得建議的弱點</span><span class="sxs-lookup"><span data-stu-id="267ff-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="267ff-125">[弱點](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="267ff-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="267ff-126">會檢索與安全性建議相關的漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="267ff-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="267ff-127">屬性</span><span class="sxs-lookup"><span data-stu-id="267ff-127">Properties</span></span>
<span data-ttu-id="267ff-128">屬性	</span><span class="sxs-lookup"><span data-stu-id="267ff-128">Property</span></span> |   <span data-ttu-id="267ff-129">類型</span><span class="sxs-lookup"><span data-stu-id="267ff-129">Type</span></span>   |   <span data-ttu-id="267ff-130">描述</span><span class="sxs-lookup"><span data-stu-id="267ff-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="267ff-131">id</span><span class="sxs-lookup"><span data-stu-id="267ff-131">id</span></span> | <span data-ttu-id="267ff-132">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-132">String</span></span> | <span data-ttu-id="267ff-133">建議識別碼</span><span class="sxs-lookup"><span data-stu-id="267ff-133">Recommendation ID</span></span>
<span data-ttu-id="267ff-134">Package.productname</span><span class="sxs-lookup"><span data-stu-id="267ff-134">productName</span></span> | <span data-ttu-id="267ff-135">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-135">String</span></span> | <span data-ttu-id="267ff-136">相關軟體名稱</span><span class="sxs-lookup"><span data-stu-id="267ff-136">Related software name</span></span>  
<span data-ttu-id="267ff-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="267ff-137">recommendationName</span></span> | <span data-ttu-id="267ff-138">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-138">String</span></span> | <span data-ttu-id="267ff-139">建議名稱</span><span class="sxs-lookup"><span data-stu-id="267ff-139">Recommendation name</span></span>
<span data-ttu-id="267ff-140">弱點</span><span class="sxs-lookup"><span data-stu-id="267ff-140">Weaknesses</span></span> | <span data-ttu-id="267ff-141">Long</span><span class="sxs-lookup"><span data-stu-id="267ff-141">Long</span></span> | <span data-ttu-id="267ff-142">發現的漏洞數目</span><span class="sxs-lookup"><span data-stu-id="267ff-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="267ff-143">廠商</span><span class="sxs-lookup"><span data-stu-id="267ff-143">Vendor</span></span> | <span data-ttu-id="267ff-144">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-144">String</span></span> | <span data-ttu-id="267ff-145">相關的供應商名稱</span><span class="sxs-lookup"><span data-stu-id="267ff-145">Related vendor name</span></span>
<span data-ttu-id="267ff-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="267ff-146">recommendedVersion</span></span> | <span data-ttu-id="267ff-147">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-147">String</span></span> | <span data-ttu-id="267ff-148">建議的版本</span><span class="sxs-lookup"><span data-stu-id="267ff-148">Recommended version</span></span>
<span data-ttu-id="267ff-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="267ff-149">recommendationCategory</span></span> | <span data-ttu-id="267ff-150">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-150">String</span></span> | <span data-ttu-id="267ff-151">建議類別。</span><span class="sxs-lookup"><span data-stu-id="267ff-151">Recommendation category.</span></span> <span data-ttu-id="267ff-152">可能的值為：「帳戶」、「應用程式」、「網路」、「OS」、「SecurityStack</span><span class="sxs-lookup"><span data-stu-id="267ff-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="267ff-153">個子</span><span class="sxs-lookup"><span data-stu-id="267ff-153">subCategory</span></span> | <span data-ttu-id="267ff-154">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-154">String</span></span> | <span data-ttu-id="267ff-155">建議子類別</span><span class="sxs-lookup"><span data-stu-id="267ff-155">Recommendation sub-category</span></span>
<span data-ttu-id="267ff-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="267ff-156">severityScore</span></span> | <span data-ttu-id="267ff-157">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="267ff-157">Double</span></span> | <span data-ttu-id="267ff-158">設定對組織之 Microsoft 安全評分的潛在影響 (1-10) </span><span class="sxs-lookup"><span data-stu-id="267ff-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="267ff-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="267ff-159">publicExploit</span></span> | <span data-ttu-id="267ff-160">布林值</span><span class="sxs-lookup"><span data-stu-id="267ff-160">Boolean</span></span> | <span data-ttu-id="267ff-161">公開利用漏洞可供使用</span><span class="sxs-lookup"><span data-stu-id="267ff-161">Public exploit is available</span></span> 
<span data-ttu-id="267ff-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="267ff-162">activeAlert</span></span> | <span data-ttu-id="267ff-163">布林值</span><span class="sxs-lookup"><span data-stu-id="267ff-163">Boolean</span></span> | <span data-ttu-id="267ff-164">主動警示與此建議相關聯</span><span class="sxs-lookup"><span data-stu-id="267ff-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="267ff-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="267ff-165">associatedThreats</span></span> | <span data-ttu-id="267ff-166">String 集合</span><span class="sxs-lookup"><span data-stu-id="267ff-166">String collection</span></span> | <span data-ttu-id="267ff-167">威脅分析報告與此建議相關聯</span><span class="sxs-lookup"><span data-stu-id="267ff-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="267ff-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="267ff-168">remediationType</span></span> | <span data-ttu-id="267ff-169">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-169">String</span></span> | <span data-ttu-id="267ff-170">修正類型。</span><span class="sxs-lookup"><span data-stu-id="267ff-170">Remediation type.</span></span> <span data-ttu-id="267ff-171">可能的值為： "ConfigurationChange"、"Update"、"Upgrade"、"Uninstall"</span><span class="sxs-lookup"><span data-stu-id="267ff-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="267ff-172">狀態</span><span class="sxs-lookup"><span data-stu-id="267ff-172">Status</span></span> | <span data-ttu-id="267ff-173">Enum</span><span class="sxs-lookup"><span data-stu-id="267ff-173">Enum</span></span> | <span data-ttu-id="267ff-174">建議例外狀況。</span><span class="sxs-lookup"><span data-stu-id="267ff-174">Recommendation exception status.</span></span> <span data-ttu-id="267ff-175">可能的值為：「Active」和「例外狀況」</span><span class="sxs-lookup"><span data-stu-id="267ff-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="267ff-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="267ff-176">configScoreImpact</span></span> | <span data-ttu-id="267ff-177">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="267ff-177">Double</span></span> | <span data-ttu-id="267ff-178">適用于裝置影響的 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="267ff-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="267ff-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="267ff-179">exposureImpacte</span></span> | <span data-ttu-id="267ff-180">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="267ff-180">Double</span></span> | <span data-ttu-id="267ff-181">曝光分數影響</span><span class="sxs-lookup"><span data-stu-id="267ff-181">Exposure score impact</span></span>
<span data-ttu-id="267ff-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="267ff-182">totalMachineCount</span></span> | <span data-ttu-id="267ff-183">Long</span><span class="sxs-lookup"><span data-stu-id="267ff-183">Long</span></span> | <span data-ttu-id="267ff-184">已安裝裝置的數目</span><span class="sxs-lookup"><span data-stu-id="267ff-184">Number of installed devices</span></span>
<span data-ttu-id="267ff-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="267ff-185">exposedMachinesCount</span></span> | <span data-ttu-id="267ff-186">Long</span><span class="sxs-lookup"><span data-stu-id="267ff-186">Long</span></span> | <span data-ttu-id="267ff-187">對漏洞公開的已安裝裝置數目</span><span class="sxs-lookup"><span data-stu-id="267ff-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="267ff-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="267ff-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="267ff-189">Long</span><span class="sxs-lookup"><span data-stu-id="267ff-189">Long</span></span> | <span data-ttu-id="267ff-190">不受影響的裝置數目</span><span class="sxs-lookup"><span data-stu-id="267ff-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="267ff-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="267ff-191">relatedComponent</span></span> | <span data-ttu-id="267ff-192">字串</span><span class="sxs-lookup"><span data-stu-id="267ff-192">String</span></span> |  <span data-ttu-id="267ff-193">相關的軟體元件</span><span class="sxs-lookup"><span data-stu-id="267ff-193">Related software component</span></span>
