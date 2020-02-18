---
title: 使用保留標籤和 DLP 保護小組中的檔案
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 摘要：為具有不同資訊保護層級的小組中的檔案套用保留標籤和資料外洩防護 (DLP) 原則。
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083391"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="c055c-103">使用保留標籤和 DLP 保護小組中的檔案</span><span class="sxs-lookup"><span data-stu-id="c055c-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="c055c-104">您可以使用本文中的步驟，為基準、敏感和高度機密小組及其基礎 SharePoint 網站設計和部署保留標籤和資料外洩防護 (DLP) 原則。</span><span class="sxs-lookup"><span data-stu-id="c055c-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="c055c-105">如需這三種保護層級的詳細資訊，請參閱[在 Microsoft Teams 中保護檔案](secure-files-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c055c-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="c055c-106">如何進行此作業</span><span class="sxs-lookup"><span data-stu-id="c055c-106">How this works</span></span>

1. <span data-ttu-id="c055c-107">建立需要的保留標籤並將它們發行。</span><span class="sxs-lookup"><span data-stu-id="c055c-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="c055c-108">發行這些標籤可能需要最多 12 小時的時間。</span><span class="sxs-lookup"><span data-stu-id="c055c-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="c055c-109">針對所需的基礎 SharePoint 網站，請編輯文件庫設定，將需要的保留標籤套用至文件庫中的項目。</span><span class="sxs-lookup"><span data-stu-id="c055c-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="c055c-110">建立 DLP 原則，以根據保留標籤採取動作。</span><span class="sxs-lookup"><span data-stu-id="c055c-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="c055c-111">當使用者將文件新增至小組的基礎 SharePoint 網站文件庫時，文件依預設取得指派的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="c055c-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="c055c-112">如有需要，使用者可以變更標籤。</span><span class="sxs-lookup"><span data-stu-id="c055c-112">Users can change the label, if needed.</span></span> <span data-ttu-id="c055c-113">當使用者共用組織外部的文件時，DLP 會檢查是否已指派標籤，並在 DLP 原則符合標籤時採取動作。</span><span class="sxs-lookup"><span data-stu-id="c055c-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="c055c-114">DLP 也會尋找其他原則相符項目，例如保護具有信用卡號碼的檔案 (如果已設定這類原則)。</span><span class="sxs-lookup"><span data-stu-id="c055c-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="c055c-115">基礎 SharePoint 網站的保留標籤</span><span class="sxs-lookup"><span data-stu-id="c055c-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="c055c-116">建立保留標籤並將其指派給基礎 SharePoint 網站需要三個階段。</span><span class="sxs-lookup"><span data-stu-id="c055c-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="c055c-117">步驟 1：決定保留標籤名稱</span><span class="sxs-lookup"><span data-stu-id="c055c-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="c055c-118">在此階段中，您會為套用至基礎 SharePoint 網站的四種資訊保護層級，決定其保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="c055c-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="c055c-119">下表列出每種層級的建議名稱。</span><span class="sxs-lookup"><span data-stu-id="c055c-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="c055c-120">**基礎 SharePoint 網站保護層級**</span><span class="sxs-lookup"><span data-stu-id="c055c-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="c055c-121">**標籤名稱**</span><span class="sxs-lookup"><span data-stu-id="c055c-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c055c-122">基準-公用</span><span class="sxs-lookup"><span data-stu-id="c055c-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="c055c-123">內部公用</span><span class="sxs-lookup"><span data-stu-id="c055c-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="c055c-124">基準-私人</span><span class="sxs-lookup"><span data-stu-id="c055c-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="c055c-125">Private</span><span class="sxs-lookup"><span data-stu-id="c055c-125">Private</span></span>  <br/> |
|<span data-ttu-id="c055c-126">敏感性</span><span class="sxs-lookup"><span data-stu-id="c055c-126">Sensitive</span></span>  <br/> |<span data-ttu-id="c055c-127">敏感性</span><span class="sxs-lookup"><span data-stu-id="c055c-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="c055c-128">高度機密</span><span class="sxs-lookup"><span data-stu-id="c055c-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="c055c-129">高度機密</span><span class="sxs-lookup"><span data-stu-id="c055c-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="c055c-130">步驟 2：建立保留標籤</span><span class="sxs-lookup"><span data-stu-id="c055c-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="c055c-131">在此階段中，您會為不同資訊保護層級建立所決定的標籤，然後將它發佈。</span><span class="sxs-lookup"><span data-stu-id="c055c-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="c055c-132">使用具有安全性系統管理員或公司系統管理員角色的帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c055c-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="c055c-133">從瀏覽器的 [首頁 - Microsoft 365 合規性]\*\*\*\* 索引標籤，按一下 [分類] > [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="c055c-134">按一下 [保留標籤] > [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="c055c-135">在 [命名您的標籤]\*\*\*\* 窗格中，鍵入標籤名稱和系統管理員與使用者的描述，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="c055c-136">在 [檔案計畫描述元]\*\*\*\* 窗格上，視需要填寫，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c055c-137">在 [標籤設定]\*\*\*\* 窗格中，視需要將 [保留]\*\*\*\* 設定為 [開啟]\*\*\*\* 並設定保留設定。</span><span class="sxs-lookup"><span data-stu-id="c055c-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="c055c-138">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="c055c-139">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="c055c-140">針對其他標籤，按一下 [建立標籤]\*\*\*\*，然後視需要重複此程序中的步驟 3-7。</span><span class="sxs-lookup"><span data-stu-id="c055c-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="c055c-141">發佈新標籤</span><span class="sxs-lookup"><span data-stu-id="c055c-141">Publish your new labels</span></span>

