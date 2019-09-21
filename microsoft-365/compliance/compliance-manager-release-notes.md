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
ms.openlocfilehash: 815862616e1bdbf4b3be1d77de2a541ad703149f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076626"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="34a9d-104">版本資訊的合規性管理員 （預覽）</span><span class="sxs-lookup"><span data-stu-id="34a9d-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="34a9d-105">公開預覽的合規性管理員為您提供搶先即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="34a9d-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="34a9d-106">您可以使用[服務信任入口網站](https://servicetrust.microsoft.com)上更新的[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)」 來追蹤、 指派，並確認與 Microsoft 雲端服務相關的法規合規性活動。</span><span class="sxs-lookup"><span data-stu-id="34a9d-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="34a9d-107">What's new 合規性管理員中 （預覽）</span><span class="sxs-lookup"><span data-stu-id="34a9d-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="34a9d-108">**整合與 Microsoft 安全分數：** 合規性管理員可藉由將客戶管理動作對應到超過 50 個安全分數動作支援與[Microsoft 安全分數](../security/mtp/microsoft-secure-score.md)的整合。</span><span class="sxs-lookup"><span data-stu-id="34a9d-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="34a9d-109">當您完成安全分數對應巨集指令時，對應的合規性管理員巨集指令會自動更新。</span><span class="sxs-lookup"><span data-stu-id="34a9d-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="34a9d-110">**匯入自訂的 「 評估 」:** 除了內建的評估，合規性管理員現在可支援匯入自訂的範本。</span><span class="sxs-lookup"><span data-stu-id="34a9d-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="34a9d-111">您可以建立自訂的 「 評估 」 的任何產品或服務以及任何標準或法規。</span><span class="sxs-lookup"><span data-stu-id="34a9d-111">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="34a9d-112">**動作項目：** 動作項目現在的個別項目，而且許多包括來自 Microsoft 安全分數 Graph API 的遙測集合。</span><span class="sxs-lookup"><span data-stu-id="34a9d-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="34a9d-113">請儘可能技術巨集指令建議現在有適用的設定] 頁面上的連結 Office 365 服務中。</span><span class="sxs-lookup"><span data-stu-id="34a9d-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="34a9d-114">**租用戶管理：** 管理新的資料元素合規性管理員中 （預覽） 的新介面：</span><span class="sxs-lookup"><span data-stu-id="34a9d-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="34a9d-115">**維度：** 檢視、 新增並自訂的中繼資料的範本、 評估以及動作項目，可讓您建立自訂的樞紐分析表的篩選器。</span><span class="sxs-lookup"><span data-stu-id="34a9d-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="34a9d-116">**擁有者：** 指定每個動作項目擁有者。</span><span class="sxs-lookup"><span data-stu-id="34a9d-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="34a9d-117">**客戶動作：** 管理動作項目包含在合規性管理員 （預覽） 的完整清單，並啟用/停用安全分數監控與安全分數整合在一起的動作項目。</span><span class="sxs-lookup"><span data-stu-id="34a9d-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="34a9d-118">**更新合規性分數**： 方法具有變更以支援透過 Microsoft 安全分數進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="34a9d-118">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="34a9d-119">計分系統會移除 Microsoft 管理控制項信用額度，並完全著重完成的客戶管理控制措施。</span><span class="sxs-lookup"><span data-stu-id="34a9d-119">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="34a9d-120">已知的問題合規性管理員中 （預覽）</span><span class="sxs-lookup"><span data-stu-id="34a9d-120">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="34a9d-121">下列各節討論在即將發行的合規性管理員中解析的已知的問題。</span><span class="sxs-lookup"><span data-stu-id="34a9d-121">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="34a9d-122">合規性分數</span><span class="sxs-lookup"><span data-stu-id="34a9d-122">Compliance Score</span></span>

- <span data-ttu-id="34a9d-123">標示為**不在範圍中**的動作項目，分數指派動作項目不是從合規性分數計算中排除。</span><span class="sxs-lookup"><span data-stu-id="34a9d-123">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="34a9d-124">標示為**不在範圍中**的動作項目不會增加您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="34a9d-124">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="34a9d-125">安全分數</span><span class="sxs-lookup"><span data-stu-id="34a9d-125">Secure Score</span></span>

- <span data-ttu-id="34a9d-126">安全分數結果訣不適用於特定 Microsoft 365 和 Office 365 訂閱中的某些動作項目。</span><span class="sxs-lookup"><span data-stu-id="34a9d-126">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="34a9d-127">結果是安全分數 '無法偵測' 在這些情況下。</span><span class="sxs-lookup"><span data-stu-id="34a9d-127">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="34a9d-128">有時安全分數結果會傳回對應的原則並不會完成的動作項目。</span><span class="sxs-lookup"><span data-stu-id="34a9d-128">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="34a9d-129">Microsoft 管理控制措施</span><span class="sxs-lookup"><span data-stu-id="34a9d-129">Microsoft-managed Controls</span></span>

