---
title: 依識別碼取得一個修復活動
description: 傳回指定之修復活動的資訊。
keywords: api、修正、修正 api、get、修復工作、清單
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061108"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="5ec8e-104">依識別碼取得一個修復活動</span><span class="sxs-lookup"><span data-stu-id="5ec8e-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ec8e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5ec8e-105">**Applies to:**</span></span>

- [<span data-ttu-id="5ec8e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5ec8e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ec8e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ec8e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5ec8e-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="5ec8e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ec8e-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="5ec8e-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="5ec8e-110">API description</span></span>

<span data-ttu-id="5ec8e-111">傳回指定之修復活動的資訊。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="5ec8e-112">會呈現與 [ [取得所有修復活動](get-remediation-all-activities.md)] 相同的資料行，但只會傳回 _其中一個指定的修復活動_ 的結果。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="5ec8e-113">[深入瞭解修復活動](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="5ec8e-114">列出 (識別碼的指定修復活動) </span><span class="sxs-lookup"><span data-stu-id="5ec8e-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="5ec8e-115">**URL:** GET:/api/remediationTasks/ \{ 識別碼\}</span><span class="sxs-lookup"><span data-stu-id="5ec8e-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="5ec8e-116">**屬性** 詳細資料</span><span class="sxs-lookup"><span data-stu-id="5ec8e-116">**Properties** details</span></span>

<span data-ttu-id="5ec8e-117">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="5ec8e-117">Property (id)</span></span> | <span data-ttu-id="5ec8e-118">資料類型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-118">Data type</span></span> | <span data-ttu-id="5ec8e-119">描述</span><span class="sxs-lookup"><span data-stu-id="5ec8e-119">Description</span></span> | <span data-ttu-id="5ec8e-120">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="5ec8e-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="5ec8e-121">類別</span><span class="sxs-lookup"><span data-stu-id="5ec8e-121">category</span></span> | <span data-ttu-id="5ec8e-122">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-122">String</span></span> | <span data-ttu-id="5ec8e-123"> (軟體/安全性設定) 的修復活動類別</span><span class="sxs-lookup"><span data-stu-id="5ec8e-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="5ec8e-124">軟體</span><span class="sxs-lookup"><span data-stu-id="5ec8e-124">Software</span></span>
<span data-ttu-id="5ec8e-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="5ec8e-125">completerEmail</span></span> | <span data-ttu-id="5ec8e-126">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-126">String</span></span> | <span data-ttu-id="5ec8e-127">若某人已手動完成修復活動，此欄會包含他們的電子郵件</span><span class="sxs-lookup"><span data-stu-id="5ec8e-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="5ec8e-128">Null</span><span class="sxs-lookup"><span data-stu-id="5ec8e-128">null</span></span>
<span data-ttu-id="5ec8e-129">completerId</span><span class="sxs-lookup"><span data-stu-id="5ec8e-129">completerId</span></span> | <span data-ttu-id="5ec8e-130">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-130">String</span></span> | <span data-ttu-id="5ec8e-131">若某人已手動完成修復活動，此欄會包含其物件識別碼</span><span class="sxs-lookup"><span data-stu-id="5ec8e-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="5ec8e-132">Null</span><span class="sxs-lookup"><span data-stu-id="5ec8e-132">null</span></span>
<span data-ttu-id="5ec8e-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="5ec8e-133">completionMethod</span></span> | <span data-ttu-id="5ec8e-134">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-134">String</span></span> | <span data-ttu-id="5ec8e-135">如果所有裝置都已) 或「手動」或「手動」（由選取「標記為完成」）進行修補，便可完成「 (自動」的修復活動。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="5ec8e-136">自動</span><span class="sxs-lookup"><span data-stu-id="5ec8e-136">Automatic</span></span>
<span data-ttu-id="5ec8e-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="5ec8e-137">createdOn</span></span> | <span data-ttu-id="5ec8e-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="5ec8e-138">DateTime</span></span> | <span data-ttu-id="5ec8e-139">建立此修復活動的時間</span><span class="sxs-lookup"><span data-stu-id="5ec8e-139">Time this remediation activity was created</span></span> | <span data-ttu-id="5ec8e-140">2021-01-12T18：54： 11.5499478 Z</span><span class="sxs-lookup"><span data-stu-id="5ec8e-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="5ec8e-141">描述</span><span class="sxs-lookup"><span data-stu-id="5ec8e-141">description</span></span> | <span data-ttu-id="5ec8e-142">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-142">String</span></span> | <span data-ttu-id="5ec8e-143">此修復活動的描述</span><span class="sxs-lookup"><span data-stu-id="5ec8e-143">Description of this remediation activity</span></span> | <span data-ttu-id="5ec8e-144">將 Chrome 更新為更新的版本，以減輕影響裝置的1248已知弱點。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="5ec8e-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="5ec8e-145">dueOn</span></span> | <span data-ttu-id="5ec8e-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="5ec8e-146">DateTime</span></span> | <span data-ttu-id="5ec8e-147">到期日此修復活動的建立者設定</span><span class="sxs-lookup"><span data-stu-id="5ec8e-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="5ec8e-148">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="5ec8e-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="5ec8e-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="5ec8e-149">fixedDevices</span></span> |  | <span data-ttu-id="5ec8e-150">已修復的裝置數目</span><span class="sxs-lookup"><span data-stu-id="5ec8e-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="5ec8e-151">第</span><span class="sxs-lookup"><span data-stu-id="5ec8e-151">2</span></span>
<span data-ttu-id="5ec8e-152">id</span><span class="sxs-lookup"><span data-stu-id="5ec8e-152">id</span></span> | <span data-ttu-id="5ec8e-153">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-153">String</span></span> | <span data-ttu-id="5ec8e-154">此修復活動的識別碼</span><span class="sxs-lookup"><span data-stu-id="5ec8e-154">ID of this remediation activity</span></span> | <span data-ttu-id="5ec8e-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="5ec8e-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="5ec8e-156">nameId</span><span class="sxs-lookup"><span data-stu-id="5ec8e-156">nameId</span></span> | <span data-ttu-id="5ec8e-157">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-157">String</span></span> | <span data-ttu-id="5ec8e-158">相關產品名稱</span><span class="sxs-lookup"><span data-stu-id="5ec8e-158">Related product name</span></span> | <span data-ttu-id="5ec8e-159">鉻</span><span class="sxs-lookup"><span data-stu-id="5ec8e-159">chrome</span></span>
<span data-ttu-id="5ec8e-160">優先</span><span class="sxs-lookup"><span data-stu-id="5ec8e-160">priority</span></span> | <span data-ttu-id="5ec8e-161">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-161">String</span></span> | <span data-ttu-id="5ec8e-162">為此修復活動的建立者設定的優先順序 (High\Medium\Low) </span><span class="sxs-lookup"><span data-stu-id="5ec8e-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="5ec8e-163">高</span><span class="sxs-lookup"><span data-stu-id="5ec8e-163">High</span></span>
<span data-ttu-id="5ec8e-164">Id</span><span class="sxs-lookup"><span data-stu-id="5ec8e-164">productId</span></span> | <span data-ttu-id="5ec8e-165">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-165">String</span></span> | <span data-ttu-id="5ec8e-166">相關產品識別碼</span><span class="sxs-lookup"><span data-stu-id="5ec8e-166">Related product ID</span></span> | <span data-ttu-id="5ec8e-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="5ec8e-167">google-_-chrome</span></span>
<span data-ttu-id="5ec8e-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="5ec8e-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="5ec8e-169">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-169">String</span></span> | <span data-ttu-id="5ec8e-170">只會對沒有使用者影響的裝置要求一些設定變更。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="5ec8e-171">此值表示「所有公開的裝置」或「只有沒有使用者影響的裝置」之間的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="5ec8e-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="5ec8e-172">AllExposedAssets</span></span>
<span data-ttu-id="5ec8e-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="5ec8e-173">rbacGroupNames</span></span> | <span data-ttu-id="5ec8e-174">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-174">String</span></span> | <span data-ttu-id="5ec8e-175">相關的裝置群組名稱</span><span class="sxs-lookup"><span data-stu-id="5ec8e-175">Related device group names</span></span> | <span data-ttu-id="5ec8e-176">[Windows Servers]，"Windows 10"]</span><span class="sxs-lookup"><span data-stu-id="5ec8e-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="5ec8e-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="5ec8e-177">recommendedProgram</span></span> | <span data-ttu-id="5ec8e-178">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-178">String</span></span> | <span data-ttu-id="5ec8e-179">升級為的建議程式</span><span class="sxs-lookup"><span data-stu-id="5ec8e-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="5ec8e-180">Null</span><span class="sxs-lookup"><span data-stu-id="5ec8e-180">null</span></span>
<span data-ttu-id="5ec8e-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="5ec8e-181">recommendedVendor</span></span> | <span data-ttu-id="5ec8e-182">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-182">String</span></span> | <span data-ttu-id="5ec8e-183">升級為的建議供應商</span><span class="sxs-lookup"><span data-stu-id="5ec8e-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="5ec8e-184">Null</span><span class="sxs-lookup"><span data-stu-id="5ec8e-184">null</span></span>
<span data-ttu-id="5ec8e-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="5ec8e-185">recommendedVersion</span></span> | <span data-ttu-id="5ec8e-186">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-186">String</span></span> | <span data-ttu-id="5ec8e-187">更新/升級的建議版本</span><span class="sxs-lookup"><span data-stu-id="5ec8e-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="5ec8e-188">Null</span><span class="sxs-lookup"><span data-stu-id="5ec8e-188">null</span></span>
<span data-ttu-id="5ec8e-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="5ec8e-189">relatedComponent</span></span> | <span data-ttu-id="5ec8e-190">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-190">String</span></span> | <span data-ttu-id="5ec8e-191">此修復活動的相關元件 (類似安全性建議的相關元件) </span><span class="sxs-lookup"><span data-stu-id="5ec8e-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="5ec8e-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="5ec8e-192">Google Chrome</span></span>
<span data-ttu-id="5ec8e-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="5ec8e-193">requesterEmail</span></span> | <span data-ttu-id="5ec8e-194">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-194">String</span></span> | <span data-ttu-id="5ec8e-195">建立者電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="5ec8e-195">Creator email address</span></span> | <span data-ttu-id="5ec8e-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ec8e-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="5ec8e-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="5ec8e-197">requesterId</span></span> | <span data-ttu-id="5ec8e-198">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-198">String</span></span> | <span data-ttu-id="5ec8e-199">Creator 物件識別碼</span><span class="sxs-lookup"><span data-stu-id="5ec8e-199">Creator object id</span></span> | <span data-ttu-id="5ec8e-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="5ec8e-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="5ec8e-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="5ec8e-201">requesterNotes</span></span> | <span data-ttu-id="5ec8e-202">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-202">String</span></span> | <span data-ttu-id="5ec8e-203">為此修復活動新增的建立者) 附注 (自由文字</span><span class="sxs-lookup"><span data-stu-id="5ec8e-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="5ec8e-204">Null</span><span class="sxs-lookup"><span data-stu-id="5ec8e-204">null</span></span>
<span data-ttu-id="5ec8e-205">Scid</span><span class="sxs-lookup"><span data-stu-id="5ec8e-205">scid</span></span> | <span data-ttu-id="5ec8e-206">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-206">String</span></span> | <span data-ttu-id="5ec8e-207">相關安全性建議的 SCID</span><span class="sxs-lookup"><span data-stu-id="5ec8e-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="5ec8e-208">Null</span><span class="sxs-lookup"><span data-stu-id="5ec8e-208">null</span></span>
<span data-ttu-id="5ec8e-209">地位</span><span class="sxs-lookup"><span data-stu-id="5ec8e-209">status</span></span> | <span data-ttu-id="5ec8e-210">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-210">String</span></span> | <span data-ttu-id="5ec8e-211">修復活動狀態 (Active/已完成) </span><span class="sxs-lookup"><span data-stu-id="5ec8e-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="5ec8e-212">作用中</span><span class="sxs-lookup"><span data-stu-id="5ec8e-212">Active</span></span>
<span data-ttu-id="5ec8e-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="5ec8e-213">statusLastModifiedOn</span></span> | <span data-ttu-id="5ec8e-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="5ec8e-214">DateTime</span></span> | <span data-ttu-id="5ec8e-215">更新狀態欄位的日期</span><span class="sxs-lookup"><span data-stu-id="5ec8e-215">Date when the status field was updated</span></span> | <span data-ttu-id="5ec8e-216">2021-01-12T18：54： 11.5499487 Z</span><span class="sxs-lookup"><span data-stu-id="5ec8e-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="5ec8e-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="5ec8e-217">targetDevices</span></span> | <span data-ttu-id="5ec8e-218">Long</span><span class="sxs-lookup"><span data-stu-id="5ec8e-218">Long</span></span> | <span data-ttu-id="5ec8e-219">此修復適用的公開裝置數目</span><span class="sxs-lookup"><span data-stu-id="5ec8e-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="5ec8e-220">43</span><span class="sxs-lookup"><span data-stu-id="5ec8e-220">43</span></span>
<span data-ttu-id="5ec8e-221">標題</span><span class="sxs-lookup"><span data-stu-id="5ec8e-221">title</span></span> | <span data-ttu-id="5ec8e-222">String</span><span class="sxs-lookup"><span data-stu-id="5ec8e-222">String</span></span> | <span data-ttu-id="5ec8e-223">此修復活動的標題</span><span class="sxs-lookup"><span data-stu-id="5ec8e-223">Title of this remediation activity</span></span> | <span data-ttu-id="5ec8e-224">更新 Google Chrome</span><span class="sxs-lookup"><span data-stu-id="5ec8e-224">Update Google Chrome</span></span>
<span data-ttu-id="5ec8e-225">類型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-225">type</span></span> | <span data-ttu-id="5ec8e-226">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-226">String</span></span> | <span data-ttu-id="5ec8e-227">修正類型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-227">Remediation type</span></span> | <span data-ttu-id="5ec8e-228">Update</span><span class="sxs-lookup"><span data-stu-id="5ec8e-228">Update</span></span>
<span data-ttu-id="5ec8e-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="5ec8e-229">vendorId</span></span> | <span data-ttu-id="5ec8e-230">字串</span><span class="sxs-lookup"><span data-stu-id="5ec8e-230">String</span></span> | <span data-ttu-id="5ec8e-231">相關的供應商名稱</span><span class="sxs-lookup"><span data-stu-id="5ec8e-231">Related vendor name</span></span> | <span data-ttu-id="5ec8e-232">谷歌</span><span class="sxs-lookup"><span data-stu-id="5ec8e-232">google</span></span>

## <a name="example"></a><span data-ttu-id="5ec8e-233">範例</span><span class="sxs-lookup"><span data-stu-id="5ec8e-233">Example</span></span>

<span data-ttu-id="5ec8e-234">**要求** 範例</span><span class="sxs-lookup"><span data-stu-id="5ec8e-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="5ec8e-235">**回應** 範例</span><span class="sxs-lookup"><span data-stu-id="5ec8e-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="5ec8e-236">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ec8e-236">See also</span></span>

- [<span data-ttu-id="5ec8e-237">修正方法和屬性</span><span class="sxs-lookup"><span data-stu-id="5ec8e-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="5ec8e-238">列出所有修復活動</span><span class="sxs-lookup"><span data-stu-id="5ec8e-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="5ec8e-239">列出某項修復活動的公開裝置</span><span class="sxs-lookup"><span data-stu-id="5ec8e-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="5ec8e-240">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="5ec8e-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="5ec8e-241">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="5ec8e-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
