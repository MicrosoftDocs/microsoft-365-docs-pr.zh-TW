---
title: Microsoft 365 企業版測試環境的資料分類
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，可在 Microsoft 365 for enterprise 測試環境中的檔上建立及使用保留標籤。
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919185"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d3334-103">Microsoft 365 企業版測試環境的資料分類</span><span class="sxs-lookup"><span data-stu-id="d3334-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d3334-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="d3334-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d3334-105">本文說明如何使用 Microsoft 365 for enterprise 測試環境中的保留標籤來設定資料分類。</span><span class="sxs-lookup"><span data-stu-id="d3334-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="d3334-106">分類測試環境中的資料包括三個階段：</span><span class="sxs-lookup"><span data-stu-id="d3334-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="d3334-107">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="d3334-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d3334-108">階段2：建立保留標籤</span><span class="sxs-lookup"><span data-stu-id="d3334-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="d3334-109">階段3：將保留標籤套用至檔</span><span class="sxs-lookup"><span data-stu-id="d3334-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d3334-111">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="d3334-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d3334-112">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="d3334-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d3334-113">如果您只想以具有最低需求的輕量方式設定保留標籤，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="d3334-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d3334-114">如果您想要在模擬的企業中設定保留標籤，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="d3334-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3334-115">測試保留標籤並不需要模擬的企業測試環境，其中包括連線到網際網路的模擬內部網路與目錄同步處理，以及 (AD DS) 樹系中的 Active Directory 網域服務的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="d3334-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d3334-116">它會以選項形式提供，以便您可以測試自動授權和群組成員資格，並在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="d3334-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="d3334-117">階段2：建立保留標籤</span><span class="sxs-lookup"><span data-stu-id="d3334-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="d3334-118">在這個階段中，針對 SharePoint 線上檔資料夾，建立不同保留層級的保留標籤：</span><span class="sxs-lookup"><span data-stu-id="d3334-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="d3334-119">使用您的全域系統管理員帳戶登入 [Microsoft 365 的安全性中心](https://security.microsoft.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="d3334-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="d3334-120">從瀏覽器的 [**主版-Microsoft 365 安全性**] 索引標籤中，選取 [**分類**  >  **保留標籤**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="d3334-121">選取 [建立標籤]。</span><span class="sxs-lookup"><span data-stu-id="d3334-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="d3334-122">在 [**命名您的標籤**] 窗格中，**輸入您標籤** 的 [**內部公用**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d3334-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="d3334-123">在 [ **檔計畫描述項** ] 窗格中，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d3334-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="d3334-124">在 [ **標籤設定** ] 窗格中，視需要將 **保留** 設定為 [ **開啟**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d3334-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="d3334-125">在 [ **複查您的設定** ] 窗格中，選取 [ **建立標籤**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="d3334-126">針對以下名稱的標籤，重複步驟 3-7：</span><span class="sxs-lookup"><span data-stu-id="d3334-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="d3334-127">私人</span><span class="sxs-lookup"><span data-stu-id="d3334-127">Private</span></span>
  - <span data-ttu-id="d3334-128">敏感性</span><span class="sxs-lookup"><span data-stu-id="d3334-128">Sensitive</span></span>
  - <span data-ttu-id="d3334-129">高度機密</span><span class="sxs-lookup"><span data-stu-id="d3334-129">Highly Confidential</span></span>
1. <span data-ttu-id="d3334-130">在 [ **保留標籤** ] 窗格中，選取 [ **發行標籤**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="d3334-131">在 [ **選擇要發佈的標籤** ] 窗格中，選取 **[選擇要發佈的標籤**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="d3334-132">在 [ **選擇標籤** ] 窗格中，選取 [ **新增** ]，然後選取所有四個標籤。</span><span class="sxs-lookup"><span data-stu-id="d3334-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="d3334-133">選取 [ **新增**]，然後選取 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="d3334-134">在 [ **選擇要發佈的標籤** ] 窗格中，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d3334-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="d3334-135">在 [ **選擇位置** ] 窗格中，選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="d3334-136">在 [**命名您的原則**] 窗格的 **[名稱] 中輸入\*\*\*\*範例組織**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d3334-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="d3334-137">在 [ **複查您的設定** ] 窗格中，選取 [ **發行標籤**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="d3334-138">可能需要幾分鐘的時間才能發佈保留標籤。</span><span class="sxs-lookup"><span data-stu-id="d3334-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="d3334-139">階段3：將保留標籤套用至檔</span><span class="sxs-lookup"><span data-stu-id="d3334-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="d3334-140">在此階段中，您會探索 SharePoint Online 網站之 Documents 資料夾中檔案的預設保留標籤行為，並手動變更檔的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="d3334-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="d3334-141">首先，建立機密層級 SharePoint Online 小組網站：</span><span class="sxs-lookup"><span data-stu-id="d3334-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="d3334-142">使用您的瀏覽器的私人實例，使用您的全域系統管理員帳戶登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="d3334-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="d3334-143">在磚清單中，選取 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="d3334-144">在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，選取 [ **建立網站**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="d3334-145">在 [ **建立網站** ] 頁面上，選取 [ **小組網站**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="d3334-146">在 [ **小組網站名稱** ] 方塊中，輸入 **SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="d3334-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="d3334-147">在 [ **小組網站描述** ] 方塊中，輸入 **機密檔的 SharePoint 網站**。</span><span class="sxs-lookup"><span data-stu-id="d3334-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="d3334-148">在 [ **隱私權設定**] 中，選取 [ **僅私人成員可以存取此網站**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d3334-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="d3334-149">在 [ **您想要新增誰？** ] 窗格中，選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d3334-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="d3334-150">接下來，針對敏感保留標籤設定 SensitiveFiles 小組網站的 Documents 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d3334-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="d3334-151">在瀏覽器的 [ **SensitiveFiles** ] 索引標籤中，選取 [ **檔**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="d3334-152">選取 [ **設定** ] 圖示，然後選取 [文檔 **庫設定**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="d3334-153">在 [ **許可權與管理**] 底下，選取 [ **將標籤套用至此清單或文件庫中的專案**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="d3334-154">如果未顯示此選項，則您的保留標籤尚未發佈。</span><span class="sxs-lookup"><span data-stu-id="d3334-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="d3334-155">請稍後再嘗試此步驟。</span><span class="sxs-lookup"><span data-stu-id="d3334-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="d3334-156">在 [設定]-[套用 **標籤**] 的下拉式方塊中，選取 [ **敏感** ]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="d3334-157">接下來，在 SensitiveFiles 網站中建立新的檔，並變更其保留標籤。</span><span class="sxs-lookup"><span data-stu-id="d3334-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="d3334-158">在 [檔] 資料夾中，選取 [**新增**  >  **Word 檔**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="d3334-159">在空白檔中輸入一些文字。</span><span class="sxs-lookup"><span data-stu-id="d3334-159">Enter some text in the blank document.</span></span> <span data-ttu-id="d3334-160">等候文字的儲存。</span><span class="sxs-lookup"><span data-stu-id="d3334-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="d3334-161">在功能表列上，選取 [ **共用檔**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="d3334-162">在 **Document.docx** 檔案名旁，選取垂直省略號，然後選取 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="d3334-163">在右窗格的 [ **屬性** ] 區段中，于 [套用 **保留標籤**] 底下，請注意檔已自動套用 **敏感** 保留標籤。</span><span class="sxs-lookup"><span data-stu-id="d3334-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="d3334-164">按一下 [ **全部編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="d3334-165">在 [ **Document.docx** ] 窗格中的 [套用 **保留標籤**] 底下，選取 [ **高度機密** ] 標籤，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d3334-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="d3334-166">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d3334-166">Next step</span></span>

<span data-ttu-id="d3334-167">在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="d3334-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3334-168">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d3334-168">See also</span></span>

[<span data-ttu-id="d3334-169">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="d3334-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d3334-170">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="d3334-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d3334-171">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="d3334-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)