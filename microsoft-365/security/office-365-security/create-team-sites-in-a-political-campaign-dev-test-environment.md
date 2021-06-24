---
title: 建立小組網站 - 政治活動開發/測試環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 摘要：在政治活動開發/測試環境中，建立公用、私用、敏感性及高度機密的 SharePoint Online 小組網站。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80c975cd181f326fc2766c6ebfbd0d7f8a5164f2
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108148"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="5d187-103">在政治活動開發/測試環境中建立小組網站</span><span class="sxs-lookup"><span data-stu-id="5d187-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5d187-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5d187-104">**Applies to**</span></span>

- [<span data-ttu-id="5d187-105">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="5d187-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="5d187-106">**摘要：** 在政治活動開發/測試環境中，建立公用、私用、敏感性及高度機密的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="5d187-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="5d187-p101">使用本文所述指示來建立開發/測試環境，其中包含針對 [適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)解決方案的四種不同類型的 SharePoint Online 小組網站。這些網站會在主題 10 中詳細說明，主題 10 的標題為 **「SharePoint 和商務用 OneDrive」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="5d187-109">階段 1：建立政治活動開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="5d187-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="5d187-110">首先，請依照[設定政治活動開發/測試環境的群組和使用者](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)中的指示來建立訂閱、使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="5d187-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="5d187-111">階段 2：建立標籤</span><span class="sxs-lookup"><span data-stu-id="5d187-111">Phase 2: Create labels</span></span>

<span data-ttu-id="5d187-112">在這個階段中，您會為 SharePoint Online 小組網站的文件資料夾，建立不同安全性層級的標籤。</span><span class="sxs-lookup"><span data-stu-id="5d187-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="5d187-p102">如果需要，請使用試用訂閱的全域系統管理員帳戶認證來登入 Microsoft 365 系統管理中心 (<https://admin.microsoft.com>)。如需說明，請參閱[在何處登入 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="5d187-p102">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription. For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="5d187-115">從您開始所在的 [首頁 **]**，按一下 [顯示全部 **]**。</span><span class="sxs-lookup"><span data-stu-id="5d187-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="5d187-116">在顯示的 [系統管理中心 **]** 區段中，按一下 [合規性 **]**。</span><span class="sxs-lookup"><span data-stu-id="5d187-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="5d187-117">從 Microsoft 365 合規性中心的 [首頁 **]**，前往 [解決方案 **]** 區段 \> [資訊保護 **]**。</span><span class="sxs-lookup"><span data-stu-id="5d187-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="5d187-118">若要直接前往 [資訊保護 **]** 頁面，請使用 <https://compliance.microsoft.com//informationprotection>。</span><span class="sxs-lookup"><span data-stu-id="5d187-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="5d187-119">在 [資訊保護 **]** 頁面上，確認已選取 [標籤 **]** 標記，然後按一下 [建立標籤圖示![]](../../media/m365-cc-sc-create-icon.png) **建立標籤**。</span><span class="sxs-lookup"><span data-stu-id="5d187-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="5d187-120">[新增敏感度標籤 **]** 精靈隨即會開啟。</span><span class="sxs-lookup"><span data-stu-id="5d187-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="5d187-121">在 [名稱與描述 **]** 步驟上，輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="5d187-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="5d187-122">**名稱**：輸入 **內部**。</span><span class="sxs-lookup"><span data-stu-id="5d187-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="5d187-123">**顯示名稱**</span><span class="sxs-lookup"><span data-stu-id="5d187-123">**Display name**</span></span>
   - <span data-ttu-id="5d187-124">**給使用者的描述**</span><span class="sxs-lookup"><span data-stu-id="5d187-124">**Description for users**</span></span>

   <span data-ttu-id="5d187-125">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="5d187-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="5d187-126">在 [標籤設定] 窗格中，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="5d187-127">在 [檢閱您的設定] 窗格中，按一下 [建立此標籤]，然後按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="5d187-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="5d187-128">重複步驟 5-8，逐一設定下列其他標籤：</span><span class="sxs-lookup"><span data-stu-id="5d187-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="5d187-129">私人</span><span class="sxs-lookup"><span data-stu-id="5d187-129">Private</span></span>
   - <span data-ttu-id="5d187-130">敏感性</span><span class="sxs-lookup"><span data-stu-id="5d187-130">Sensitive</span></span>
   - <span data-ttu-id="5d187-131">高度機密</span><span class="sxs-lookup"><span data-stu-id="5d187-131">Highly Confidential</span></span>

9. <span data-ttu-id="5d187-132">從 [首頁] > [標籤] 窗格中，按一下 [Publish labels]\(發佈標籤)。</span><span class="sxs-lookup"><span data-stu-id="5d187-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="5d187-133">在 [選擇要發佈的標籤] 窗格中，按一下 [選擇要發佈的標籤]。</span><span class="sxs-lookup"><span data-stu-id="5d187-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="5d187-134">在 [Choose labels]\(選擇標籤) 窗格中，按一下 [新增] 並選取所有四個標籤。</span><span class="sxs-lookup"><span data-stu-id="5d187-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="5d187-135">按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="5d187-135">Click **Done**.</span></span>

13. <span data-ttu-id="5d187-136">在 [選擇要發佈的標籤] 窗格上，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="5d187-137">在 [選擇位置] 窗格中，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="5d187-138">在 [命名您的原則] 窗格上，於 [名稱] 中鍵入 **Campaign**，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="5d187-139">在 [檢閱您的設定] 窗格中，按一下 [發佈標籤]，然後按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="5d187-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="5d187-140">階段 3：建立 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5d187-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="5d187-141">在這個階段，您可以為政治活動建立及設定 SharePoint Online 小組網站，其對應到四種類型的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="5d187-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="5d187-142">整個活動的小組網站</span><span class="sxs-lookup"><span data-stu-id="5d187-142">Campaign wide team site</span></span>

<span data-ttu-id="5d187-143">若要建立公用的基準 SharePoint Online 小組網站，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="5d187-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="5d187-144">如果需要，請使用本機電腦上的瀏覽器，並使用全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="5d187-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="5d187-145">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="5d187-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="5d187-146">在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="5d187-147">在 [建立網站] 頁面上，按一下 [小組網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="5d187-148">在 [網站名稱] 中，鍵入 **「整個活動」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="5d187-149">在 [小組網站描述] 中，鍵入 **「整個活動的 SharePoint 網站」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="5d187-150">在 [隱私權設定] 中，選取 [公用 - 組織中的任何人都可以存取此網站]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="5d187-151">在 [您想要新增誰?] 窗格上，按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="5d187-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="5d187-152">接下來，針對 [Internal]\(內部) 標籤設定整個活動小組網站的文件資料夾。</span><span class="sxs-lookup"><span data-stu-id="5d187-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="5d187-153">在瀏覽器的 [Campaign wide-Home]\(整個活動 - 首頁) 索引標籤中，按一下 [文件]。</span><span class="sxs-lookup"><span data-stu-id="5d187-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="5d187-154">按一下設定圖示，然後按一下 [文件庫設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="5d187-155">在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。</span><span class="sxs-lookup"><span data-stu-id="5d187-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="5d187-156">在 [設定 - 套用標籤] 中，選取 [Internal (內部)]，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5d187-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="5d187-157">活動專案 1 小組網站</span><span class="sxs-lookup"><span data-stu-id="5d187-157">Campaign project 1 team site</span></span>

<span data-ttu-id="5d187-158">若要為活動內部的專案建立私用的基準 SharePoint Online 小組網站，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="5d187-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="5d187-159">如果需要，請使用本機電腦上的瀏覽器，並使用全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="5d187-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="5d187-160">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="5d187-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="5d187-161">在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="5d187-162">在 [建立網站] 頁面上，按一下 [小組網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="5d187-163">在 [網站名稱] 中，鍵入 **「活動專案 1」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="5d187-164">在 [小組網站描述] 中，鍵入 **「活動專案 1 的 SharePoint 網站」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="5d187-165">在 [隱私權設定] 中，選取 [私人 - 只有成員可以存取此網站]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="5d187-166">在 [您想要新增誰?] 窗格上，按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="5d187-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="5d187-167">接下來，為「活動專案 1」小組網站的文件資料夾設定「私用」標籤。</span><span class="sxs-lookup"><span data-stu-id="5d187-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="5d187-168">在瀏覽器的 [Campaign project 1-Home (活動專案 1 - 首頁)] 索引標籤中，按一下 [文件]。</span><span class="sxs-lookup"><span data-stu-id="5d187-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="5d187-169">按一下設定圖示，然後按一下 [文件庫設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="5d187-170">在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。</span><span class="sxs-lookup"><span data-stu-id="5d187-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="5d187-171">在 [設定 - 套用標籤] 中，選取 [私用]，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5d187-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="5d187-172">活動行銷小組網站</span><span class="sxs-lookup"><span data-stu-id="5d187-172">Campaign marketing team site</span></span>

<span data-ttu-id="5d187-173">若要為活動行銷資源建立敏感性層級的隔離 SharePoint Online 小組網站，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="5d187-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="5d187-174">使用本機電腦上的瀏覽器，並以全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="5d187-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="5d187-175">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="5d187-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="5d187-176">在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="5d187-177">在 [建立網站] 頁面上，按一下 [小組網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="5d187-178">在 [小組網站名稱] 中，鍵入 **「活動行銷」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="5d187-179">在 [小組網站描述] 中，鍵入 **「活動行銷 (敏感) 的 SharePoint 網站」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="5d187-180">在 [隱私權設定] 中，選取 [私人 - 只有成員可以存取此網站]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="5d187-181">在 [您想要新增誰?] 窗格上，按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="5d187-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="5d187-182">在瀏覽器中新的 [活動行銷] 索引標籤上，在工具列中按一下設定圖示，然後按一下 [網站權限]。</span><span class="sxs-lookup"><span data-stu-id="5d187-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="5d187-183">在 [網站權限] 窗格中，按一下 [進階權限設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="5d187-184">在瀏覽器的新 [權限] 索引標籤中，按一下 [存取要求設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="5d187-185">在 **[存取要求設定]** 對話方塊中，清除 **[允許成員共用網站以及個別檔案和資料夾]** 和 **[允許成員邀請其他人加入網站成員群組]** 核取方塊，在 **[傳送存取的所有要求]** 中鍵入 **ITAdmin1@**\<your organization name\>**.onmicrosoft.com**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5d187-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="5d187-186">按一下清單中的 [活動行銷成員]。</span><span class="sxs-lookup"><span data-stu-id="5d187-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="5d187-187">在 [人員與群組] 頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="5d187-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="5d187-188">在 [共用] 對話方塊中，輸入 **Senior and strategic staff**，選取它，然後按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="5d187-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="5d187-189">為 **分析人員** 群組和 **Regular1** 使用者帳戶重複步驟 14 與 15。</span><span class="sxs-lookup"><span data-stu-id="5d187-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="5d187-190">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d187-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="5d187-191">按一下清單中的 [活動行銷擁有者]。</span><span class="sxs-lookup"><span data-stu-id="5d187-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="5d187-192">在 [人員與群組] 頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="5d187-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="5d187-193">在 [共用] 對話方塊中，鍵入 **IT 人員**，並加以選取，然後按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="5d187-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="5d187-194">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d187-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="5d187-195">關閉瀏覽器中的 [人員與群組] 索引標籤，按一下瀏覽器中的 [活動行銷 - 首頁] 索引標籤，然後關閉 [網站權限] 窗格。</span><span class="sxs-lookup"><span data-stu-id="5d187-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="5d187-196">以下是設定權限的結果：</span><span class="sxs-lookup"><span data-stu-id="5d187-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="5d187-197">**「活動行銷 - 成員」** 的 SharePoint 群組僅包含 **資深和策略人員** 群組 (其中包含 Candidate、ChiefOfStaff 和 Strategic1 使用者帳戶)、**活動行銷** 群組 (其中包含全域系統管理員使用者帳戶)、**分析人員** 群組 (其中包含 DataScientist1 使用者帳戶)，以及 **Regular1** 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="5d187-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="5d187-198">**「活動行銷 - 擁有者」** 的 SharePoint 群組僅包含 **IT 人員** 群組 (其中僅包含 ITAdmin1 和 ITAdmin2 使用者帳戶)。</span><span class="sxs-lookup"><span data-stu-id="5d187-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="5d187-199">**「活動行銷 - 訪客」** 的 SharePoint 群組未包含任何群組或使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="5d187-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="5d187-200">成員無法修改網站層級的權限 (這只能由 **「活動行銷 - 擁有者」** 群組成員來執行)。</span><span class="sxs-lookup"><span data-stu-id="5d187-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="5d187-201">其他使用者帳戶無法存取網站或其資源，但可以將電子郵件傳送至 ITAdmin1 使用者帳戶信箱，以要求存取網站。</span><span class="sxs-lookup"><span data-stu-id="5d187-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="5d187-202">接下來，為「活動行銷」小組網站的文件資料夾設定「敏感性」標籤。</span><span class="sxs-lookup"><span data-stu-id="5d187-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="5d187-203">在瀏覽器的 [活動行銷 - 首頁] 索引標籤中，按一下 [文件]。</span><span class="sxs-lookup"><span data-stu-id="5d187-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="5d187-204">按一下設定圖示，然後按一下 [文件庫設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="5d187-205">在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。</span><span class="sxs-lookup"><span data-stu-id="5d187-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="5d187-206">在 [設定 - 套用標籤] 中，選取 [敏感性]，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5d187-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="5d187-p106">接下來，設定一個資料外洩防護 (DLP) 原則，該原則會在使用者與組織外部共用具敏感性標籤的 SharePoint Online 小組網站上的文件時，即會通知使用者。此 DLP 原則會套用到活動行銷網站中的資源。</span><span class="sxs-lookup"><span data-stu-id="5d187-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="5d187-209">從瀏覽器的 [Microsoft Office 首頁] 索引標籤，按一下 [安全性與合規性] 磚。</span><span class="sxs-lookup"><span data-stu-id="5d187-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="5d187-210">在瀏覽器的新 [安全性與合規性] 索引標籤上，按一下 [資料外洩防護] > [原則]。</span><span class="sxs-lookup"><span data-stu-id="5d187-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="5d187-211">在 [資料外洩防護] 窗格中，按一下 [+ 建立原則]。</span><span class="sxs-lookup"><span data-stu-id="5d187-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="5d187-212">在 [從範本開始或建立自訂原則] 窗格中，按一下 [自訂]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="5d187-213">在 [命名您的原則] 窗格的 [名稱] 中，鍵入 **Sensitive label SharePoint Online team sites**，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="5d187-214">在 [選擇位置] 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="5d187-215">在位置清單中，停用 [Exchange 電子郵件] 和 [OneDrive 帳戶] 位置，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="5d187-216">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="5d187-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="5d187-217">在 [選擇要保護的內容類型] 窗格中，從下拉式方塊按一下 [新增]，然後按一下 [標籤]。</span><span class="sxs-lookup"><span data-stu-id="5d187-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="5d187-218">在 [標籤] 窗格中，按一下 [+ 新增] 並選取 [敏感性] 標籤，然後依序按一下 [新增] 和 [完成]。</span><span class="sxs-lookup"><span data-stu-id="5d187-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="5d187-219">在 [Choose the types of content to protect]\(選擇要保護的內容類型) 窗格中，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5d187-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="5d187-220">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="5d187-221">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?) 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)。</span><span class="sxs-lookup"><span data-stu-id="5d187-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="5d187-222">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知) 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)。</span><span class="sxs-lookup"><span data-stu-id="5d187-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="5d187-223">在文字方塊中，鍵入或貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="5d187-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="5d187-p107">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="5d187-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="5d187-227">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-227">Click **OK**.</span></span>

17. <span data-ttu-id="5d187-228">在 [如果偵測到機密資訊要如何處理?] 窗格中，清除 [禁止人員共用及限制共用內容的存取] 核取方塊，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="5d187-229">在 [要先開啟原則或測試內容嗎?] 窗格中，按一下 [是] 立即將它開啟，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="5d187-230">在 [檢閱您的設定] 窗格中，按一下 [建立]，然後按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="5d187-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="5d187-231">活動策略小組網站</span><span class="sxs-lookup"><span data-stu-id="5d187-231">Campaign strategy team site</span></span>

<span data-ttu-id="5d187-232">若要為活動策略資源建立高度機密層級的隔離 SharePoint Online 小組網站，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="5d187-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="5d187-233">如果需要，請使用本機電腦上的瀏覽器，並使用全域管理員帳戶登入系統管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="5d187-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="5d187-234">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="5d187-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="5d187-235">在瀏覽器的新 [SharePoint] 索引標籤上，按一下 [+ 建立網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="5d187-236">在 [建立網站] 頁面上，按一下 [小組網站]。</span><span class="sxs-lookup"><span data-stu-id="5d187-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="5d187-237">在 [小組網站名稱] 中，鍵入 **「活動策略」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="5d187-238">在 [小組網站描述] 中，鍵入 **「活動策略的 SharePoint 網站 (高度機密)」**。</span><span class="sxs-lookup"><span data-stu-id="5d187-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="5d187-239">在 [隱私權設定] 中，選取 [私人 - 只有成員可以存取此網站]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="5d187-240">在 [您想要新增誰?] 窗格上，按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="5d187-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="5d187-241">在瀏覽器中新的 [活動策略] 索引標籤上，在工具列中按一下設定圖示，然後按一下 [網站權限]。</span><span class="sxs-lookup"><span data-stu-id="5d187-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="5d187-242">在 [網站權限] 窗格中，按一下 [進階權限設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="5d187-243">在瀏覽器的新 [權限] 索引標籤中，按一下 [存取要求設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="5d187-244">在 [存取要求設定] 對話方塊中，清除 [允許成員共用網站以及個別檔案和資料夾] 和 [允許成員邀請其他人加入網站成員群組]\(亦即清除所有三個核取方塊)，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="5d187-245">按一下清單中的 [活動策略成員]。</span><span class="sxs-lookup"><span data-stu-id="5d187-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="5d187-246">在 [人員與群組] 頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="5d187-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="5d187-247">在 [共用] 對話方塊中，輸入 **Senior and strategic staff**，選取它，然後按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="5d187-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="5d187-248">按一下清單中的 [活動策略擁有者]。</span><span class="sxs-lookup"><span data-stu-id="5d187-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="5d187-249">在 [人員與群組] 頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="5d187-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="5d187-250">在 [共用] 對話方塊中，鍵入 **IT 人員**，並加以選取，然後按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="5d187-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="5d187-251">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d187-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="5d187-252">關閉瀏覽器中的 [人員與群組] 索引標籤，按一下瀏覽器中的 [活動策略 - 首頁] 索引標籤，然後關閉 [網站權限] 窗格。</span><span class="sxs-lookup"><span data-stu-id="5d187-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="5d187-253">以下是設定權限的結果：</span><span class="sxs-lookup"><span data-stu-id="5d187-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="5d187-254">**「活動策略 - 成員」** 的 SharePoint 群組僅包含 **資深和策略人員** 群組 (其中僅包含 Candidate、ChiefOfStaff 和 Strategic1 使用者帳戶) 和 **活動策略** 群組 (其中僅包含全域系統管理員使用者帳戶)。</span><span class="sxs-lookup"><span data-stu-id="5d187-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="5d187-255">**「活動策略 - 擁有者」** 的 SharePoint 群組僅包含 **IT 人員** 群組 (其中僅包含 ITAdmin1 和 ITAdmin2 使用者帳戶)。</span><span class="sxs-lookup"><span data-stu-id="5d187-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="5d187-256">**「活動策略 - 訪客」** 的 SharePoint 群組未包含任何群組或使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="5d187-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="5d187-257">成員無法修改網站層級的權限 (這只能由 **「活動策略 - 擁有者」** 群組成員來執行)。</span><span class="sxs-lookup"><span data-stu-id="5d187-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="5d187-p108">其他使用者帳戶無法存取網站或其資源，或要求存取網站。網站的額外權限必須由全域管理員或 **「活動策略 - 擁有者」** 群組成員來執行。</span><span class="sxs-lookup"><span data-stu-id="5d187-p108">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="5d187-260">接下來，為「活動策略」小組網站的文件資料夾設定「高度機密」標籤。</span><span class="sxs-lookup"><span data-stu-id="5d187-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="5d187-261">在瀏覽器的 [活動策略 - 首頁] 索引標籤中，按一下 [文件]。</span><span class="sxs-lookup"><span data-stu-id="5d187-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="5d187-262">按一下設定圖示，然後按一下 [文件庫設定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="5d187-263">在 [權限與管理] 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)。</span><span class="sxs-lookup"><span data-stu-id="5d187-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="5d187-264">在 [設定 - 套用標籤] 中，選取 [高度機密]，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5d187-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="5d187-p109">接下來，設定 DLP 原則；當使用者在組織外部共用具「高度機密」標籤之 SharePoint Online 小組網站上的文件時，即會封鎖使用者。此 DLP 原則會套用到活動策略網站中的資源。</span><span class="sxs-lookup"><span data-stu-id="5d187-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="5d187-267">如果需要，請使用本機電腦上的瀏覽器，並使用具有安全性系統管理員或公司系統管理員角色的帳戶登入系統管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="5d187-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="5d187-268">從瀏覽器的 [Microsoft Office 首頁] 索引標籤，按一下 [安全性與合規性] 磚。</span><span class="sxs-lookup"><span data-stu-id="5d187-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="5d187-269">在瀏覽器的新 [安全性與合規性] 索引標籤上，按一下 [資料外洩防護] > [原則]。</span><span class="sxs-lookup"><span data-stu-id="5d187-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="5d187-270">在 [資料外洩防護] 窗格中，按一下 [+ 建立原則]。</span><span class="sxs-lookup"><span data-stu-id="5d187-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="5d187-271">在 [從範本開始或建立自訂原則] 窗格中，按一下 [自訂]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="5d187-272">在 [命名您的原則] 窗格的 [名稱] 中，鍵入 **Highly Confidential label SharePoint Online team sites**，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="5d187-273">在 [選擇位置] 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="5d187-274">在位置清單中，停用 [Exchange 電子郵件] 和 [OneDrive 帳戶] 位置，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="5d187-275">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="5d187-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="5d187-276">在 [選擇要保護的內容類型] 窗格中，從下拉式方塊按一下 [新增]，然後按一下 [標籤]。</span><span class="sxs-lookup"><span data-stu-id="5d187-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="5d187-277">在 [標籤] 窗格中，按一下 [+ 新增]，並選取 [高度機密] 標籤，然後依序按一下 [新增] 和 [完成]。</span><span class="sxs-lookup"><span data-stu-id="5d187-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="5d187-278">在 [Choose the types of content to protect]\(選擇要保護的內容類型) 窗格中，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5d187-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="5d187-279">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型) 窗格中，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="5d187-280">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?) 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)。</span><span class="sxs-lookup"><span data-stu-id="5d187-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="5d187-281">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知) 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)。</span><span class="sxs-lookup"><span data-stu-id="5d187-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="5d187-282">在文字方塊中，鍵入或貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="5d187-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="5d187-p110">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="5d187-p110">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="5d187-286">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-286">Click **OK**.</span></span>

