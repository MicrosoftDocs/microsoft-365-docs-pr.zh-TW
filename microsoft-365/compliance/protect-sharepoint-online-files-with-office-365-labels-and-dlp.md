---
title: 使用保留標籤與 DLP 來保護 SharePoint Online 檔案
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
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
description: 摘要：使用各種資訊保護層級，對 SharePoint Online 小組網站套用保留標籤和資料外洩防護 (DLP) 原則。
ms.openlocfilehash: cf1565f2a3fbe420abf7739528a78befda9dfe82
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077805"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="ab418-103">使用保留標籤與 DLP 來保護 SharePoint Online 檔案</span><span class="sxs-lookup"><span data-stu-id="ab418-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 <span data-ttu-id="ab418-104">**摘要：** 使用各種資訊保護層級，對 SharePoint Online 小組網站套用保留標籤和資料外洩防護 (DLP) 原則。</span><span class="sxs-lookup"><span data-stu-id="ab418-104">**Summary:** Apply retention labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="ab418-105">您可以使用本文中的步驟，為基準、機密和高度機密 SharePoint Online 小組網站設計及部署保留標籤和 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="ab418-105">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="ab418-106">如需這三種保護層級的詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="ab418-106">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="ab418-107">如何進行此作業</span><span class="sxs-lookup"><span data-stu-id="ab418-107">How this works</span></span>

