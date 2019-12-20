---
title: Microsoft Compliance Manager 版本資訊
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
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: c988a727bc48a5b27146168a66a0831c9b57b216
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806686"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="aafde-104">版本資訊的合規性管理員 （預覽）</span><span class="sxs-lookup"><span data-stu-id="aafde-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="aafde-105">公開預覽的合規性管理員為您提供搶先即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="aafde-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="aafde-106">您可以使用[服務信任入口網站](https://servicetrust.microsoft.com)上更新的[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)」 來追蹤、 指派，並確認與 Microsoft 雲端服務相關的法規合規性活動。</span><span class="sxs-lookup"><span data-stu-id="aafde-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="aafde-107">What's new 合規性管理員中 （預覽）</span><span class="sxs-lookup"><span data-stu-id="aafde-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="aafde-108">**角色型存取合規性管理員：** 已移除預設**的來賓存取**角色。</span><span class="sxs-lookup"><span data-stu-id="aafde-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="aafde-109">為了讓使用者存取合規性管理員中，全域系統管理員必須[指派每位使用者的權限](compliance-manager-overview.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="aafde-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="aafde-110">**更新合規性分數**： 合規性分數現在包含分數的 Microsoft 受管理的動作。</span><span class="sxs-lookup"><span data-stu-id="aafde-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="aafde-111">因此會增加您的分數。</span><span class="sxs-lookup"><span data-stu-id="aafde-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="aafde-112">**動作項目：** 動作項目現在的個別項目，而且許多包括來自 Microsoft 安全分數 Graph API 的遙測集合。</span><span class="sxs-lookup"><span data-stu-id="aafde-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="aafde-113">請儘可能技術巨集指令建議現在有適用的設定] 頁面上的連結 Office 365 服務中。</span><span class="sxs-lookup"><span data-stu-id="aafde-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="aafde-114">**租用戶管理：** 管理新的資料元素合規性管理員中 （預覽） 的新介面：</span><span class="sxs-lookup"><span data-stu-id="aafde-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="aafde-115">**維度：** 檢視、 新增並自訂的中繼資料的範本、 評估以及動作項目，可讓您建立自訂的樞紐分析表的篩選器。</span><span class="sxs-lookup"><span data-stu-id="aafde-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="aafde-116">**擁有者：** 指定每個動作項目擁有者。</span><span class="sxs-lookup"><span data-stu-id="aafde-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="aafde-117">**客戶動作：** 管理動作項目包含在合規性管理員 （預覽） 的完整清單，並啟用/停用安全分數監控與安全分數整合在一起的動作項目。</span><span class="sxs-lookup"><span data-stu-id="aafde-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="aafde-118">已知的問題合規性管理員中 （預覽）</span><span class="sxs-lookup"><span data-stu-id="aafde-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="aafde-119">下列各節討論在即將發行的合規性管理員中解析的已知的問題。</span><span class="sxs-lookup"><span data-stu-id="aafde-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="aafde-120">合規性分數</span><span class="sxs-lookup"><span data-stu-id="aafde-120">Compliance Score</span></span>

- <span data-ttu-id="aafde-121">標示為**不在範圍中**的動作項目，如分數指派動作項目不排除合規性分數計算。</span><span class="sxs-lookup"><span data-stu-id="aafde-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="aafde-122">標示為**不在範圍中**的動作項目不會增加合規性分數。</span><span class="sxs-lookup"><span data-stu-id="aafde-122">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="aafde-123">安全分數</span><span class="sxs-lookup"><span data-stu-id="aafde-123">Secure Score</span></span>