18. <span data-ttu-id="5d187-287">在 [如果偵測到機密資訊要如何處理?] 窗格中，選取 [需要有業務上的正當理由才能覆寫]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="5d187-288">在 [要先開啟原則或測試內容嗎?] 窗格中，按一下 [是] 立即將它開啟，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5d187-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="5d187-289">在 [檢閱您的設定] 窗格中，按一下 [建立]，然後按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="5d187-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="5d187-290">遵循[使用 Office 365 系統管理中心啟用 Azure RMS](/information-protection/deploy-use/activate-office365) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="5d187-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="5d187-291">接著，遵循下列步驟，為 Azure 資訊保護設定新的限域原則與子標籤，以提供保護及權限：</span><span class="sxs-lookup"><span data-stu-id="5d187-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="5d187-p111">使用具有安全性系統管理員或公司系統管理員角色的帳戶登入系統管理中心。如需說明，請參閱[在何處登入 Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="5d187-p111">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="5d187-294">在您瀏覽器的個別索引標籤中，移至 Azure 入口網站 (<https://portal.azure.com>)。</span><span class="sxs-lookup"><span data-stu-id="5d187-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="5d187-295">在搜尋窗格中，輸入 **[資訊]**，然後按一下 **Azure 資訊保護**。</span><span class="sxs-lookup"><span data-stu-id="5d187-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="5d187-296">按一下 [標籤]。</span><span class="sxs-lookup"><span data-stu-id="5d187-296">Click **Labels**.</span></span>

