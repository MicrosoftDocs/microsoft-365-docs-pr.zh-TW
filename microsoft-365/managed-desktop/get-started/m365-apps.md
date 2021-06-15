---
title: Microsoft 365 Apps 企業版
description: 如何部署 Microsoft 365 Apps、更新方式及設定的管理方式
keywords: 變更歷程記錄
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: c3928b5814332f2585adc613e1e84cbe5cc883a0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925608"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="09e97-104">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="09e97-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="09e97-105">初始部署</span><span class="sxs-lookup"><span data-stu-id="09e97-105">Initial deployment</span></span>

<span data-ttu-id="09e97-106">Microsoft 受管理的電腦確保將 Microsoft 365 Apps 企業版 (64 位) 安裝為所有[程式裝置](../service-description/device-list.md)上的影像的一部分。</span><span class="sxs-lookup"><span data-stu-id="09e97-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="09e97-107">傳送裝置時，裝置上應會出現下列所有應用程式：</span><span class="sxs-lookup"><span data-stu-id="09e97-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="09e97-108">Word</span><span class="sxs-lookup"><span data-stu-id="09e97-108">Word</span></span>
- <span data-ttu-id="09e97-109">Excel</span><span class="sxs-lookup"><span data-stu-id="09e97-109">Excel</span></span>
- <span data-ttu-id="09e97-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="09e97-110">PowerPoint</span></span>
- <span data-ttu-id="09e97-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="09e97-111">Outlook</span></span>
- <span data-ttu-id="09e97-112">發行者</span><span class="sxs-lookup"><span data-stu-id="09e97-112">Publisher</span></span>
- <span data-ttu-id="09e97-113">Access</span><span class="sxs-lookup"><span data-stu-id="09e97-113">Access</span></span>
- <span data-ttu-id="09e97-114">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="09e97-114">Skype for Business</span></span>
- <span data-ttu-id="09e97-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="09e97-115">OneNote</span></span>

<span data-ttu-id="09e97-116">這種方法會將網路影響降至最低，並確保使用者在收到其裝置時可以立即生產力。</span><span class="sxs-lookup"><span data-stu-id="09e97-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="09e97-117">然後，我們會將更多原則部署到受管理的裝置，以設定要使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="09e97-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="09e97-118">Microsoft Teams 會與 Microsoft 365 Apps 企業版分開部署，而且不會包含在基底影像中。</span><span class="sxs-lookup"><span data-stu-id="09e97-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="09e97-119">適用于使用者的部署</span><span class="sxs-lookup"><span data-stu-id="09e97-119">Available deployment to users</span></span>

<span data-ttu-id="09e97-120">如果使用者在其裝置上沒有任何原因的 Microsoft 365 Apps，您可以使用套件將裝置傳回其預期的狀態。</span><span class="sxs-lookup"><span data-stu-id="09e97-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="09e97-121">將使用者新增至 **新式的工作場所 Office Office365_Install** 群組，且應用程式會在公司入口網站中變為可用。</span><span class="sxs-lookup"><span data-stu-id="09e97-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="09e97-122">Microsoft 365 Apps 企業版 (32 位) </span><span class="sxs-lookup"><span data-stu-id="09e97-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="09e97-123">Microsoft 受管理的電腦不支援部署32位版本的 M365 應用程式的 enterprise。</span><span class="sxs-lookup"><span data-stu-id="09e97-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="09e97-124">Microsoft 365 Apps 的更新</span><span class="sxs-lookup"><span data-stu-id="09e97-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="09e97-125">Microsoft 365 Apps 會設定為[每月 Enterprise 通道](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)更新。</span><span class="sxs-lookup"><span data-stu-id="09e97-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="09e97-126">這項作法每月都會為您的使用者提供新的 Office 功能，但每月只會收到一次更新的版本，以供預測的發行排程使用。</span><span class="sxs-lookup"><span data-stu-id="09e97-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="09e97-127">更新會在每月的第二個星期二發佈;這些更新可包含功能、安全性和品質更新。</span><span class="sxs-lookup"><span data-stu-id="09e97-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="09e97-128">這些更新會自動進行，並且直接從該特定通道的 Office CDN 中拉入。</span><span class="sxs-lookup"><span data-stu-id="09e97-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="09e97-129">Microsoft 受管理的電腦 staggers 每個版本，以找出您環境中的任何潛在問題。</span><span class="sxs-lookup"><span data-stu-id="09e97-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="09e97-130">從 Microsoft 365 應用程式產品群組發行一開始28天，我們就會完成。</span><span class="sxs-lookup"><span data-stu-id="09e97-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="09e97-131">Microsoft 受管理的電腦排程將更新版本更新成不同的群組，允許驗證及測試的時間如下：</span><span class="sxs-lookup"><span data-stu-id="09e97-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="09e97-132">測試：零天</span><span class="sxs-lookup"><span data-stu-id="09e97-132">Test: zero days</span></span>
- <span data-ttu-id="09e97-133">第一：零天</span><span class="sxs-lookup"><span data-stu-id="09e97-133">First: zero days</span></span>
- <span data-ttu-id="09e97-134">Fast：3天</span><span class="sxs-lookup"><span data-stu-id="09e97-134">Fast: 3 days</span></span>
- <span data-ttu-id="09e97-135">寬：7天</span><span class="sxs-lookup"><span data-stu-id="09e97-135">Broad: 7 days</span></span>

