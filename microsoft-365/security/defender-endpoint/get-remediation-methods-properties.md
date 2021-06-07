---
title: 補救活動方法和屬性
description: API 回應包含您租使用者中建立弱點管理修復活動 & 威脅。 您可以要求所有修復活動、只有一個修復活動，或選取的修復工作的公開裝置相關資訊。
keywords: api，修正，修正 api，get，修正工作，修正方法，修正屬性
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 67009961ecc3755b5af21b2e773bc817ea46bec0
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769230"
---
# <a name="remediation-activity-methods-and-properties"></a><span data-ttu-id="5c689-105">補救活動方法和屬性</span><span class="sxs-lookup"><span data-stu-id="5c689-105">Remediation activity methods and properties</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c689-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5c689-106">**Applies to:**</span></span>

- [<span data-ttu-id="5c689-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5c689-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c689-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c689-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5c689-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="5c689-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5c689-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5c689-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="5c689-111">API 回應包含 [](next-gen-threat-and-vuln-mgt.md)   已在您的租使用者中建立弱點管理修復活動的威脅 &。</span><span class="sxs-lookup"><span data-stu-id="5c689-111">The API response contains [Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md) remediation activities that have been created in your tenant.</span></span>  

## <a name="methods"></a><span data-ttu-id="5c689-112">方法</span><span class="sxs-lookup"><span data-stu-id="5c689-112">Methods</span></span>

<span data-ttu-id="5c689-113">方法	</span><span class="sxs-lookup"><span data-stu-id="5c689-113">Method</span></span> | <span data-ttu-id="5c689-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="5c689-114">Data type</span></span> | <span data-ttu-id="5c689-115">描述</span><span class="sxs-lookup"><span data-stu-id="5c689-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="5c689-116">列出所有補救活動</span><span class="sxs-lookup"><span data-stu-id="5c689-116">List all remediation activities</span></span>](get-remediation-all-activities.md) | <span data-ttu-id="5c689-117">調查集合</span><span class="sxs-lookup"><span data-stu-id="5c689-117">Investigation collection</span></span> | <span data-ttu-id="5c689-118">傳回所有修復活動的資訊。</span><span class="sxs-lookup"><span data-stu-id="5c689-118">Returns information about all remediation activities.</span></span>
[<span data-ttu-id="5c689-119">列出一個補救活動的公開裝置</span><span class="sxs-lookup"><span data-stu-id="5c689-119">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md) | <span data-ttu-id="5c689-120">調查實體</span><span class="sxs-lookup"><span data-stu-id="5c689-120">Investigation entity</span></span> | <span data-ttu-id="5c689-121">傳回所指定修復活動的公開裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="5c689-121">Returns information about exposed devices for the specified remediation activity.</span></span>
[<span data-ttu-id="5c689-122">根據識別碼取得一個補救活動</span><span class="sxs-lookup"><span data-stu-id="5c689-122">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md) | <span data-ttu-id="5c689-123">調查實體</span><span class="sxs-lookup"><span data-stu-id="5c689-123">Investigation entity</span></span> | <span data-ttu-id="5c689-124">傳回指定之修復活動的資訊。</span><span class="sxs-lookup"><span data-stu-id="5c689-124">Returns information for the specified remediation activity.</span></span>

