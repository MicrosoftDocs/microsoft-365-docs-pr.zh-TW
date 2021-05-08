---
title: 根據識別碼取得一個補救活動
description: 傳回指定之修復活動的資訊。
keywords: api，修正，修正 api，get，修正任務，依識別碼修正
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
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244440"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="115dc-104">根據識別碼取得一個補救活動</span><span class="sxs-lookup"><span data-stu-id="115dc-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="115dc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="115dc-105">**Applies to:**</span></span>

- [<span data-ttu-id="115dc-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="115dc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="115dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="115dc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="115dc-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="115dc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="115dc-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="115dc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="115dc-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="115dc-110">API description</span></span>

<span data-ttu-id="115dc-111">傳回指定之修復活動的資訊。</span><span class="sxs-lookup"><span data-stu-id="115dc-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="115dc-112">會呈現與 [ [取得所有修復活動](get-remediation-all-activities.md)] 相同的資料行，但只會傳回 _其中一個指定的修復活動_ 的結果。</span><span class="sxs-lookup"><span data-stu-id="115dc-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="115dc-113">[深入瞭解修復活動](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="115dc-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="115dc-114">列出 (識別碼的指定修復活動) </span><span class="sxs-lookup"><span data-stu-id="115dc-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="115dc-115">**URL:** GET:/api/remediationTasks/ \{ 識別碼\}</span><span class="sxs-lookup"><span data-stu-id="115dc-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="115dc-116">權限</span><span class="sxs-lookup"><span data-stu-id="115dc-116">Permissions</span></span>

<span data-ttu-id="115dc-117">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="115dc-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="115dc-118">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="115dc-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="115dc-119">許可權類型</span><span class="sxs-lookup"><span data-stu-id="115dc-119">Permission type</span></span> | <span data-ttu-id="115dc-120">權限</span><span class="sxs-lookup"><span data-stu-id="115dc-120">Permission</span></span> | <span data-ttu-id="115dc-121">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="115dc-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="115dc-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="115dc-122">Application</span></span> | <span data-ttu-id="115dc-123">RemediationTask Read。 All</span><span class="sxs-lookup"><span data-stu-id="115dc-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="115dc-124">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="115dc-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="115dc-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="115dc-125">Delegated (work or school account)</span></span> | <span data-ttu-id="115dc-126">RemediationTask 讀取。</span><span class="sxs-lookup"><span data-stu-id="115dc-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="115dc-127">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="115dc-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="115dc-128">屬性</span><span class="sxs-lookup"><span data-stu-id="115dc-128">Properties</span></span>

<span data-ttu-id="115dc-129">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="115dc-129">Property (id)</span></span> | <span data-ttu-id="115dc-130">資料類型</span><span class="sxs-lookup"><span data-stu-id="115dc-130">Data type</span></span> | <span data-ttu-id="115dc-131">描述</span><span class="sxs-lookup"><span data-stu-id="115dc-131">Description</span></span> | <span data-ttu-id="115dc-132">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="115dc-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="115dc-133">類別</span><span class="sxs-lookup"><span data-stu-id="115dc-133">category</span></span> | <span data-ttu-id="115dc-134">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-134">String</span></span> | <span data-ttu-id="115dc-135"> (軟體/安全性設定) 的修復活動類別</span><span class="sxs-lookup"><span data-stu-id="115dc-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="115dc-136">軟體</span><span class="sxs-lookup"><span data-stu-id="115dc-136">Software</span></span>
<span data-ttu-id="115dc-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="115dc-137">completerEmail</span></span> | <span data-ttu-id="115dc-138">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-138">String</span></span> | <span data-ttu-id="115dc-139">若某人已手動完成修復活動，此欄會包含他們的電子郵件</span><span class="sxs-lookup"><span data-stu-id="115dc-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="115dc-140">Null</span><span class="sxs-lookup"><span data-stu-id="115dc-140">null</span></span>
<span data-ttu-id="115dc-141">completerId</span><span class="sxs-lookup"><span data-stu-id="115dc-141">completerId</span></span> | <span data-ttu-id="115dc-142">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-142">String</span></span> | <span data-ttu-id="115dc-143">若某人已手動完成修復活動，此欄會包含其物件識別碼</span><span class="sxs-lookup"><span data-stu-id="115dc-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="115dc-144">Null</span><span class="sxs-lookup"><span data-stu-id="115dc-144">null</span></span>
<span data-ttu-id="115dc-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="115dc-145">completionMethod</span></span> | <span data-ttu-id="115dc-146">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-146">String</span></span> | <span data-ttu-id="115dc-147">如果所有裝置都已) 或「手動」或「手動」（由選取「標記為完成」）進行修補，便可完成「 (自動」的修復活動。</span><span class="sxs-lookup"><span data-stu-id="115dc-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="115dc-148">自動</span><span class="sxs-lookup"><span data-stu-id="115dc-148">Automatic</span></span>
<span data-ttu-id="115dc-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="115dc-149">createdOn</span></span> | <span data-ttu-id="115dc-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="115dc-150">DateTime</span></span> | <span data-ttu-id="115dc-151">建立此修復活動的時間</span><span class="sxs-lookup"><span data-stu-id="115dc-151">Time this remediation activity was created</span></span> | <span data-ttu-id="115dc-152">2021-01-12T18：54： 11.5499478 Z</span><span class="sxs-lookup"><span data-stu-id="115dc-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="115dc-153">描述</span><span class="sxs-lookup"><span data-stu-id="115dc-153">description</span></span> | <span data-ttu-id="115dc-154">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-154">String</span></span> | <span data-ttu-id="115dc-155">此修復活動的描述</span><span class="sxs-lookup"><span data-stu-id="115dc-155">Description of this remediation activity</span></span> | <span data-ttu-id="115dc-156">將 Microsoft Silverlight 更新成更新的版本，以減輕影響裝置的已知弱點。</span><span class="sxs-lookup"><span data-stu-id="115dc-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="115dc-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="115dc-157">dueOn</span></span> | <span data-ttu-id="115dc-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="115dc-158">DateTime</span></span> | <span data-ttu-id="115dc-159">到期日此修復活動的建立者設定</span><span class="sxs-lookup"><span data-stu-id="115dc-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="115dc-160">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="115dc-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="115dc-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="115dc-161">fixedDevices</span></span> |  | <span data-ttu-id="115dc-162">已修復的裝置數目</span><span class="sxs-lookup"><span data-stu-id="115dc-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="115dc-163">第</span><span class="sxs-lookup"><span data-stu-id="115dc-163">2</span></span>
<span data-ttu-id="115dc-164">id</span><span class="sxs-lookup"><span data-stu-id="115dc-164">id</span></span> | <span data-ttu-id="115dc-165">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-165">String</span></span> | <span data-ttu-id="115dc-166">此修復活動的識別碼</span><span class="sxs-lookup"><span data-stu-id="115dc-166">ID of this remediation activity</span></span> | <span data-ttu-id="115dc-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="115dc-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="115dc-168">nameId</span><span class="sxs-lookup"><span data-stu-id="115dc-168">nameId</span></span> | <span data-ttu-id="115dc-169">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-169">String</span></span> | <span data-ttu-id="115dc-170">相關產品名稱</span><span class="sxs-lookup"><span data-stu-id="115dc-170">Related product name</span></span> | <span data-ttu-id="115dc-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="115dc-171">Microsoft Silverlight</span></span>
<span data-ttu-id="115dc-172">優先</span><span class="sxs-lookup"><span data-stu-id="115dc-172">priority</span></span> | <span data-ttu-id="115dc-173">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-173">String</span></span> | <span data-ttu-id="115dc-174">為此修復活動的建立者設定的優先順序 (High\Medium\Low) </span><span class="sxs-lookup"><span data-stu-id="115dc-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="115dc-175">高</span><span class="sxs-lookup"><span data-stu-id="115dc-175">High</span></span>
<span data-ttu-id="115dc-176">Id</span><span class="sxs-lookup"><span data-stu-id="115dc-176">productId</span></span> | <span data-ttu-id="115dc-177">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-177">String</span></span> | <span data-ttu-id="115dc-178">相關產品識別碼</span><span class="sxs-lookup"><span data-stu-id="115dc-178">Related product ID</span></span> | <span data-ttu-id="115dc-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="115dc-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="115dc-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="115dc-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="115dc-181">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-181">String</span></span> | <span data-ttu-id="115dc-182">只會對沒有使用者影響的裝置要求一些設定變更。</span><span class="sxs-lookup"><span data-stu-id="115dc-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="115dc-183">此值表示「所有公開的裝置」或「只有沒有使用者影響的裝置」之間的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="115dc-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="115dc-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="115dc-184">AllExposedAssets</span></span>
<span data-ttu-id="115dc-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="115dc-185">rbacGroupNames</span></span> | <span data-ttu-id="115dc-186">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-186">String</span></span> | <span data-ttu-id="115dc-187">相關的裝置群組名稱</span><span class="sxs-lookup"><span data-stu-id="115dc-187">Related device group names</span></span> | <span data-ttu-id="115dc-188">[「Windows Servers "，" Windows 10 "]</span><span class="sxs-lookup"><span data-stu-id="115dc-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="115dc-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="115dc-189">recommendedProgram</span></span> | <span data-ttu-id="115dc-190">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-190">String</span></span> | <span data-ttu-id="115dc-191">升級為的建議程式</span><span class="sxs-lookup"><span data-stu-id="115dc-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="115dc-192">Null</span><span class="sxs-lookup"><span data-stu-id="115dc-192">null</span></span>
<span data-ttu-id="115dc-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="115dc-193">recommendedVendor</span></span> | <span data-ttu-id="115dc-194">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-194">String</span></span> | <span data-ttu-id="115dc-195">升級為的建議供應商</span><span class="sxs-lookup"><span data-stu-id="115dc-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="115dc-196">Null</span><span class="sxs-lookup"><span data-stu-id="115dc-196">null</span></span>
<span data-ttu-id="115dc-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="115dc-197">recommendedVersion</span></span> | <span data-ttu-id="115dc-198">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-198">String</span></span> | <span data-ttu-id="115dc-199">更新/升級的建議版本</span><span class="sxs-lookup"><span data-stu-id="115dc-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="115dc-200">Null</span><span class="sxs-lookup"><span data-stu-id="115dc-200">null</span></span>
<span data-ttu-id="115dc-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="115dc-201">relatedComponent</span></span> | <span data-ttu-id="115dc-202">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-202">String</span></span> | <span data-ttu-id="115dc-203">此修復活動的相關元件 (類似安全性建議的相關元件) </span><span class="sxs-lookup"><span data-stu-id="115dc-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="115dc-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="115dc-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="115dc-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="115dc-205">requesterEmail</span></span> | <span data-ttu-id="115dc-206">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-206">String</span></span> | <span data-ttu-id="115dc-207">建立者電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="115dc-207">Creator email address</span></span> | <span data-ttu-id="115dc-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="115dc-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="115dc-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="115dc-209">requesterId</span></span> | <span data-ttu-id="115dc-210">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-210">String</span></span> | <span data-ttu-id="115dc-211">Creator 物件識別碼</span><span class="sxs-lookup"><span data-stu-id="115dc-211">Creator object id</span></span> | <span data-ttu-id="115dc-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="115dc-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="115dc-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="115dc-213">requesterNotes</span></span> | <span data-ttu-id="115dc-214">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-214">String</span></span> | <span data-ttu-id="115dc-215">為此修復活動新增的建立者) 附注 (自由文字</span><span class="sxs-lookup"><span data-stu-id="115dc-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="115dc-216">Null</span><span class="sxs-lookup"><span data-stu-id="115dc-216">null</span></span>
<span data-ttu-id="115dc-217">Scid</span><span class="sxs-lookup"><span data-stu-id="115dc-217">scid</span></span> | <span data-ttu-id="115dc-218">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-218">String</span></span> | <span data-ttu-id="115dc-219">相關安全性建議的 SCID</span><span class="sxs-lookup"><span data-stu-id="115dc-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="115dc-220">Null</span><span class="sxs-lookup"><span data-stu-id="115dc-220">null</span></span>
<span data-ttu-id="115dc-221">地位</span><span class="sxs-lookup"><span data-stu-id="115dc-221">status</span></span> | <span data-ttu-id="115dc-222">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-222">String</span></span> | <span data-ttu-id="115dc-223">修復活動狀態 (Active/已完成) </span><span class="sxs-lookup"><span data-stu-id="115dc-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="115dc-224">作用中</span><span class="sxs-lookup"><span data-stu-id="115dc-224">Active</span></span>
<span data-ttu-id="115dc-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="115dc-225">statusLastModifiedOn</span></span> | <span data-ttu-id="115dc-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="115dc-226">DateTime</span></span> | <span data-ttu-id="115dc-227">更新狀態欄位的日期</span><span class="sxs-lookup"><span data-stu-id="115dc-227">Date when the status field was updated</span></span> | <span data-ttu-id="115dc-228">2021-01-12T18：54： 11.5499487 Z</span><span class="sxs-lookup"><span data-stu-id="115dc-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="115dc-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="115dc-229">targetDevices</span></span> | <span data-ttu-id="115dc-230">Long</span><span class="sxs-lookup"><span data-stu-id="115dc-230">Long</span></span> | <span data-ttu-id="115dc-231">此修復適用的公開裝置數目</span><span class="sxs-lookup"><span data-stu-id="115dc-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="115dc-232">43</span><span class="sxs-lookup"><span data-stu-id="115dc-232">43</span></span>
<span data-ttu-id="115dc-233">標題</span><span class="sxs-lookup"><span data-stu-id="115dc-233">title</span></span> | <span data-ttu-id="115dc-234">String</span><span class="sxs-lookup"><span data-stu-id="115dc-234">String</span></span> | <span data-ttu-id="115dc-235">此修復活動的標題</span><span class="sxs-lookup"><span data-stu-id="115dc-235">Title of this remediation activity</span></span> | <span data-ttu-id="115dc-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="115dc-236">Microsoft Silverlight</span></span>
<span data-ttu-id="115dc-237">類型</span><span class="sxs-lookup"><span data-stu-id="115dc-237">type</span></span> | <span data-ttu-id="115dc-238">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-238">String</span></span> | <span data-ttu-id="115dc-239">修正類型</span><span class="sxs-lookup"><span data-stu-id="115dc-239">Remediation type</span></span> | <span data-ttu-id="115dc-240">Update</span><span class="sxs-lookup"><span data-stu-id="115dc-240">Update</span></span>
<span data-ttu-id="115dc-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="115dc-241">vendorId</span></span> | <span data-ttu-id="115dc-242">字串</span><span class="sxs-lookup"><span data-stu-id="115dc-242">String</span></span> | <span data-ttu-id="115dc-243">相關的供應商名稱</span><span class="sxs-lookup"><span data-stu-id="115dc-243">Related vendor name</span></span> | <span data-ttu-id="115dc-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="115dc-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="115dc-245">範例</span><span class="sxs-lookup"><span data-stu-id="115dc-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="115dc-246">要求範例</span><span class="sxs-lookup"><span data-stu-id="115dc-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="115dc-247">回應範例</span><span class="sxs-lookup"><span data-stu-id="115dc-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="115dc-248">另請參閱</span><span class="sxs-lookup"><span data-stu-id="115dc-248">See also</span></span>

- [<span data-ttu-id="115dc-249">修正方法和屬性</span><span class="sxs-lookup"><span data-stu-id="115dc-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="115dc-250">列出所有補救活動</span><span class="sxs-lookup"><span data-stu-id="115dc-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="115dc-251">列出一個補救活動的公開裝置</span><span class="sxs-lookup"><span data-stu-id="115dc-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="115dc-252">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="115dc-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="115dc-253">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="115dc-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
