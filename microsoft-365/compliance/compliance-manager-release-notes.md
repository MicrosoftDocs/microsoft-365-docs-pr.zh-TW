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
ms.openlocfilehash: 1a490212b2275b9f297e2585e7242f5331d0fe56
ms.sourcegitcommit: 5c6c30ec5541d2fb77e53a1309db1fe7b75fc3e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "38685408"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="2f4c9-104">版本資訊的合規性管理員 （預覽）</span><span class="sxs-lookup"><span data-stu-id="2f4c9-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="2f4c9-105">公開預覽的合規性管理員為您提供搶先即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="2f4c9-106">您可以使用[服務信任入口網站](https://servicetrust.microsoft.com)上更新的[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)」 來追蹤、 指派，並確認與 Microsoft 雲端服務相關的法規合規性活動。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="2f4c9-107">What's new 合規性管理員中 （預覽）</span><span class="sxs-lookup"><span data-stu-id="2f4c9-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="2f4c9-108">**角色型存取合規性管理員：** 已移除預設**的來賓存取**角色。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="2f4c9-109">為了讓使用者存取合規性管理員中，全域系統管理員必須[指派每位使用者的權限](compliance-manager-overview.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="2f4c9-110">**更新合規性分數**： 合規性分數現在包含分數的 Microsoft 受管理的動作。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="2f4c9-111">因此會增加您的分數。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="2f4c9-112">**動作項目：** 動作項目現在的個別項目，而且許多包括來自 Microsoft 安全分數 Graph API 的遙測集合。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="2f4c9-113">請儘可能技術巨集指令建議現在有適用的設定] 頁面上的連結 Office 365 服務中。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="2f4c9-114">**租用戶管理：** 管理新的資料元素合規性管理員中 （預覽） 的新介面：</span><span class="sxs-lookup"><span data-stu-id="2f4c9-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="2f4c9-115">**維度：** 檢視、 新增並自訂的中繼資料的範本、 評估以及動作項目，可讓您建立自訂的樞紐分析表的篩選器。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="2f4c9-116">**擁有者：** 指定每個動作項目擁有者。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="2f4c9-117">**客戶動作：** 管理動作項目包含在合規性管理員 （預覽） 的完整清單，並啟用/停用安全分數監控與安全分數整合在一起的動作項目。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="2f4c9-118">已知的問題合規性管理員中 （預覽）</span><span class="sxs-lookup"><span data-stu-id="2f4c9-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="2f4c9-119">下列各節討論在即將發行的合規性管理員中解析的已知的問題。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="2f4c9-120">合規性分數</span><span class="sxs-lookup"><span data-stu-id="2f4c9-120">Compliance Score</span></span>

- <span data-ttu-id="2f4c9-121">標示為**不在範圍中**的動作項目，分數指派動作項目不是從合規性分數計算中排除。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the compliance score calculation.</span></span> <span data-ttu-id="2f4c9-122">標示為**不在範圍中**的動作項目不會增加您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-122">Action Items marked **Not in Scope** do not increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="2f4c9-123">安全分數</span><span class="sxs-lookup"><span data-stu-id="2f4c9-123">Secure Score</span></span>

- <span data-ttu-id="2f4c9-124">安全分數結果訣不適用於特定 Microsoft 365 和 Office 365 訂閱中的某些動作項目。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-124">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="2f4c9-125">安全分數結果是**無法偵測**在這些情況下。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="2f4c9-126">有時安全分數結果會傳回對應的原則並不會完成的動作項目。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="2f4c9-127">針對新租用戶的所有動作的安全分數更新自動處於開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="2f4c9-128">全域系統管理員可以設定安全分數連續更新切換到關閉，這會關閉的所有動作的更新。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
- <span data-ttu-id="2f4c9-129">安全分數更新已開啟時，會主動監視動作可以安全分數，雖然巨集指令的測試日期不會更新以反映監視。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-129">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date will not be updated to reflect monitoring.</span></span>
- <span data-ttu-id="2f4c9-130">當建立新的評估時，分數自動包含 Microsoft 管理控制項分數和安全分數整合。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-130">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="2f4c9-131">Microsoft 管理控制措施</span><span class="sxs-lookup"><span data-stu-id="2f4c9-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="2f4c9-132">Microsoft 管理控制措施的測試日期不會出現在 UI 中，即使納入評估。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="2f4c9-133">若要查看測試日期的詳細資訊，您必須先匯出評估。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="2f4c9-134">自訂</span><span class="sxs-lookup"><span data-stu-id="2f4c9-134">Customization</span></span>

- <span data-ttu-id="2f4c9-135">新增自訂控制項可讓將新的控制項新增至現有的控制項系列，但不允許您將新增新的控制項系列。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="2f4c9-136">此版本不支援連結動作項目新增動作項目或評估控制項。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="2f4c9-137">如果您建立的自訂動作，您無法編輯或刪除它。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="2f4c9-138">不會顯示在 「 評估 」 控制項系列</span><span class="sxs-lookup"><span data-stu-id="2f4c9-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="2f4c9-139">當您匯入範本時，該範本為基礎的所有評定都反映是範本的一部份的所有控制項系列。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="2f4c9-140">但是，如果您新增至範本的新控制項系列，任何現有 「 評估 」 不會反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="2f4c9-141">僅限關閉更新的範本建立新的評估會反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="2f4c9-142">範本</span><span class="sxs-lookup"><span data-stu-id="2f4c9-142">Templates</span></span>

- <span data-ttu-id="2f4c9-143">在建立範本時，您必須包含維度這兩個**產品**和**憑證**以確保您的範本會顯示在 [合規性分數。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-143">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="2f4c9-144">封存的範本可編輯，而且它們不應該是可編輯。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-144">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="2f4c9-145">當他們不應該評估建立允許鎖定的範本。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-145">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="2f4c9-146">鎖定範本是用來防止其被用來建立評估。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-146">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="2f4c9-147">匯出</span><span class="sxs-lookup"><span data-stu-id="2f4c9-147">Export</span></span>

- <span data-ttu-id="2f4c9-148">範本匯出至 JSON 失敗時的範本狀態設為**匯入**或**擱置中的核准**。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-148">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="2f4c9-149">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="2f4c9-149">Supported browsers</span></span>

- <span data-ttu-id="2f4c9-150">支援最新版的 Microsoft Edge、 Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-150">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="2f4c9-151">可能會有更新的資料不會在重新整理瀏覽器直到出現的執行個體。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-151">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="2f4c9-152">Microsoft Edge 的預覽版本不支援，但有任何已知的問題。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-152">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="2f4c9-153">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-153">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="2f4c9-154">工作階段逾時</span><span class="sxs-lookup"><span data-stu-id="2f4c9-154">Session timeout</span></span>

- <span data-ttu-id="2f4c9-155">當工作階段逾時，可能會出現 「 發生錯誤 」 錯誤。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-155">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="2f4c9-156">若要解決，移至[合規性管理員中](https://servicetrust.microsoft.com/ComplianceManager)，並再次登入。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-156">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="2f4c9-157">語言支援</span><span class="sxs-lookup"><span data-stu-id="2f4c9-157">Language support</span></span>

- <span data-ttu-id="2f4c9-158">所有語言都不支援所有的網頁。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-158">All languages are not supported for all webpages.</span></span> <span data-ttu-id="2f4c9-159">如果您當地語言不受支援，在美式英文的檢視。</span><span class="sxs-lookup"><span data-stu-id="2f4c9-159">If your local language is unsupported, view in US English.</span></span>