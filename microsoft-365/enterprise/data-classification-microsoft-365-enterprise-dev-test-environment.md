---
title: Microsoft 365 企業版的資料分類測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南建立及使用 Office 365 標籤在 Microsoft 365 企業版測試環境中的文件。
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866733"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d37b4-103">Microsoft 365 企業版的資料分類測試環境</span><span class="sxs-lookup"><span data-stu-id="d37b4-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d37b4-104">本文中的指示，您設定 Microsoft 365 企業版測試環境中使用 Office 365 標籤的資料分類。</span><span class="sxs-lookup"><span data-stu-id="d37b4-104">With the instructions in this article, you configure data classification using Office 365 labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d37b4-106">按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="d37b4-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d37b4-107">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="d37b4-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d37b4-108">如果只想要設定 Office 365 標籤具有的基本硬體需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="d37b4-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d37b4-109">如果您要設定模擬企業中的 Office 365 標籤，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="d37b4-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d37b4-p101">測試 Office 365 標籤不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="d37b4-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="d37b4-112">階段 2：建立 Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="d37b4-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="d37b4-113">在此階段中，您可以建立不同的層級的 SharePoint Online 的文件資料夾的安全性的標籤。</span><span class="sxs-lookup"><span data-stu-id="d37b4-113">In this phase, you create the labels for the different levels of security for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="d37b4-p102">必要時，使用專用的網際網路瀏覽器並登入 Office 365 入口網站以全域管理員帳戶。為了協助，請參閱 ＜[登入 Office 365 的位置](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="d37b4-p102">If needed, use a private instance of your Internet browser and sign in to the Office 365 portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="d37b4-116">從 [Microsoft Office 的首頁]\*\*\*\* 索引標籤中，按一下 [管理]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="d37b4-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="d37b4-117">從瀏覽器的新 [Office 系統管理中心]\*\*\*\* 索引標籤中，按一下 [系統管理中心] > [安全性 &amp; 合規性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="d37b4-118">從瀏覽器的新 [首頁 - 安全性 &amp; 合規性]\*\*\*\* 索引標籤中，按一下 [分類] > [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-118">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="d37b4-119">從 [首頁] > [標籤]\*\*\*\* 窗格中，按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-119">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="d37b4-120">在 [命名您的標籤]\*\*\*\* 窗格中，輸入 **內部公用**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-120">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d37b4-121">在 [標籤設定]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-121">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="d37b4-122">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立此標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-122">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="d37b4-123">重複步驟 5-8，逐一設定下列其他標籤：</span><span class="sxs-lookup"><span data-stu-id="d37b4-123">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="d37b4-124">Private</span><span class="sxs-lookup"><span data-stu-id="d37b4-124">Private</span></span>
    
  - <span data-ttu-id="d37b4-125">敏感性</span><span class="sxs-lookup"><span data-stu-id="d37b4-125">Sensitive</span></span>
    
  - <span data-ttu-id="d37b4-126">高度機密</span><span class="sxs-lookup"><span data-stu-id="d37b4-126">Highly Confidential</span></span>
    
10. <span data-ttu-id="d37b4-127">從 [首頁] > [標籤]\*\*\*\* 窗格中，按一下 [Publish labels]\(發佈標籤)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-127">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="d37b4-128">在 [選擇要發佈的標籤]\*\*\*\* 窗格中，按一下 [選擇要發佈的標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-128">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="d37b4-129">在 [Choose labels]\(選擇標籤)\*\*\*\* 窗格中，按一下 [新增]\*\*\*\* 並選取所有四個標籤。</span><span class="sxs-lookup"><span data-stu-id="d37b4-129">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="d37b4-130">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-130">Click **Done**.</span></span>
    
14. <span data-ttu-id="d37b4-131">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-131">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="d37b4-132">在 [選擇位置]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-132">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="d37b4-133">在 [命名您的原則]\*\*\*\* 窗格上，於 [名稱]\*\*\*\* 中輸入 **範例組織**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-133">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="d37b4-134">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [發佈標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-134">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="d37b4-135">請注意可能需要幾分鐘時間要發佈之標籤。</span><span class="sxs-lookup"><span data-stu-id="d37b4-135">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-labels-to-documents"></a><span data-ttu-id="d37b4-136">階段 3： 將 Office 365 標籤套用至文件</span><span class="sxs-lookup"><span data-stu-id="d37b4-136">Phase 3: Apply Office 365 labels to documents</span></span>

<span data-ttu-id="d37b4-137">在此階段中，您會發現 label 的預設行為的 SharePoint Online 網站的 [文件] 資料夾中的檔案與手動變更文件的標籤。</span><span class="sxs-lookup"><span data-stu-id="d37b4-137">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="d37b4-138">首先，建立機密層級 SharePoint Online 小組網站：</span><span class="sxs-lookup"><span data-stu-id="d37b4-138">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="d37b4-p103">請使用本機電腦上的瀏覽器，並以全域管理員帳戶登入 Office 365 入口網站。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="d37b4-p103">Using a browser on your local computer, sign in to the Office 365 portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="d37b4-141">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-141">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="d37b4-142">在 [新增**SharePoint** ] 索引標籤在瀏覽器中按一下 [**建立網站**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-142">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="d37b4-143">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-143">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="d37b4-144">在**小組網站名稱**] 中輸入**SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-144">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="d37b4-145">在**小組網站描述**] 中，輸入**SharePoint 網站的機密檔案**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-145">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="d37b4-146">在 [隱私權設定]\*\*\*\* 中，選取 [私人 - 只有成員可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-146">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d37b4-147">在 [您想要新增誰?]\*\*\*\* 窗格上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-147">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="d37b4-148">接下來，設定機密標籤 SensitiveFiles 小組網站的 [文件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d37b4-148">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="d37b4-149">在瀏覽器中的 [ **SensitiveFiles** ] 索引標籤中，按一下 [**文件**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-149">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="d37b4-150">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-150">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="d37b4-151">在 [權限與管理]\*\*\*\* 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37b4-151">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="d37b4-152">在**套用設定的標籤**、 下拉式方塊中，選取 [**機密**] 和 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="d37b4-153">接下來，SensitiveFiles 網站中建立新的文件並變更其標籤。</span><span class="sxs-lookup"><span data-stu-id="d37b4-153">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="d37b4-154">在 [文件] 資料夾中，按一下 [**新增 > Word 文件**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="d37b4-p104">在空白的文件中輸入一些文字。等待儲存的文字。</span><span class="sxs-lookup"><span data-stu-id="d37b4-p104">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="d37b4-157">在功能表列中，按一下 [**共享文件**]。</span><span class="sxs-lookup"><span data-stu-id="d37b4-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="d37b4-158">按一下 [Word 圖示旁**Document.docx**檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="d37b4-158">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="d37b4-159">在右窗格的 [**屬性**] 區段的 [**套用] 標籤**、 中記下文件已經有自動套用**敏感**標籤。</span><span class="sxs-lookup"><span data-stu-id="d37b4-159">In the right-hand pane, in the **Properties** section, under **Apply label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="d37b4-160">按一下 [**編輯所有**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="d37b4-161">在**Document.docx**窗格**套用標籤**、 選取的**高度機密**的標籤和 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="d37b4-161">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="d37b4-162">請參閱[Configure 分類環境的](data-classification-microsoft-365-enterprise-dev-test-environment.md)步驟中的資訊及連結至 Office 365 標籤在生產環境中的**資訊保護**階段。</span><span class="sxs-lookup"><span data-stu-id="d37b4-162">See the [Configure classification for your environment](data-classification-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to Office 365 labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="d37b4-163">下一步</span><span class="sxs-lookup"><span data-stu-id="d37b4-163">Next step</span></span>

<span data-ttu-id="d37b4-164">探索測試環境的其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)特色和功能。</span><span class="sxs-lookup"><span data-stu-id="d37b4-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d37b4-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d37b4-165">See also</span></span>

[<span data-ttu-id="d37b4-166">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="d37b4-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d37b4-167">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="d37b4-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d37b4-168">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="d37b4-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 