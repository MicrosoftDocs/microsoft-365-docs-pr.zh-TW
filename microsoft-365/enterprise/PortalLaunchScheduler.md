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
ms.openlocfilehash: 7e488caba5e4df47bb3f51f195e093891565d95c
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367198"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="90cf8-103">使用入口網站啟動計畫程式啟動入口網站</span><span class="sxs-lookup"><span data-stu-id="90cf8-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="90cf8-104">入口網站是您內部網路上的 SharePoint 網站，擁有大量網站檢視者在該網站上取用內容。</span><span class="sxs-lookup"><span data-stu-id="90cf8-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="90cf8-105">以波形的式啟動入口網站是確保使用者能夠存取新 SharePoint 線上入口網站的流暢且具能力的經驗的重要部分。</span><span class="sxs-lookup"><span data-stu-id="90cf8-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="90cf8-106">以聲波發射是一種重要方式，可讓您在 [線上 SharePoint 中規劃入口網站發佈的計畫](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)，以逐步展示您的入口網站。</span><span class="sxs-lookup"><span data-stu-id="90cf8-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="90cf8-107">入口網站啟動排程程式的設計目的是為了協助您追蹤新入口網站的重新導向，以進行波形/逐步化方法。</span><span class="sxs-lookup"><span data-stu-id="90cf8-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="90cf8-108">在每個波形期間，您可以在每個部署浪潮期間收集使用者意見反應並監控效能。</span><span class="sxs-lookup"><span data-stu-id="90cf8-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="90cf8-109">這具有逐步引入入口網站的優勢，讓您可以選擇暫停及解決問題，再繼續進行下一個浪潮，最後確保使用者的取得積極的經驗。</span><span class="sxs-lookup"><span data-stu-id="90cf8-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="90cf8-110">重新導向的類型有兩種：</span><span class="sxs-lookup"><span data-stu-id="90cf8-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="90cf8-111">雙向：啟動新的現代 SharePoint 線上入口網站以取代現有的 SharePoint 傳統或新式入口網站</span><span class="sxs-lookup"><span data-stu-id="90cf8-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="90cf8-112">暫時頁面重新導向：使用沒有現有 SharePoint 入口網站的新新式 SharePoint 線上入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="90cf8-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="90cf8-113">入口網站啟動排程器僅可用於啟動新式 SharePoint Online 入口網站，亦即通訊網站和現代小組網站。</span><span class="sxs-lookup"><span data-stu-id="90cf8-113">The portal launch scheduler is only available to launch modern SharePoint Online portals, i.e. communication sites and modern team sites.</span></span> <span data-ttu-id="90cf8-114">啟動時間必須預先排程至少7天。</span><span class="sxs-lookup"><span data-stu-id="90cf8-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="90cf8-115">所需的無線電波數目取決於預期的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="90cf8-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="90cf8-116">在排程入口網站之前，必須執行 [SharePoint 工具的頁面診斷](https://aka.ms/perftool) ，以驗證入口網站上的首頁狀況良好。</span><span class="sxs-lookup"><span data-stu-id="90cf8-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="90cf8-117">在入口網站的最後一開始，所有具有網站許可權的使用者都可以存取新網站。</span><span class="sxs-lookup"><span data-stu-id="90cf8-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="90cf8-118">如需有關啟動成功入口網站的詳細資訊，請遵循 [建立、啟動及維護健康入口網站](https://docs.microsoft.com/sharepoint/portal-health)的基本原則、作法和建議。</span><span class="sxs-lookup"><span data-stu-id="90cf8-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="90cf8-119">這項功能不適用於 Office 365 德國、由世紀運作的 Office 365 (中國) 或 Microsoft 365 美國政府方案。</span><span class="sxs-lookup"><span data-stu-id="90cf8-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="90cf8-120">應用程式安裝並聯機至 SharePoint 線上</span><span class="sxs-lookup"><span data-stu-id="90cf8-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="90cf8-121">[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="90cf8-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="90cf8-p104">如果您安裝的是舊版 SharePoint Online 管理命令介面，請移至 [新增或移除程式]，並解除安裝 [SharePoint Online 管理命令介面]。 </span><span class="sxs-lookup"><span data-stu-id="90cf8-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="90cf8-123">在下載中心頁面上，選取您的語言，然後按一下 [下載] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="90cf8-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="90cf8-124">系統會請您選擇下載 x64 或 x86 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="90cf8-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="90cf8-125">如果您執行的是 64 位元版本的 Windows，請下載 x64 檔案；或如果您執行的是 32 位元版本，請下載 x86 檔案。</span><span class="sxs-lookup"><span data-stu-id="90cf8-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="90cf8-126">如果您不知道，請參閱[我正在執行哪個版本的 Windows 作業系統？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="90cf8-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="90cf8-127">下載檔案之後，請執行檔案，並按照安裝精靈中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="90cf8-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="90cf8-128">在 Microsoft 365 以[全域系統管理員或 SharePoint 管理員](/sharepoint/sharepoint-admin-role)的身分登入。</span><span class="sxs-lookup"><span data-stu-id="90cf8-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="90cf8-129">若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="90cf8-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="90cf8-130">查看任何現有的入口網站啟動設置</span><span class="sxs-lookup"><span data-stu-id="90cf8-130">View any existing portal launch setups</span></span>

<span data-ttu-id="90cf8-131">若要查看是否有現有的入口網站啟動設定：</span><span class="sxs-lookup"><span data-stu-id="90cf8-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="90cf8-132">在網站上排程入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="90cf8-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="90cf8-133">所需的波形數目取決於您預期的啟動大小。</span><span class="sxs-lookup"><span data-stu-id="90cf8-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="90cf8-134">小於10k 使用者：1個波形</span><span class="sxs-lookup"><span data-stu-id="90cf8-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="90cf8-135">10k 至30k 使用者：3波浪</span><span class="sxs-lookup"><span data-stu-id="90cf8-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="90cf8-136">30k + 至100k 使用者：5無線電波</span><span class="sxs-lookup"><span data-stu-id="90cf8-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="90cf8-137">超過100k 的使用者：5無線電波，並與您的 Microsoft 帳戶小組聯繫</span><span class="sxs-lookup"><span data-stu-id="90cf8-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="90cf8-138">雙向重新定向的步驟</span><span class="sxs-lookup"><span data-stu-id="90cf8-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="90cf8-139">雙向重新導向包括啟動新的現代 SharePoint Online 入口網站取代現有的 SharePoint 傳統或新式入口網站。</span><span class="sxs-lookup"><span data-stu-id="90cf8-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="90cf8-140">主動波形中的使用者將會重新導向至新網站，不論其流覽的是舊的還是新的網站。</span><span class="sxs-lookup"><span data-stu-id="90cf8-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="90cf8-141">嘗試存取新網站的非啟動浪潮中的使用者，將會重新導向至舊網站，直到其 wave 啟動為止。</span><span class="sxs-lookup"><span data-stu-id="90cf8-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="90cf8-142">我們只支援舊網站上的預設首頁與新網站上的預設首頁之間的重定向。</span><span class="sxs-lookup"><span data-stu-id="90cf8-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="90cf8-143">若要讓系統管理員或擁有者必須存取舊的和新的網站，而不重新導向，請確定它們是以 `WaveOverrideUsers` 參數列出。</span><span class="sxs-lookup"><span data-stu-id="90cf8-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="90cf8-144">若要讓系統管理員或擁有者必須存取舊的和新的網站，而不重新導向，請確定它們是以 `WaveOverrideUsers` 參數列出。</span><span class="sxs-lookup"><span data-stu-id="90cf8-144">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="90cf8-145">我們只支援舊網站上的預設首頁與新網站上的預設首頁之間的重定向。</span><span class="sxs-lookup"><span data-stu-id="90cf8-145">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span>

<span data-ttu-id="90cf8-146">若要以分段方式將現有的 SharePoint 網站中的使用者遷移至新的 SharePoint 網站，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="90cf8-146">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="90cf8-147">執行下列命令以指定入口啟動波形。</span><span class="sxs-lookup"><span data-stu-id="90cf8-147">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="90cf8-148">範例：</span><span class="sxs-lookup"><span data-stu-id="90cf8-148">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="90cf8-149">完整驗證。</span><span class="sxs-lookup"><span data-stu-id="90cf8-149">Complete validation.</span></span> <span data-ttu-id="90cf8-150">重新導向會花5-10 分鐘的時間來完成整個服務的設定。</span><span class="sxs-lookup"><span data-stu-id="90cf8-150">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="90cf8-151">重定向至暫存頁面的步驟</span><span class="sxs-lookup"><span data-stu-id="90cf8-151">Steps for redirection to temporary page</span></span>

<span data-ttu-id="90cf8-152">當不存在現有的 SharePoint 入口網站時，應使用暫存頁面重新導向。</span><span class="sxs-lookup"><span data-stu-id="90cf8-152">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="90cf8-153">使用者會以分段的方式，將使用者導向至新的現代 SharePoint Online 入口網站。</span><span class="sxs-lookup"><span data-stu-id="90cf8-153">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="90cf8-154">如果使用者處於尚未啟動的 wave，將會重新導向至臨時頁面 (任何 URL) 。</span><span class="sxs-lookup"><span data-stu-id="90cf8-154">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="90cf8-155">執行下列命令以指定入口啟動波形。</span><span class="sxs-lookup"><span data-stu-id="90cf8-155">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="90cf8-156">範例：</span><span class="sxs-lookup"><span data-stu-id="90cf8-156">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="90cf8-157">完整驗證。</span><span class="sxs-lookup"><span data-stu-id="90cf8-157">Complete validation.</span></span> <span data-ttu-id="90cf8-158">重新導向會花5-10 分鐘的時間來完成整個服務的設定。</span><span class="sxs-lookup"><span data-stu-id="90cf8-158">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="90cf8-159">暫停或重新開機網站上的入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="90cf8-159">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="90cf8-160">若要暫停進行中的入口網站啟動，並暫時避免發生即將進行的 wave progressions，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="90cf8-160">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="90cf8-161">驗證是否所有使用者都已重新導向到舊網站。</span><span class="sxs-lookup"><span data-stu-id="90cf8-161">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="90cf8-162">若要重新開機已暫停的入口網站啟動，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="90cf8-162">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="90cf8-163">驗證重新定向現在已還原。</span><span class="sxs-lookup"><span data-stu-id="90cf8-163">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="90cf8-164">在網站上刪除入口網站啟動</span><span class="sxs-lookup"><span data-stu-id="90cf8-164">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="90cf8-165">建立入口網站啟動 Wave。</span><span class="sxs-lookup"><span data-stu-id="90cf8-165">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="90cf8-166">執行下列命令，以刪除針對網站排程或進行中的入口網站啟動。</span><span class="sxs-lookup"><span data-stu-id="90cf8-166">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="90cf8-167">驗證所有使用者都不會進行重新導向。</span><span class="sxs-lookup"><span data-stu-id="90cf8-167">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="90cf8-168">深入了解</span><span class="sxs-lookup"><span data-stu-id="90cf8-168">Learn more</span></span>
[<span data-ttu-id="90cf8-169">在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫</span><span class="sxs-lookup"><span data-stu-id="90cf8-169">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