<span data-ttu-id="09e97-136">Microsoft 受管理的電腦會設定裝置的7天[更新期限](/deployoffice/configure-update-settings-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="09e97-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="09e97-137">更新可供使用後，必須在七天內安裝。</span><span class="sxs-lookup"><span data-stu-id="09e97-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="09e97-138">使用者會 [收到](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 下列數個位置要求的更新：應用程式，在最後期限之前的系統託盤12小時內，而且會在最後期限之前收到15分鐘的警告。</span><span class="sxs-lookup"><span data-stu-id="09e97-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="09e97-139">所有 Microsoft 365 Apps 都必須關閉，更新才會完成。</span><span class="sxs-lookup"><span data-stu-id="09e97-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="09e97-140">暫停或回復更新</span><span class="sxs-lookup"><span data-stu-id="09e97-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="09e97-141">如果您出於任何原因需要暫停或復原 Microsoft 365 的應用程式更新，請透過 Microsoft 受管理的電腦入口網站，將系統[管理員支援要求](../working-with-managed-desktop/admin-support.md)歸檔。</span><span class="sxs-lookup"><span data-stu-id="09e97-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="09e97-142">在發行時，Microsoft 受管理的電腦會監控所有 Microsoft 365 Apps 的錯誤率。</span><span class="sxs-lookup"><span data-stu-id="09e97-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="09e97-143">如果我們注意到新版本與其前置任務之間的品質差別很大，我們可以透過 Microsoft 受管理的電腦管理入口網站與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="09e97-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="09e97-144">根據嚴重性，我們會詢問您是否要暫停發行，或通知您我們採取行動來緩解問題。</span><span class="sxs-lookup"><span data-stu-id="09e97-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="09e97-145">傳遞優化</span><span class="sxs-lookup"><span data-stu-id="09e97-145">Delivery optimization</span></span>

<span data-ttu-id="09e97-146">傳遞優化是 Windows 10 中可用的對等發佈技術。</span><span class="sxs-lookup"><span data-stu-id="09e97-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="09e97-147">它可讓裝置共用從 Microsoft 透過網際網路下載之裝置的內容，例如更新。</span><span class="sxs-lookup"><span data-stu-id="09e97-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="09e97-148">因為裝置可以從其本機網路上的另一個裝置取得更新的某些部分，而不是完全從 Microsoft 下載更新，所以使用它可協助減少網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="09e97-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="09e97-149">預設會在執行 Windows 10 企業版或 Windows 10 教育版版本的裝置上啟用[傳遞優化](/deployoffice/delivery-optimization)。</span><span class="sxs-lookup"><span data-stu-id="09e97-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="09e97-150">由 Microsoft 受管理的電腦管理設定</span><span class="sxs-lookup"><span data-stu-id="09e97-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="09e97-151">Microsoft 會管理部分設定為服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="09e97-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="09e97-152">Microsoft 受管理的電腦不會管理 Office 的安全性基準，但是您可以遵循[您管理設定](#settings-you-manage)中的指導方針加以設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="09e97-153">更新設定</span><span class="sxs-lookup"><span data-stu-id="09e97-153">Update settings</span></span>

<span data-ttu-id="09e97-154">Microsoft 受管理的電腦維護受管理裝置的所有[更新設定](/deployoffice/configure-update-settings-microsoft-365-apps)，您應該修改這些設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="09e97-155">將更新設定為自動進行</span><span class="sxs-lookup"><span data-stu-id="09e97-155">Set updates to occur automatically</span></span>

<span data-ttu-id="09e97-156">**預設值**： Enabled</span><span class="sxs-lookup"><span data-stu-id="09e97-156">**Default value**: Enabled</span></span>

<span data-ttu-id="09e97-157">設定此原則是為了確保所有 Office 裝置都可以從雲端保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="09e97-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="09e97-158">設定必須套用更新的截止期限</span><span class="sxs-lookup"><span data-stu-id="09e97-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="09e97-159">**預設值**：7天</span><span class="sxs-lookup"><span data-stu-id="09e97-159">**Default value**: 7 days</span></span>

<span data-ttu-id="09e97-160">**UpdateDeadline** 原則是用來設定使用者在裝置上強制執行更新之前所用的寬限期。</span><span class="sxs-lookup"><span data-stu-id="09e97-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="09e97-161">此期限原則也會觸發 [通知](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 給使用者，以通知他們其裝置所需的變更。</span><span class="sxs-lookup"><span data-stu-id="09e97-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="09e97-162">推遲裝置上的更新時間</span><span class="sxs-lookup"><span data-stu-id="09e97-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="09e97-163">針對每個更新管理裝置群組，此原則的設定會有所不同，而且 Microsoft 受管理的電腦以滿足其更新目標的要求：</span><span class="sxs-lookup"><span data-stu-id="09e97-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="09e97-164">測試：零天</span><span class="sxs-lookup"><span data-stu-id="09e97-164">Test: zero days</span></span>
- <span data-ttu-id="09e97-165">第一：零天</span><span class="sxs-lookup"><span data-stu-id="09e97-165">First: zero days</span></span>
- <span data-ttu-id="09e97-166">快7天</span><span class="sxs-lookup"><span data-stu-id="09e97-166">Fast 7 days</span></span>
- <span data-ttu-id="09e97-167">寬：21天</span><span class="sxs-lookup"><span data-stu-id="09e97-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="09e97-168">更新通知設定</span><span class="sxs-lookup"><span data-stu-id="09e97-168">Update notifications settings</span></span>

<span data-ttu-id="09e97-169">**預設值**： False</span><span class="sxs-lookup"><span data-stu-id="09e97-169">**Default value**: False</span></span>

<span data-ttu-id="09e97-170">[隱藏更新通知] 設定會在 Microsoft 受管理的電腦裝置上設定為 **False** ，以便在需要更新時 [通知](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)使用者，以提供最佳的更新經驗。</span><span class="sxs-lookup"><span data-stu-id="09e97-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="09e97-171">指定要尋找更新的位置</span><span class="sxs-lookup"><span data-stu-id="09e97-171">Specify a location to look for updates</span></span>

<span data-ttu-id="09e97-172">**預設值**：每月 Enterprise 通道</span><span class="sxs-lookup"><span data-stu-id="09e97-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="09e97-173">使用 **UpdatePath** 和 **UpdateChannel** 原則的組合，以達到更新排程的需求。</span><span class="sxs-lookup"><span data-stu-id="09e97-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="09e97-174">設定這些原則，以確保所有 Office 裝置都直接從每月 Enterprise 通道的 CDN 接收更新。</span><span class="sxs-lookup"><span data-stu-id="09e97-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="09e97-175">指定 Microsoft 365 Apps 的目標版本</span><span class="sxs-lookup"><span data-stu-id="09e97-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="09e97-176">目標版本原則有時候會用 Microsoft 受管理的電腦，以復原或固定特定版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="09e97-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="09e97-177">隱藏啟用或停用 Office 自動更新的選項</span><span class="sxs-lookup"><span data-stu-id="09e97-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="09e97-178">**預設值**： Enabled</span><span class="sxs-lookup"><span data-stu-id="09e97-178">**Default value**: Enabled</span></span>

<span data-ttu-id="09e97-179">Microsoft 受管理的電腦以滿足 Microsoft 365 應用程式的更新目標，必須要有此設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="09e97-180">第一次執行設定</span><span class="sxs-lookup"><span data-stu-id="09e97-180">First run settings</span></span> 

<span data-ttu-id="09e97-181">在 Office 第一次執行時，有數個設定會影響行為。</span><span class="sxs-lookup"><span data-stu-id="09e97-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="09e97-182">代表使用者接受授權條款</span><span class="sxs-lookup"><span data-stu-id="09e97-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="09e97-183">**預設值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="09e97-183">**Default value**: Disabled</span></span>

<span data-ttu-id="09e97-184">當使用者第一次開啟 Microsoft 365 應用程式時，系統會提示他們接受授權條款。</span><span class="sxs-lookup"><span data-stu-id="09e97-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="09e97-185">如果您想要代表使用者接受授權條款，請將服務要求歸檔至 Microsoft 受管理的電腦作業小組要求啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="09e97-186">隱藏 Outlook 行動裝置核取方塊</span><span class="sxs-lookup"><span data-stu-id="09e97-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="09e97-187">**預設值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="09e97-187">**Default value**: Disabled</span></span>

<span data-ttu-id="09e97-188">當使用者第一次開啟時 Outlook 系統會提示他們安裝 Outlook Mobile。</span><span class="sxs-lookup"><span data-stu-id="09e97-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="09e97-189">如果您不想讓使用者看到該核取方塊，請將服務要求歸檔至 Microsoft 受管理的電腦作業小組要求為您的裝置啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="09e97-190">其他設定</span><span class="sxs-lookup"><span data-stu-id="09e97-190">Other settings</span></span>

<span data-ttu-id="09e97-191">其他一些 Microsoft 365 應用程式設定 Microsoft 受管理的電腦可以選擇性地加以設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="09e97-192">停用個人 OneDrive</span><span class="sxs-lookup"><span data-stu-id="09e97-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="09e97-193">**預設值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="09e97-193">**Default value**: Disabled</span></span>

<span data-ttu-id="09e97-194">有些組織擔心使用者可以存取其裝置上的公司和個人檔案。</span><span class="sxs-lookup"><span data-stu-id="09e97-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="09e97-195">您可以將服務要求與 Microsoft 受管理的電腦作業小組一起要求啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="09e97-196">您管理的設定</span><span class="sxs-lookup"><span data-stu-id="09e97-196">Settings you manage</span></span>

<span data-ttu-id="09e97-197">還有許多其他原則 Microsoft 受管理的電腦尚未設定為我們的服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="09e97-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="09e97-198">您可以使用 Microsoft Intune，使用[Office 雲端原則](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)服務來設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="09e97-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="09e97-199">若要設定這些原則，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="09e97-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="09e97-200">登入 Microsoft 端點管理員系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="09e97-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="09e97-201">**針對 Office > 建立的應用程式選取應用程式 > 原則**</span><span class="sxs-lookup"><span data-stu-id="09e97-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="09e97-202">在 [ **建立原則** 設定] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="09e97-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="09e97-203">輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="09e97-203">Enter a name.</span></span>
    - <span data-ttu-id="09e97-204">提供 (選用) 的描述。</span><span class="sxs-lookup"><span data-stu-id="09e97-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="09e97-205">在 [**工作分派**] 中，選擇是否要將這個原則套用至 Microsoft 365 Apps 企業版的所有使用者，或僅針對使用 Office 網頁版匿名存取檔的使用者。</span><span class="sxs-lookup"><span data-stu-id="09e97-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="09e97-206">選取指派給原則設定的 AAD 型安全性群組。</span><span class="sxs-lookup"><span data-stu-id="09e97-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="09e97-207">每個原則設定只可指派給一個群組，而每個群組只能指派一個原則設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="09e97-208">設定要包含在 policy configuration 中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="09e97-209">您可以搜尋原則設定名稱，以尋找您要設定的原則設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="09e97-210">您也可以在應用程式上進行篩選，不論原則是建議的安全性基準，還是原則是否已設定。</span><span class="sxs-lookup"><span data-stu-id="09e97-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="09e97-211">[平臺] 欄位會指出是否將原則套用至 Windows 裝置、Office 網頁版或全部的 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="09e97-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="09e97-212">進行選取之後，請選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="09e97-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="09e97-213">Office設定原則只支援以使用者為基礎的部署</span><span class="sxs-lookup"><span data-stu-id="09e97-213">Office Configuration Policies only support user-based deployment</span></span>