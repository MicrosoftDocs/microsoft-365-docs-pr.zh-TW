---
title: 使用 Autopilot 和 [註冊狀態] 頁面的初次執行體驗
description: 如何部署 ESP 體驗、使用的設定，以及設定變更
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e2340c7c0bf00165bb43740d3d095b5b0402fc0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126622"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="68218-104">使用 Autopilot 和 [註冊狀態] 頁面的初次執行體驗</span><span class="sxs-lookup"><span data-stu-id="68218-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="68218-105">Microsoft 受管理的桌面會使用 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) 和 Microsoft Intune 的 [註冊狀態頁面 (ESP) ](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) ，為您的使用者提供最佳的初次執行體驗。</span><span class="sxs-lookup"><span data-stu-id="68218-105">Microsoft Managed Desktop uses both [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="68218-106">[註冊狀態] 頁面目前是公開預覽。</span><span class="sxs-lookup"><span data-stu-id="68218-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="68218-107">初始部署</span><span class="sxs-lookup"><span data-stu-id="68218-107">Initial deployment</span></span>

<span data-ttu-id="68218-108">若要提供 ESP 經驗，您必須在 Microsoft Managed Desktop service 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="68218-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="68218-109">如需註冊的詳細資訊，請參閱 [自行註冊新裝置](../get-started/register-devices-self.md) 或 [取得協力廠商的步驟，以登錄裝置](../get-started/register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="68218-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="68218-110">當裝置向服務註冊後，您可以透過 [管理入口網站](https://portal.azure.com/)來歸檔支援憑證，以啟用 Microsoft 受管理桌面裝置的 ESP。</span><span class="sxs-lookup"><span data-stu-id="68218-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="68218-111">當您檔案票據時，我們會最初將 ESP 設定部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="68218-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="68218-112">將其部署到其他後續的部署群組 (會在每24小時) 一開始、快及寬。</span><span class="sxs-lookup"><span data-stu-id="68218-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="68218-113">若要暫停部署，請 file 另一個票證要求作業保留。</span><span class="sxs-lookup"><span data-stu-id="68218-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="68218-114">Autopilot 設定檔設定</span><span class="sxs-lookup"><span data-stu-id="68218-114">Autopilot profile settings</span></span>

<span data-ttu-id="68218-115">Microsoft 受管理的桌面會在用於使用者裝置的 Autopilot 設定檔中，使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="68218-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>


|<span data-ttu-id="68218-116">設定</span><span class="sxs-lookup"><span data-stu-id="68218-116">Setting</span></span>  |<span data-ttu-id="68218-117">值</span><span class="sxs-lookup"><span data-stu-id="68218-117">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="68218-118">部署模式</span><span class="sxs-lookup"><span data-stu-id="68218-118">Deployment mode</span></span> |  <span data-ttu-id="68218-119">使用者驅動</span><span class="sxs-lookup"><span data-stu-id="68218-119">User Driven</span></span>       |
|<span data-ttu-id="68218-120">加入 Azure AD as</span><span class="sxs-lookup"><span data-stu-id="68218-120">Join to Azure AD as</span></span>     |  <span data-ttu-id="68218-121">Azure AD 已加入</span><span class="sxs-lookup"><span data-stu-id="68218-121">Azure AD joined</span></span>       |
|<span data-ttu-id="68218-122">語言 (地區) </span><span class="sxs-lookup"><span data-stu-id="68218-122">Language (Region)</span></span>     | <span data-ttu-id="68218-123">作業系統預設值</span><span class="sxs-lookup"><span data-stu-id="68218-123">Operating system default</span></span>        |
|<span data-ttu-id="68218-124">自動設定鍵盤</span><span class="sxs-lookup"><span data-stu-id="68218-124">Automatically configure keyboard</span></span>     | <span data-ttu-id="68218-125">否</span><span class="sxs-lookup"><span data-stu-id="68218-125">No</span></span>        |
|<span data-ttu-id="68218-126">Microsoft 軟體授權條款</span><span class="sxs-lookup"><span data-stu-id="68218-126">Microsoft Software License Terms</span></span>     |  <span data-ttu-id="68218-127">隱藏</span><span class="sxs-lookup"><span data-stu-id="68218-127">Hide</span></span>       |
|<span data-ttu-id="68218-128">隱私權設定</span><span class="sxs-lookup"><span data-stu-id="68218-128">Privacy settings</span></span>     | <span data-ttu-id="68218-129">隱藏</span><span class="sxs-lookup"><span data-stu-id="68218-129">Hide</span></span>        |
|<span data-ttu-id="68218-130">隱藏變更帳戶選項</span><span class="sxs-lookup"><span data-stu-id="68218-130">Hide change account options</span></span>     | <span data-ttu-id="68218-131">顯示</span><span class="sxs-lookup"><span data-stu-id="68218-131">Show</span></span>        |
|<span data-ttu-id="68218-132">使用者帳戶類型</span><span class="sxs-lookup"><span data-stu-id="68218-132">User account type</span></span>     |  <span data-ttu-id="68218-133">標準版</span><span class="sxs-lookup"><span data-stu-id="68218-133">Standard</span></span>       |
|<span data-ttu-id="68218-134">允許白色 Glove OOBE</span><span class="sxs-lookup"><span data-stu-id="68218-134">Allow White Glove OOBE</span></span>     |  <span data-ttu-id="68218-135">是</span><span class="sxs-lookup"><span data-stu-id="68218-135">Yes</span></span>       |
|<span data-ttu-id="68218-136">套用裝置名稱範本</span><span class="sxs-lookup"><span data-stu-id="68218-136">Apply device name template</span></span>     | <span data-ttu-id="68218-137">是</span><span class="sxs-lookup"><span data-stu-id="68218-137">Yes</span></span>        |
|<span data-ttu-id="68218-138">輸入名稱</span><span class="sxs-lookup"><span data-stu-id="68218-138">Enter a name</span></span>     | <span data-ttu-id="68218-139">MMD-% RAND：11%</span><span class="sxs-lookup"><span data-stu-id="68218-139">MMD-%RAND:11%</span></span>        |

> [!NOTE]
> <span data-ttu-id="68218-140">[白色 glove] 布建只對已開啟 ESP 的客戶啟用時，Microsoft 受管理的電腦目前不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="68218-140">While "white glove" provisioning is only enabled for customers with ESP turned on, it is not currently supported in Microsoft Managed Desktop.</span></span>

## <a name="enrollment-status-page-settings"></a><span data-ttu-id="68218-141">註冊狀態頁面設定</span><span class="sxs-lookup"><span data-stu-id="68218-141">Enrollment Status Page settings</span></span>

<span data-ttu-id="68218-142">Microsoft 受管理的桌面會使用這些設定的註冊狀態頁面體驗：</span><span class="sxs-lookup"><span data-stu-id="68218-142">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>


|<span data-ttu-id="68218-143">設定</span><span class="sxs-lookup"><span data-stu-id="68218-143">Setting</span></span>  |<span data-ttu-id="68218-144">值</span><span class="sxs-lookup"><span data-stu-id="68218-144">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="68218-145">顯示應用程式與設定檔設定進度</span><span class="sxs-lookup"><span data-stu-id="68218-145">Show app and profile configuration progress</span></span>     | <span data-ttu-id="68218-146">是</span><span class="sxs-lookup"><span data-stu-id="68218-146">Yes</span></span>        |
|<span data-ttu-id="68218-147">安裝時間超過指定的分鐘數時顯示錯誤</span><span class="sxs-lookup"><span data-stu-id="68218-147">Show an error when installation takes longer than specified number of minutes</span></span>     |  <span data-ttu-id="68218-148">60</span><span class="sxs-lookup"><span data-stu-id="68218-148">60</span></span>       |
|<span data-ttu-id="68218-149">發生時間限制錯誤時顯示自訂訊息</span><span class="sxs-lookup"><span data-stu-id="68218-149">Show custom message when time limit error occurs</span></span>     |  <span data-ttu-id="68218-150">是</span><span class="sxs-lookup"><span data-stu-id="68218-150">Yes</span></span>       |
|<span data-ttu-id="68218-151">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="68218-151">Error message</span></span>     | <span data-ttu-id="68218-152">是的，設定您的裝置所需的時間會比預期的少。</span><span class="sxs-lookup"><span data-stu-id="68218-152">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="68218-153">按一下下方開始開始，我們會在背景中完成設定</span><span class="sxs-lookup"><span data-stu-id="68218-153">Click below to get started and we'll finish setting up in the background</span></span>        |
|<span data-ttu-id="68218-154">允許使用者收集有關安裝錯誤的記錄</span><span class="sxs-lookup"><span data-stu-id="68218-154">Allow users to collect logs about installation errors</span></span>     |  <span data-ttu-id="68218-155">是</span><span class="sxs-lookup"><span data-stu-id="68218-155">Yes</span></span>       |
|<span data-ttu-id="68218-156">僅顯示頁面至已布由全新體驗 (OOBE) 所布建的裝置</span><span class="sxs-lookup"><span data-stu-id="68218-156">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>     | <span data-ttu-id="68218-157">是</span><span class="sxs-lookup"><span data-stu-id="68218-157">Yes</span></span>        |
|<span data-ttu-id="68218-158">在安裝所有應用程式和設定檔之前封鎖裝置使用</span><span class="sxs-lookup"><span data-stu-id="68218-158">Block device use until all apps and profiles are installed</span></span>     |  <span data-ttu-id="68218-159">是</span><span class="sxs-lookup"><span data-stu-id="68218-159">Yes</span></span>       |
|<span data-ttu-id="68218-160">當安裝錯誤發生時，允許使用者重設裝置</span><span class="sxs-lookup"><span data-stu-id="68218-160">Allow users to reset device if installation error occurs</span></span>     |  <span data-ttu-id="68218-161">是</span><span class="sxs-lookup"><span data-stu-id="68218-161">Yes</span></span>       |
|<span data-ttu-id="68218-162">當安裝錯誤發生時，允許使用者使用裝置</span><span class="sxs-lookup"><span data-stu-id="68218-162">Allow users to use device if installation error occurs</span></span>     |  <span data-ttu-id="68218-163">是</span><span class="sxs-lookup"><span data-stu-id="68218-163">Yes</span></span>       |
|<span data-ttu-id="68218-164">在這些必要的應用程式被指派給使用者/裝置之前，封鎖裝置的使用</span><span class="sxs-lookup"><span data-stu-id="68218-164">Block device use until these required apps are installed if they are assigned to the user/device</span></span>     |  <span data-ttu-id="68218-165">新式工作場所-時間修正</span><span class="sxs-lookup"><span data-stu-id="68218-165">Modern Workplace - Time Correction</span></span>       |



<span data-ttu-id="68218-166">「註冊狀態」頁面經驗會出現三個階段。</span><span class="sxs-lookup"><span data-stu-id="68218-166">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="68218-167">如需詳細資訊，請參閱 [註冊狀態頁面追蹤資訊](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。</span><span class="sxs-lookup"><span data-stu-id="68218-167">For more, see [Enrollment Status Page tracking information](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="68218-168">其經驗如下：</span><span class="sxs-lookup"><span data-stu-id="68218-168">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="68218-169">Autopilot 體驗隨即啟動，且使用者輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="68218-169">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="68218-170">裝置會開啟 [註冊狀態] 頁面，並繼續進行裝置準備和裝置安裝階段。</span><span class="sxs-lookup"><span data-stu-id="68218-170">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="68218-171">因為停用使用者 ESP，所以第三個步驟 (帳戶設定) *目前已略過* Microsoft Managed Desktop configuration。</span><span class="sxs-lookup"><span data-stu-id="68218-171">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="68218-172">裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="68218-172">The device restarts.</span></span>
3. <span data-ttu-id="68218-173">重新開機之後，裝置會開啟與 **其他使用者** 的 Windows 登入頁面。</span><span class="sxs-lookup"><span data-stu-id="68218-173">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="68218-174">使用者再次輸入他們的認證，桌面隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="68218-174">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="68218-175">只有在 Windows 10 版本為1903或更新版本的情況時，才會在 ESP 期間部署 Win32 應用程式。</span><span class="sxs-lookup"><span data-stu-id="68218-175">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

![Autopilot 安裝程式的起始頁面，顯示「裝置準備」和「裝置設定」階段。](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a><span data-ttu-id="68218-177">白色 glove 布建</span><span class="sxs-lookup"><span data-stu-id="68218-177">White glove provisioning</span></span>

<span data-ttu-id="68218-178">Microsoft 受管理的桌面目前不支援 Windows Autopilot 的「白色 glove」功能。</span><span class="sxs-lookup"><span data-stu-id="68218-178">Microsoft Managed Desktop doesn't currently support the "white glove" feature of Windows Autopilot.</span></span>

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a><span data-ttu-id="68218-179">變更為 Autopilot 和註冊狀態頁面設定</span><span class="sxs-lookup"><span data-stu-id="68218-179">Change to Autopilot and Enrollment Status Page settings</span></span>

<span data-ttu-id="68218-180">如果 Microsoft 受管理的桌面所用的安裝程式不完全符合您的需求，您可以透過 [管理入口網站](https://portal.azure.com/)來提供支援票證。</span><span class="sxs-lookup"><span data-stu-id="68218-180">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can  file a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="68218-181">以下是您可能需要的設定類型的一些範例：</span><span class="sxs-lookup"><span data-stu-id="68218-181">Here are some examples of the types of configuration you might need:</span></span>

### <a name="autopilot-settings-change"></a><span data-ttu-id="68218-182">Autopilot 設定變更</span><span class="sxs-lookup"><span data-stu-id="68218-182">Autopilot settings change</span></span>

<span data-ttu-id="68218-183">您可能想要要求其他的裝置名稱範本。</span><span class="sxs-lookup"><span data-stu-id="68218-183">You might want to request a different device name template.</span></span> <span data-ttu-id="68218-184">不過，您無法變更部署模式、加入 Azure AD As、隱私權設定或使用者帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="68218-184">You cannot, however, change Deployment Mode, Join to Azure AD As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-settings-change"></a><span data-ttu-id="68218-185">註冊狀態頁面設定變更</span><span class="sxs-lookup"><span data-stu-id="68218-185">Enrollment Status Page settings change</span></span>

- <span data-ttu-id="68218-186">[當安裝時間超過指定的分鐘數] 設定時，會顯示 [錯誤] 的較長分鐘數。</span><span class="sxs-lookup"><span data-stu-id="68218-186">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="68218-187">顯示的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="68218-187">The error message displayed</span></span>
- <span data-ttu-id="68218-188">新增或移除「封鎖裝置使用之前，請先安裝這些必要的應用程式，否則會指派給使用者/裝置」設定中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="68218-188">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="68218-189">必要的應用程式</span><span class="sxs-lookup"><span data-stu-id="68218-189">Required applications</span></span>

- <span data-ttu-id="68218-190">您必須以新式的工作場所 *裝置群組* 測試、優先、快速及廣泛的目標為目標應用程式。</span><span class="sxs-lookup"><span data-stu-id="68218-190">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="68218-191">必須在「系統」內容中安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="68218-191">Applications must install in the "System" context.</span></span> <span data-ttu-id="68218-192">在指派給所有群組之前，請務必先使用 Test 群組中的 ESP 完成測試。</span><span class="sxs-lookup"><span data-stu-id="68218-192">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="68218-193">任何應用程式都不應該需要重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="68218-193">No applications should require the device to restart.</span></span> <span data-ttu-id="68218-194">建議您在建立應用程式套件時，將應用程式設定為「無任何作用」（如果需要重新開機）。</span><span class="sxs-lookup"><span data-stu-id="68218-194">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="68218-195">僅在使用者登入裝置時立即需要的核心應用程式中，才限制必要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="68218-195">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="68218-196">保留所有低於 1 GB 的應用程式總大小，以避免應用程式安裝階段超時。</span><span class="sxs-lookup"><span data-stu-id="68218-196">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="68218-197">理想狀況下，應用程式不應有任何相依性。</span><span class="sxs-lookup"><span data-stu-id="68218-197">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="68218-198">如果您的應用程式 *必須* 有相依性，請務必在 ESP 評估中進行設定、測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="68218-198">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="68218-199">不需要 "user" 內容的應用程式 (例如，小組) 可以包含在 ESP 的公開預覽中。</span><span class="sxs-lookup"><span data-stu-id="68218-199">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>
