---
title: Microsoft 合規性分數版本資訊
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
description: 版本資訊及已知的問題的 Microsoft 合規性分數 （預覽），可協助簡化和自動化風險評定 M365 合規性中心中的功能。
ms.openlocfilehash: 370c714c927d09a16272f8ab265c7b0c4e36381a
ms.sourcegitcommit: 5fc0f2cd1f2596fd10299333c826c501936dcd98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2020
ms.locfileid: "41261867"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a><span data-ttu-id="56339-103">Microsoft 合規性分數 （預覽） 版本資訊</span><span class="sxs-lookup"><span data-stu-id="56339-103">Microsoft Compliance Score (Preview) release notes</span></span>

<span data-ttu-id="56339-104">Microsoft 合規性分數公開預覽為您提供搶先即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="56339-104">The public preview of Microsoft Compliance Score provides you with early access to upcoming functionality and updates.</span></span> <span data-ttu-id="56339-105">檢查此頁面，經常若要了解 what's new。</span><span class="sxs-lookup"><span data-stu-id="56339-105">Check this page frequently to learn what's new.</span></span>

<span data-ttu-id="56339-106">合規性分數是在[Microsoft 365 合規性中心](microsoft-365-compliance-center.md)，計算風險分數，測量向完成建議的動作，協助減少合規性風險您進行的新功能。</span><span class="sxs-lookup"><span data-stu-id="56339-106">Compliance Score is a new feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that calculates a risk-based score, measuring your progress towards completing recommended actions that help reduce compliance risks.</span></span>

## <a name="whats-new"></a><span data-ttu-id="56339-107">新功能</span><span class="sxs-lookup"><span data-stu-id="56339-107">What's new</span></span>

### <a name="new-templates-for-assessments"></a><span data-ttu-id="56339-108">評估適用的新範本</span><span class="sxs-lookup"><span data-stu-id="56339-108">New templates for assessments</span></span>

