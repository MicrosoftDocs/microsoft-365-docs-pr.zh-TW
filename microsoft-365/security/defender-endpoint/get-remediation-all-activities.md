---
title: 列出所有修復活動
description: 傳回所有修復活動的資訊。
keywords: api，修正，修正 api，get，修復工作，
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
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061107"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="b0ff4-104">列出所有修復活動</span><span class="sxs-lookup"><span data-stu-id="b0ff4-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0ff4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b0ff4-105">**Applies to:**</span></span>

- [<span data-ttu-id="b0ff4-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0ff4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b0ff4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0ff4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b0ff4-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b0ff4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b0ff4-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b0ff4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b0ff4-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="b0ff4-110">API description</span></span>

<span data-ttu-id="b0ff4-111">傳回所有修復活動的資訊。</span><span class="sxs-lookup"><span data-stu-id="b0ff4-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="b0ff4-112">[深入瞭解修復活動](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="b0ff4-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="b0ff4-113">**URL:** GET:/api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="b0ff4-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="b0ff4-114">**屬性** 詳細資料</span><span class="sxs-lookup"><span data-stu-id="b0ff4-114">**Properties** details</span></span>

<span data-ttu-id="b0ff4-115">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="b0ff4-115">Property (id)</span></span> | <span data-ttu-id="b0ff4-116">資料類型</span><span class="sxs-lookup"><span data-stu-id="b0ff4-116">Data type</span></span> | <span data-ttu-id="b0ff4-117">描述</span><span class="sxs-lookup"><span data-stu-id="b0ff4-117">Description</span></span> | <span data-ttu-id="b0ff4-118">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="b0ff4-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="b0ff4-119">類別</span><span class="sxs-lookup"><span data-stu-id="b0ff4-119">category</span></span> | <span data-ttu-id="b0ff4-120">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-120">String</span></span> | <span data-ttu-id="b0ff4-121"> (軟體/安全性設定) 的修復活動類別</span><span class="sxs-lookup"><span data-stu-id="b0ff4-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="b0ff4-122">軟體</span><span class="sxs-lookup"><span data-stu-id="b0ff4-122">Software</span></span>
<span data-ttu-id="b0ff4-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="b0ff4-123">completerEmail</span></span> | <span data-ttu-id="b0ff4-124">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-124">String</span></span> | <span data-ttu-id="b0ff4-125">若某人已手動完成修復活動，此欄會包含他們的電子郵件</span><span class="sxs-lookup"><span data-stu-id="b0ff4-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="b0ff4-126">Null</span><span class="sxs-lookup"><span data-stu-id="b0ff4-126">null</span></span>
<span data-ttu-id="b0ff4-127">completerId</span><span class="sxs-lookup"><span data-stu-id="b0ff4-127">completerId</span></span> | <span data-ttu-id="b0ff4-128">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-128">String</span></span> | <span data-ttu-id="b0ff4-129">若某人已手動完成修復活動，此欄會包含其物件識別碼</span><span class="sxs-lookup"><span data-stu-id="b0ff4-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="b0ff4-130">Null</span><span class="sxs-lookup"><span data-stu-id="b0ff4-130">null</span></span>
<span data-ttu-id="b0ff4-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="b0ff4-131">completionMethod</span></span> | <span data-ttu-id="b0ff4-132">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-132">String</span></span> | <span data-ttu-id="b0ff4-133">如果所有裝置都已) 或「手動」或「手動」（由選取「標記為完成」）進行修補，便可完成「 (自動」的修復活動。</span><span class="sxs-lookup"><span data-stu-id="b0ff4-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="b0ff4-134">自動</span><span class="sxs-lookup"><span data-stu-id="b0ff4-134">Automatic</span></span>
<span data-ttu-id="b0ff4-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="b0ff4-135">createdOn</span></span> | <span data-ttu-id="b0ff4-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="b0ff4-136">DateTime</span></span> | <span data-ttu-id="b0ff4-137">建立此修復活動的時間</span><span class="sxs-lookup"><span data-stu-id="b0ff4-137">Time this remediation activity was created</span></span> | <span data-ttu-id="b0ff4-138">2021-01-12T18：54： 11.5499478 Z</span><span class="sxs-lookup"><span data-stu-id="b0ff4-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="b0ff4-139">描述</span><span class="sxs-lookup"><span data-stu-id="b0ff4-139">description</span></span> | <span data-ttu-id="b0ff4-140">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-140">String</span></span> | <span data-ttu-id="b0ff4-141">此修復活動的描述</span><span class="sxs-lookup"><span data-stu-id="b0ff4-141">Description of this remediation activity</span></span> | <span data-ttu-id="b0ff4-142">將 Chrome 更新為更新的版本，以減輕影響裝置的1248已知弱點。</span><span class="sxs-lookup"><span data-stu-id="b0ff4-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="b0ff4-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="b0ff4-143">dueOn</span></span> | <span data-ttu-id="b0ff4-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="b0ff4-144">DateTime</span></span> | <span data-ttu-id="b0ff4-145">到期日此修復活動的建立者設定</span><span class="sxs-lookup"><span data-stu-id="b0ff4-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="b0ff4-146">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="b0ff4-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="b0ff4-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="b0ff4-147">fixedDevices</span></span> | <span data-ttu-id="b0ff4-148">.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-148">.</span></span> | <span data-ttu-id="b0ff4-149">已修復的裝置數目</span><span class="sxs-lookup"><span data-stu-id="b0ff4-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="b0ff4-150">第</span><span class="sxs-lookup"><span data-stu-id="b0ff4-150">2</span></span>
<span data-ttu-id="b0ff4-151">id</span><span class="sxs-lookup"><span data-stu-id="b0ff4-151">id</span></span> | <span data-ttu-id="b0ff4-152">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-152">String</span></span> | <span data-ttu-id="b0ff4-153">此修復活動的識別碼</span><span class="sxs-lookup"><span data-stu-id="b0ff4-153">ID of this remediation activity</span></span> | <span data-ttu-id="b0ff4-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="b0ff4-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="b0ff4-155">nameId</span><span class="sxs-lookup"><span data-stu-id="b0ff4-155">nameId</span></span> | <span data-ttu-id="b0ff4-156">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-156">String</span></span> | <span data-ttu-id="b0ff4-157">相關產品名稱</span><span class="sxs-lookup"><span data-stu-id="b0ff4-157">Related product name</span></span> | <span data-ttu-id="b0ff4-158">鉻</span><span class="sxs-lookup"><span data-stu-id="b0ff4-158">chrome</span></span>
<span data-ttu-id="b0ff4-159">優先</span><span class="sxs-lookup"><span data-stu-id="b0ff4-159">priority</span></span> | <span data-ttu-id="b0ff4-160">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-160">String</span></span> | <span data-ttu-id="b0ff4-161">為此修復活動的建立者設定的優先順序 (High\Medium\Low) </span><span class="sxs-lookup"><span data-stu-id="b0ff4-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="b0ff4-162">高</span><span class="sxs-lookup"><span data-stu-id="b0ff4-162">High</span></span>
<span data-ttu-id="b0ff4-163">Id</span><span class="sxs-lookup"><span data-stu-id="b0ff4-163">productId</span></span> | <span data-ttu-id="b0ff4-164">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-164">String</span></span> | <span data-ttu-id="b0ff4-165">相關產品識別碼</span><span class="sxs-lookup"><span data-stu-id="b0ff4-165">Related product ID</span></span> | <span data-ttu-id="b0ff4-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="b0ff4-166">google-_-chrome</span></span>
<span data-ttu-id="b0ff4-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="b0ff4-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="b0ff4-168">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-168">String</span></span> | <span data-ttu-id="b0ff4-169">只會對沒有使用者影響的裝置要求一些設定變更。</span><span class="sxs-lookup"><span data-stu-id="b0ff4-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="b0ff4-170">此值表示「所有公開的裝置」或「只有沒有使用者影響的裝置」之間的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="b0ff4-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="b0ff4-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="b0ff4-171">AllExposedAssets</span></span>
<span data-ttu-id="b0ff4-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="b0ff4-172">rbacGroupNames</span></span> | <span data-ttu-id="b0ff4-173">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-173">String</span></span> | <span data-ttu-id="b0ff4-174">相關的裝置群組名稱</span><span class="sxs-lookup"><span data-stu-id="b0ff4-174">Related device group names</span></span> | <span data-ttu-id="b0ff4-175">[Windows Servers]，"Windows 10"]</span><span class="sxs-lookup"><span data-stu-id="b0ff4-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="b0ff4-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="b0ff4-176">recommendedProgram</span></span> | <span data-ttu-id="b0ff4-177">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-177">String</span></span> | <span data-ttu-id="b0ff4-178">升級為的建議程式</span><span class="sxs-lookup"><span data-stu-id="b0ff4-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="b0ff4-179">Null</span><span class="sxs-lookup"><span data-stu-id="b0ff4-179">null</span></span>
<span data-ttu-id="b0ff4-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="b0ff4-180">recommendedVendor</span></span> | <span data-ttu-id="b0ff4-181">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-181">String</span></span> | <span data-ttu-id="b0ff4-182">升級為的建議供應商</span><span class="sxs-lookup"><span data-stu-id="b0ff4-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="b0ff4-183">Null</span><span class="sxs-lookup"><span data-stu-id="b0ff4-183">null</span></span>
<span data-ttu-id="b0ff4-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="b0ff4-184">recommendedVersion</span></span> | <span data-ttu-id="b0ff4-185">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-185">String</span></span> | <span data-ttu-id="b0ff4-186">更新/升級的建議版本</span><span class="sxs-lookup"><span data-stu-id="b0ff4-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="b0ff4-187">Null</span><span class="sxs-lookup"><span data-stu-id="b0ff4-187">null</span></span>
<span data-ttu-id="b0ff4-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="b0ff4-188">relatedComponent</span></span> | <span data-ttu-id="b0ff4-189">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-189">String</span></span> | <span data-ttu-id="b0ff4-190">此修復活動的相關元件 (類似安全性建議的相關元件) </span><span class="sxs-lookup"><span data-stu-id="b0ff4-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="b0ff4-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="b0ff4-191">Google Chrome</span></span>
<span data-ttu-id="b0ff4-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="b0ff4-192">requesterEmail</span></span> | <span data-ttu-id="b0ff4-193">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-193">String</span></span> | <span data-ttu-id="b0ff4-194">建立者電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="b0ff4-194">Creator email address</span></span> | <span data-ttu-id="b0ff4-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b0ff4-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="b0ff4-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="b0ff4-196">requesterId</span></span> | <span data-ttu-id="b0ff4-197">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-197">String</span></span> | <span data-ttu-id="b0ff4-198">Creator 物件識別碼</span><span class="sxs-lookup"><span data-stu-id="b0ff4-198">Creator object id</span></span> | <span data-ttu-id="b0ff4-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="b0ff4-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="b0ff4-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="b0ff4-200">requesterNotes</span></span> | <span data-ttu-id="b0ff4-201">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-201">String</span></span> | <span data-ttu-id="b0ff4-202">為此修復活動新增的建立者) 附注 (自由文字</span><span class="sxs-lookup"><span data-stu-id="b0ff4-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="b0ff4-203">Null</span><span class="sxs-lookup"><span data-stu-id="b0ff4-203">null</span></span>
<span data-ttu-id="b0ff4-204">Scid</span><span class="sxs-lookup"><span data-stu-id="b0ff4-204">scid</span></span> | <span data-ttu-id="b0ff4-205">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-205">String</span></span> | <span data-ttu-id="b0ff4-206">相關安全性建議的 SCID</span><span class="sxs-lookup"><span data-stu-id="b0ff4-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="b0ff4-207">Null</span><span class="sxs-lookup"><span data-stu-id="b0ff4-207">null</span></span>
<span data-ttu-id="b0ff4-208">地位</span><span class="sxs-lookup"><span data-stu-id="b0ff4-208">status</span></span> | <span data-ttu-id="b0ff4-209">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-209">String</span></span> | <span data-ttu-id="b0ff4-210">修復活動狀態 (Active/已完成) </span><span class="sxs-lookup"><span data-stu-id="b0ff4-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="b0ff4-211">作用中</span><span class="sxs-lookup"><span data-stu-id="b0ff4-211">Active</span></span>
<span data-ttu-id="b0ff4-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="b0ff4-212">statusLastModifiedOn</span></span> | <span data-ttu-id="b0ff4-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="b0ff4-213">DateTime</span></span> | <span data-ttu-id="b0ff4-214">更新狀態欄位的日期</span><span class="sxs-lookup"><span data-stu-id="b0ff4-214">Date when the status field was updated</span></span> | <span data-ttu-id="b0ff4-215">2021-01-12T18：54： 11.5499487 Z</span><span class="sxs-lookup"><span data-stu-id="b0ff4-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="b0ff4-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="b0ff4-216">targetDevices</span></span> | <span data-ttu-id="b0ff4-217">Long</span><span class="sxs-lookup"><span data-stu-id="b0ff4-217">Long</span></span> | <span data-ttu-id="b0ff4-218">此修復適用的公開裝置數目</span><span class="sxs-lookup"><span data-stu-id="b0ff4-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="b0ff4-219">43</span><span class="sxs-lookup"><span data-stu-id="b0ff4-219">43</span></span>
<span data-ttu-id="b0ff4-220">標題</span><span class="sxs-lookup"><span data-stu-id="b0ff4-220">title</span></span> | <span data-ttu-id="b0ff4-221">String</span><span class="sxs-lookup"><span data-stu-id="b0ff4-221">String</span></span> | <span data-ttu-id="b0ff4-222">此修復活動的標題</span><span class="sxs-lookup"><span data-stu-id="b0ff4-222">Title of this remediation activity</span></span> | <span data-ttu-id="b0ff4-223">更新 Google Chrome</span><span class="sxs-lookup"><span data-stu-id="b0ff4-223">Update Google Chrome</span></span>
<span data-ttu-id="b0ff4-224">類型</span><span class="sxs-lookup"><span data-stu-id="b0ff4-224">type</span></span> | <span data-ttu-id="b0ff4-225">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-225">String</span></span> | <span data-ttu-id="b0ff4-226">修正類型</span><span class="sxs-lookup"><span data-stu-id="b0ff4-226">Remediation type</span></span> | <span data-ttu-id="b0ff4-227">Update</span><span class="sxs-lookup"><span data-stu-id="b0ff4-227">Update</span></span>
<span data-ttu-id="b0ff4-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="b0ff4-228">vendorId</span></span> | <span data-ttu-id="b0ff4-229">字串</span><span class="sxs-lookup"><span data-stu-id="b0ff4-229">String</span></span> | <span data-ttu-id="b0ff4-230">相關的供應商名稱</span><span class="sxs-lookup"><span data-stu-id="b0ff4-230">Related vendor name</span></span> | <span data-ttu-id="b0ff4-231">谷歌</span><span class="sxs-lookup"><span data-stu-id="b0ff4-231">google</span></span>

## <a name="example"></a><span data-ttu-id="b0ff4-232">範例</span><span class="sxs-lookup"><span data-stu-id="b0ff4-232">Example</span></span>

<span data-ttu-id="b0ff4-233">**要求** 範例</span><span class="sxs-lookup"><span data-stu-id="b0ff4-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="b0ff4-234">**回應** 範例</span><span class="sxs-lookup"><span data-stu-id="b0ff4-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="b0ff4-235">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b0ff4-235">See also</span></span>

- [<span data-ttu-id="b0ff4-236">修正方法和屬性</span><span class="sxs-lookup"><span data-stu-id="b0ff4-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="b0ff4-237">依識別碼取得一個修復活動</span><span class="sxs-lookup"><span data-stu-id="b0ff4-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="b0ff4-238">列出某項修復活動的公開裝置</span><span class="sxs-lookup"><span data-stu-id="b0ff4-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="b0ff4-239">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="b0ff4-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="b0ff4-240">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="b0ff4-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