- <span data-ttu-id="34a9d-130">Microsoft 管理控制措施的測試日期不會出現在 UI 中，即使納入評估。</span><span class="sxs-lookup"><span data-stu-id="34a9d-130">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="34a9d-131">若要查看測試日期的詳細資訊，您必須先匯出評估。</span><span class="sxs-lookup"><span data-stu-id="34a9d-131">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="34a9d-132">自訂</span><span class="sxs-lookup"><span data-stu-id="34a9d-132">Customization</span></span>

- <span data-ttu-id="34a9d-133">新增自訂控制項可讓將新的控制項新增至現有的控制項系列，但不允許您將新增新的控制項系列。</span><span class="sxs-lookup"><span data-stu-id="34a9d-133">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="34a9d-134">此版本不支援連結動作項目新增動作項目或評估控制項。</span><span class="sxs-lookup"><span data-stu-id="34a9d-134">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="34a9d-135">如果您建立的自訂動作，您無法編輯或刪除它。</span><span class="sxs-lookup"><span data-stu-id="34a9d-135">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="34a9d-136">不會顯示在 「 評估 」 控制項系列</span><span class="sxs-lookup"><span data-stu-id="34a9d-136">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="34a9d-137">當您匯入範本時，該範本為基礎的所有評定都反映是範本的一部份的所有控制項系列。</span><span class="sxs-lookup"><span data-stu-id="34a9d-137">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="34a9d-138">但是，如果您新增至範本的新控制項系列，任何現有 「 評估 」 不會反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="34a9d-138">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="34a9d-139">僅限關閉更新的範本建立新的評估會反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="34a9d-139">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="34a9d-140">篩選</span><span class="sxs-lookup"><span data-stu-id="34a9d-140">Filters</span></span>

- <span data-ttu-id="34a9d-141">篩選動作項目或控制項時，不一致地產生正確的結果。</span><span class="sxs-lookup"><span data-stu-id="34a9d-141">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="34a9d-142">範本</span><span class="sxs-lookup"><span data-stu-id="34a9d-142">Templates</span></span>

- <span data-ttu-id="34a9d-143">封存的範本可編輯，而且它們不應該是可編輯。</span><span class="sxs-lookup"><span data-stu-id="34a9d-143">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="34a9d-144">當他們不應該評估建立允許鎖定的範本。</span><span class="sxs-lookup"><span data-stu-id="34a9d-144">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="34a9d-145">鎖定範本是用來防止其被用來建立評估。</span><span class="sxs-lookup"><span data-stu-id="34a9d-145">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="34a9d-146">匯出</span><span class="sxs-lookup"><span data-stu-id="34a9d-146">Export</span></span>

- <span data-ttu-id="34a9d-147">範本匯出至 JSON 失敗時的範本狀態設為**匯入**或**擱置中的核准**。</span><span class="sxs-lookup"><span data-stu-id="34a9d-147">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="34a9d-148">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="34a9d-148">Supported browsers</span></span>

- <span data-ttu-id="34a9d-149">支援最新版的 Microsoft Edge、 Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="34a9d-149">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="34a9d-150">可能會有更新的資料不會在重新整理瀏覽器直到出現的執行個體。</span><span class="sxs-lookup"><span data-stu-id="34a9d-150">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="34a9d-151">Microsoft Edge 的預覽版本不支援，但有任何已知的問題。</span><span class="sxs-lookup"><span data-stu-id="34a9d-151">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="34a9d-152">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="34a9d-152">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="34a9d-153">工作階段逾時</span><span class="sxs-lookup"><span data-stu-id="34a9d-153">Session timeout</span></span>

- <span data-ttu-id="34a9d-154">當工作階段逾時，可能會出現 「 發生錯誤 」 錯誤。</span><span class="sxs-lookup"><span data-stu-id="34a9d-154">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="34a9d-155">若要解決，移至[合規性管理員中](https://servicetrust.microsoft.com/ComplianceManager)，並再次登入。</span><span class="sxs-lookup"><span data-stu-id="34a9d-155">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="34a9d-156">語言支援</span><span class="sxs-lookup"><span data-stu-id="34a9d-156">Language support</span></span>

- <span data-ttu-id="34a9d-157">所有語言都不支援所有的網頁。</span><span class="sxs-lookup"><span data-stu-id="34a9d-157">All languages are not supported for all webpages.</span></span> <span data-ttu-id="34a9d-158">如果您當地語言不受支援，在美式英文的檢視。</span><span class="sxs-lookup"><span data-stu-id="34a9d-158">If your local language is unsupported, view in US English.</span></span>