1. <span data-ttu-id="ab418-108">建立需要的保留標籤並將它們發行。</span><span class="sxs-lookup"><span data-stu-id="ab418-108">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="ab418-109">發行這些標籤可能需要最多 12 小時的時間。</span><span class="sxs-lookup"><span data-stu-id="ab418-109">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="ab418-110">針對所需的 SharePoint 網站，請編輯文件庫設定，將需要的保留標籤套用至文件庫中的項目。</span><span class="sxs-lookup"><span data-stu-id="ab418-110">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="ab418-111">建立 DLP 原則，以根據保留標籤採取動作。</span><span class="sxs-lookup"><span data-stu-id="ab418-111">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="ab418-112">當使用者新增文件至文件庫時，依預設，文件會收到指派的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ab418-112">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="ab418-113">如有需要，使用者可以變更標籤。</span><span class="sxs-lookup"><span data-stu-id="ab418-113">Users can change the label, if needed.</span></span> <span data-ttu-id="ab418-114">當使用者共用組織外部的文件時，DLP 會檢查是否已指派標籤，並在 DLP 原則符合標籤時採取動作。</span><span class="sxs-lookup"><span data-stu-id="ab418-114">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="ab418-115">DLP 也會尋找其他原則相符項目，例如保護具有信用卡號碼的檔案 (如果已設定這類原則)。</span><span class="sxs-lookup"><span data-stu-id="ab418-115">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="ab418-116">適用於 SharePoint Online 網站的保留標籤</span><span class="sxs-lookup"><span data-stu-id="ab418-116">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="ab418-117">建立保留標籤並將其指派給 SharePoint Online 小組網站需要三個階段。</span><span class="sxs-lookup"><span data-stu-id="ab418-117">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="ab418-118">階段 1：決定保留標籤名稱</span><span class="sxs-lookup"><span data-stu-id="ab418-118">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="ab418-119">在此階段中，您會為套用至 SharePoint Online 小組網站的四種資訊保護層級，決定其保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="ab418-119">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="ab418-120">下表列出每種層級的建議名稱。</span><span class="sxs-lookup"><span data-stu-id="ab418-120">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="ab418-121">**SharePoint Online 小組網站保護層級**</span><span class="sxs-lookup"><span data-stu-id="ab418-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="ab418-122">**標籤名稱**</span><span class="sxs-lookup"><span data-stu-id="ab418-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab418-123">基準-公用</span><span class="sxs-lookup"><span data-stu-id="ab418-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="ab418-124">內部公用</span><span class="sxs-lookup"><span data-stu-id="ab418-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="ab418-125">基準-私人</span><span class="sxs-lookup"><span data-stu-id="ab418-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="ab418-126">Private</span><span class="sxs-lookup"><span data-stu-id="ab418-126">Private</span></span>  <br/> |
|<span data-ttu-id="ab418-127">敏感性</span><span class="sxs-lookup"><span data-stu-id="ab418-127">Sensitive</span></span>  <br/> |<span data-ttu-id="ab418-128">敏感性</span><span class="sxs-lookup"><span data-stu-id="ab418-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="ab418-129">高度機密</span><span class="sxs-lookup"><span data-stu-id="ab418-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="ab418-130">高度機密</span><span class="sxs-lookup"><span data-stu-id="ab418-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="ab418-131">階段 2：建立保留標籤</span><span class="sxs-lookup"><span data-stu-id="ab418-131">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="ab418-132">在此階段中，您會為不同資訊保護層級建立所決定的標籤，然後將它發佈。</span><span class="sxs-lookup"><span data-stu-id="ab418-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="ab418-133">使用具有安全性系統管理員或公司系統管理員角色的帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ab418-133">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="ab418-134">從瀏覽器的 [首頁 - Microsoft 365 合規性]\*\*\*\* 索引標籤，按一下 [分類] > [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-134">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="ab418-135">按一下 [保留標籤] > [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-135">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="ab418-136">在 [命名您的標籤]\*\*\*\* 窗格中，鍵入標籤名稱和系統管理員與使用者的描述，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-136">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="ab418-137">在 [檔案計畫描述元]\*\*\*\* 窗格上，視需要填寫，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-137">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ab418-138">在 [標籤設定]\*\*\*\* 窗格中，視需要將 [保留]\*\*\*\* 設定為 [開啟]\*\*\*\* 並設定保留設定。</span><span class="sxs-lookup"><span data-stu-id="ab418-138">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="ab418-139">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-139">Click **Next**.</span></span>
    
7. <span data-ttu-id="ab418-140">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-140">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="ab418-141">對於其他標籤，按一下 [建立標籤]\*\*\*\*，然後視需要重複步驟 3-7。</span><span class="sxs-lookup"><span data-stu-id="ab418-141">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="ab418-142">發佈新標籤</span><span class="sxs-lookup"><span data-stu-id="ab418-142">Publish your new labels</span></span>

<span data-ttu-id="ab418-143">接下來，使用下列步驟來發佈新的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ab418-143">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="ab418-144">從 [標籤]\*\*\*\* 窗格，按一下 [保留標籤]\*\*\*\* 索引標籤，然後按一下 [發佈標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-144">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="ab418-145">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [選擇要發佈的標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-145">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="ab418-146">在 [選擇標籤]\*\*\*\* 窗格上，按一下 [新增]\*\*\*\*，選取所有四個標籤，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-146">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="ab418-147">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-147">Click **Done**.</span></span>
    
5. <span data-ttu-id="ab418-148">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-148">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="ab418-149">在 [選擇位置]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-149">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="ab418-150">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入標籤集的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-150">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ab418-151">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [發佈標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-151">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="ab418-152">階段 3：將保留標籤套用至 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="ab418-152">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="ab418-153">使用下列步驟，將保留標籤套用至 SharePoint Online 小組網站的文件資料夾。</span><span class="sxs-lookup"><span data-stu-id="ab418-153">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="ab418-154">登入 [Office 365 入口網站](https://www.office.com)，按一下 **SharePoint** App。</span><span class="sxs-lookup"><span data-stu-id="ab418-154">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="ab418-155">在瀏覽器的新 [SharePoint]\*\*\*\* 索引標籤中，按一下需要指派保留標籤的網站。</span><span class="sxs-lookup"><span data-stu-id="ab418-155">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="ab418-156">在瀏覽器的新 [SharePoint 網站] 索引標籤中，按一下 [文件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-156">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="ab418-157">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-157">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="ab418-158">在 [權限與管理]\*\*\*\* 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-158">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="ab418-159">在 [設定] - [套用標籤]\*\*\*\* 中，選取適當的保留標籤，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-159">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="ab418-160">關閉 SharePoint Online 網站的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ab418-160">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="ab418-161">重複步驟 2-8，將保留標籤指派給其他 SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="ab418-161">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="ab418-162">以下是產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ab418-162">Here is your resulting configuration.</span></span>
  
![用於四種類型 SharePoint Online 小組網站的保留標籤。](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="ab418-164">適用於 SharePoint Online 網站的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="ab418-164">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="ab418-165">使用下列步驟來設定 DLP 原則，以在使用者共用組織外部 SharePoint Online 機密小組網站上的文件時通知使用者。</span><span class="sxs-lookup"><span data-stu-id="ab418-165">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="ab418-166">使用具有安全性系統管理員或公司系統管理員角色的帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ab418-166">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="ab418-167">在瀏覽器的新 [Microsoft 365 合規性]\*\*\*\* 索引標籤上，按一下 [原則] > [資料外洩防護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-167">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="ab418-168">在 [首頁] > [資料外洩防護]\*\*\*\* 窗格中，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-168">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="ab418-169">在 [使用範本開始，或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-169">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="ab418-170">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入機密層級 DLP 原則的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-170">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ab418-171">在 [選擇位置]\*\*\*\* 窗格中，按一下 [讓我選擇一個特定位置]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-171">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="ab418-172">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\*、[OneDrive 帳戶]\*\*\*\* 和 [Teams 聊天與通道訊息]\*\*\*\* 位置，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-172">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ab418-173">在 [自訂您要保護的內容類型]\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-173">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="ab418-174">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [保留標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-174">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="ab418-175">在 [保留標籤]\*\*\*\* 窗格中，按一下 [新增]\*\*\*\* 並選取 [敏感性]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-175">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="ab418-176">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-176">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="ab418-177">在 [Customize the type of content you want to protect] (自訂您要保護的內容類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-177">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="ab418-178">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-178">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="ab418-179">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-179">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="ab418-180">在文字方塊中，根據您是否實作 Azure 資訊保護來保護高度機密的檔案，以鍵入或貼上下列其中一個提示：</span><span class="sxs-lookup"><span data-stu-id="ab418-180">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="ab418-p106">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="ab418-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="ab418-p107">高度機密的檔案會受加密保護。只有獲得您 IT 部門授與權限的外部使用者可以讀取它們。</span><span class="sxs-lookup"><span data-stu-id="ab418-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="ab418-186">或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。</span><span class="sxs-lookup"><span data-stu-id="ab418-186">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="ab418-187">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-187">Click **OK**.</span></span>
    
17. <span data-ttu-id="ab418-188">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-188">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="ab418-189">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-189">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="ab418-190">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-190">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="ab418-191">以下是敏感性 SharePoint Online 小組網站的設定結果。</span><span class="sxs-lookup"><span data-stu-id="ab418-191">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![使用 [敏感性] 保留標籤之隔離 SharePoint Online 小組網站的 DLP 原則](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="ab418-193">接下來，使用下列步驟來設定 DLP 原則，以在使用者共用組織外部 SharePoint Online 高度機密小組網站上的文件時封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="ab418-193">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="ab418-194">在瀏覽器的新 [Microsoft 365 合規性]\*\*\*\* 索引標籤上，按一下 [原則] > [資料外洩防護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-194">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="ab418-195">在 [資料外洩防護]\*\*\*\* 窗格中，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-195">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="ab418-196">在 [從範本開始或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-196">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="ab418-197">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入高度機密層級 DLP 原則的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-197">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="ab418-198">在 [選擇位置]\*\*\*\* 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-198">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ab418-199">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\*、[OneDrive 帳戶]\*\*\*\* 和 [Teams 聊天與通道訊息]\*\*\*\* 位置，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-199">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="ab418-200">在 [自訂要保護的敏感性資訊類型]\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-200">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="ab418-201">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [保留標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-201">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="ab418-202">在 [保留標籤]\*\*\*\* 窗格中，按一下 [新增]\*\*\*\*，並選取 [高度機密性]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-202">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="ab418-203">在 [Choose the types of content to protect]\(選擇要保護的內容類型)\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-203">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="ab418-204">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-204">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="ab418-205">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-205">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="ab418-206">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-206">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="ab418-207">在文字方塊中，鍵入或貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="ab418-207">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="ab418-p108">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="ab418-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="ab418-211">或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。</span><span class="sxs-lookup"><span data-stu-id="ab418-211">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="ab418-212">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-212">Click **OK**.</span></span>
    
17. <span data-ttu-id="ab418-213">在 [如果偵測到敏感性資訊，您要怎麼做?]\*\*\*\* 窗格中，於 [偵測是否一次共用特定數目的敏感性資訊]\*\*\*\* 下，按一下 [限制存取或加密內容]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-213">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="ab418-214">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-214">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="ab418-215">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab418-215">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="ab418-216">以下是高度機密 SharePoint Online 小組網站的設定結果。</span><span class="sxs-lookup"><span data-stu-id="ab418-216">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![使用 [高度機密性] 保留標籤之隔離 SharePoint Online 小組網站的 DLP 原則](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="ab418-218">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ab418-218">Next step</span></span>

[<span data-ttu-id="ab418-219">使用 Azure 資訊保護來保護 SharePoint Online 檔案</span><span class="sxs-lookup"><span data-stu-id="ab418-219">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="ab418-220">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ab418-220">See Also</span></span>

<span data-ttu-id="ab418-221"><<<<<<< HEAD [保護 SharePoint Online 網站和檔案](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="ab418-221">[Secure SharePoint Online sites and files](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)</span></span>
  
<a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizationssecurityoffice-365-securitymicrosoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-omd"></a>[<span data-ttu-id="ab418-222">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="ab418-222">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
=======
[<span data-ttu-id="ab418-223">保護 SharePoint Online 網站與檔案</span><span class="sxs-lookup"><span data-stu-id="ab418-223">Secure SharePoint Online sites and files</span></span>](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="ab418-224">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="ab418-224">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
>>>>>>> <span data-ttu-id="ab418-225">9904103ea22646c71f6541e03c7491a767a783ce</span><span class="sxs-lookup"><span data-stu-id="ab418-225">9904103ea22646c71f6541e03c7491a767a783ce</span></span>
  
[<span data-ttu-id="ab418-226">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="ab418-226">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


