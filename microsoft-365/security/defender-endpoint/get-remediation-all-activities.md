---
title: 列出所有補救活動
description: 傳回所有修復活動的資訊。
keywords: api，修正，修正 api，get，修復工作，所有修復
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
ms.openlocfilehash: b95fa2da177a3ecb93bcf3e2085be6111c2c641e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770514"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="79466-104">列出所有補救活動</span><span class="sxs-lookup"><span data-stu-id="79466-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79466-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="79466-105">**Applies to:**</span></span>

- [<span data-ttu-id="79466-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="79466-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="79466-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79466-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="79466-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="79466-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79466-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="79466-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="79466-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="79466-110">API description</span></span>

<span data-ttu-id="79466-111">傳回所有修復活動的資訊。</span><span class="sxs-lookup"><span data-stu-id="79466-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="79466-112">[深入瞭解修復活動](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="79466-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="79466-113">**URL:** GET:/api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="79466-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="79466-114">權限</span><span class="sxs-lookup"><span data-stu-id="79466-114">Permissions</span></span>

<span data-ttu-id="79466-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="79466-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="79466-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="79466-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="79466-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="79466-117">Permission type</span></span> | <span data-ttu-id="79466-118">權限</span><span class="sxs-lookup"><span data-stu-id="79466-118">Permission</span></span> | <span data-ttu-id="79466-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="79466-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="79466-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="79466-120">Application</span></span> | <span data-ttu-id="79466-121">RemediationTask Read。 All</span><span class="sxs-lookup"><span data-stu-id="79466-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="79466-122">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="79466-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="79466-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="79466-123">Delegated (work or school account)</span></span> | <span data-ttu-id="79466-124">RemediationTask 讀取。</span><span class="sxs-lookup"><span data-stu-id="79466-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="79466-125">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="79466-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="79466-126">屬性</span><span class="sxs-lookup"><span data-stu-id="79466-126">Properties</span></span>

<span data-ttu-id="79466-127">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="79466-127">Property (id)</span></span> | <span data-ttu-id="79466-128">資料類型</span><span class="sxs-lookup"><span data-stu-id="79466-128">Data type</span></span> | <span data-ttu-id="79466-129">描述</span><span class="sxs-lookup"><span data-stu-id="79466-129">Description</span></span> | <span data-ttu-id="79466-130">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="79466-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="79466-131">類別</span><span class="sxs-lookup"><span data-stu-id="79466-131">category</span></span> | <span data-ttu-id="79466-132">字串</span><span class="sxs-lookup"><span data-stu-id="79466-132">String</span></span> | <span data-ttu-id="79466-133"> (軟體/安全性設定) 的修復活動類別</span><span class="sxs-lookup"><span data-stu-id="79466-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="79466-134">軟體</span><span class="sxs-lookup"><span data-stu-id="79466-134">Software</span></span>
<span data-ttu-id="79466-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="79466-135">completerEmail</span></span> | <span data-ttu-id="79466-136">字串</span><span class="sxs-lookup"><span data-stu-id="79466-136">String</span></span> | <span data-ttu-id="79466-137">若某人已手動完成修復活動，此欄會包含他們的電子郵件</span><span class="sxs-lookup"><span data-stu-id="79466-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="79466-138">Null</span><span class="sxs-lookup"><span data-stu-id="79466-138">null</span></span>
<span data-ttu-id="79466-139">completerId</span><span class="sxs-lookup"><span data-stu-id="79466-139">completerId</span></span> | <span data-ttu-id="79466-140">字串</span><span class="sxs-lookup"><span data-stu-id="79466-140">String</span></span> | <span data-ttu-id="79466-141">若某人已手動完成修復活動，此欄會包含其物件識別碼</span><span class="sxs-lookup"><span data-stu-id="79466-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="79466-142">Null</span><span class="sxs-lookup"><span data-stu-id="79466-142">null</span></span>
<span data-ttu-id="79466-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="79466-143">completionMethod</span></span> | <span data-ttu-id="79466-144">字串</span><span class="sxs-lookup"><span data-stu-id="79466-144">String</span></span> | <span data-ttu-id="79466-145">如果所有裝置都已) 或「手動」或「手動」（由選取「標記為完成」）進行修補，便可完成「 (自動」的修復活動。</span><span class="sxs-lookup"><span data-stu-id="79466-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="79466-146">自動</span><span class="sxs-lookup"><span data-stu-id="79466-146">Automatic</span></span>
<span data-ttu-id="79466-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="79466-147">createdOn</span></span> | <span data-ttu-id="79466-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="79466-148">DateTime</span></span> | <span data-ttu-id="79466-149">建立此修復活動的時間</span><span class="sxs-lookup"><span data-stu-id="79466-149">Time this remediation activity was created</span></span> | <span data-ttu-id="79466-150">2021-01-12T18：54： 11.5499478 Z</span><span class="sxs-lookup"><span data-stu-id="79466-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="79466-151">描述</span><span class="sxs-lookup"><span data-stu-id="79466-151">description</span></span> | <span data-ttu-id="79466-152">字串</span><span class="sxs-lookup"><span data-stu-id="79466-152">String</span></span> | <span data-ttu-id="79466-153">此修復活動的描述</span><span class="sxs-lookup"><span data-stu-id="79466-153">Description of this remediation activity</span></span> | <span data-ttu-id="79466-154">將 Microsoft Silverlight 更新成更新的版本，以減輕影響裝置的已知弱點。</span><span class="sxs-lookup"><span data-stu-id="79466-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="79466-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="79466-155">dueOn</span></span> | <span data-ttu-id="79466-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="79466-156">DateTime</span></span> | <span data-ttu-id="79466-157">到期日此修復活動的建立者設定</span><span class="sxs-lookup"><span data-stu-id="79466-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="79466-158">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="79466-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="79466-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="79466-159">fixedDevices</span></span> | <span data-ttu-id="79466-160">.</span><span class="sxs-lookup"><span data-stu-id="79466-160">.</span></span> | <span data-ttu-id="79466-161">已修復的裝置數目</span><span class="sxs-lookup"><span data-stu-id="79466-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="79466-162">第</span><span class="sxs-lookup"><span data-stu-id="79466-162">2</span></span>
<span data-ttu-id="79466-163">id</span><span class="sxs-lookup"><span data-stu-id="79466-163">id</span></span> | <span data-ttu-id="79466-164">字串</span><span class="sxs-lookup"><span data-stu-id="79466-164">String</span></span> | <span data-ttu-id="79466-165">此修復活動的識別碼</span><span class="sxs-lookup"><span data-stu-id="79466-165">ID of this remediation activity</span></span> | <span data-ttu-id="79466-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="79466-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="79466-167">nameId</span><span class="sxs-lookup"><span data-stu-id="79466-167">nameId</span></span> | <span data-ttu-id="79466-168">字串</span><span class="sxs-lookup"><span data-stu-id="79466-168">String</span></span> | <span data-ttu-id="79466-169">相關產品名稱</span><span class="sxs-lookup"><span data-stu-id="79466-169">Related product name</span></span> | <span data-ttu-id="79466-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="79466-170">Microsoft Silverlight</span></span>
<span data-ttu-id="79466-171">優先</span><span class="sxs-lookup"><span data-stu-id="79466-171">priority</span></span> | <span data-ttu-id="79466-172">字串</span><span class="sxs-lookup"><span data-stu-id="79466-172">String</span></span> | <span data-ttu-id="79466-173">為此修復活動的建立者設定的優先順序 (High\Medium\Low) </span><span class="sxs-lookup"><span data-stu-id="79466-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="79466-174">高</span><span class="sxs-lookup"><span data-stu-id="79466-174">High</span></span>
<span data-ttu-id="79466-175">Id</span><span class="sxs-lookup"><span data-stu-id="79466-175">productId</span></span> | <span data-ttu-id="79466-176">字串</span><span class="sxs-lookup"><span data-stu-id="79466-176">String</span></span> | <span data-ttu-id="79466-177">相關產品識別碼</span><span class="sxs-lookup"><span data-stu-id="79466-177">Related product ID</span></span> | <span data-ttu-id="79466-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="79466-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="79466-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="79466-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="79466-180">字串</span><span class="sxs-lookup"><span data-stu-id="79466-180">String</span></span> | <span data-ttu-id="79466-181">只會對沒有使用者影響的裝置要求一些設定變更。</span><span class="sxs-lookup"><span data-stu-id="79466-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="79466-182">此值表示「所有公開的裝置」或「只有沒有使用者影響的裝置」之間的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="79466-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="79466-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="79466-183">AllExposedAssets</span></span>
<span data-ttu-id="79466-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="79466-184">rbacGroupNames</span></span> | <span data-ttu-id="79466-185">字串</span><span class="sxs-lookup"><span data-stu-id="79466-185">String</span></span> | <span data-ttu-id="79466-186">相關的裝置群組名稱</span><span class="sxs-lookup"><span data-stu-id="79466-186">Related device group names</span></span> | <span data-ttu-id="79466-187">[「Windows Servers "，" Windows 10 "]</span><span class="sxs-lookup"><span data-stu-id="79466-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="79466-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="79466-188">recommendedProgram</span></span> | <span data-ttu-id="79466-189">字串</span><span class="sxs-lookup"><span data-stu-id="79466-189">String</span></span> | <span data-ttu-id="79466-190">升級為的建議程式</span><span class="sxs-lookup"><span data-stu-id="79466-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="79466-191">Null</span><span class="sxs-lookup"><span data-stu-id="79466-191">null</span></span>
<span data-ttu-id="79466-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="79466-192">recommendedVendor</span></span> | <span data-ttu-id="79466-193">字串</span><span class="sxs-lookup"><span data-stu-id="79466-193">String</span></span> | <span data-ttu-id="79466-194">升級為的建議供應商</span><span class="sxs-lookup"><span data-stu-id="79466-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="79466-195">Null</span><span class="sxs-lookup"><span data-stu-id="79466-195">null</span></span>
<span data-ttu-id="79466-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="79466-196">recommendedVersion</span></span> | <span data-ttu-id="79466-197">字串</span><span class="sxs-lookup"><span data-stu-id="79466-197">String</span></span> | <span data-ttu-id="79466-198">更新/升級的建議版本</span><span class="sxs-lookup"><span data-stu-id="79466-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="79466-199">Null</span><span class="sxs-lookup"><span data-stu-id="79466-199">null</span></span>
<span data-ttu-id="79466-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="79466-200">relatedComponent</span></span> | <span data-ttu-id="79466-201">字串</span><span class="sxs-lookup"><span data-stu-id="79466-201">String</span></span> | <span data-ttu-id="79466-202">此修復活動的相關元件 (類似安全性建議的相關元件) </span><span class="sxs-lookup"><span data-stu-id="79466-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="79466-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="79466-203">Microsoft Silverlight</span></span>
<span data-ttu-id="79466-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="79466-204">requesterEmail</span></span> | <span data-ttu-id="79466-205">字串</span><span class="sxs-lookup"><span data-stu-id="79466-205">String</span></span> | <span data-ttu-id="79466-206">建立者電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="79466-206">Creator email address</span></span> | <span data-ttu-id="79466-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79466-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="79466-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="79466-208">requesterId</span></span> | <span data-ttu-id="79466-209">字串</span><span class="sxs-lookup"><span data-stu-id="79466-209">String</span></span> | <span data-ttu-id="79466-210">Creator 物件識別碼</span><span class="sxs-lookup"><span data-stu-id="79466-210">Creator object id</span></span> | <span data-ttu-id="79466-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="79466-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="79466-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="79466-212">requesterNotes</span></span> | <span data-ttu-id="79466-213">字串</span><span class="sxs-lookup"><span data-stu-id="79466-213">String</span></span> | <span data-ttu-id="79466-214">為此修復活動新增的建立者) 附注 (自由文字</span><span class="sxs-lookup"><span data-stu-id="79466-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="79466-215">Null</span><span class="sxs-lookup"><span data-stu-id="79466-215">null</span></span>
<span data-ttu-id="79466-216">Scid</span><span class="sxs-lookup"><span data-stu-id="79466-216">scid</span></span> | <span data-ttu-id="79466-217">字串</span><span class="sxs-lookup"><span data-stu-id="79466-217">String</span></span> | <span data-ttu-id="79466-218">相關安全性建議的 SCID</span><span class="sxs-lookup"><span data-stu-id="79466-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="79466-219">Null</span><span class="sxs-lookup"><span data-stu-id="79466-219">null</span></span>
<span data-ttu-id="79466-220">地位</span><span class="sxs-lookup"><span data-stu-id="79466-220">status</span></span> | <span data-ttu-id="79466-221">字串</span><span class="sxs-lookup"><span data-stu-id="79466-221">String</span></span> | <span data-ttu-id="79466-222">修復活動狀態 (Active/已完成) </span><span class="sxs-lookup"><span data-stu-id="79466-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="79466-223">作用中</span><span class="sxs-lookup"><span data-stu-id="79466-223">Active</span></span>
<span data-ttu-id="79466-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="79466-224">statusLastModifiedOn</span></span> | <span data-ttu-id="79466-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="79466-225">DateTime</span></span> | <span data-ttu-id="79466-226">更新狀態欄位的日期</span><span class="sxs-lookup"><span data-stu-id="79466-226">Date when the status field was updated</span></span> | <span data-ttu-id="79466-227">2021-01-12T18：54： 11.5499487 Z</span><span class="sxs-lookup"><span data-stu-id="79466-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="79466-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="79466-228">targetDevices</span></span> | <span data-ttu-id="79466-229">Long</span><span class="sxs-lookup"><span data-stu-id="79466-229">Long</span></span> | <span data-ttu-id="79466-230">此修復適用的公開裝置數目</span><span class="sxs-lookup"><span data-stu-id="79466-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="79466-231">43</span><span class="sxs-lookup"><span data-stu-id="79466-231">43</span></span>
<span data-ttu-id="79466-232">標題</span><span class="sxs-lookup"><span data-stu-id="79466-232">title</span></span> | <span data-ttu-id="79466-233">String</span><span class="sxs-lookup"><span data-stu-id="79466-233">String</span></span> | <span data-ttu-id="79466-234">此修復活動的標題</span><span class="sxs-lookup"><span data-stu-id="79466-234">Title of this remediation activity</span></span> | <span data-ttu-id="79466-235">更新 Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="79466-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="79466-236">類型</span><span class="sxs-lookup"><span data-stu-id="79466-236">type</span></span> | <span data-ttu-id="79466-237">字串</span><span class="sxs-lookup"><span data-stu-id="79466-237">String</span></span> | <span data-ttu-id="79466-238">修正類型</span><span class="sxs-lookup"><span data-stu-id="79466-238">Remediation type</span></span> | <span data-ttu-id="79466-239">Update</span><span class="sxs-lookup"><span data-stu-id="79466-239">Update</span></span>
<span data-ttu-id="79466-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="79466-240">vendorId</span></span> | <span data-ttu-id="79466-241">字串</span><span class="sxs-lookup"><span data-stu-id="79466-241">String</span></span> | <span data-ttu-id="79466-242">相關的供應商名稱</span><span class="sxs-lookup"><span data-stu-id="79466-242">Related vendor name</span></span> | <span data-ttu-id="79466-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="79466-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="79466-244">範例</span><span class="sxs-lookup"><span data-stu-id="79466-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="79466-245">要求範例</span><span class="sxs-lookup"><span data-stu-id="79466-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="79466-246">回應範例</span><span class="sxs-lookup"><span data-stu-id="79466-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="79466-247">請參閱</span><span class="sxs-lookup"><span data-stu-id="79466-247">See also</span></span>

- [<span data-ttu-id="79466-248">修正方法和屬性</span><span class="sxs-lookup"><span data-stu-id="79466-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="79466-249">根據識別碼取得一個補救活動</span><span class="sxs-lookup"><span data-stu-id="79466-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="79466-250">列出一個補救活動的公開裝置</span><span class="sxs-lookup"><span data-stu-id="79466-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="79466-251">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="79466-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="79466-252">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="79466-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