<span data-ttu-id="5c689-125">深入瞭解 [修復活動](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="5c689-125">Learn more about [remediation activities](tvm-remediation.md).</span></span>

## <a name="properties"></a><span data-ttu-id="5c689-126">屬性</span><span class="sxs-lookup"><span data-stu-id="5c689-126">Properties</span></span>

<span data-ttu-id="5c689-127">屬性識別碼</span><span class="sxs-lookup"><span data-stu-id="5c689-127">Property id</span></span> | <span data-ttu-id="5c689-128">資料類型</span><span class="sxs-lookup"><span data-stu-id="5c689-128">Data type</span></span> | <span data-ttu-id="5c689-129">描述</span><span class="sxs-lookup"><span data-stu-id="5c689-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="5c689-130">類別</span><span class="sxs-lookup"><span data-stu-id="5c689-130">category</span></span> | <span data-ttu-id="5c689-131">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-131">String</span></span> | <span data-ttu-id="5c689-132"> (軟體/安全性設定) 的修復活動類別</span><span class="sxs-lookup"><span data-stu-id="5c689-132">Category of the remediation activity (Software/Security configuration)</span></span>
<span data-ttu-id="5c689-133">completerEmail</span><span class="sxs-lookup"><span data-stu-id="5c689-133">completerEmail</span></span> | <span data-ttu-id="5c689-134">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-134">String</span></span> | <span data-ttu-id="5c689-135">若某人已手動完成修復活動，此欄會包含他們的電子郵件</span><span class="sxs-lookup"><span data-stu-id="5c689-135">If the remediation activity was manually completed by someone, this column contains their email</span></span>
<span data-ttu-id="5c689-136">completerId</span><span class="sxs-lookup"><span data-stu-id="5c689-136">completerId</span></span> | <span data-ttu-id="5c689-137">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-137">String</span></span> | <span data-ttu-id="5c689-138">若某人已手動完成修復活動，此欄會包含其物件識別碼</span><span class="sxs-lookup"><span data-stu-id="5c689-138">If the remediation activity was manually completed by someone, this column contains their object id</span></span>
<span data-ttu-id="5c689-139">completionMethod</span><span class="sxs-lookup"><span data-stu-id="5c689-139">completionMethod</span></span> | <span data-ttu-id="5c689-140">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-140">String</span></span> | <span data-ttu-id="5c689-141">若所有裝置都已) 或「手動」或「手動」（由選取「標記為完成」）進行修補，便可執行「 (自動」的修復活動。</span><span class="sxs-lookup"><span data-stu-id="5c689-141">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed.”</span></span>
<span data-ttu-id="5c689-142">createdOn</span><span class="sxs-lookup"><span data-stu-id="5c689-142">createdOn</span></span> | <span data-ttu-id="5c689-143">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c689-143">DateTime</span></span> | <span data-ttu-id="5c689-144">建立此修復活動的時間</span><span class="sxs-lookup"><span data-stu-id="5c689-144">Time this remediation activity was created</span></span>
<span data-ttu-id="5c689-145">描述</span><span class="sxs-lookup"><span data-stu-id="5c689-145">description</span></span> | <span data-ttu-id="5c689-146">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-146">String</span></span> | <span data-ttu-id="5c689-147">此修復活動的描述</span><span class="sxs-lookup"><span data-stu-id="5c689-147">Description of this remediation activity</span></span>
<span data-ttu-id="5c689-148">dueOn</span><span class="sxs-lookup"><span data-stu-id="5c689-148">dueOn</span></span> | <span data-ttu-id="5c689-149">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c689-149">DateTime</span></span> | <span data-ttu-id="5c689-150">到期日此修復活動的建立者設定</span><span class="sxs-lookup"><span data-stu-id="5c689-150">Due date the creator set for this remediation activity</span></span>
<span data-ttu-id="5c689-151">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="5c689-151">fixedDevices</span></span> |  | <span data-ttu-id="5c689-152">已修復的裝置數目</span><span class="sxs-lookup"><span data-stu-id="5c689-152">The number of devices that have been fixed</span></span>
<span data-ttu-id="5c689-153">id</span><span class="sxs-lookup"><span data-stu-id="5c689-153">id</span></span> | <span data-ttu-id="5c689-154">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-154">String</span></span> | <span data-ttu-id="5c689-155">此修復活動的識別碼</span><span class="sxs-lookup"><span data-stu-id="5c689-155">ID of this remediation activity</span></span>
<span data-ttu-id="5c689-156">nameId</span><span class="sxs-lookup"><span data-stu-id="5c689-156">nameId</span></span> | <span data-ttu-id="5c689-157">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-157">String</span></span> | <span data-ttu-id="5c689-158">相關產品名稱</span><span class="sxs-lookup"><span data-stu-id="5c689-158">Related product name</span></span>
<span data-ttu-id="5c689-159">優先</span><span class="sxs-lookup"><span data-stu-id="5c689-159">priority</span></span> | <span data-ttu-id="5c689-160">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-160">String</span></span> | <span data-ttu-id="5c689-161">為此修復活動的建立者設定的優先順序 (High\Medium\Low) </span><span class="sxs-lookup"><span data-stu-id="5c689-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span>
<span data-ttu-id="5c689-162">Id</span><span class="sxs-lookup"><span data-stu-id="5c689-162">productId</span></span> | <span data-ttu-id="5c689-163">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-163">String</span></span> | <span data-ttu-id="5c689-164">相關產品識別碼</span><span class="sxs-lookup"><span data-stu-id="5c689-164">Related product ID</span></span>
<span data-ttu-id="5c689-165">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="5c689-165">productivityImpactRemediationType</span></span> | <span data-ttu-id="5c689-166">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-166">String</span></span> | <span data-ttu-id="5c689-167">只會對沒有使用者影響的裝置要求一些設定變更。</span><span class="sxs-lookup"><span data-stu-id="5c689-167">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="5c689-168">此值表示「所有公開的裝置」或「只有沒有使用者影響的裝置」之間的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="5c689-168">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span>
<span data-ttu-id="5c689-169">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="5c689-169">rbacGroupNames</span></span> | <span data-ttu-id="5c689-170">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-170">String</span></span> | <span data-ttu-id="5c689-171">相關的裝置群組名稱</span><span class="sxs-lookup"><span data-stu-id="5c689-171">Related device group names</span></span>
<span data-ttu-id="5c689-172">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="5c689-172">recommendedProgram</span></span> | <span data-ttu-id="5c689-173">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-173">String</span></span> | <span data-ttu-id="5c689-174">升級為的建議程式</span><span class="sxs-lookup"><span data-stu-id="5c689-174">Recommended program to upgrade to</span></span>
<span data-ttu-id="5c689-175">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="5c689-175">recommendedVendor</span></span> | <span data-ttu-id="5c689-176">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-176">String</span></span> | <span data-ttu-id="5c689-177">升級為的建議供應商</span><span class="sxs-lookup"><span data-stu-id="5c689-177">Recommended vendor to upgrade to</span></span>
<span data-ttu-id="5c689-178">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="5c689-178">recommendedVersion</span></span> | <span data-ttu-id="5c689-179">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-179">String</span></span> | <span data-ttu-id="5c689-180">更新/升級的建議版本</span><span class="sxs-lookup"><span data-stu-id="5c689-180">Recommended version to update/upgrade to</span></span>
<span data-ttu-id="5c689-181">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="5c689-181">relatedComponent</span></span> | <span data-ttu-id="5c689-182">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-182">String</span></span> | <span data-ttu-id="5c689-183">此修復活動的相關元件 (類似安全性建議的相關元件) </span><span class="sxs-lookup"><span data-stu-id="5c689-183">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span>
<span data-ttu-id="5c689-184">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="5c689-184">requesterEmail</span></span> | <span data-ttu-id="5c689-185">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-185">String</span></span> | <span data-ttu-id="5c689-186">建立者電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="5c689-186">Creator email address</span></span>
<span data-ttu-id="5c689-187">requesterId</span><span class="sxs-lookup"><span data-stu-id="5c689-187">requesterId</span></span> | <span data-ttu-id="5c689-188">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-188">String</span></span> | <span data-ttu-id="5c689-189">Creator 物件識別碼</span><span class="sxs-lookup"><span data-stu-id="5c689-189">Creator object id</span></span>
<span data-ttu-id="5c689-190">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="5c689-190">requesterNotes</span></span> | <span data-ttu-id="5c689-191">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-191">String</span></span> | <span data-ttu-id="5c689-192">為此修復活動新增的建立者) 附注 (自由文字</span><span class="sxs-lookup"><span data-stu-id="5c689-192">The notes (free text) the creator added for this remediation activity</span></span>
<span data-ttu-id="5c689-193">Scid</span><span class="sxs-lookup"><span data-stu-id="5c689-193">scid</span></span> | <span data-ttu-id="5c689-194">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-194">String</span></span> | <span data-ttu-id="5c689-195">相關安全性建議的 SCID</span><span class="sxs-lookup"><span data-stu-id="5c689-195">SCID of the related security recommendation</span></span>
<span data-ttu-id="5c689-196">地位</span><span class="sxs-lookup"><span data-stu-id="5c689-196">status</span></span> | <span data-ttu-id="5c689-197">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-197">String</span></span> | <span data-ttu-id="5c689-198">修復活動狀態 (Active/已完成) </span><span class="sxs-lookup"><span data-stu-id="5c689-198">Remediation activity status (Active/Completed)</span></span>
<span data-ttu-id="5c689-199">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="5c689-199">statusLastModifiedOn</span></span> | <span data-ttu-id="5c689-200">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c689-200">DateTime</span></span> | <span data-ttu-id="5c689-201">更新狀態欄位的日期</span><span class="sxs-lookup"><span data-stu-id="5c689-201">Date when the status field was updated</span></span>
<span data-ttu-id="5c689-202">targetDevices</span><span class="sxs-lookup"><span data-stu-id="5c689-202">targetDevices</span></span> | <span data-ttu-id="5c689-203">Long</span><span class="sxs-lookup"><span data-stu-id="5c689-203">Long</span></span> | <span data-ttu-id="5c689-204">此修復適用的公開裝置數目</span><span class="sxs-lookup"><span data-stu-id="5c689-204">Number of exposed devices that this remediation is applicable to</span></span>
<span data-ttu-id="5c689-205">標題</span><span class="sxs-lookup"><span data-stu-id="5c689-205">title</span></span> | <span data-ttu-id="5c689-206">String</span><span class="sxs-lookup"><span data-stu-id="5c689-206">String</span></span> | <span data-ttu-id="5c689-207">此修復活動的標題</span><span class="sxs-lookup"><span data-stu-id="5c689-207">Title of this remediation activity</span></span>
<span data-ttu-id="5c689-208">類型</span><span class="sxs-lookup"><span data-stu-id="5c689-208">type</span></span> | <span data-ttu-id="5c689-209">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-209">String</span></span> | <span data-ttu-id="5c689-210">修正類型</span><span class="sxs-lookup"><span data-stu-id="5c689-210">Remediation type</span></span>
<span data-ttu-id="5c689-211">vendorId</span><span class="sxs-lookup"><span data-stu-id="5c689-211">vendorId</span></span> | <span data-ttu-id="5c689-212">字串</span><span class="sxs-lookup"><span data-stu-id="5c689-212">String</span></span> | <span data-ttu-id="5c689-213">相關的供應商名稱</span><span class="sxs-lookup"><span data-stu-id="5c689-213">Related vendor name</span></span>

## <a name="see-also"></a><span data-ttu-id="5c689-214">請參閱</span><span class="sxs-lookup"><span data-stu-id="5c689-214">See also</span></span>

- [<span data-ttu-id="5c689-215">根據識別碼取得一個補救活動</span><span class="sxs-lookup"><span data-stu-id="5c689-215">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="5c689-216">列出所有補救活動</span><span class="sxs-lookup"><span data-stu-id="5c689-216">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="5c689-217">列出一個補救活動的公開裝置</span><span class="sxs-lookup"><span data-stu-id="5c689-217">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="5c689-218">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="5c689-218">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="5c689-219">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="5c689-219">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
