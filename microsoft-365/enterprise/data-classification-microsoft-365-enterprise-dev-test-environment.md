---
title: 資料分類您的 Microsoft 365 企業版測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南來建立及使用 Microsoft 365 企業版測試環境中的文件上的 Office 365 保留標籤。
ms.openlocfilehash: 3d64cd245e117813cb4c81a6e9099cd1a0120317
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283536"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="00d22-103">資料分類您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="00d22-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="00d22-104">透過本文中的指示，您可以設定 Microsoft 365 企業版測試環境中使用 Office 365 保留標籤的資料分類。</span><span class="sxs-lookup"><span data-stu-id="00d22-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="00d22-106">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="00d22-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="00d22-107">階段 1： 建置 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="00d22-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="00d22-108">如果您只想以具有最小需求的輕量型方式設定 Office 365 保留標籤，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="00d22-108">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="00d22-109">如果您想要在模擬的企業中設定 Office 365 保留標籤，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="00d22-109">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="00d22-110">測試 Office 365 保留標籤不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。</span><span class="sxs-lookup"><span data-stu-id="00d22-110">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="00d22-111">它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="00d22-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="00d22-112">階段 2： 建立 Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="00d22-112">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="00d22-113">在這個階段，您可以建立不同的層級的保留為 SharePoint Online 的文件資料夾的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="00d22-113">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="00d22-114">請使用您的全域系統管理員帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="00d22-114">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="00d22-115">從瀏覽器的 [首頁 - Microsoft 365 合規性]\*\*\*\* 索引標籤，按一下 [分類] > [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-115">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="00d22-116">按一下 [保留標籤] > [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-116">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="00d22-117">在 [命名您的標籤]\*\*\*\* 窗格中，在 [命名您的標籤]\*\*\*\* 中輸入 **內部公用**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-117">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="00d22-118">在 [檔案計畫描述元]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-118">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="00d22-119">在 [標籤設定]\*\*\*\* 窗格中，視需要將 [保留]\*\*\*\* 設定為 [開啟]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-119">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="00d22-120">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-120">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="00d22-121">使用這些名稱的其他標籤重複步驟 3-7:</span><span class="sxs-lookup"><span data-stu-id="00d22-121">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="00d22-122">Private</span><span class="sxs-lookup"><span data-stu-id="00d22-122">Private</span></span>
    
  - <span data-ttu-id="00d22-123">敏感性</span><span class="sxs-lookup"><span data-stu-id="00d22-123">Sensitive</span></span>
    
  - <span data-ttu-id="00d22-124">高度機密</span><span class="sxs-lookup"><span data-stu-id="00d22-124">Highly Confidential</span></span>
  
9. <span data-ttu-id="00d22-125">從 [首頁] > [標籤]\*\*\*\* 窗格中，按一下 [Publish labels]\(發佈標籤)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-125">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="00d22-126">在 [選擇要發佈的標籤]\*\*\*\* 窗格中，按一下 [選擇要發佈的標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-126">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="00d22-127">在 [Choose labels]\(選擇標籤)\*\*\*\* 窗格中，按一下 [新增]\*\*\*\* 並選取所有四個標籤。</span><span class="sxs-lookup"><span data-stu-id="00d22-127">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="00d22-128">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-128">Click **Done**.</span></span>
    
13. <span data-ttu-id="00d22-129">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-129">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="00d22-130">在 [選擇位置]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-130">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="00d22-131">在 [命名您的原則]\*\*\*\* 窗格上，於 [名稱]\*\*\*\* 中輸入 **範例組織**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-131">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="00d22-132">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [發佈標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-132">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="00d22-133">請注意，可能需要幾分鐘的時間要發佈保留標籤。</span><span class="sxs-lookup"><span data-stu-id="00d22-133">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="00d22-134">階段 3： 將 Office 365 保留標籤套用至文件</span><span class="sxs-lookup"><span data-stu-id="00d22-134">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="00d22-135">在這個階段，您探索的 SharePoint Online 網站的文件資料夾中檔案的預設保留標籤行為，並以手動方式變更文件的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="00d22-135">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="00d22-136">首先，建立敏感性層級 SharePoint Online 小組網站：</span><span class="sxs-lookup"><span data-stu-id="00d22-136">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="00d22-137">請使用本機電腦上的瀏覽器，並以全域管理員帳戶登入 [Office 365 入口網站](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="00d22-137">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="00d22-138">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-138">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="00d22-139">新**SharePoint**索引標籤上瀏覽器中，按一下 [**建立網站**]。</span><span class="sxs-lookup"><span data-stu-id="00d22-139">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="00d22-140">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-140">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="00d22-141">在 [**小組網站名稱**] 中，輸入**SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="00d22-141">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="00d22-142">在 [**小組網站描述**] 中，輸入**SharePoint 網站的敏感性檔案**。</span><span class="sxs-lookup"><span data-stu-id="00d22-142">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="00d22-143">在 [隱私權設定]\*\*\*\* 中，選取 [私人 - 只有成員可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-143">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="00d22-144">在 [您想要新增誰?]\*\*\*\* 窗格上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-144">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="00d22-145">接下來，設定敏感的保留標籤的 SensitiveFiles 小組網站的文件資料夾。</span><span class="sxs-lookup"><span data-stu-id="00d22-145">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="00d22-146">在瀏覽器的 [ **SensitiveFiles** ] 索引標籤中，按一下 [**文件**]。</span><span class="sxs-lookup"><span data-stu-id="00d22-146">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="00d22-147">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-147">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="00d22-148">在 [權限與管理]\*\*\*\* 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00d22-148">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="00d22-149">在 [**設定-套用標籤**] 中，在下拉式方塊中，選取 [**敏感性**，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="00d22-149">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="00d22-150">接下來，在 SensitiveFiles 網站中建立新的文件，並變更其保留標籤。</span><span class="sxs-lookup"><span data-stu-id="00d22-150">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="00d22-151">在 [文件] 資料夾中，按一下 [**新增 > Word 文件**。</span><span class="sxs-lookup"><span data-stu-id="00d22-151">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="00d22-152">在空白的文件中輸入一些文字。</span><span class="sxs-lookup"><span data-stu-id="00d22-152">Type some text in the blank document.</span></span> <span data-ttu-id="00d22-153">等待要儲存的文字。</span><span class="sxs-lookup"><span data-stu-id="00d22-153">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="00d22-154">在功能表列中，按一下 [**共享文件**。</span><span class="sxs-lookup"><span data-stu-id="00d22-154">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="00d22-155">按一下**Document.docx**檔案名稱旁的 [Word] 圖示。</span><span class="sxs-lookup"><span data-stu-id="00d22-155">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="00d22-156">在右窗格中，在 [**屬性**] 區段的 [**套用保留標籤**] 中，記下的文件已有 「**敏感性**」 標籤自動套用。</span><span class="sxs-lookup"><span data-stu-id="00d22-156">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="00d22-157">按一下 [**編輯所有**。</span><span class="sxs-lookup"><span data-stu-id="00d22-157">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="00d22-158">在 [ **Document.docx** ] 窗格中，[**套用標籤**] 中，選取 [**高度機密**] 標籤，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="00d22-158">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="00d22-159">在**資訊保護**階段中的資訊，以及如何部署 Office 365 保留標籤在生產環境中的連結，請參閱[設定環境的分類](infoprotect-configure-classification.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="00d22-159">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="00d22-160">下一步</span><span class="sxs-lookup"><span data-stu-id="00d22-160">Next step</span></span>

<span data-ttu-id="00d22-161">瀏覽額外的[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和測試環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="00d22-161">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="00d22-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="00d22-162">See also</span></span>

[<span data-ttu-id="00d22-163">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="00d22-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="00d22-164">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="00d22-164">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="00d22-165">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="00d22-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 