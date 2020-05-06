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
ms.custom:
- seo-marvel-mar2020
description: 查看版本資訊，其中包含 Microsoft 合規性管理員中的新功能和已知問題（要在即將推出的版本中解決）的相關資訊。
ms.openlocfilehash: fb462939ef1b1bf0c6f7f4552359d50645b528f3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033703"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a><span data-ttu-id="97f61-103">Microsoft 合規性管理員（預覽）發行附注</span><span class="sxs-lookup"><span data-stu-id="97f61-103">Microsoft Compliance Manager (preview) release notes</span></span>

<span data-ttu-id="97f61-104">合規性管理員的公開預覽可讓您及早存取即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-104">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span> <span data-ttu-id="97f61-105">此頁面包含目前版本的新功能、改進功能和已知問題的更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-105">This page contains updates on new features, improved functionality, and known issues with the current release.</span></span>

<span data-ttu-id="97f61-106">您可以在[服務信任入口網站](https://servicetrust.microsoft.com)上使用[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)工具，以追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。</span><span class="sxs-lookup"><span data-stu-id="97f61-106">You can use the [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="improved-template-creation-and-update-process"></a><span data-ttu-id="97f61-107">改進範本的建立和更新程式</span><span class="sxs-lookup"><span data-stu-id="97f61-107">Improved template creation and update process</span></span>

<span data-ttu-id="97f61-108">我們已更新用來匯入、匯出及修改評估範本的程式。</span><span class="sxs-lookup"><span data-stu-id="97f61-108">We've updated the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="97f61-109">新的簡化體驗可讓您更輕鬆地將自己的評估帶入您的工作流程中並保持更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-109">The new, simplified experience will make it easier for you to bring your own assessments into your workflow and keep them updated.</span></span>

### <a name="the-old-process"></a><span data-ttu-id="97f61-110">舊進程</span><span class="sxs-lookup"><span data-stu-id="97f61-110">The old process</span></span>

<span data-ttu-id="97f61-111">在合規性管理員中建立範本的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="97f61-111">There were two ways of creating a template in Compliance Manager.</span></span> <span data-ttu-id="97f61-112">您可以複製現有的範本，或將範本資料從 Excel 試算表匯入新的範本。</span><span class="sxs-lookup"><span data-stu-id="97f61-112">You could copy an existing template, or import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="97f61-113">您可以從 [**範本**] 頁面中，選取 [**新增範本**]，以建立全新的範本，方法是輸入名稱、選取 [維度]，並上傳具有特定格式及架構的 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="97f61-113">From your **Templates** page, you'd select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="97f61-114">或者，您可以選取 [**從現有範本複製**] 方塊中，選取要複製的範本，然後驗證維度。</span><span class="sxs-lookup"><span data-stu-id="97f61-114">Or you could check the **Copy from an existing template** box, select a template to copy, and verify dimensions.</span></span> <span data-ttu-id="97f61-115">設計自訂您的範本需要執行多步驟程式，方法是在建立範本後選取 [**新增自訂控制項**]。</span><span class="sxs-lookup"><span data-stu-id="97f61-115">Design customization your template required a multi-step process that began by selecting **Add custom control** after creating your template.</span></span>

### <a name="the-new-process"></a><span data-ttu-id="97f61-116">新進程</span><span class="sxs-lookup"><span data-stu-id="97f61-116">The new process</span></span>

<span data-ttu-id="97f61-117">我們使您建立新的範本變得更容易。</span><span class="sxs-lookup"><span data-stu-id="97f61-117">We made it easier for you to create new templates.</span></span> <span data-ttu-id="97f61-118">在單一步驟**擴充**過程中，您可以將動作和控制項的試算表新增至現有的 Microsoft 範本，以製作您自己的自訂版本。</span><span class="sxs-lookup"><span data-stu-id="97f61-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="97f61-119">在 [合規性管理員] 的 [**範本**] 頁面上，選取 [ **+ 新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="97f61-119">At your **Templates** page in Compliance Manager, select **+ Add template**.</span></span> <span data-ttu-id="97f61-120">在 [**範本**] 飛入窗格上，選取 [**從通用範本建立副檔名**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="97f61-120">On the **Template** flyout pane, select the **Create extension from global template** checkbox.</span></span> <span data-ttu-id="97f61-121">您可以使用比上一個複雜的新 Excel 格式，新增自訂。</span><span class="sxs-lookup"><span data-stu-id="97f61-121">You can add customizations with a new Excel format that is less complex than the previous one.</span></span> <span data-ttu-id="97f61-122">這個新程式會取代**現有範本**的先前副本，並**新增自訂控制項**函數。</span><span class="sxs-lookup"><span data-stu-id="97f61-122">This new process replaces the former **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="97f61-123">每次使用下列所述的版本設定程式更新原始評估時，您的自訂評估會繼承這些更新，並保留您的自訂控制項。</span><span class="sxs-lookup"><span data-stu-id="97f61-123">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="97f61-124">此外，您也可以輕鬆修改您自己的現有範本。</span><span class="sxs-lookup"><span data-stu-id="97f61-124">It's also easier to modify your own existing templates.</span></span> <span data-ttu-id="97f61-125">您可以匯出範本，在相同的活頁簿中進行變更，然後使用儲存的編輯匯入。</span><span class="sxs-lookup"><span data-stu-id="97f61-125">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="97f61-126">查看使用此新程式[建立範本](working-with-compliance-manager.md#templates)的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="97f61-126">View detailed instructions on [creating templates](working-with-compliance-manager.md#templates) with this new process.</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="97f61-127">版本設定通知和控制</span><span class="sxs-lookup"><span data-stu-id="97f61-127">Versioning notice and control</span></span>

<span data-ttu-id="97f61-128">您的組織已于2020年4月發行的合規性管理員中收到更新的評估，以協助您對齊認證和法規更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-128">Your organization received updated assessments in the April 2020 release of Compliance Manager to help you align with certification and regulation updates.</span></span> <span data-ttu-id="97f61-129">向前發展，我們將為您提供一種方法，讓您瞭解並透過版本設定**警示**接受所有未來的更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-129">Moving forward, we'll provide a clear way for you to understand and accept all future updates through **versioning alerts**.</span></span>

<span data-ttu-id="97f61-130">每當可用於評估範本或改進動作的更新時，提醒圖示會通知您已準備好更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-130">Whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="97f61-131">當您按一下該圖示時，會快顯視窗來說明更新，並提示您接受。</span><span class="sxs-lookup"><span data-stu-id="97f61-131">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="97f61-132">選取警示圖示會顯示彈出窗格，說明更新並提示您接受。</span><span class="sxs-lookup"><span data-stu-id="97f61-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept.</span></span> <span data-ttu-id="97f61-133">深入瞭解[接受評估的更新](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates)。</span><span class="sxs-lookup"><span data-stu-id="97f61-133">Learn more about [accepting updates to assessments](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="97f61-134">一般動作會在群組間同步處理狀態</span><span class="sxs-lookup"><span data-stu-id="97f61-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="97f61-135">如果您的組織有多個評估群組，**技術**動作的行為（也就是影響整個組織的動作）已變更。</span><span class="sxs-lookup"><span data-stu-id="97f61-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) has changed.</span></span> <span data-ttu-id="97f61-136">群組間的任何重複動作都已合併成一個單一動作。</span><span class="sxs-lookup"><span data-stu-id="97f61-136">Any duplicate actions across groups have been combined into one single action.</span></span> <span data-ttu-id="97f61-137">單一巨集指令包含重複版本的所有上傳的記事及證據。</span><span class="sxs-lookup"><span data-stu-id="97f61-137">That single action contains all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="97f61-138">使用此變更，技術動作現在會如同屬於相同群組時的行為。</span><span class="sxs-lookup"><span data-stu-id="97f61-138">With this change, technical actions will now behave as they did when they belonged to the same group.</span></span> <span data-ttu-id="97f61-139">在一個群組或評估中對動作所做的任何變更現在都會反映在所有的實例中。</span><span class="sxs-lookup"><span data-stu-id="97f61-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="97f61-140">「**實施」狀態**、「**實施日期**」、「**測試狀態**」及「**測試日期**」會反映最新的更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-140">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="97f61-141">語言支援</span><span class="sxs-lookup"><span data-stu-id="97f61-141">Language support</span></span>

<span data-ttu-id="97f61-142">合規性管理員現在可用於下列語言，除了英文：中文（簡體）、中文（繁體）、法文、德文、義大利文、日文、韓文、葡萄牙文（巴西）、俄文及西班牙文。</span><span class="sxs-lookup"><span data-stu-id="97f61-142">Compliance Manager is now available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="97f61-143">合規性管理員中的已知問題（預覽）</span><span class="sxs-lookup"><span data-stu-id="97f61-143">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="97f61-144">下列章節涵蓋合規性管理員目前版本中的已知問題。</span><span class="sxs-lookup"><span data-stu-id="97f61-144">The following section covers known issues in the current release of Compliance Manager.</span></span>

### <a name="dimension-values"></a><span data-ttu-id="97f61-145">維度值</span><span class="sxs-lookup"><span data-stu-id="97f61-145">Dimension values</span></span>

<span data-ttu-id="97f61-146">在2020年4月的資料移轉過程中，有些組織可能會在其評估與範本中看到**產品\*\*\*\*或憑證**值「custom」。</span><span class="sxs-lookup"><span data-stu-id="97f61-146">As a result of data migration during the April 2020 release, some organizations may see a **Product** or **Certification** value of "custom" in their assessments and templates.</span></span> <span data-ttu-id="97f61-147">如果 [**產品**] 或 [**證書**] 欄位是空白的，則此值會自動插入，而且不會影響資料工作流程。</span><span class="sxs-lookup"><span data-stu-id="97f61-147">This value was inserted automatically if the **Product** or **Certification** fields were blank, and there won't be an effect on data workflows.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="97f61-148">合規性分數</span><span class="sxs-lookup"><span data-stu-id="97f61-148">Compliance Score</span></span>

- <span data-ttu-id="97f61-149">對於標示為**Not In 範圍**的動作專案，指派給交辦事項的分數不會從相容性分數計算中排除。</span><span class="sxs-lookup"><span data-stu-id="97f61-149">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="97f61-150">標記為**Not In 範圍的**動作專案不會提升您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="97f61-150">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="97f61-151">安全分數</span><span class="sxs-lookup"><span data-stu-id="97f61-151">Secure Score</span></span>

- <span data-ttu-id="97f61-152">在某些 Microsoft 365 和 Office 365 訂閱中，有些動作專案無法使用安全分數結果。</span><span class="sxs-lookup"><span data-stu-id="97f61-152">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="97f61-153">在這些情況下，**無法偵測到**安全分數結果。</span><span class="sxs-lookup"><span data-stu-id="97f61-153">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="97f61-154">有時候會為對應的原則及未完成的動作專案傳回安全分數結果。</span><span class="sxs-lookup"><span data-stu-id="97f61-154">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="97f61-155">針對新承租人，會自動開啟所有動作的安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-155">For new tenants, Secure Score updates for all actions are automatically turned on.</span></span> <span data-ttu-id="97f61-156">全域管理員可以將安全計分連續更新切換為 [關閉]，這樣會關閉所有動作的更新。</span><span class="sxs-lookup"><span data-stu-id="97f61-156">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="97f61-157">**附注**：當組織第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行安全的評分，以完全收集資料，並將其劃分為您的分數。</span><span class="sxs-lookup"><span data-stu-id="97f61-157">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="97f61-158">在這段時間內，將安全計分連續更新參數設定為**Off** ，並手動設定所要**執行**的動作，就會將該動作計算為您的分數。</span><span class="sxs-lookup"><span data-stu-id="97f61-158">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="97f61-159">在最初7天后，開啟安全分數連續更新會啟用從該點繼續進行監視。</span><span class="sxs-lookup"><span data-stu-id="97f61-159">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="97f61-160">當安全分數更新開啟時，安全分數會積極監控動作，不過動作的測試日期不會更新以反映監控。</span><span class="sxs-lookup"><span data-stu-id="97f61-160">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action's test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="97f61-161">當建立新的評估時，會自動包含 Microsoft 受管理的控制分數和安全分數整合。</span><span class="sxs-lookup"><span data-stu-id="97f61-161">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="97f61-162">安全分數整合不支援的任何動作都可以手動實施。</span><span class="sxs-lookup"><span data-stu-id="97f61-162">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="97f61-163">手動執行將會考慮該動作群組的分數。</span><span class="sxs-lookup"><span data-stu-id="97f61-163">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="export"></a><span data-ttu-id="97f61-164">匯出</span><span class="sxs-lookup"><span data-stu-id="97f61-164">Export</span></span>

- <span data-ttu-id="97f61-165">當範本的狀態設定為 [匯**入**] 或 [**待處理核准**] 時，範本匯出至 JSON 失敗。</span><span class="sxs-lookup"><span data-stu-id="97f61-165">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="97f61-166">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="97f61-166">Supported browsers</span></span>

- <span data-ttu-id="97f61-167">支援最新版本的 Microsoft Edge、Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="97f61-167">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="97f61-168">在您的瀏覽器重新整理之前，可能會出現更新的資料不會出現的情況。</span><span class="sxs-lookup"><span data-stu-id="97f61-168">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="97f61-169">不支援預覽版本的 Microsoft Edge，但沒有已知問題。</span><span class="sxs-lookup"><span data-stu-id="97f61-169">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="97f61-170">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="97f61-170">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="97f61-171">會話超時</span><span class="sxs-lookup"><span data-stu-id="97f61-171">Session timeout</span></span>

- <span data-ttu-id="97f61-172">當會話超時時，可能會出現「發生錯誤」錯誤。</span><span class="sxs-lookup"><span data-stu-id="97f61-172">When a session times out, a "Something went wrong" error may appear.</span></span> <span data-ttu-id="97f61-173">若要解決此問題，請移至 [[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)]，然後再登入。</span><span class="sxs-lookup"><span data-stu-id="97f61-173">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
