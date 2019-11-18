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
ms.openlocfilehash: 192519e323f9d23420f82a603979b50f4581ac4f
ms.sourcegitcommit: e2ed110c4c3a8434f9fcc9d610069bc77bc39220
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2019
ms.locfileid: "38685554"
---
# <a name="microsoft-compliance-score-release-notes-preview"></a><span data-ttu-id="bae9c-103">Microsoft 合規性分數版本資訊 （預覽）</span><span class="sxs-lookup"><span data-stu-id="bae9c-103">Microsoft Compliance Score release notes (Preview)</span></span>

<span data-ttu-id="bae9c-104">Microsoft 合規性分數公開預覽為您提供搶先即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="bae9c-104">The public preview of Microsoft Compliance Score provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="bae9c-105">合規性分數是在[Microsoft 365 合規性中心](microsoft-365-compliance-center.md)，計算風險分數，測量向完成建議的動作，協助減少合規性風險您進行的新功能。</span><span class="sxs-lookup"><span data-stu-id="bae9c-105">Compliance Score is a new feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that calculates a risk-based score, measuring your progress towards completing recommended actions that help reduce compliance risks.</span></span>

## <a name="compliance-score-and-compliance-manager-relationship"></a><span data-ttu-id="bae9c-106">合規性分數和合規性管理員中的關聯性</span><span class="sxs-lookup"><span data-stu-id="bae9c-106">Compliance Score and Compliance Manager relationship</span></span>

<span data-ttu-id="bae9c-107">許多處理合規性管理員中的符合性功能現在可以完成合規性分數。</span><span class="sxs-lookup"><span data-stu-id="bae9c-107">Many of the compliance functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="bae9c-108">不過部分功能仍會保留僅限合規性管理員中，並公開預覽期間變更合規性管理員中的某些舊版功能。</span><span class="sxs-lookup"><span data-stu-id="bae9c-108">However some functionality still resides only in Compliance Manager, and some previous functionality in Compliance Manager is altered during the public preview period.</span></span> 

<span data-ttu-id="bae9c-109">當您在公開預覽期間使用合規性分數和合規性管理員中，請記住以下幾點：</span><span class="sxs-lookup"><span data-stu-id="bae9c-109">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

