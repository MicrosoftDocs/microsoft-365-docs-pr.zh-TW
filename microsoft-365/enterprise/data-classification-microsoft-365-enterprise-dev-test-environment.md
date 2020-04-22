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
description: 使用此測試實驗室指南，可在 Microsoft 365 企業版測試環境中的檔上建立及使用保留標籤。
ms.openlocfilehash: 41873eba8f2d6168d68d771c6feb17a44c775f6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636089"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="42499-103">Microsoft 365 企業版測試環境的資料分類</span><span class="sxs-lookup"><span data-stu-id="42499-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="42499-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="42499-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="42499-105">透過本文中的指示，您可以使用 Microsoft 365 企業版測試環境中的保留標籤來設定資料分類。</span><span class="sxs-lookup"><span data-stu-id="42499-105">With the instructions in this article, you configure data classification using retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="42499-107">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="42499-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="42499-108">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="42499-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="42499-109">如果您只想以具有最低需求的輕量方式設定保留標籤，請遵循[輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="42499-109">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="42499-110">如果您想要在模擬的企業中設定保留標籤，請依照[傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="42499-110">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="42499-111">測試保留標籤並不需要模擬的企業測試環境，其中包括連線到網際網路的模擬內部網路和 Active Directory 網域服務（AD DS）樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="42499-111">Testing retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="42499-112">這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="42499-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="42499-113">階段2：建立保留標籤</span><span class="sxs-lookup"><span data-stu-id="42499-113">Phase 2: Create retention labels</span></span>

<span data-ttu-id="42499-114">在此階段中，您會為 SharePoint 線上檔資料夾，建立不同保留層級的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="42499-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="42499-115">使用您的全域系統管理員帳戶登入[Microsoft 365 的安全性中心](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="42499-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="42499-116">從瀏覽器的 [**主版-Microsoft 365 安全性**] 索引標籤中，按一下 [**分類 > 保留標籤**]。</span><span class="sxs-lookup"><span data-stu-id="42499-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="42499-117">按一下 **[建立標籤]**。</span><span class="sxs-lookup"><span data-stu-id="42499-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="42499-118">在 [**命名您的標籤**] 窗格中，**輸入您標籤**的 [**內部公用**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42499-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="42499-119">在 [**檔計畫描述項**] 窗格中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42499-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="42499-120">在 [**標籤設定**] 窗格中，視需要將**保留**設定為 [**開啟**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42499-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="42499-121">在 [**複查您的設定**] 窗格中，按一下 [**建立標籤**]。</span><span class="sxs-lookup"><span data-stu-id="42499-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="42499-122">針對以下名稱的標籤，重複步驟 3-7：</span><span class="sxs-lookup"><span data-stu-id="42499-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="42499-123">私人</span><span class="sxs-lookup"><span data-stu-id="42499-123">Private</span></span>
    
  - <span data-ttu-id="42499-124">敏感性</span><span class="sxs-lookup"><span data-stu-id="42499-124">Sensitive</span></span>
    
  - <span data-ttu-id="42499-125">高度機密</span><span class="sxs-lookup"><span data-stu-id="42499-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="42499-126">在 [**保留標籤**] 窗格中，按一下 [**發佈標籤**]。</span><span class="sxs-lookup"><span data-stu-id="42499-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="42499-127">在 [**選擇要發佈的標籤**] 窗格中，按一下 **[選擇要發佈的標籤**]。</span><span class="sxs-lookup"><span data-stu-id="42499-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="42499-128">在 [**選擇標籤**] 窗格中，按一下 [**新增**]，然後選取所有四個標籤。</span><span class="sxs-lookup"><span data-stu-id="42499-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="42499-129">按一下 [**新增**]，然後按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="42499-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="42499-130">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42499-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="42499-131">在 [選擇位置]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42499-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="42499-132">在 [命名您的原則]\*\*\*\* 窗格上，於 [名稱]\*\*\*\* 中輸入 **範例組織**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42499-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="42499-133">在 [**複查您的設定**] 窗格上，按一下 [**發佈標籤**]。</span><span class="sxs-lookup"><span data-stu-id="42499-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="42499-134">請注意，保留標籤可能需要幾分鐘的時間才能發行。</span><span class="sxs-lookup"><span data-stu-id="42499-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="42499-135">階段3：將保留標籤套用至檔</span><span class="sxs-lookup"><span data-stu-id="42499-135">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="42499-136">在此階段中，您會探索 SharePoint Online 網站之 Documents 資料夾中檔案的預設保留標籤行為，並手動變更檔的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="42499-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="42499-137">首先，建立機密層級 SharePoint Online 小組網站：</span><span class="sxs-lookup"><span data-stu-id="42499-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="42499-138">使用您的瀏覽器的私人實例，使用您的全域系統管理員帳戶登入[Office 365 入口網站](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="42499-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="42499-139">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42499-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="42499-140">在瀏覽器的 [新增**SharePoint** ] 索引標籤上，按一下 [**建立網站**]。</span><span class="sxs-lookup"><span data-stu-id="42499-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="42499-141">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42499-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="42499-142">在 [**小組網站名稱**] 中，輸入**SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="42499-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="42499-143">在 [**小組網站描述**] 中，輸入**機密檔的 SharePoint 網站**。</span><span class="sxs-lookup"><span data-stu-id="42499-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="42499-144">在 [隱私權設定]\*\*\*\* 中，選取 [私人 - 只有成員可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42499-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="42499-145">在 [**您想要新增誰？** ] 窗格中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="42499-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="42499-146">接下來，針對敏感保留標籤設定 SensitiveFiles 小組網站的 Documents 資料夾。</span><span class="sxs-lookup"><span data-stu-id="42499-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="42499-147">在瀏覽器的 [ **SensitiveFiles** ] 索引標籤中，按一下 [**檔**]。</span><span class="sxs-lookup"><span data-stu-id="42499-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="42499-148">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42499-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="42499-149">在 [**許可權與管理**] 底下，按一下 [**對此清單或文件庫中的專案套用標籤**]。</span><span class="sxs-lookup"><span data-stu-id="42499-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="42499-150">如果未顯示此選項，則您的保留標籤尚未發行。</span><span class="sxs-lookup"><span data-stu-id="42499-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="42499-151">請稍後再嘗試此步驟。</span><span class="sxs-lookup"><span data-stu-id="42499-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="42499-152">在 [設定]-[套用**標籤**] 的下拉式方塊中，選取 [**敏感**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="42499-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="42499-153">接下來，在 SensitiveFiles 網站中建立新的檔，並變更其保留標籤。</span><span class="sxs-lookup"><span data-stu-id="42499-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="42499-154">在 [檔] 資料夾中，按一下 [**新增 > Word 檔**]。</span><span class="sxs-lookup"><span data-stu-id="42499-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="42499-155">在空白檔中輸入一些文字。</span><span class="sxs-lookup"><span data-stu-id="42499-155">Type some text in the blank document.</span></span> <span data-ttu-id="42499-156">等候文字的儲存。</span><span class="sxs-lookup"><span data-stu-id="42499-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="42499-157">在功能表列中，按一下 [**共用檔**]。</span><span class="sxs-lookup"><span data-stu-id="42499-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="42499-158">按一下檔 **.docx**檔案名旁邊的垂直省略號，然後按一下 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="42499-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="42499-159">在右窗格的 [**屬性**] 區段中，于 [套用**保留標籤**] 底下，請注意檔已自動套用**敏感**保留標籤。</span><span class="sxs-lookup"><span data-stu-id="42499-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="42499-160">按一下 [**全部編輯**]。</span><span class="sxs-lookup"><span data-stu-id="42499-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="42499-161">在 [**檔 .docx** ] 窗格中的 [套用**保留標籤**] 底下，選取 [**高度機密**] 標籤，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="42499-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="42499-162">如需如何在生產環境中部署保留標籤的資訊和連結，請參閱**資訊保護**階段中[設定環境](infoprotect-configure-classification.md)步驟的分類。</span><span class="sxs-lookup"><span data-stu-id="42499-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="42499-163">下一步</span><span class="sxs-lookup"><span data-stu-id="42499-163">Next step</span></span>

<span data-ttu-id="42499-164">在您的測試環境中探索其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和功能。</span><span class="sxs-lookup"><span data-stu-id="42499-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="42499-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="42499-165">See also</span></span>

[<span data-ttu-id="42499-166">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="42499-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="42499-167">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="42499-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="42499-168">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="42499-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
