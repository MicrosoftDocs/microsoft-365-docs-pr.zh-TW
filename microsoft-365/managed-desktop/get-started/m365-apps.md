---
title: Microsoft 365 Apps 企業版
description: 如何部署 Microsoft 365 應用程式、其更新方式及設定的管理方式
keywords: 變更歷程記錄
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 26e62d6e59f1f90e35d9e18e6eed917a66876645
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453918"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="e2b22-104">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="e2b22-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="e2b22-105">初始部署</span><span class="sxs-lookup"><span data-stu-id="e2b22-105">Initial deployment</span></span>

<span data-ttu-id="e2b22-106">Microsoft 受管理的桌面機，可確保在所有 [程式裝置](../service-description/device-list.md)上安裝 Microsoft 365 應用程式 for enterprise (64 位) 。</span><span class="sxs-lookup"><span data-stu-id="e2b22-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="e2b22-107">傳送裝置時，裝置上應會出現下列所有應用程式：</span><span class="sxs-lookup"><span data-stu-id="e2b22-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="e2b22-108">Word</span><span class="sxs-lookup"><span data-stu-id="e2b22-108">Word</span></span>
- <span data-ttu-id="e2b22-109">Excel</span><span class="sxs-lookup"><span data-stu-id="e2b22-109">Excel</span></span>
- <span data-ttu-id="e2b22-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="e2b22-110">PowerPoint</span></span>
- <span data-ttu-id="e2b22-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="e2b22-111">Outlook</span></span>
- <span data-ttu-id="e2b22-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="e2b22-112">Publisher</span></span>
- <span data-ttu-id="e2b22-113">Access</span><span class="sxs-lookup"><span data-stu-id="e2b22-113">Access</span></span>
- <span data-ttu-id="e2b22-114">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e2b22-114">Skype for Business</span></span>
- <span data-ttu-id="e2b22-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="e2b22-115">OneNote</span></span>

<span data-ttu-id="e2b22-116">這種方法會將網路影響降至最低，並確保使用者在收到其裝置時可以立即生產力。</span><span class="sxs-lookup"><span data-stu-id="e2b22-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="e2b22-117">然後，我們會將更多原則部署到受管理的裝置，以設定要使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e2b22-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="e2b22-118">Microsoft 團隊會獨立于適用于企業的 Microsoft 365 應用程式進行部署，而且不會包含在基底影像中。</span><span class="sxs-lookup"><span data-stu-id="e2b22-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="e2b22-119">適用于使用者的部署</span><span class="sxs-lookup"><span data-stu-id="e2b22-119">Available deployment to users</span></span>

<span data-ttu-id="e2b22-120">如果使用者在其裝置上沒有 Microsoft 365 應用程式出於任何原因，您可以使用套件，將裝置傳回其預期的狀態。</span><span class="sxs-lookup"><span data-stu-id="e2b22-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="e2b22-121">將使用者新增至新式的辦公 **Office365_Install** 群組，在公司入口網站中，這些應用程式就能使用。</span><span class="sxs-lookup"><span data-stu-id="e2b22-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="e2b22-122">適用于企業的 Microsoft 365 應用程式 (32-位) </span><span class="sxs-lookup"><span data-stu-id="e2b22-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="e2b22-123">Microsoft 受管理的桌面不支援部署 M365 應用程式的32位版本的 enterprise。</span><span class="sxs-lookup"><span data-stu-id="e2b22-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="e2b22-124">Microsoft 365 應用程式的更新</span><span class="sxs-lookup"><span data-stu-id="e2b22-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="e2b22-125">Microsoft 365 應用程式已設定為在 [每月的 Enterprise 通道](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)上更新。</span><span class="sxs-lookup"><span data-stu-id="e2b22-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="e2b22-126">這項練習每月都會為您的使用者提供新的 Office 功能，但每月只會收到一次更新，且可預測的發行排程。</span><span class="sxs-lookup"><span data-stu-id="e2b22-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="e2b22-127">更新會在每月的第二個星期二發佈;這些更新可包含功能、安全性和品質更新。</span><span class="sxs-lookup"><span data-stu-id="e2b22-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="e2b22-128">這些更新會自動進行，而且會直接從 Office CDN （適用于該特定通道）上抽出。</span><span class="sxs-lookup"><span data-stu-id="e2b22-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="e2b22-129">Microsoft 受管理的桌面 staggers 每個版本，以找出您環境中的任何潛在問題。</span><span class="sxs-lookup"><span data-stu-id="e2b22-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="e2b22-130">從 Microsoft 365 應用程式產品群組發行的28天后，我們會完成首展。</span><span class="sxs-lookup"><span data-stu-id="e2b22-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="e2b22-131">Microsoft 受管理的桌面排程將更新版本更新成不同的群組，允許驗證和測試的時間如下：</span><span class="sxs-lookup"><span data-stu-id="e2b22-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="e2b22-132">測試：零天</span><span class="sxs-lookup"><span data-stu-id="e2b22-132">Test: zero days</span></span>
- <span data-ttu-id="e2b22-133">第一：零天</span><span class="sxs-lookup"><span data-stu-id="e2b22-133">First: zero days</span></span>
- <span data-ttu-id="e2b22-134">Fast：3天</span><span class="sxs-lookup"><span data-stu-id="e2b22-134">Fast: 3 days</span></span>
- <span data-ttu-id="e2b22-135">寬：7天</span><span class="sxs-lookup"><span data-stu-id="e2b22-135">Broad: 7 days</span></span>

