---
title: 使用入口網站啟動計畫程式啟動入口網站
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 本文說明如何使用入口網站啟動排程器來啟動入口網站
ms.openlocfilehash: e77668b3c21b43de1a2e30dc7181842770a24784
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769200"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="0fbf5-103">使用 SharePoint 入口網站啟動計畫程式啟動入口網站</span><span class="sxs-lookup"><span data-stu-id="0fbf5-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="0fbf5-104">入口網站是內部網路上的 SharePoint 通訊網站，它是高流量–一部星期內從10000到100000查看者的網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="0fbf5-105">使用入口網站啟動排程器啟動您的入口網站，以確保使用者在存取新的 SharePoint 入口網站時有光滑的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="0fbf5-106">入口網站啟動排程器的設計目的是為了協助您遵循分階段的處理常式，並以波形方式批次處理檢視器並管理新入口網站的 URL 重新導向。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="0fbf5-107">在啟動每個 wave 時，您可以收集使用者意見反應、監控入口效能，並暫停啟動以解決問題，再繼續進行下一個波形。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="0fbf5-108">深入瞭解如何[在 SharePoint 中規劃入口網站啟動](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="0fbf5-109">**有兩種類型的重定向：**</span><span class="sxs-lookup"><span data-stu-id="0fbf5-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="0fbf5-110">**雙向**：啟動新的現代 SharePoint 入口網站以取代現有的 SharePoint 傳統或新式入口網站</span><span class="sxs-lookup"><span data-stu-id="0fbf5-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="0fbf5-111">重新 **導向至暫存頁面**：啟動新的現代 SharePoint 入口網站（沒有現有的 SharePoint 入口網站）</span><span class="sxs-lookup"><span data-stu-id="0fbf5-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="0fbf5-112">在發射過程中，網站許可權必須與波形分開設定。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="0fbf5-113">例如，如果您要發行整個組織的入口網站，您可以將許可權設定為「外部使用者以外的所有人」，然後使用安全性群組將您的使用者分隔成波形。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="0fbf5-114">將安全性群組新增至 wave 不會讓該安全性群組存取網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="0fbf5-115">從 2021 2021 年5月開始的目標版本客戶的「**設定** SharePoint 面板」首頁，可以存取這項功能，並將在年7月後取得給所有客戶使用。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="0fbf5-116">目前可以使用此工具的 PowerShell 版本</span><span class="sxs-lookup"><span data-stu-id="0fbf5-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="0fbf5-117">這項功能只可用於現代的 SharePoint 通訊網站上</span><span class="sxs-lookup"><span data-stu-id="0fbf5-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="0fbf5-118">您必須具有網站的網站擁有者許可權，才可自訂及排程入口網站的啟動</span><span class="sxs-lookup"><span data-stu-id="0fbf5-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="0fbf5-119">啟動之前必須至少排程7天，且每個波形可以持續1到7天</span><span class="sxs-lookup"><span data-stu-id="0fbf5-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="0fbf5-120">所需的波形數目會根據預期的使用者數目自動決定</span><span class="sxs-lookup"><span data-stu-id="0fbf5-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="0fbf5-121">在排程入口網站啟動之前，必須執行[SharePoint 工具的頁面診斷](https://aka.ms/perftool)，以確認網站的首頁健康情況良好</span><span class="sxs-lookup"><span data-stu-id="0fbf5-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="0fbf5-122">在啟動結束時，具有網站許可權的所有使用者都可以存取新網站</span><span class="sxs-lookup"><span data-stu-id="0fbf5-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="0fbf5-123">如果您的組織使用的是[Viva](https://docs.microsoft.com/SharePoint/viva-connections)連線，使用者可能會在 Microsoft Teams 應用程式欄中看到您組織的圖示，但是當圖示已選取時，使用者將無法存取入口網站，直到其 wave 啟動為止</span><span class="sxs-lookup"><span data-stu-id="0fbf5-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="0fbf5-124">這項功能不適用於 Office 365 德國、由世紀 (中國) Office 365 運作，或 Microsoft 365 美國政府方案。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="0fbf5-125">瞭解入口網站啟動排程器選項之間的差異：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="0fbf5-126">原來的入口網站啟動只能透過 SharePoint PowerShell 排程。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="0fbf5-127">現在，您有兩個選項可協助您排程和管理入口網站的啟動。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="0fbf5-128">深入瞭解這兩種工具之間的主要差異：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="0fbf5-129">**SharePointPowerShell 版本：**</span><span class="sxs-lookup"><span data-stu-id="0fbf5-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="0fbf5-130">需要有系統管理員認證，才能使用[SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="0fbf5-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="0fbf5-131">一個波形的最低需求</span><span class="sxs-lookup"><span data-stu-id="0fbf5-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="0fbf5-132">根據協調世界時 (UTC) 時區排程您的啟動</span><span class="sxs-lookup"><span data-stu-id="0fbf5-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="0fbf5-133">**產品內版本：**</span><span class="sxs-lookup"><span data-stu-id="0fbf5-133">**In-product version:**</span></span>

- <span data-ttu-id="0fbf5-134">需要網站擁有者認證</span><span class="sxs-lookup"><span data-stu-id="0fbf5-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="0fbf5-135">雙波浪的基本需求</span><span class="sxs-lookup"><span data-stu-id="0fbf5-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="0fbf5-136">根據 [區域設定] 中所示的入口網站時區，排程您的啟動</span><span class="sxs-lookup"><span data-stu-id="0fbf5-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="0fbf5-137">開始使用入口網站啟動調度程式</span><span class="sxs-lookup"><span data-stu-id="0fbf5-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="0fbf5-138">在使用入口網站啟動排程器工具之前，請先新增需要透過 **網站** 擁有者、網站成員或訪客 [存取此網站的所有使用者](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="0fbf5-139">接著，以下列其中一種方式存取入口網站啟動排程器，以開始排程入口網站的啟動：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="0fbf5-140">**選項 1**：在首頁版本3.0 之前，您可以編輯或重新發佈首頁或更新至首頁，直到首頁版本-您將會收到使用入口網站啟動排程器工具的提示。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="0fbf5-141">選取 [排程 **啟動** ]，以排程。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="0fbf5-142">或選取 [重新 **發佈** ] 以重新發佈您的頁面編輯，而不排程啟動。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![重新發佈首頁時，提示使用入口網站啟動排程器的影像](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="0fbf5-144">**選項 2**：您可以在任何時候流覽至 SharePoint 的通訊網站首頁，選取 [**設定**]，然後 **排程網站啟動** 以排程入口網站的啟動。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![[設定] 窗格的圖像，其排程網站啟動已反白顯示](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="0fbf5-146">接下來，請先確認入口網站的健康情況分數，並在需要時使用 [SharePoint 工具的頁面診斷](https://aka.ms/perftool)，對入口網站進行改進，直到您的入口網站收到 **良好** 的分數為止。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="0fbf5-147">然後，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-147">Then, select **Next**.</span></span>

    ![入口網站啟動調度程式工具的影像](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="0fbf5-149">無法從入口網站啟動排程器編輯網站名稱和描述，但可以從首頁上選取 [**設定**]，然後選取 [**網站資訊**] 以加以變更。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="0fbf5-150">從下拉式清單中選取 **期望的使用者數目** 。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="0fbf5-151">此圖代表最可能需要網站存取權的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="0fbf5-152">入口網站啟動排程器會根據預期的使用者，自動判斷波形數目的理想專案如下：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="0fbf5-153">小於10k 使用者：兩個波浪</span><span class="sxs-lookup"><span data-stu-id="0fbf5-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="0fbf5-154">10k 至30k 使用者：三聲波</span><span class="sxs-lookup"><span data-stu-id="0fbf5-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="0fbf5-155">30k + 至100k 使用者：五台聲波</span><span class="sxs-lookup"><span data-stu-id="0fbf5-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="0fbf5-156">超過100k 的使用者：5個無線電波，您透過使用啟動入口網站中所列的步驟，與您的 Microsoft 聯繫一節。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span> 

5.  <span data-ttu-id="0fbf5-157">然後，判斷所需的重新 **導向類型** ：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="0fbf5-158">**選項1：將使用者傳送至現有的 SharePoint 頁面 (雙向)** –使用此選項啟動新的現代 SharePoint 入口網站以取代現有的 SharePoint 入口網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="0fbf5-159">主動波形中的使用者將會重新導向至新網站，不論其流覽的是舊的還是新的網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="0fbf5-160">嘗試存取新網站的非啟動浪潮中的使用者，將會重新導向至舊網站，直到其 wave 啟動為止。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="0fbf5-161">使用雙向選項時，排程啟動的人員也必須具有其他 SharePoint 入口網站的網站擁有者許可權。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="0fbf5-162">**選項2：將使用者傳送至自動產生的暫存頁面 (暫時頁面** 重新導向) –若不存在現有的 SharePoint 入口網站，應使用暫存頁面重新導向。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="0fbf5-163">使用者會被導向至新的現代 SharePoint 入口網站，而且如果使用者處於尚未啟動的 wave，將會重新導向至暫存頁面。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="0fbf5-164">**選項3：將使用者傳送至外部頁面** –在使用者的 wave 啟動之前，提供暫時登陸頁面體驗的外部 URL。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="0fbf5-165">將您的物件分解成波形。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-165">Break up your audience into waves.</span></span> <span data-ttu-id="0fbf5-166">每個浪潮新增最多20個安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="0fbf5-167">在每次聲波啟動之前，可以編輯波形詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="0fbf5-168">每個浪潮至少可以一天 (24 小時) 至少7天。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="0fbf5-169">這可讓 SharePoint 和您的技術環境有機會 acclimate 及擴充至大量的網站使用者。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="0fbf5-170">當您透過 UI 排程啟動時，時區是以網站的區域設定為基礎。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="0fbf5-171">入口網站啟動排程器的預設值會自動設為至少2個波形。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="0fbf5-172">不過，此工具的 PowerShell 版本將允許1個波形。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="0fbf5-173">此版本的入口網站啟動計畫程式不支援 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="0fbf5-174">決定誰需要立即查看網站，並將其資訊輸入 [豁免的 **使用者** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="0fbf5-175">這些使用者會從波形中排除，不會在發射之前、期間或之後重新導向。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    >[!NOTE]
    > <span data-ttu-id="0fbf5-176">最多可新增50個不同的使用者或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-176">Up to 50 distinct users or security groups max can be added.</span></span> <span data-ttu-id="0fbf5-177">在聲波開始啟動之前，您需要超過50個人才能存取入口網站，請使用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-177">Use security groups when you need more than 50 individuals to get access to the portal before the waves start launching.</span></span> 

8.  <span data-ttu-id="0fbf5-178">確認入口網站啟動詳細資料並選取 **排程**。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-178">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="0fbf5-179">開始排程後，對 SharePoint 入口網站首頁所做的任何變更，都必須先接收正常的診斷結果，再繼續進行入口網站啟動。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-179">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="0fbf5-180">啟動超過100k 使用者的入口網站</span><span class="sxs-lookup"><span data-stu-id="0fbf5-180">Launch a portal with over 100k users</span></span>

<span data-ttu-id="0fbf5-181">如果您打算使用超過100000的使用者啟動入口網站，請遵循下列所列的步驟提交支援要求。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-181">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="0fbf5-182">請務必包含所有要求的資訊。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-182">Make sure to include all the requested information.</span></span>

<span data-ttu-id="0fbf5-183">**遵循下列步驟：**</span><span class="sxs-lookup"><span data-stu-id="0fbf5-183">**Follow these steps:**</span></span>
1. <span data-ttu-id="0fbf5-184">請移至 https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0fbf5-184">Go to https://admin.microsoft.com</span></span>
2. <span data-ttu-id="0fbf5-185">確定您使用的是新的系統管理中心預覽</span><span class="sxs-lookup"><span data-stu-id="0fbf5-185">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="0fbf5-186">在左導覽窗格中，選取 [**支援**]，然後選取 [**新增服務要求**]。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-186">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="0fbf5-187">這會在您的畫面右側啟動「需要協助嗎？」窗格。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-187">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="0fbf5-188">若要 **暫時描述您的問題**，請輸入「使用100k 使用者的啟動 SharePoint 入口網站」。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-188">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="0fbf5-189">然後，選取 [**連絡人支援**]</span><span class="sxs-lookup"><span data-stu-id="0fbf5-189">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="0fbf5-190">在 [**描述**] 底下，輸入「啟動含100k 使用者的 SharePoint 入口網站」</span><span class="sxs-lookup"><span data-stu-id="0fbf5-190">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="0fbf5-191">填寫其餘資訊，然後選取 [**與我們聯繫**]</span><span class="sxs-lookup"><span data-stu-id="0fbf5-191">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="0fbf5-192">建立票證之後，請確定提供支援代理人以下資訊：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-192">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="0fbf5-193">入口網站 URL</span><span class="sxs-lookup"><span data-stu-id="0fbf5-193">Portal URL's</span></span> 
   - <span data-ttu-id="0fbf5-194">預期的使用者數目</span><span class="sxs-lookup"><span data-stu-id="0fbf5-194">Number of users expected</span></span>
   - <span data-ttu-id="0fbf5-195">預估啟動排程</span><span class="sxs-lookup"><span data-stu-id="0fbf5-195">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="0fbf5-196">對已排程的入口網站啟動進行變更</span><span class="sxs-lookup"><span data-stu-id="0fbf5-196">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="0fbf5-197">您可以針對每個波浪形編輯啟動詳細資料，直到波形的啟動日期為止。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-197">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="0fbf5-198">若要編輯入口網站啟動詳細資料，請流覽至 **設定**，然後選取 [**排程網站啟動**]。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-198">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="0fbf5-199">然後，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-199">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="0fbf5-200">完成編輯後，請選取 [ **更新**]。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-200">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="0fbf5-201">刪除排程的入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="0fbf5-201">Delete a scheduled portal launch</span></span>

<span data-ttu-id="0fbf5-202">您可以在任何時間（即使已啟動某些聲波）使用入口網站啟動排程工具，也可以取消或刪除啟動排程。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-202">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="0fbf5-203">若要取消入口網站的啟動，請流覽至 [**設定** 及 **排程網站啟動**]。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-203">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="0fbf5-204">然後，選取 [ **刪除** ]，當您看到下列的訊息時，請選取 **[刪除]** 。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-204">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![入口網站啟動調度程式工具的影像](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="0fbf5-206">使用 PowerShell 入口網站啟動排程器</span><span class="sxs-lookup"><span data-stu-id="0fbf5-206">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="0fbf5-207">SharePoint 入口網站啟動排程器工具最初隻可透過[SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)取得，PowerShell 而且會繼續透過 PowerShell 使用此方法的客戶取得支援。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-207">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="0fbf5-208">本文開頭的相同附注適用于這兩個版本的入口網站啟動排程器。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-208">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="0fbf5-209">您必須具有系統管理員許可權，才能使用 SharePoint PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-209">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="0fbf5-210">在 PowerShell 中建立的入口網站啟動詳細資料將會出現，而且可以在 SharePoint 中的新入口網站啟動排程器工具中管理。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-210">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="0fbf5-211">應用程式安裝並聯機至 SharePoint 線上</span><span class="sxs-lookup"><span data-stu-id="0fbf5-211">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="0fbf5-212">[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-212">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0fbf5-p118">如果您安裝的是舊版 SharePoint Online 管理命令介面，請移至 [新增或移除程式]，並解除安裝 [SharePoint Online 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-p118">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="0fbf5-214">在下載中心頁面上，選擇您的語言，然後按一下 [下載] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-214">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="0fbf5-215">系統會請您選擇下載 x64 或 x86 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-215">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="0fbf5-216">如果您執行的是 64 位元版本的 Windows，請下載 x64 檔案；或如果您執行的是 32 位元版本，請下載 x86 檔案。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-216">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="0fbf5-217">如果您不知道，請參閱[我正在執行哪個版本的 Windows 作業系統？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-217">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="0fbf5-218">下載檔案之後，請執行檔案，並按照安裝精靈中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-218">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="0fbf5-219">在 Microsoft 365 以[全域系統管理員或 SharePoint 管理員](/sharepoint/sharepoint-admin-role)的身分登入。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-219">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="0fbf5-220">若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-220">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="0fbf5-221">查看任何現有的入口網站啟動設置</span><span class="sxs-lookup"><span data-stu-id="0fbf5-221">View any existing portal launch setups</span></span>

<span data-ttu-id="0fbf5-222">若要查看是否有現有的入口網站啟動設定：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-222">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="0fbf5-223">在網站上排程入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="0fbf5-223">Schedule a portal launch on the site</span></span>

<span data-ttu-id="0fbf5-224">所需的波形數目取決於您預期的啟動大小。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-224">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="0fbf5-225">小於10k 使用者：一個波形</span><span class="sxs-lookup"><span data-stu-id="0fbf5-225">Less than 10k users: One wave</span></span>
- <span data-ttu-id="0fbf5-226">10k 至30k 使用者：三聲波</span><span class="sxs-lookup"><span data-stu-id="0fbf5-226">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="0fbf5-227">30k + 至100k 使用者：五台聲波</span><span class="sxs-lookup"><span data-stu-id="0fbf5-227">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="0fbf5-228">超過100k 的使用者：五台聲波，並與您的 Microsoft 帳戶小組聯繫</span><span class="sxs-lookup"><span data-stu-id="0fbf5-228">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="0fbf5-229">雙向重新定向的步驟</span><span class="sxs-lookup"><span data-stu-id="0fbf5-229">Steps for bidirectional redirection</span></span>

<span data-ttu-id="0fbf5-230">雙向重新導向包括啟動新的現代 SharePoint Online 入口網站取代現有的 SharePoint 傳統或新式入口網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-230">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="0fbf5-231">主動波形中的使用者將會重新導向至新網站，不論其流覽的是舊的還是新的網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-231">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="0fbf5-232">嘗試存取新網站的非啟動浪潮中的使用者，將會重新導向至舊網站，直到其 wave 啟動為止。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-232">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="0fbf5-233">我們只支援舊網站上的預設首頁與新網站上的預設首頁之間的重定向。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-233">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="0fbf5-234">若要讓系統管理員或擁有者必須存取舊的和新的網站，而不重新導向，請確定它們是以 `WaveOverrideUsers` 參數列出。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-234">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="0fbf5-235">若要以分段方式將現有的 SharePoint 網站中的使用者遷移至新的 SharePoint 網站，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-235">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="0fbf5-236">執行下列命令以指定入口啟動波形。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-236">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="0fbf5-237">範例：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-237">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="0fbf5-238">完整驗證。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-238">Complete validation.</span></span> <span data-ttu-id="0fbf5-239">重新導向會花5-10 分鐘的時間來完成整個服務的設定。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-239">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="0fbf5-240">重定向至暫存頁面的步驟</span><span class="sxs-lookup"><span data-stu-id="0fbf5-240">Steps for redirection to temporary page</span></span>

<span data-ttu-id="0fbf5-241">當不存在現有的 SharePoint 入口網站時，應使用暫存頁面重新導向。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-241">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="0fbf5-242">使用者會以分段的方式，將使用者導向至新的現代 SharePoint Online 入口網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-242">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="0fbf5-243">如果使用者處於尚未啟動的 wave，將會重新導向至臨時頁面 (任何 URL) 。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-243">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="0fbf5-244">執行下列命令以指定入口啟動波形。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-244">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="0fbf5-245">範例：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-245">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="0fbf5-246">完整驗證。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-246">Complete validation.</span></span> <span data-ttu-id="0fbf5-247">重新導向會花5-10 分鐘的時間來完成整個服務的設定。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-247">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="0fbf5-248">暫停或重新開機網站上的入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="0fbf5-248">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="0fbf5-249">若要暫停進行中的入口網站啟動，並暫時避免發生即將進行的 wave progressions，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-249">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="0fbf5-250">驗證是否所有使用者都已重新導向到舊網站。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-250">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="0fbf5-251">若要重新開機已暫停的入口網站啟動，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0fbf5-251">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="0fbf5-252">驗證重新定向現在已還原。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-252">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="0fbf5-253">在網站上刪除入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="0fbf5-253">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="0fbf5-254">執行下列命令，以刪除針對網站排程或進行中的入口網站啟動。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-254">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="0fbf5-255">驗證所有使用者都不會進行重新導向。</span><span class="sxs-lookup"><span data-stu-id="0fbf5-255">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="0fbf5-256">深入了解</span><span class="sxs-lookup"><span data-stu-id="0fbf5-256">Learn more</span></span>

[<span data-ttu-id="0fbf5-257">在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫</span><span class="sxs-lookup"><span data-stu-id="0fbf5-257">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="0fbf5-258">規劃您的通訊網站</span><span class="sxs-lookup"><span data-stu-id="0fbf5-258">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