<span data-ttu-id="c055c-142">接下來，使用下列步驟來發佈新的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="c055c-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="c055c-143">從 [標籤]\*\*\*\* 窗格，按一下 [保留標籤]\*\*\*\* 索引標籤，然後按一下 [發佈標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="c055c-144">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [選擇要發佈的標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="c055c-145">在 [選擇標籤]\*\*\*\* 窗格上，按一下 [新增]\*\*\*\*，選取所有四個標籤，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="c055c-146">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="c055c-147">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="c055c-148">在 [選擇位置]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="c055c-149">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入標籤集的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="c055c-150">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [發佈標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="c055c-151">步驟 3：將保留標籤套用至基礎 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="c055c-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="c055c-152">使用下列步驟，將保留標籤套用至基礎 SharePoint 網站的文件資料夾。</span><span class="sxs-lookup"><span data-stu-id="c055c-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="c055c-153">在小組中按一下 [檔案]\*\*\*\*，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="c055c-154">在瀏覽器的新 [SharePoint 網站] 索引標籤中，按一下 [文件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="c055c-155">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="c055c-156">在 [權限與管理]\*\*\*\* 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="c055c-157">在 [設定] - [套用標籤]\*\*\*\* 中，選取適當的保留標籤，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="c055c-158">關閉 SharePoint 網站的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c055c-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="c055c-159">重複步驟 1-6，將保留標籤指派給其他基礎 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="c055c-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="c055c-160">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="c055c-160">Here is your resulting configuration.</span></span>
  