<span data-ttu-id="e2b22-136">Microsoft 受管理的桌面會設定裝置的7天 [更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 。</span><span class="sxs-lookup"><span data-stu-id="e2b22-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="e2b22-137">更新可供使用後，必須在七天內安裝。</span><span class="sxs-lookup"><span data-stu-id="e2b22-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="e2b22-138">使用者會 [收到](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 下列數個位置要求的更新：應用程式，在最後期限之前的系統託盤12小時內，而且會在最後期限之前收到15分鐘的警告。</span><span class="sxs-lookup"><span data-stu-id="e2b22-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="e2b22-139">所有 Microsoft 365 應用程式必須關閉，更新才能完成。</span><span class="sxs-lookup"><span data-stu-id="e2b22-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="e2b22-140">暫停或回復更新</span><span class="sxs-lookup"><span data-stu-id="e2b22-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="e2b22-141">若由於任何原因需要暫停或回復 Microsoft 365 應用程式更新，請透過 Microsoft 受管理的桌面入口網站來歸檔系統 [管理員支援要求](../working-with-managed-desktop/admin-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="e2b22-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="e2b22-142">在發行期間，Microsoft 管理的桌面會監控所有 Microsoft 365 應用程式的錯誤率。</span><span class="sxs-lookup"><span data-stu-id="e2b22-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="e2b22-143">如果我們注意到新版本與其前置任務之間的品質差別很大，我們可以透過 Microsoft Managed Desktop Admin 入口網站與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="e2b22-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="e2b22-144">根據嚴重性，我們會詢問您是否要暫停發行，或通知您我們採取行動來緩解問題。</span><span class="sxs-lookup"><span data-stu-id="e2b22-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="e2b22-145">傳遞優化</span><span class="sxs-lookup"><span data-stu-id="e2b22-145">Delivery optimization</span></span>

<span data-ttu-id="e2b22-146">傳遞優化是 Windows 10 中可用的對等發佈技術。</span><span class="sxs-lookup"><span data-stu-id="e2b22-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="e2b22-147">它可讓裝置共用從 Microsoft 透過網際網路下載之裝置的內容，例如更新。</span><span class="sxs-lookup"><span data-stu-id="e2b22-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="e2b22-148">因為裝置可以從其本機網路上的另一個裝置取得更新的某些部分，而不是完全從 Microsoft 下載更新，所以使用它可協助減少網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="e2b22-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="e2b22-149">預設會在執行 Windows 10 企業版或 Windows 10 教育版的裝置上啟用[傳遞優化](https://docs.microsoft.com/deployoffice/delivery-optimization)。</span><span class="sxs-lookup"><span data-stu-id="e2b22-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="e2b22-150">Microsoft 受管理的桌面所管理的設定</span><span class="sxs-lookup"><span data-stu-id="e2b22-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="e2b22-151">Microsoft 會管理部分設定為服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="e2b22-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="e2b22-152">Microsoft 受管理的桌面不會管理 Office 安全性基準，但是您可以遵循 [您管理的設定](#settings-you-manage) 一節中的指導方針來設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="e2b22-153">更新設定</span><span class="sxs-lookup"><span data-stu-id="e2b22-153">Update settings</span></span>

<span data-ttu-id="e2b22-154">Microsoft 受管理的桌面維護受管理裝置的所有 [更新設定](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) ，您應該修改這些設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="e2b22-155">將更新設定為自動進行</span><span class="sxs-lookup"><span data-stu-id="e2b22-155">Set updates to occur automatically</span></span>

<span data-ttu-id="e2b22-156">**預設值**： Enabled</span><span class="sxs-lookup"><span data-stu-id="e2b22-156">**Default value**: Enabled</span></span>

<span data-ttu-id="e2b22-157">設定此原則是為了確保所有的 Office 裝置都可以從雲端保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="e2b22-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="e2b22-158">設定必須套用更新的截止期限</span><span class="sxs-lookup"><span data-stu-id="e2b22-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="e2b22-159">**預設值**：7天</span><span class="sxs-lookup"><span data-stu-id="e2b22-159">**Default value**: 7 days</span></span>

<span data-ttu-id="e2b22-160">**UpdateDeadline** 原則是用來設定使用者在裝置上強制執行更新之前所用的寬限期。</span><span class="sxs-lookup"><span data-stu-id="e2b22-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="e2b22-161">此期限原則也會觸發 [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 給使用者，以通知他們其裝置所需的變更。</span><span class="sxs-lookup"><span data-stu-id="e2b22-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="e2b22-162">推遲裝置上的更新時間</span><span class="sxs-lookup"><span data-stu-id="e2b22-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="e2b22-163">針對每個更新管理裝置群組，這項原則的設定會有所不同，Microsoft 受管理的桌上型電腦必須符合其更新目標：</span><span class="sxs-lookup"><span data-stu-id="e2b22-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="e2b22-164">測試：零天</span><span class="sxs-lookup"><span data-stu-id="e2b22-164">Test: zero days</span></span>
- <span data-ttu-id="e2b22-165">第一：零天</span><span class="sxs-lookup"><span data-stu-id="e2b22-165">First: zero days</span></span>
- <span data-ttu-id="e2b22-166">快7天</span><span class="sxs-lookup"><span data-stu-id="e2b22-166">Fast 7 days</span></span>
- <span data-ttu-id="e2b22-167">寬：21天</span><span class="sxs-lookup"><span data-stu-id="e2b22-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="e2b22-168">更新通知設定</span><span class="sxs-lookup"><span data-stu-id="e2b22-168">Update notifications settings</span></span>

<span data-ttu-id="e2b22-169">**預設值**： False</span><span class="sxs-lookup"><span data-stu-id="e2b22-169">**Default value**: False</span></span>

<span data-ttu-id="e2b22-170">在 Microsoft 受管理的桌面裝置上，[隱藏更新通知] 設定為 **False** ，可在需要更新時 [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 使用者，以提供最佳的更新體驗。</span><span class="sxs-lookup"><span data-stu-id="e2b22-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="e2b22-171">指定要尋找更新的位置</span><span class="sxs-lookup"><span data-stu-id="e2b22-171">Specify a location to look for updates</span></span>

<span data-ttu-id="e2b22-172">**預設值**：每月的 Enterprise 通道</span><span class="sxs-lookup"><span data-stu-id="e2b22-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="e2b22-173">使用 **UpdatePath** 和 **UpdateChannel** 原則的組合，以達到更新排程的需求。</span><span class="sxs-lookup"><span data-stu-id="e2b22-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="e2b22-174">設定這些原則，以確保所有 Office 裝置都直接從 CDN 接收更新，以進行每月的 Enterprise 通道。</span><span class="sxs-lookup"><span data-stu-id="e2b22-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="e2b22-175">指定 Microsoft 365 應用程式的目標版本</span><span class="sxs-lookup"><span data-stu-id="e2b22-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="e2b22-176">Microsoft 受管理的桌面有時會使用目標版本原則，以復原或固定特定版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="e2b22-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="e2b22-177">隱藏啟用或停用 Office 自動更新的選項</span><span class="sxs-lookup"><span data-stu-id="e2b22-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="e2b22-178">**預設值**： Enabled</span><span class="sxs-lookup"><span data-stu-id="e2b22-178">**Default value**: Enabled</span></span>

<span data-ttu-id="e2b22-179">Microsoft 受管理的桌面需要此設定，以符合 Microsoft 365 應用程式的更新目標。</span><span class="sxs-lookup"><span data-stu-id="e2b22-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="e2b22-180">第一次執行設定</span><span class="sxs-lookup"><span data-stu-id="e2b22-180">First run settings</span></span> 

<span data-ttu-id="e2b22-181">有幾個設定會影響第一次執行 Office 的行為。</span><span class="sxs-lookup"><span data-stu-id="e2b22-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="e2b22-182">代表使用者接受授權條款</span><span class="sxs-lookup"><span data-stu-id="e2b22-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="e2b22-183">**預設值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="e2b22-183">**Default value**: Disabled</span></span>

<span data-ttu-id="e2b22-184">當使用者第一次開啟 Microsoft 365 應用程式時，系統會提示他們接受授權條款。</span><span class="sxs-lookup"><span data-stu-id="e2b22-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="e2b22-185">如果您想要代表使用者接受授權條款，請使用 Microsoft Managed Desktop Operations 團隊要求服務要求，以供啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="e2b22-186">[隱藏 Outlook mobile] 核取方塊</span><span class="sxs-lookup"><span data-stu-id="e2b22-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="e2b22-187">**預設值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="e2b22-187">**Default value**: Disabled</span></span>

<span data-ttu-id="e2b22-188">當使用者第一次開啟 Outlook 時，系統會提示您安裝 Outlook Mobile。</span><span class="sxs-lookup"><span data-stu-id="e2b22-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="e2b22-189">如果您不想讓使用者看到該核取方塊，請向 Microsoft Managed Desktop Operations 團隊索要服務要求，要求為您的裝置啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="e2b22-190">其他設定</span><span class="sxs-lookup"><span data-stu-id="e2b22-190">Other settings</span></span>

<span data-ttu-id="e2b22-191">Microsoft 受管理的桌面也可以隨意設定其他 Microsoft 365 應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="e2b22-192">停用個人 OneDrive</span><span class="sxs-lookup"><span data-stu-id="e2b22-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="e2b22-193">**預設值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="e2b22-193">**Default value**: Disabled</span></span>

<span data-ttu-id="e2b22-194">有些組織擔心使用者可以存取其裝置上的公司和個人檔案。</span><span class="sxs-lookup"><span data-stu-id="e2b22-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="e2b22-195">您可以使用 Microsoft Managed Desktop Operations 團隊傳送服務要求，以要求啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="e2b22-196">您管理的設定</span><span class="sxs-lookup"><span data-stu-id="e2b22-196">Settings you manage</span></span>

<span data-ttu-id="e2b22-197">Microsoft 受管理的桌面尚未設定許多其他原則成為我們的服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="e2b22-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="e2b22-198">您可以使用使用 [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Service 的 Microsoft Intune 來設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="e2b22-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="e2b22-199">若要設定這些原則，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e2b22-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="e2b22-200">登入 Microsoft 端點管理員管理中心。</span><span class="sxs-lookup"><span data-stu-id="e2b22-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="e2b22-201">**針對 Office app > 建立，選取應用程式 > 原則**</span><span class="sxs-lookup"><span data-stu-id="e2b22-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="e2b22-202">在 [ **建立原則** 設定] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e2b22-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="e2b22-203">輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="e2b22-203">Enter a name.</span></span>
    - <span data-ttu-id="e2b22-204">提供 (選用) 的描述。</span><span class="sxs-lookup"><span data-stu-id="e2b22-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="e2b22-205">在 [ **指派**] 中，選擇 [這項原則是套用至 Microsoft 365 應用程式的所有使用者]，還是只適用于以 web 方式匿名存取檔的使用者。</span><span class="sxs-lookup"><span data-stu-id="e2b22-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="e2b22-206">選取指派給原則設定的 AAD 型安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e2b22-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="e2b22-207">每個原則設定只可指派給一個群組，而每個群組只能指派一個原則設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="e2b22-208">設定要包含在 policy configuration 中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="e2b22-209">您可以搜尋原則設定名稱，以尋找您要設定的原則設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="e2b22-210">您也可以在應用程式上進行篩選，不論原則是建議的安全性基準，還是原則是否已設定。</span><span class="sxs-lookup"><span data-stu-id="e2b22-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="e2b22-211">[平臺] 欄位會指出是否將原則套用至適用于 Windows 裝置的 Microsoft 365 應用程式、適用于 web 的 Office 或全部。</span><span class="sxs-lookup"><span data-stu-id="e2b22-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="e2b22-212">進行選取之後，請選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="e2b22-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="e2b22-213">Office 配置原則只支援以使用者為基礎的部署</span><span class="sxs-lookup"><span data-stu-id="e2b22-213">Office Configuration Policies only support user-based deployment</span></span>