5. <span data-ttu-id="5d187-297">以滑鼠右鍵按一下 [高度機密] 標籤，然後再按一下 [新增子標籤]。</span><span class="sxs-lookup"><span data-stu-id="5d187-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="5d187-298">在 [名稱] 中鍵入 **CampaignStrategy**，並在 [描述] 中鍵入 **活動策略小組網站中的文件標籤**。</span><span class="sxs-lookup"><span data-stu-id="5d187-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="5d187-299">在 [為包含此標籤的文件與電子郵件設定權限] 中，按一下 [保護]。</span><span class="sxs-lookup"><span data-stu-id="5d187-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="5d187-300">在 [保護] 區段中，按一下 [Azure (雲端金鑰)]。</span><span class="sxs-lookup"><span data-stu-id="5d187-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="5d187-301">在 [保護] 刀鋒視窗中，按一下 [保護設定] 下的 [+ 新增權限]。</span><span class="sxs-lookup"><span data-stu-id="5d187-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="5d187-302">在 [新增權限] 刀鋒視窗中，按一下 [指定使用者與群組] 下的 [+ 瀏覽目錄]。</span><span class="sxs-lookup"><span data-stu-id="5d187-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="5d187-303">在 [AAD 使用者和群組] 窗格中，選取 [資深和策略人員]，然後按一下 [選取]。</span><span class="sxs-lookup"><span data-stu-id="5d187-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="5d187-304">在 [選擇預設的權限，或設定自訂] 下，按一下 [自訂]，然後選取 [檢視權限]、[編輯內容]、[儲存]、[回覆]、[全部回覆] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5d187-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="5d187-305">按兩次 [確定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="5d187-306">在 [子標籤] 刀鋒視窗中，按一下 [儲存]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="5d187-307">在 [Azure 資訊保護] 刀鋒視窗中，按一下 [原則] > [+ 新增原則]。</span><span class="sxs-lookup"><span data-stu-id="5d187-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="5d187-308">在 [名稱] 中鍵入 **CampaignStrategy**，並在 [描述] 中鍵入 **活動策略小組網站中的文件**。</span><span class="sxs-lookup"><span data-stu-id="5d187-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="5d187-309">按一下 [選取取得此原則的使用者或群組] > [使用者/群組]，然後選取 [資深和策略人員]。</span><span class="sxs-lookup"><span data-stu-id="5d187-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="5d187-310">按一下 **[選取]\> [確定]**。</span><span class="sxs-lookup"><span data-stu-id="5d187-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="5d187-p112">按一下 [新增或移除標籤]。在 [原則: 新增或移除標籤] 窗格中，按一下 [CampaignStrategy]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-p112">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="5d187-313">按一下 [儲存]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="5d187-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="5d187-314">您現在準備好開始建立這四個網站中的文件，以及使用不同的使用者帳戶來測試其存取。</span><span class="sxs-lookup"><span data-stu-id="5d187-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="5d187-315">若要使用 Azure 資訊保護和此新標籤來保護文件，您必須在測試電腦上 [安裝 Azure 資訊保護用戶端](/information-protection/rms-client/install-client-app)，並從系統管理中心安裝 Office，然後使用試用訂用帳戶 **「資深和策略人員」** 群組中的帳戶登入 Microsoft Word。</span><span class="sxs-lookup"><span data-stu-id="5d187-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d187-316">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5d187-316">See Also</span></span>

[<span data-ttu-id="5d187-317">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="5d187-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="5d187-318">設定政治活動開發/測試環境的群組和使用者</span><span class="sxs-lookup"><span data-stu-id="5d187-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="5d187-319">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="5d187-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="5d187-320">Microsoft 365 解決方案與架構中心</span><span class="sxs-lookup"><span data-stu-id="5d187-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)