![四種基礎 SharePoint 網站類型的保留標籤。](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="c055c-162">基礎 SharePoint 網站的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="c055c-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="c055c-163">使用下列步驟設定 DLP 原則，以在使用者在組織外部共用基礎 SharePoint 網站上的文件時通知使用者。</span><span class="sxs-lookup"><span data-stu-id="c055c-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="c055c-164">使用具有安全性系統管理員或公司系統管理員角色的帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="c055c-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="c055c-165">在瀏覽器的新 [Microsoft 365 合規性]\*\*\*\* 索引標籤上，按一下 [原則] > [資料外洩防護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="c055c-166">在 [首頁] > [資料外洩防護]\*\*\*\* 窗格中，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="c055c-167">在 [使用範本開始，或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="c055c-168">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入機密層級 DLP 原則的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c055c-169">在 [選擇位置]\*\*\*\* 窗格中，按一下 [讓我選擇一個特定位置]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="c055c-170">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\*、[OneDrive 帳戶]\*\*\*\* 和 [Teams 聊天與通道訊息]\*\*\*\* 位置，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="c055c-171">在 [自訂您要保護的內容類型]\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="c055c-172">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [保留標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="c055c-173">在 [保留標籤]\*\*\*\* 窗格中，按一下 [新增]\*\*\*\* 並選取 [敏感性]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="c055c-174">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="c055c-175">在 [Customize the type of content you want to protect] (自訂您要保護的內容類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="c055c-176">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="c055c-177">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="c055c-178">在文字方塊中，鍵入或貼上下列其中一個提示：</span><span class="sxs-lookup"><span data-stu-id="c055c-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="c055c-p106">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="c055c-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="c055c-p107">高度機密的檔案會受加密保護。只有獲得您 IT 部門授與權限的外部使用者可以讀取它們。</span><span class="sxs-lookup"><span data-stu-id="c055c-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="c055c-184">或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。</span><span class="sxs-lookup"><span data-stu-id="c055c-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="c055c-185">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="c055c-186">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="c055c-187">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="c055c-188">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="c055c-189">以下是敏感小組的設定結果。</span><span class="sxs-lookup"><span data-stu-id="c055c-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![使用敏感保留標籤的敏感小組適用的 DLP 原則](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="c055c-191">然後，使用下列步驟設定 DLP 原則，以在使用者在組織外部共用基礎 SharePoint 網站上的文件時封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="c055c-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="c055c-192">在瀏覽器的新 [Microsoft 365 合規性]\*\*\*\* 索引標籤上，按一下 [原則] > [資料外洩防護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="c055c-193">在 [資料外洩防護]\*\*\*\* 窗格中，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="c055c-194">在 [從範本開始或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="c055c-195">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入高度機密層級 DLP 原則的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="c055c-196">在 [選擇位置]\*\*\*\* 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c055c-197">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\*、[OneDrive 帳戶]\*\*\*\* 和 [Teams 聊天與通道訊息]\*\*\*\* 位置，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="c055c-198">在 [自訂要保護的敏感性資訊類型]\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="c055c-199">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [保留標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="c055c-200">在 [保留標籤]\*\*\*\* 窗格中，按一下 [新增]\*\*\*\*，並選取 [高度機密性]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="c055c-201">在 [Choose the types of content to protect]\(選擇要保護的內容類型)\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="c055c-202">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="c055c-203">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="c055c-204">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="c055c-205">在文字方塊中，鍵入或貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="c055c-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="c055c-p108">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="c055c-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="c055c-209">或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。</span><span class="sxs-lookup"><span data-stu-id="c055c-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="c055c-210">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="c055c-211">在 [如果偵測到敏感性資訊，您要怎麼做?]\*\*\*\* 窗格中，於 [偵測是否一次共用特定數目的敏感性資訊]\*\*\*\* 下，按一下 [限制存取或加密內容]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="c055c-212">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="c055c-213">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c055c-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="c055c-214">以下是高度機密小組的設定結果。</span><span class="sxs-lookup"><span data-stu-id="c055c-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![使用高度機密保留標籤的高度機密小組適用的 DLP 原則](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="c055c-216">下一步</span><span class="sxs-lookup"><span data-stu-id="c055c-216">Next step</span></span>

[<span data-ttu-id="c055c-217">使用敏感度標籤保護小組中的檔案</span><span class="sxs-lookup"><span data-stu-id="c055c-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="c055c-218">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c055c-218">See Also</span></span>

[<span data-ttu-id="c055c-219">在 Microsoft Teams 中保護檔案</span><span class="sxs-lookup"><span data-stu-id="c055c-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="c055c-220">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="c055c-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