- <span data-ttu-id="aafde-124">安全分數結果不適用於特定 Microsoft 365 和 Office 365 訂閱中的某些動作項目。</span><span class="sxs-lookup"><span data-stu-id="aafde-124">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="aafde-125">安全分數結果是**無法偵測**在這些情況下。</span><span class="sxs-lookup"><span data-stu-id="aafde-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="aafde-126">有時安全分數結果會傳回對應的原則並不會完成的動作項目。</span><span class="sxs-lookup"><span data-stu-id="aafde-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="aafde-127">針對新租用戶的所有動作的安全分數更新自動處於開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="aafde-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="aafde-128">全域系統管理員可以設定安全分數連續更新切換到關閉，這會關閉的所有動作的更新。</span><span class="sxs-lookup"><span data-stu-id="aafde-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="aafde-129">**附註**： 當組織第一次部署 Microsoft 365 或 Office 365，它會採用約七天的安全分數 」 來完全收集資料，並因素入您的分數。</span><span class="sxs-lookup"><span data-stu-id="aafde-129">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="aafde-130">在這段時間，將安全分數連續更新參數設定為 [**關閉**，並以手動方式設定為**實作**的 [巨集指令會計算向您的分數該巨集指令。</span><span class="sxs-lookup"><span data-stu-id="aafde-130">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="aafde-131">初始七天之後，開啟安全分數連續更新將會啟用該點之後的持續監視。</span><span class="sxs-lookup"><span data-stu-id="aafde-131">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="aafde-132">安全分數更新已開啟時，會主動監視動作可以安全分數，雖然巨集指令的測試日期不會更新以反映監視。</span><span class="sxs-lookup"><span data-stu-id="aafde-132">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="aafde-133">當建立新的評估時，分數自動包含 Microsoft 管理控制項分數和安全分數整合。</span><span class="sxs-lookup"><span data-stu-id="aafde-133">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="aafde-134">安全分數整合不支援任何動作以手動方式可實作。</span><span class="sxs-lookup"><span data-stu-id="aafde-134">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="aafde-135">手動實作將因素入該巨集指令群組的分數。</span><span class="sxs-lookup"><span data-stu-id="aafde-135">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="aafde-136">Microsoft 管理控制措施</span><span class="sxs-lookup"><span data-stu-id="aafde-136">Microsoft-managed controls</span></span>

- <span data-ttu-id="aafde-137">Microsoft 受管理控制項的測試日期未出現在 UI 中，即使納入評估。</span><span class="sxs-lookup"><span data-stu-id="aafde-137">The test date for Microsoft-managed controls isn't appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="aafde-138">若要查看測試日期的詳細資訊，您必須先匯出評估。</span><span class="sxs-lookup"><span data-stu-id="aafde-138">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="aafde-139">自訂</span><span class="sxs-lookup"><span data-stu-id="aafde-139">Customization</span></span>

- <span data-ttu-id="aafde-140">新增自訂控制項可讓將新的控制項新增至現有的控制項系列，但它不會讓您新增新的控制項系列。</span><span class="sxs-lookup"><span data-stu-id="aafde-140">Adding custom Controls enables adding a new control to an existing control family, but it doesn't allow you to add a new Control Family.</span></span>
- <span data-ttu-id="aafde-141">此版本不支援連結動作項目新增動作項目或評估控制項。</span><span class="sxs-lookup"><span data-stu-id="aafde-141">This release doesn't support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="aafde-142">如果您建立的自訂動作，您無法編輯或刪除它。</span><span class="sxs-lookup"><span data-stu-id="aafde-142">If you create a custom Action, you can't edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="aafde-143">不會顯示在 「 評估 」 控制項系列</span><span class="sxs-lookup"><span data-stu-id="aafde-143">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="aafde-144">當您匯入範本時，該範本為基礎的所有評定都反映是範本的一部份的所有控制項系列。</span><span class="sxs-lookup"><span data-stu-id="aafde-144">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="aafde-145">但是，如果您新增至範本的新控制項系列，任何現有 「 評估 」 不會反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="aafde-145">But if you add new Control Families to the Template, any existing Assessments won't reflect the changes.</span></span> <span data-ttu-id="aafde-146">僅限關閉更新的範本建立新的評估會反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="aafde-146">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="aafde-147">範本</span><span class="sxs-lookup"><span data-stu-id="aafde-147">Templates</span></span>

- <span data-ttu-id="aafde-148">在建立範本時，您必須包含維度這兩個**產品**和**憑證**以確保您的範本會顯示在 [合規性分數。</span><span class="sxs-lookup"><span data-stu-id="aafde-148">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="aafde-149">封存的範本可編輯且不應該加以編輯。</span><span class="sxs-lookup"><span data-stu-id="aafde-149">Archived templates are editable and they shouldn't be editable.</span></span>
- <span data-ttu-id="aafde-150">當他們不應該評估建立允許鎖定的範本。</span><span class="sxs-lookup"><span data-stu-id="aafde-150">Locked templates allow for Assessment creation when they shouldn't.</span></span> <span data-ttu-id="aafde-151">鎖定範本是用來防止其被用來建立評估。</span><span class="sxs-lookup"><span data-stu-id="aafde-151">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="aafde-152">匯出</span><span class="sxs-lookup"><span data-stu-id="aafde-152">Export</span></span>

- <span data-ttu-id="aafde-153">範本匯出至 JSON 失敗時的範本狀態設為**匯入**或**擱置中的核准**。</span><span class="sxs-lookup"><span data-stu-id="aafde-153">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="aafde-154">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="aafde-154">Supported browsers</span></span>

- <span data-ttu-id="aafde-155">支援最新版的 Microsoft Edge、 Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="aafde-155">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="aafde-156">可能會在重新整理瀏覽器直到更新的資料不會出現的位置的執行個體。</span><span class="sxs-lookup"><span data-stu-id="aafde-156">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="aafde-157">Microsoft Edge 的預覽版本不支援，但有任何已知的問題。</span><span class="sxs-lookup"><span data-stu-id="aafde-157">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="aafde-158">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="aafde-158">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="aafde-159">工作階段逾時</span><span class="sxs-lookup"><span data-stu-id="aafde-159">Session timeout</span></span>

- <span data-ttu-id="aafde-160">當工作階段逾時，可能會出現 「 發生錯誤 」 錯誤。</span><span class="sxs-lookup"><span data-stu-id="aafde-160">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="aafde-161">若要解決，移至[合規性管理員中](https://servicetrust.microsoft.com/ComplianceManager)，並再次登入。</span><span class="sxs-lookup"><span data-stu-id="aafde-161">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="aafde-162">語言支援</span><span class="sxs-lookup"><span data-stu-id="aafde-162">Language support</span></span>

- <span data-ttu-id="aafde-163">所有語言不支援所有的網頁。</span><span class="sxs-lookup"><span data-stu-id="aafde-163">All languages aren't supported for all webpages.</span></span> <span data-ttu-id="aafde-164">如果您當地語言不受支援，在美式英文的檢視。</span><span class="sxs-lookup"><span data-stu-id="aafde-164">If your local language is unsupported, view in US English.</span></span>