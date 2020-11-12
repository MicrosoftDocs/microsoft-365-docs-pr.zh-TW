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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999566"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="94d4e-103">使用入口網站啟動計畫程式啟動入口網站</span><span class="sxs-lookup"><span data-stu-id="94d4e-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="94d4e-104">您可以先驗證租使用者管理員為新入口網站設定聲波的能力，以啟動入口網站的入口網站啟動程式。</span><span class="sxs-lookup"><span data-stu-id="94d4e-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="94d4e-105">然後，系統管理員可以根據主動無線電波中的使用者是否存在，來驗證要求重新定向。</span><span class="sxs-lookup"><span data-stu-id="94d4e-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="94d4e-106">如需有關啟動成功入口網站的詳細資訊，請遵循 [建立、啟動及維護健康入口網站](https://go.microsoft.com/fwlink/?linkid=2105838)的基本原則、作法和建議。</span><span class="sxs-lookup"><span data-stu-id="94d4e-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="94d4e-107">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="94d4e-107">App setup</span></span>
1. <span data-ttu-id="94d4e-108">如果有現有 `Microsoft.Online.SharePoint.PowerShell` 從您的機器透過控制台，請卸載。</span><span class="sxs-lookup"><span data-stu-id="94d4e-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="94d4e-109">在 PowerShell 通過 `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="94d4e-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="94d4e-110">連線至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="94d4e-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="94d4e-111">在 Windows 中開啟 [SharePoint 線上管理命令](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 介面。</span><span class="sxs-lookup"><span data-stu-id="94d4e-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="94d4e-112">以系統管理員身分連線到您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="94d4e-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="94d4e-113">出現提示時提供您的密碼。</span><span class="sxs-lookup"><span data-stu-id="94d4e-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="94d4e-114">用於取得現有安裝程式的命令</span><span class="sxs-lookup"><span data-stu-id="94d4e-114">Command to get an existing setup</span></span>

<span data-ttu-id="94d4e-115">若要查看現有的入口網站啟動設定：</span><span class="sxs-lookup"><span data-stu-id="94d4e-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="94d4e-116">傳遞 `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` 。</span><span class="sxs-lookup"><span data-stu-id="94d4e-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="94d4e-117">`-DisplayFormat Raw`如果您想要看到格式化為原始輸入格式的 wave 集合，請傳遞其他參數。</span><span class="sxs-lookup"><span data-stu-id="94d4e-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="94d4e-118">雙向重新定向的命令</span><span class="sxs-lookup"><span data-stu-id="94d4e-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="94d4e-119">若要以分段方式將舊網站使用者遷移至新網站，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="94d4e-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="94d4e-120">建立入口網站啟動無線電波。</span><span class="sxs-lookup"><span data-stu-id="94d4e-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="94d4e-121">這僅適用于早期版本測試階段。</span><span class="sxs-lookup"><span data-stu-id="94d4e-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="94d4e-122">若要立即測試變更的影響，請確定第一個波形 `LaunchDateUtc` 已設定為目前日期。</span><span class="sxs-lookup"><span data-stu-id="94d4e-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="94d4e-123">如果您沒有提供此旗標，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="94d4e-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="94d4e-124">發生此錯誤的原因是，在實際執行中的啟動必須預先排程至少7天。</span><span class="sxs-lookup"><span data-stu-id="94d4e-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="94d4e-125">完整驗證。</span><span class="sxs-lookup"><span data-stu-id="94d4e-125">Complete validation.</span></span>
  - <span data-ttu-id="94d4e-126">重新導向必須花5分鐘的時間才能完成整個服務的設定，因此請稍候，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="94d4e-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="94d4e-127">如果您以指定的使用者登入 `WaveOverrideUsers` ，則不會有任何變更。</span><span class="sxs-lookup"><span data-stu-id="94d4e-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="94d4e-128">您應該在所流覽的網站上進行。</span><span class="sxs-lookup"><span data-stu-id="94d4e-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="94d4e-129">登入 *SG1 觀眾* 的使用者。</span><span class="sxs-lookup"><span data-stu-id="94d4e-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="94d4e-130">流覽至舊的網站，您應該重新導向至新的網站。</span><span class="sxs-lookup"><span data-stu-id="94d4e-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="94d4e-131">流覽至新的網站，您應該保留在新的網站。</span><span class="sxs-lookup"><span data-stu-id="94d4e-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="94d4e-132">使用 *查看者 SG2* 中的使用者登入，並流覽至舊的網站，並停留在舊網站。</span><span class="sxs-lookup"><span data-stu-id="94d4e-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="94d4e-133">流覽至新的網站，您應該重新導向至舊的網站。</span><span class="sxs-lookup"><span data-stu-id="94d4e-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="94d4e-134">暫停入口網站啟動。</span><span class="sxs-lookup"><span data-stu-id="94d4e-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="94d4e-135">如果您需要暫停啟動波形，您可以將其暫停為 "x" 天。</span><span class="sxs-lookup"><span data-stu-id="94d4e-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="94d4e-136">將旗標設定 `Status` 為 pause 可避免所有即將到來的 wave progressions。</span><span class="sxs-lookup"><span data-stu-id="94d4e-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="94d4e-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="94d4e-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="94d4e-138">這會驗證所有使用者都已重新導向到舊網站。</span><span class="sxs-lookup"><span data-stu-id="94d4e-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="94d4e-139">重新開機入口網站啟動進展。</span><span class="sxs-lookup"><span data-stu-id="94d4e-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="94d4e-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="94d4e-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="94d4e-141">驗證重新定向現在已還原。</span><span class="sxs-lookup"><span data-stu-id="94d4e-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="94d4e-142">刪除入口網站啟動設定。</span><span class="sxs-lookup"><span data-stu-id="94d4e-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="94d4e-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="94d4e-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="94d4e-144">驗證所有使用者都不會進行重新導向。</span><span class="sxs-lookup"><span data-stu-id="94d4e-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="94d4e-145">重新導向至暫存頁面的命令</span><span class="sxs-lookup"><span data-stu-id="94d4e-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="94d4e-146">如果您沒有舊版網站，而且想要在新的入口網站頁面上忽略不在 wave 中的使用者，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="94d4e-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="94d4e-147">若要在任何網站中建立暫存頁面：</span><span class="sxs-lookup"><span data-stu-id="94d4e-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="94d4e-148">建立入口網站啟動 Wave。</span><span class="sxs-lookup"><span data-stu-id="94d4e-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="94d4e-149">完整驗證。</span><span class="sxs-lookup"><span data-stu-id="94d4e-149">Complete validation.</span></span>

  - <span data-ttu-id="94d4e-150">請等候五分鐘之後繼續，因為動作可能需要最多五分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="94d4e-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="94d4e-151">使用 [ *查看者* ] 的一部分使用者記錄 SG1 及：</span><span class="sxs-lookup"><span data-stu-id="94d4e-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="94d4e-152">流覽至新的網站，您應該保留在新的網站。</span><span class="sxs-lookup"><span data-stu-id="94d4e-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="94d4e-153">流覽至 [temp] 頁面，您應該停留在 [temp] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="94d4e-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="94d4e-154">記錄屬於 [ *查看者] SG2* 的使用者，並：</span><span class="sxs-lookup"><span data-stu-id="94d4e-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="94d4e-155">流覽至新的網站，您應該重新導向至 [temp] 頁面。</span><span class="sxs-lookup"><span data-stu-id="94d4e-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="94d4e-156">流覽至 [temp] 頁面，您應該停留在 [temp] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="94d4e-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="94d4e-157">刪除入口網站啟動設定。</span><span class="sxs-lookup"><span data-stu-id="94d4e-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="94d4e-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="94d4e-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="94d4e-159">驗證所有使用者都不會進行重新導向。</span><span class="sxs-lookup"><span data-stu-id="94d4e-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="94d4e-160">深入了解</span><span class="sxs-lookup"><span data-stu-id="94d4e-160">Learn more</span></span>
[<span data-ttu-id="94d4e-161">在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫</span><span class="sxs-lookup"><span data-stu-id="94d4e-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)