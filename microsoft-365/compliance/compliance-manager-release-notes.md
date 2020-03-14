---
title: Microsoft 合規性管理員版本資訊
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性管理員是 Microsoft 服務信任入口網站中免費的工作流程型風險評估工具。 合規性管理員可讓您追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。
ms.openlocfilehash: 3fc16e92e912676d7aedc861ffe8306d68388c95
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635141"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="79da1-104">合規性管理員的版本附注（預覽）</span><span class="sxs-lookup"><span data-stu-id="79da1-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="79da1-105">合規性管理員的公開預覽可讓您及早存取即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="79da1-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="79da1-106">您可以在[服務信任入口網站](https://servicetrust.microsoft.com)上使用更新的[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)工具，以追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。</span><span class="sxs-lookup"><span data-stu-id="79da1-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="79da1-107">合規性管理員的新功能（預覽）</span><span class="sxs-lookup"><span data-stu-id="79da1-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="79da1-108">**以角色為基礎的訪問合規性管理員：** 已移除預設**來賓存取**角色。</span><span class="sxs-lookup"><span data-stu-id="79da1-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="79da1-109">若要讓使用者存取合規性管理員，全域管理員必須[將許可權指派給每位使用者](compliance-manager-overview.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="79da1-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="79da1-110">**更新的合規性分數**：符合性分數現在包括 Microsoft 管理的動作分數。</span><span class="sxs-lookup"><span data-stu-id="79da1-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="79da1-111">結果會使您的分數增加。</span><span class="sxs-lookup"><span data-stu-id="79da1-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="79da1-112">**Actions 專案：** 動作專案現在是個別專案，許多包括來自 Microsoft 安全分數圖形 API 的遙測集合。</span><span class="sxs-lookup"><span data-stu-id="79da1-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="79da1-113">您可以盡可能使用技術動作建議，以連結至 Office 365 服務中適用的設定頁面。</span><span class="sxs-lookup"><span data-stu-id="79da1-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="79da1-114">**承租人管理：** 在合規性管理員中管理新資料元素的新介面（預覽）：</span><span class="sxs-lookup"><span data-stu-id="79da1-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="79da1-115">**維度：** View、新增及自訂範本、評估和動作專案的中繼資料，可讓您建立自訂的篩選器。</span><span class="sxs-lookup"><span data-stu-id="79da1-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="79da1-116">**擁有者：** 指定每個即席專案的擁有者。</span><span class="sxs-lookup"><span data-stu-id="79da1-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="79da1-117">**客戶動作：** 管理合規性管理員（預覽）中包含的完整動作專案清單，並啟用/停用以安全得分整合之動作專案的安全評分監控。</span><span class="sxs-lookup"><span data-stu-id="79da1-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="79da1-118">合規性管理員中的已知問題（預覽）</span><span class="sxs-lookup"><span data-stu-id="79da1-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="79da1-119">下列各節涵蓋合規性管理員即將推出的版本中解決的已知問題。</span><span class="sxs-lookup"><span data-stu-id="79da1-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="79da1-120">合規性分數</span><span class="sxs-lookup"><span data-stu-id="79da1-120">Compliance Score</span></span>

- <span data-ttu-id="79da1-121">對於標示為**Not In 範圍**的動作專案，指派給交辦事項的分數不會從相容性分數計算中排除。</span><span class="sxs-lookup"><span data-stu-id="79da1-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="79da1-122">標記為**Not In 範圍的**動作專案不會提升您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="79da1-122">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="79da1-123">安全分數</span><span class="sxs-lookup"><span data-stu-id="79da1-123">Secure Score</span></span>

- <span data-ttu-id="79da1-124">在某些 Microsoft 365 和 Office 365 訂閱中，有些動作專案無法使用安全分數結果。</span><span class="sxs-lookup"><span data-stu-id="79da1-124">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="79da1-125">在這些情況下，**無法偵測到**安全分數結果。</span><span class="sxs-lookup"><span data-stu-id="79da1-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="79da1-126">有時候會為對應的原則及未完成的動作專案傳回安全分數結果。</span><span class="sxs-lookup"><span data-stu-id="79da1-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="79da1-127">針對新承租人，會自動開啟所有動作的安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="79da1-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="79da1-128">全域管理員可以將安全計分連續更新切換為 [關閉]，這樣會關閉所有動作的更新。</span><span class="sxs-lookup"><span data-stu-id="79da1-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="79da1-129">**附注**：當組織第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行安全的評分，以完全收集資料，並將其劃分為您的分數。</span><span class="sxs-lookup"><span data-stu-id="79da1-129">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="79da1-130">在這段時間內，將安全計分連續更新參數設定為**Off** ，並手動設定所要**執行**的動作，就會將該動作計算為您的分數。</span><span class="sxs-lookup"><span data-stu-id="79da1-130">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="79da1-131">在最初7天后，開啟安全分數連續更新會啟用從該點繼續進行監視。</span><span class="sxs-lookup"><span data-stu-id="79da1-131">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="79da1-132">當安全分數更新開啟時，安全分數會積極監控動作，不過動作的測試日期不會更新以反映監控。</span><span class="sxs-lookup"><span data-stu-id="79da1-132">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="79da1-133">當建立新的評估時，會自動包含 Microsoft 受管理的控制分數和安全分數整合。</span><span class="sxs-lookup"><span data-stu-id="79da1-133">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="79da1-134">安全分數整合不支援的任何動作都可以手動實施。</span><span class="sxs-lookup"><span data-stu-id="79da1-134">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="79da1-135">手動執行將會考慮該動作群組的分數。</span><span class="sxs-lookup"><span data-stu-id="79da1-135">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="79da1-136">Microsoft 管理的控制項</span><span class="sxs-lookup"><span data-stu-id="79da1-136">Microsoft-managed controls</span></span>

- <span data-ttu-id="79da1-137">Microsoft 管理控制項的測試日期不會出現在 UI 中，甚至會包含在評估中。</span><span class="sxs-lookup"><span data-stu-id="79da1-137">The test date for Microsoft-managed controls isn't appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="79da1-138">若要查看測試日期資訊，您必須匯出評估。</span><span class="sxs-lookup"><span data-stu-id="79da1-138">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="79da1-139">自訂</span><span class="sxs-lookup"><span data-stu-id="79da1-139">Customization</span></span>

- <span data-ttu-id="79da1-140">新增自訂控制項可將新控制項新增至現有的控制項系列，但不允許您新增新的控制項系列。</span><span class="sxs-lookup"><span data-stu-id="79da1-140">Adding custom Controls enables adding a new control to an existing control family, but it doesn't allow you to add a new Control Family.</span></span>
- <span data-ttu-id="79da1-141">此版本不支援連結動作專案，或新增動作專案或控制項給評估。</span><span class="sxs-lookup"><span data-stu-id="79da1-141">This release doesn't support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="79da1-142">如果您建立自訂動作，便無法進行編輯或刪除。</span><span class="sxs-lookup"><span data-stu-id="79da1-142">If you create a custom Action, you can't edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="79da1-143">控制評估中未顯示的系列</span><span class="sxs-lookup"><span data-stu-id="79da1-143">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="79da1-144">當您匯入範本時，以該範本為基礎的所有評估會反映屬於該範本的所有控制系列。</span><span class="sxs-lookup"><span data-stu-id="79da1-144">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="79da1-145">不過，如果您將新的控制項系列新增至範本，任何現有評估將不會反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="79da1-145">But if you add new Control Families to the Template, any existing Assessments won't reflect the changes.</span></span> <span data-ttu-id="79da1-146">只有已更新的範本所建立的新評估會反映這些變更。</span><span class="sxs-lookup"><span data-stu-id="79da1-146">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="79da1-147">範本</span><span class="sxs-lookup"><span data-stu-id="79da1-147">Templates</span></span>

- <span data-ttu-id="79da1-148">建立範本時，您必須同時包含**產品**和憑證的維度 **，以**確保您的範本會以合規性分數顯示。</span><span class="sxs-lookup"><span data-stu-id="79da1-148">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="79da1-149">封存的範本是可編輯的，不應是可編輯的。</span><span class="sxs-lookup"><span data-stu-id="79da1-149">Archived templates are editable and they shouldn't be editable.</span></span>
- <span data-ttu-id="79da1-150">鎖定的範本允許評估建立。</span><span class="sxs-lookup"><span data-stu-id="79da1-150">Locked templates allow for Assessment creation when they shouldn't.</span></span> <span data-ttu-id="79da1-151">鎖定範本的目的是為了避免使用它來建立評估。</span><span class="sxs-lookup"><span data-stu-id="79da1-151">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="79da1-152">匯出</span><span class="sxs-lookup"><span data-stu-id="79da1-152">Export</span></span>

- <span data-ttu-id="79da1-153">當範本的狀態設定為 [匯**入**] 或 [**待處理核准**] 時，範本匯出至 JSON 失敗。</span><span class="sxs-lookup"><span data-stu-id="79da1-153">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="79da1-154">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="79da1-154">Supported browsers</span></span>

- <span data-ttu-id="79da1-155">支援最新版本的 Microsoft Edge、Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="79da1-155">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="79da1-156">在您的瀏覽器重新整理之前，可能會出現更新的資料不會出現的情況。</span><span class="sxs-lookup"><span data-stu-id="79da1-156">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="79da1-157">不支援預覽版本的 Microsoft Edge，但沒有已知問題。</span><span class="sxs-lookup"><span data-stu-id="79da1-157">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="79da1-158">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="79da1-158">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="79da1-159">會話超時</span><span class="sxs-lookup"><span data-stu-id="79da1-159">Session timeout</span></span>

- <span data-ttu-id="79da1-160">當會話超時時，可能會出現「發生錯誤」錯誤。</span><span class="sxs-lookup"><span data-stu-id="79da1-160">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="79da1-161">若要解決此問題，請移至 [[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)]，然後再登入。</span><span class="sxs-lookup"><span data-stu-id="79da1-161">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="79da1-162">語言支援</span><span class="sxs-lookup"><span data-stu-id="79da1-162">Language support</span></span>

- <span data-ttu-id="79da1-163">所有語言都不支援所有的網頁。</span><span class="sxs-lookup"><span data-stu-id="79da1-163">All languages aren't supported for all webpages.</span></span> <span data-ttu-id="79da1-164">如果不支援您的本機語言，請以美國英文查看。</span><span class="sxs-lookup"><span data-stu-id="79da1-164">If your local language is unsupported, view in US English.</span></span>