<span data-ttu-id="56339-109">新預先設定的範本，針對評估發行至生產環境的合規性分數 （預覽） 時，他們就可以使用。</span><span class="sxs-lookup"><span data-stu-id="56339-109">New pre-configured templates for assessments are released into production for Compliance Score (Preview) as they become available.</span></span> <span data-ttu-id="56339-110">請檢查[以下範本的完整清單](compliance-score.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="56339-110">Check the [full list of templates here](compliance-score.md#templates).</span></span> <span data-ttu-id="56339-111">最近新增的範本包括：</span><span class="sxs-lookup"><span data-stu-id="56339-111">Recently-added templates include:</span></span>

- <span data-ttu-id="56339-112">巴西一般資料保護 Law (LGPD)</span><span class="sxs-lookup"><span data-stu-id="56339-112">Brazil General Data Protection Law (LGPD)</span></span>
- <span data-ttu-id="56339-113">次 / 澳洲政府 ISM （預覽）</span><span class="sxs-lookup"><span data-stu-id="56339-113">IRAP / Australian Government ISM (Preview)</span></span>
- <span data-ttu-id="56339-114">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="56339-114">ISO 27701:2019</span></span>
- <span data-ttu-id="56339-115">SOC 1</span><span class="sxs-lookup"><span data-stu-id="56339-115">SOC 1</span></span>
- <span data-ttu-id="56339-116">SOC 2</span><span class="sxs-lookup"><span data-stu-id="56339-116">SOC 2</span></span>

### <a name="compliance-score-relationship-to-compliance-manager"></a><span data-ttu-id="56339-117">合規性分數關係到合規性管理員</span><span class="sxs-lookup"><span data-stu-id="56339-117">Compliance Score relationship to Compliance Manager</span></span>

<span data-ttu-id="56339-118">許多處理合規性管理員中的符合性功能現在可以完成合規性分數。</span><span class="sxs-lookup"><span data-stu-id="56339-118">Many of the compliance functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="56339-119">不過部分功能仍會保留僅限合規性管理員中，並公開預覽期間變更合規性管理員中的某些舊版功能。</span><span class="sxs-lookup"><span data-stu-id="56339-119">However some functionality still resides only in Compliance Manager, and some previous functionality in Compliance Manager is altered during the public preview period.</span></span> 

<span data-ttu-id="56339-120">當您在公開預覽期間使用合規性分數和合規性管理員中，請記住以下幾點：</span><span class="sxs-lookup"><span data-stu-id="56339-120">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

- <span data-ttu-id="56339-121">**管理評估**： 使用者可以檢視 「 評估 」 以及其狀態的詳細資料合規性分數。</span><span class="sxs-lookup"><span data-stu-id="56339-121">**Managing assessments**: users can view assessments and their status details in Compliance Score.</span></span> <span data-ttu-id="56339-122">不過使用者可以只執行評估管理工作合規性管理員中 （的[檢視指示](working-with-compliance-manager.md#assessments)），以及工作僅限於下列：</span><span class="sxs-lookup"><span data-stu-id="56339-122">However users can only perform assessment management tasks in Compliance Manager ([view instructions](working-with-compliance-manager.md#assessments)), and tasks are limited to the following:</span></span>
    - <span data-ttu-id="56339-123">上傳新的評估，但不是能修改現有 「 評估 」。</span><span class="sxs-lookup"><span data-stu-id="56339-123">Upload new assessments, but not modify existing assessments.</span></span> <span data-ttu-id="56339-124">如果您要修改現有的評估，您將需要上傳新的範本。</span><span class="sxs-lookup"><span data-stu-id="56339-124">If you need to modify an existing assessment, you will need to upload a new template.</span></span>
    - <span data-ttu-id="56339-125">匯出評估</span><span class="sxs-lookup"><span data-stu-id="56339-125">Export assessments</span></span>
    - <span data-ttu-id="56339-126">封存評估</span><span class="sxs-lookup"><span data-stu-id="56339-126">Archive assessments</span></span>
    - <span data-ttu-id="56339-127">檢視封存的評估</span><span class="sxs-lookup"><span data-stu-id="56339-127">View archived assessments</span></span>
 - <span data-ttu-id="56339-128">**建立範本的 「 評估 」**:</span><span class="sxs-lookup"><span data-stu-id="56339-128">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="56339-129">使用者必須移至合規性管理員中建立新的範本，並匯出現有範本。</span><span class="sxs-lookup"><span data-stu-id="56339-129">Users must go to Compliance Manager to create new templates and export existing templates.</span></span> 
   - <span data-ttu-id="56339-130">無法自訂現有範本。</span><span class="sxs-lookup"><span data-stu-id="56339-130">Existing templates cannot be customized.</span></span> <span data-ttu-id="56339-131">請閱讀[管理範本合規性管理員中](working-with-compliance-manager.md#templates)的指示。</span><span class="sxs-lookup"><span data-stu-id="56339-131">Read instructions for [managing templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="56339-132">在建立範本時，您必須包含維度這兩個**產品**和**憑證**以確保您的範本會顯示在 [合規性分數。</span><span class="sxs-lookup"><span data-stu-id="56339-132">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
 - <span data-ttu-id="56339-133">**設定權限**： 不先前授與權限合規性管理員中的合規性分數使用者必須在 Microsoft 365 合規性中心 （[如深入了解](compliance-score-setup.md#set-user-permissions-and-assign-roles)） 中設定其權限。</span><span class="sxs-lookup"><span data-stu-id="56339-133">**Setting permissions**: Compliance Score users who were not previously granted permissions in Compliance Manager must have their permissions set in the Microsoft 365 compliance center ([learn more](compliance-score-setup.md#set-user-permissions-and-assign-roles)).</span></span> <span data-ttu-id="56339-134">使用合規性分數時，其角色先前設定合規性管理員中的使用者可以使用該相同層級的存取。</span><span class="sxs-lookup"><span data-stu-id="56339-134">Users whose roles were previously set in Compliance Manager can use that same level of access when working in Compliance Score.</span></span>
- <span data-ttu-id="56339-135">**傳輸的資料**： 組織的合規性管理員中的資料將會看到的資料合規性分數，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="56339-135">**Transfer of data**: organizations with data residing in Compliance Manger will see that data in Compliance Score, and vice-versa.</span></span>
- <span data-ttu-id="56339-136">**登入到合規性管理員從合規性分數**： 如果使用者登入合規性分數，並選取連結移至合規性管理員中，使用者將不必再次登入。</span><span class="sxs-lookup"><span data-stu-id="56339-136">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user will not have to sign in again.</span></span> <span data-ttu-id="56339-137">按下連結之後, 的新索引標籤開啟瀏覽器主講人是舊檔] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="56339-137">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="56339-138">在 [使用標頭 [top] 區段中，「 已 Microsoft 雲端服務客戶嗎？</span><span class="sxs-lookup"><span data-stu-id="56339-138">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="56339-139">您的帳戶，登入]，選取 [自動登入到合規性管理員的**登入**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="56339-139">Sign in to your account,” select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="56339-140">在 [合規性分數 （預覽） 的已知的問題</span><span class="sxs-lookup"><span data-stu-id="56339-140">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="56339-141">下列各節涵蓋解析的合規性分數的未來版本的已知的問題。</span><span class="sxs-lookup"><span data-stu-id="56339-141">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="launch-now-links-in-certain-improvement-actions"></a><span data-ttu-id="56339-142">啟動現在特定改進動作中的連結</span><span class="sxs-lookup"><span data-stu-id="56339-142">Launch Now links in certain improvement actions</span></span>

<span data-ttu-id="56339-143">在某些改進的動作，選取 [**立即啟動**連結下方的實作指示出現會產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="56339-143">In certain improvement actions, selecting the **Launch Now** link that appears underneath the implementation instructions gives an error.</span></span> <span data-ttu-id="56339-144">若要存取的適當的目的地，也就是 SharePoint 系統管理中心，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="56339-144">To access the proper destination, which is the SharePoint admin center, follow these steps:</span></span>

1. <span data-ttu-id="56339-145">移至[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="56339-145">Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="56339-146">在左的導覽功能表上，選取 [**全部顯示**]。</span><span class="sxs-lookup"><span data-stu-id="56339-146">On the left navigation menu, select **Show all**.</span></span>
3. <span data-ttu-id="56339-147">在**系統管理中心，** 選取 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="56339-147">Under **Admin centers,** select **SharePoint**.</span></span>

<span data-ttu-id="56339-148">以下是受影響的改進的動作，所有位於**保護資訊**類別：</span><span class="sxs-lookup"><span data-stu-id="56339-148">Below are the affected improvement actions, which all reside in the **Protect information** category:</span></span>
  - <span data-ttu-id="56339-149">將加密套用至 SharePoint 文件庫</span><span class="sxs-lookup"><span data-stu-id="56339-149">Apply encryption to SharePoint Library</span></span>
  - <span data-ttu-id="56339-150">線上分類 SharePoint 中的資料</span><span class="sxs-lookup"><span data-stu-id="56339-150">Classify Data in SharePoint Online</span></span>
  - <span data-ttu-id="56339-151">設定到期的外部共用連結</span><span class="sxs-lookup"><span data-stu-id="56339-151">Configure External Sharing Links to Expire</span></span>
  - <span data-ttu-id="56339-152">啟用版本設定的文件庫</span><span class="sxs-lookup"><span data-stu-id="56339-152">Enable Versioning for Document Libraries</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="56339-153">非管理員使用者的長載入時間</span><span class="sxs-lookup"><span data-stu-id="56339-153">Long load times for non-admin users</span></span>
<span data-ttu-id="56339-154">保留以外的系統管理員角色的角色的合規性分數使用者可能會遇到長載入時間時，嘗試登入。</span><span class="sxs-lookup"><span data-stu-id="56339-154">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="56339-155">重新整理瀏覽器可解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="56339-155">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="56339-156">（深入了解[合規性分數角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)。）</span><span class="sxs-lookup"><span data-stu-id="56339-156">(Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="56339-157">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="56339-157">Supported browsers</span></span>

- <span data-ttu-id="56339-158">支援最新版的 Microsoft Edge、 Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="56339-158">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="56339-159">可能會有更新的資料不會在重新整理瀏覽器直到出現的執行個體。</span><span class="sxs-lookup"><span data-stu-id="56339-159">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="56339-160">Microsoft Edge 的預覽版本不支援，但有任何已知的問題。</span><span class="sxs-lookup"><span data-stu-id="56339-160">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="56339-161">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="56339-161">Internet Explorer is not supported.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="56339-162">語言支援</span><span class="sxs-lookup"><span data-stu-id="56339-162">Language support</span></span>

- <span data-ttu-id="56339-163">合規性分數是僅提供英文 （美國）。</span><span class="sxs-lookup"><span data-stu-id="56339-163">Compliance Score is only available in U.S. English.</span></span>