- <span data-ttu-id="bae9c-110">**管理評估**： 使用者可以檢視 「 評估 」 以及其狀態的詳細資料合規性分數。</span><span class="sxs-lookup"><span data-stu-id="bae9c-110">**Managing assessments**: users can view assessments and their status details in Compliance Score.</span></span> <span data-ttu-id="bae9c-111">不過使用者只能在合規性管理員 （的[檢視指示](working-with-compliance-manager.md#assessments)），以及工作執行評定的管理工作，並受限於下列：</span><span class="sxs-lookup"><span data-stu-id="bae9c-111">However users can only perform assessment management tasks in Compliance Manager ([view instructions](working-with-compliance-manager.md#assessments)), and tasks and are limited to the following:</span></span>
    - <span data-ttu-id="bae9c-112">上傳新的評估，但不是能修改現有 「 評估 」。</span><span class="sxs-lookup"><span data-stu-id="bae9c-112">Upload new assessments, but not modify existing assessments.</span></span> <span data-ttu-id="bae9c-113">如果您要修改現有的評估，您將需要上傳新的範本。</span><span class="sxs-lookup"><span data-stu-id="bae9c-113">If you need to modify an existing assessment, you will need to upload a new template.</span></span>
    - <span data-ttu-id="bae9c-114">匯出評估</span><span class="sxs-lookup"><span data-stu-id="bae9c-114">Export assessments</span></span>
    - <span data-ttu-id="bae9c-115">封存評估</span><span class="sxs-lookup"><span data-stu-id="bae9c-115">Archive assessments</span></span>
    - <span data-ttu-id="bae9c-116">檢視封存的評估</span><span class="sxs-lookup"><span data-stu-id="bae9c-116">View archived assessments</span></span>
 - <span data-ttu-id="bae9c-117">**建立範本的 「 評估 」**:</span><span class="sxs-lookup"><span data-stu-id="bae9c-117">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="bae9c-118">使用者必須移至合規性管理員中建立新的範本，並匯出現有範本。</span><span class="sxs-lookup"><span data-stu-id="bae9c-118">Users must go to Compliance Manager to create new templates and export existing templates.</span></span> 
   - <span data-ttu-id="bae9c-119">無法自訂現有範本。</span><span class="sxs-lookup"><span data-stu-id="bae9c-119">Existing templates cannot be customized.</span></span> <span data-ttu-id="bae9c-120">請閱讀[管理範本合規性管理員中](working-with-compliance-manager.md#templates)的指示。</span><span class="sxs-lookup"><span data-stu-id="bae9c-120">Read instructions for [managing templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="bae9c-121">在建立範本時，您必須包含維度這兩個**產品**和**憑證**以確保您的範本會顯示在 [合規性分數。</span><span class="sxs-lookup"><span data-stu-id="bae9c-121">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
 - <span data-ttu-id="bae9c-122">**設定權限**： 不先前授與權限合規性管理員中的合規性分數使用者必須在 Microsoft 365 合規性中心中設定其權限。</span><span class="sxs-lookup"><span data-stu-id="bae9c-122">**Setting permissions**: Compliance Score users who were not previously granted permissions in Compliance Manager must have their permissions set in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="bae9c-123">使用合規性分數時，其角色先前設定合規性管理員中的使用者可以使用該相同層級的存取。</span><span class="sxs-lookup"><span data-stu-id="bae9c-123">Users whose roles were previously set in Compliance Manager can use that same level of access when working in Compliance Score.</span></span>
- <span data-ttu-id="bae9c-124">**傳輸的資料**： 組織的合規性管理員中的資料將會看到的資料合規性分數，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bae9c-124">**Transfer of data**: organizations with data residing in Compliance Manger will see that data in Compliance Score, and vice-versa.</span></span>
- <span data-ttu-id="bae9c-125">**登入到合規性管理員從合規性分數**： 如果使用者登入合規性分數，並選取連結移至合規性管理員中，使用者將不必再次登入。</span><span class="sxs-lookup"><span data-stu-id="bae9c-125">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user will not have to sign in again.</span></span> <span data-ttu-id="bae9c-126">按下連結之後, 的新索引標籤開啟瀏覽器主講人是舊檔] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="bae9c-126">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="bae9c-127">在 [使用標頭 [top] 區段中，「 已 Microsoft 雲端服務客戶嗎？</span><span class="sxs-lookup"><span data-stu-id="bae9c-127">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="bae9c-128">您的帳戶，登入]，選取 [自動登入到合規性管理員的**登入**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bae9c-128">Sign in to your account,” select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="bae9c-129">在 [合規性分數 （預覽） 的已知的問題</span><span class="sxs-lookup"><span data-stu-id="bae9c-129">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="bae9c-130">下列各節涵蓋解析的合規性分數的未來版本的已知的問題。</span><span class="sxs-lookup"><span data-stu-id="bae9c-130">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="launch-now-links-in-certain-improvement-actions"></a><span data-ttu-id="bae9c-131">啟動現在特定改進動作中的連結</span><span class="sxs-lookup"><span data-stu-id="bae9c-131">Launch Now links in certain improvement actions</span></span>

<span data-ttu-id="bae9c-132">在某些改進的動作，選取 [**立即啟動**連結下方的實作指示出現會產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="bae9c-132">In certain improvement actions, selecting the **Launch Now** link that appears underneath the implementation instructions gives an error.</span></span> <span data-ttu-id="bae9c-133">若要存取的適當的目的地，也就是 SharePoint 系統管理中心，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bae9c-133">To access the proper destination, which is the the SharePoint admin center, follow these steps:</span></span>

1. <span data-ttu-id="bae9c-134">移至[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bae9c-134">Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="bae9c-135">在左的導覽功能表上，選取 [**全部顯示**]。</span><span class="sxs-lookup"><span data-stu-id="bae9c-135">On the left navigation menu, select **Show all**.</span></span>
3. <span data-ttu-id="bae9c-136">在**系統管理中心，** 選取 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="bae9c-136">Under **Admin centers,** select **SharePoint**.</span></span>

<span data-ttu-id="bae9c-137">以下是受影響的改進的動作，所有位於**保護資訊**類別：</span><span class="sxs-lookup"><span data-stu-id="bae9c-137">Below are the affected improvement actions, which all reside in the **Protect information** category:</span></span>
  - <span data-ttu-id="bae9c-138">將加密套用至 SharePoint 文件庫</span><span class="sxs-lookup"><span data-stu-id="bae9c-138">Apply encryption to SharePoint Library</span></span>
  - <span data-ttu-id="bae9c-139">線上分類 SharePoint 中的資料</span><span class="sxs-lookup"><span data-stu-id="bae9c-139">Classify Data in SharePoint Online</span></span>
  - <span data-ttu-id="bae9c-140">設定到期的外部共用連結</span><span class="sxs-lookup"><span data-stu-id="bae9c-140">Configure External Sharing Links to Expire</span></span>
  - <span data-ttu-id="bae9c-141">啟用版本設定的文件庫</span><span class="sxs-lookup"><span data-stu-id="bae9c-141">Enable Versioning for Document Libraries</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="bae9c-142">非管理員使用者的長載入時間</span><span class="sxs-lookup"><span data-stu-id="bae9c-142">Long load times for non-admin users</span></span>
<span data-ttu-id="bae9c-143">保留以外的系統管理員角色的角色的合規性分數使用者可能會遇到長載入時間時，嘗試登入。</span><span class="sxs-lookup"><span data-stu-id="bae9c-143">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="bae9c-144">重新整理瀏覽器可解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="bae9c-144">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="bae9c-145">（深入了解[合規性分數角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)。）</span><span class="sxs-lookup"><span data-stu-id="bae9c-145">(Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="bae9c-146">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="bae9c-146">Supported browsers</span></span>

- <span data-ttu-id="bae9c-147">支援最新版的 Microsoft Edge、 Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="bae9c-147">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="bae9c-148">可能會有更新的資料不會在重新整理瀏覽器直到出現的執行個體。</span><span class="sxs-lookup"><span data-stu-id="bae9c-148">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="bae9c-149">Microsoft Edge 的預覽版本不支援，但有任何已知的問題。</span><span class="sxs-lookup"><span data-stu-id="bae9c-149">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="bae9c-150">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="bae9c-150">Internet Explorer is not supported.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="bae9c-151">語言支援</span><span class="sxs-lookup"><span data-stu-id="bae9c-151">Language support</span></span>

- <span data-ttu-id="bae9c-152">合規性分數是僅提供英文 （美國）。</span><span class="sxs-lookup"><span data-stu-id="bae9c-152">Compliance Score is only available in U.S. English.</span></span>