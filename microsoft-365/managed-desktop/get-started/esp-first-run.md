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
ms.openlocfilehash: b65ad2a6ac1a9b9abe06cc108a980be21152bc86
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844955"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="663f7-104">使用 Autopilot 和 [註冊狀態] 頁面的初次執行體驗</span><span class="sxs-lookup"><span data-stu-id="663f7-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="663f7-105">Microsoft 受管理的電腦會同時使用[Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot)和 Microsoft Intune 的[註冊狀態頁面 (ESP) ](/windows/deployment/windows-autopilot/enrollment-status) ，為您的使用者提供最佳的初次執行體驗。</span><span class="sxs-lookup"><span data-stu-id="663f7-105">Microsoft Managed Desktop uses both [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="663f7-106">[註冊狀態] 頁面目前是公開預覽。</span><span class="sxs-lookup"><span data-stu-id="663f7-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="663f7-107">初始部署</span><span class="sxs-lookup"><span data-stu-id="663f7-107">Initial deployment</span></span>

<span data-ttu-id="663f7-108">若要提供 ESP 經驗，您必須在 Microsoft 受管理的電腦服務中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="663f7-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="663f7-109">如需註冊的詳細資訊，請參閱 [自行註冊新裝置](../get-started/register-devices-self.md) 或 [取得協力廠商的步驟，以登錄裝置](../get-started/register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="663f7-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="663f7-110">當裝置向服務註冊後，您可以透過[管理入口網站](https://portal.azure.com/)來歸檔支援票證，以啟用 Microsoft 受管理的電腦裝置的 ESP。</span><span class="sxs-lookup"><span data-stu-id="663f7-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="663f7-111">當您檔案票據時，我們會最初將 ESP 設定部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="663f7-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="663f7-112">將其部署到其他後續的部署群組 (會在每24小時) 一開始、快及寬。</span><span class="sxs-lookup"><span data-stu-id="663f7-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="663f7-113">若要暫停部署，請 file 另一個票證要求作業保留。</span><span class="sxs-lookup"><span data-stu-id="663f7-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="663f7-114">Autopilot 設定檔設定</span><span class="sxs-lookup"><span data-stu-id="663f7-114">Autopilot profile settings</span></span>

<span data-ttu-id="663f7-115">Microsoft 受管理的電腦會在用於使用者裝置的 Autopilot 設定檔中使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="663f7-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>

<br>

****

|<span data-ttu-id="663f7-116">設定</span><span class="sxs-lookup"><span data-stu-id="663f7-116">Setting</span></span>|<span data-ttu-id="663f7-117">值</span><span class="sxs-lookup"><span data-stu-id="663f7-117">Value</span></span>|
|---|---|
|<span data-ttu-id="663f7-118">部署模式</span><span class="sxs-lookup"><span data-stu-id="663f7-118">Deployment mode</span></span>|<span data-ttu-id="663f7-119">使用者驅動</span><span class="sxs-lookup"><span data-stu-id="663f7-119">User Driven</span></span>|
|<span data-ttu-id="663f7-120">加入 Azure AD as</span><span class="sxs-lookup"><span data-stu-id="663f7-120">Join to Azure AD as</span></span>|<span data-ttu-id="663f7-121">Azure AD 已加入</span><span class="sxs-lookup"><span data-stu-id="663f7-121">Azure AD joined</span></span>|
|<span data-ttu-id="663f7-122">語言 (地區) </span><span class="sxs-lookup"><span data-stu-id="663f7-122">Language (Region)</span></span>|<span data-ttu-id="663f7-123">使用者選取</span><span class="sxs-lookup"><span data-stu-id="663f7-123">User Select</span></span>|
|<span data-ttu-id="663f7-124">自動設定鍵盤</span><span class="sxs-lookup"><span data-stu-id="663f7-124">Automatically configure keyboard</span></span>|<span data-ttu-id="663f7-125">否</span><span class="sxs-lookup"><span data-stu-id="663f7-125">No</span></span>|
|<span data-ttu-id="663f7-126">Microsoft 軟體授權條款</span><span class="sxs-lookup"><span data-stu-id="663f7-126">Microsoft Software License Terms</span></span>|<span data-ttu-id="663f7-127">隱藏</span><span class="sxs-lookup"><span data-stu-id="663f7-127">Hide</span></span>|
|<span data-ttu-id="663f7-128">隱私權設定</span><span class="sxs-lookup"><span data-stu-id="663f7-128">Privacy settings</span></span>|<span data-ttu-id="663f7-129">隱藏</span><span class="sxs-lookup"><span data-stu-id="663f7-129">Hide</span></span>|
|<span data-ttu-id="663f7-130">隱藏變更帳戶選項</span><span class="sxs-lookup"><span data-stu-id="663f7-130">Hide change account options</span></span>|<span data-ttu-id="663f7-131">顯示</span><span class="sxs-lookup"><span data-stu-id="663f7-131">Show</span></span>|
|<span data-ttu-id="663f7-132">使用者帳戶類型</span><span class="sxs-lookup"><span data-stu-id="663f7-132">User account type</span></span>|<span data-ttu-id="663f7-133">標準版</span><span class="sxs-lookup"><span data-stu-id="663f7-133">Standard</span></span>|
|<span data-ttu-id="663f7-134">允許白色 Glove OOBE</span><span class="sxs-lookup"><span data-stu-id="663f7-134">Allow White Glove OOBE</span></span>|<span data-ttu-id="663f7-135">是</span><span class="sxs-lookup"><span data-stu-id="663f7-135">Yes</span></span>|
|<span data-ttu-id="663f7-136">套用裝置名稱範本</span><span class="sxs-lookup"><span data-stu-id="663f7-136">Apply device name template</span></span>|<span data-ttu-id="663f7-137">是</span><span class="sxs-lookup"><span data-stu-id="663f7-137">Yes</span></span>|
|<span data-ttu-id="663f7-138">輸入名稱</span><span class="sxs-lookup"><span data-stu-id="663f7-138">Enter a name</span></span>|<span data-ttu-id="663f7-139">MMD-% RAND：11%</span><span class="sxs-lookup"><span data-stu-id="663f7-139">MMD-%RAND:11%</span></span>|
|

## <a name="enrollment-status-page-settings"></a><span data-ttu-id="663f7-140">註冊狀態頁面設定</span><span class="sxs-lookup"><span data-stu-id="663f7-140">Enrollment Status Page settings</span></span>

<span data-ttu-id="663f7-141">Microsoft 受管理的電腦針對註冊狀態頁面體驗使用這些設定：</span><span class="sxs-lookup"><span data-stu-id="663f7-141">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>

<br>

****

|<span data-ttu-id="663f7-142">設定</span><span class="sxs-lookup"><span data-stu-id="663f7-142">Setting</span></span>|<span data-ttu-id="663f7-143">值</span><span class="sxs-lookup"><span data-stu-id="663f7-143">Value</span></span>|
|---|---|
|<span data-ttu-id="663f7-144">顯示應用程式與設定檔設定進度</span><span class="sxs-lookup"><span data-stu-id="663f7-144">Show app and profile configuration progress</span></span>|<span data-ttu-id="663f7-145">是</span><span class="sxs-lookup"><span data-stu-id="663f7-145">Yes</span></span>|
|<span data-ttu-id="663f7-146">安裝時間超過指定的分鐘數時顯示錯誤</span><span class="sxs-lookup"><span data-stu-id="663f7-146">Show an error when installation takes longer than specified number of minutes</span></span>|<span data-ttu-id="663f7-147">60</span><span class="sxs-lookup"><span data-stu-id="663f7-147">60</span></span>|
|<span data-ttu-id="663f7-148">發生時間限制錯誤時顯示自訂訊息</span><span class="sxs-lookup"><span data-stu-id="663f7-148">Show custom message when time limit error occurs</span></span>|<span data-ttu-id="663f7-149">是</span><span class="sxs-lookup"><span data-stu-id="663f7-149">Yes</span></span>|
|<span data-ttu-id="663f7-150">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="663f7-150">Error message</span></span>|<span data-ttu-id="663f7-151">是的，設定您的裝置所需的時間會比預期的少。</span><span class="sxs-lookup"><span data-stu-id="663f7-151">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="663f7-152">按一下下方開始開始，我們會在背景中完成設定</span><span class="sxs-lookup"><span data-stu-id="663f7-152">Click below to get started and we'll finish setting up in the background</span></span>|
|<span data-ttu-id="663f7-153">允許使用者收集有關安裝錯誤的記錄</span><span class="sxs-lookup"><span data-stu-id="663f7-153">Allow users to collect logs about installation errors</span></span>|<span data-ttu-id="663f7-154">是</span><span class="sxs-lookup"><span data-stu-id="663f7-154">Yes</span></span>|
|<span data-ttu-id="663f7-155">僅顯示頁面至已布由全新體驗 (OOBE) 所布建的裝置</span><span class="sxs-lookup"><span data-stu-id="663f7-155">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>|<span data-ttu-id="663f7-156">是</span><span class="sxs-lookup"><span data-stu-id="663f7-156">Yes</span></span>|
|<span data-ttu-id="663f7-157">在安裝所有應用程式和設定檔之前封鎖裝置使用</span><span class="sxs-lookup"><span data-stu-id="663f7-157">Block device use until all apps and profiles are installed</span></span>|<span data-ttu-id="663f7-158">是</span><span class="sxs-lookup"><span data-stu-id="663f7-158">Yes</span></span>|
|<span data-ttu-id="663f7-159">當安裝錯誤發生時，允許使用者重設裝置</span><span class="sxs-lookup"><span data-stu-id="663f7-159">Allow users to reset device if installation error occurs</span></span>|<span data-ttu-id="663f7-160">是</span><span class="sxs-lookup"><span data-stu-id="663f7-160">Yes</span></span>|
|<span data-ttu-id="663f7-161">當安裝錯誤發生時，允許使用者使用裝置</span><span class="sxs-lookup"><span data-stu-id="663f7-161">Allow users to use device if installation error occurs</span></span>|<span data-ttu-id="663f7-162">是</span><span class="sxs-lookup"><span data-stu-id="663f7-162">Yes</span></span>|
|<span data-ttu-id="663f7-163">在這些必要的應用程式被指派給使用者/裝置之前，封鎖裝置的使用</span><span class="sxs-lookup"><span data-stu-id="663f7-163">Block device use until these required apps are installed if they are assigned to the user/device</span></span>|<span data-ttu-id="663f7-164">新式工作場所-時間修正</span><span class="sxs-lookup"><span data-stu-id="663f7-164">Modern Workplace - Time Correction</span></span>|
|

<span data-ttu-id="663f7-165">「註冊狀態」頁面經驗會出現三個階段。</span><span class="sxs-lookup"><span data-stu-id="663f7-165">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="663f7-166">如需詳細資訊，請參閱 [註冊狀態頁面追蹤資訊](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。</span><span class="sxs-lookup"><span data-stu-id="663f7-166">For more, see [Enrollment Status Page tracking information](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="663f7-167">其經驗如下：</span><span class="sxs-lookup"><span data-stu-id="663f7-167">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="663f7-168">Autopilot 體驗隨即啟動，且使用者輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="663f7-168">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="663f7-169">裝置會開啟 [註冊狀態] 頁面，並繼續進行裝置準備和裝置安裝階段。</span><span class="sxs-lookup"><span data-stu-id="663f7-169">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="663f7-170">因為停用使用者 ESP，所以第三個步驟 (帳戶設定) *目前已略過* Microsoft 受管理的電腦設定。</span><span class="sxs-lookup"><span data-stu-id="663f7-170">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="663f7-171">裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="663f7-171">The device restarts.</span></span>
3. <span data-ttu-id="663f7-172">重新開機後，裝置會開啟與 **其他使用者** 的 Windows 登入頁面。</span><span class="sxs-lookup"><span data-stu-id="663f7-172">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="663f7-173">使用者再次輸入他們的認證，桌面隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="663f7-173">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="663f7-174">如果 Windows 10 版本為1903或更新版本，則只有在 ESP 中部署 Win32 應用程式。</span><span class="sxs-lookup"><span data-stu-id="663f7-174">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

![Autopilot 安裝程式的起始頁面，顯示「裝置準備」和「裝置設定」階段。](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="663f7-176">預先布建部署的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="663f7-176">Autopilot for pre-provisioned deployment</span></span>

> [!NOTE]
> <span data-ttu-id="663f7-177">Microsoft 受管理的電腦中預先布建部署的 Autopilot 目前是公開預覽。</span><span class="sxs-lookup"><span data-stu-id="663f7-177">Autopilot for pre-provisioned deployment in Microsoft Managed Desktop is currently in public preview.</span></span>

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="663f7-178">預先布建部署的額外必要條件 Autopilot</span><span class="sxs-lookup"><span data-stu-id="663f7-178">Additional prerequisites for Autopilot for pre-provisioned deployment</span></span>

- <span data-ttu-id="663f7-179">您必須已啟用 [註冊狀態] 頁面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="663f7-179">You must have Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="663f7-180">如需詳細資訊，請參閱 [初始部署](#initial-deployment)。</span><span class="sxs-lookup"><span data-stu-id="663f7-180">For more information, see [Initial deployment](#initial-deployment).</span></span>
- <span data-ttu-id="663f7-181">裝置必須具有有線網路連接。</span><span class="sxs-lookup"><span data-stu-id="663f7-181">Device must have a wired network connection.</span></span>
- <span data-ttu-id="663f7-182">如果您有在2020年8月之前使用 Microsoft 受管理的電腦入口網站註冊的裝置，請取消註冊，然後再次註冊。</span><span class="sxs-lookup"><span data-stu-id="663f7-182">If you have devices that were registered using the Microsoft Managed Desktop portal before August 2020, de-register and register them again.</span></span>
- <span data-ttu-id="663f7-183">裝置必須有一個原廠映像，其中包含11月2020累積更新[19H1/19H2 2020.11 c](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3)或[20H1 2020.11 c](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) （如有適當安裝），或必須以最新的 Microsoft 受管理的電腦影像為 reimaged。</span><span class="sxs-lookup"><span data-stu-id="663f7-183">Devices must must have a factory image that includes the November 2020 cumulative update [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) or [20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) as appropriate installed or must be reimaged with the latest Microsoft Managed Desktop image.</span></span>
- <span data-ttu-id="663f7-184">實體裝置必須支援 TPM 2.0 和裝置證明。</span><span class="sxs-lookup"><span data-stu-id="663f7-184">Physical devices must support TPM 2.0 and device attestation.</span></span> <span data-ttu-id="663f7-185">不支援虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="663f7-185">Virtual machines aren't supported.</span></span> <span data-ttu-id="663f7-186">預先布建程式使用 Windows Autopilot 自我部署功能，因此需要使用 TPM 2.0。</span><span class="sxs-lookup"><span data-stu-id="663f7-186">The pre-provisioning process uses Windows Autopilot self-deploying capabilities, so TPM 2.0 is required.</span></span> <span data-ttu-id="663f7-187">TPM 證明程式也需要存取一組 HTTPS URLs，這組 HTTPS 對於每個 TPM 提供者都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="663f7-187">The TPM attestation process also requires access to a set of HTTPS URLs that are unique for each TPM provider.</span></span> <span data-ttu-id="663f7-188">如需詳細資訊，請參閱[Windows Autopilot 網路需求](/mem/autopilot/networking-requirements#tpm)中的 Autopilot 自行部署模式和 Autopilot 預先布建部署的專案。</span><span class="sxs-lookup"><span data-stu-id="663f7-188">For more information, see the entry for Autopilot self-deploying mode and Autopilot pre-provisioned deployment in [Windows Autopilot networking requirements](/mem/autopilot/networking-requirements#tpm).</span></span>

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="663f7-189">預先布建部署的 Autopilot 中的事件順序</span><span class="sxs-lookup"><span data-stu-id="663f7-189">Sequence of events in Autopilot for pre-provisioned deployment</span></span>

1. <span data-ttu-id="663f7-190">必要時，IT 系統管理員 reimages 或重設裝置。</span><span class="sxs-lookup"><span data-stu-id="663f7-190">IT Admin reimages or resets the device if needed.</span></span>
2. <span data-ttu-id="663f7-191">IT 系統管理員會引導裝置、達到現成的體驗，然後按 Windows 鍵五次。</span><span class="sxs-lookup"><span data-stu-id="663f7-191">IT Admin boots the device, reaches the out-of-box-experience, and presses the Windows key five times.</span></span>
3. <span data-ttu-id="663f7-192">IT 系統管理員會選取 [Windows Autopilot 布建]，然後選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="663f7-192">IT Admin selects Windows Autopilot Provisioning and then selects **Continue**.</span></span> <span data-ttu-id="663f7-193">在 [Windows Autopilot 設定] 畫面上，會顯示裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="663f7-193">On the Windows Autopilot configuration screen, information will be displayed about the device.</span></span>
4. <span data-ttu-id="663f7-194">IT 系統管理員 **會選取 [** 布建]，以啟動布建處理常式。</span><span class="sxs-lookup"><span data-stu-id="663f7-194">IT admin selects **Provision** to start the provisioning process.</span></span>
5. <span data-ttu-id="663f7-195">裝置啟動 ESP，並透過裝置準備工作和設定階段進行。</span><span class="sxs-lookup"><span data-stu-id="663f7-195">Device starts ESP and goes through device preparation and setup phases.</span></span> <span data-ttu-id="663f7-196">在裝置設定階段中，您會視 ESP 設定檔) 的確切設定而定，顯示 (**的應用程式安裝 x** 。</span><span class="sxs-lookup"><span data-stu-id="663f7-196">During the device setup phase, you'll see **App installation x of x** displayed (depending on the exact configuration of the ESP profile).</span></span>
6. <span data-ttu-id="663f7-197">因為我們停用使用者 ESP，所以在 Microsoft 受管理的電腦設定中，目前已略過 [帳戶設定] 步驟。</span><span class="sxs-lookup"><span data-stu-id="663f7-197">The account setup step is currently skipped in the Microsoft Managed Desktop configuration, since we disable User ESP.</span></span>
7. <span data-ttu-id="663f7-198">裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="663f7-198">The device restarts.</span></span>

<span data-ttu-id="663f7-199">重新開機之後，裝置會顯示綠色的狀態畫面，並提供重新 **封裝** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="663f7-199">After it restarts, the device will show the green status screen, with a **Reseal** button.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="663f7-200">已知問題：</span><span class="sxs-lookup"><span data-stu-id="663f7-200">Known issues:</span></span>
>
> - <span data-ttu-id="663f7-201">在 Autopilot 預先布建的部署重新封裝功能之後，ESP 不會再次執行。</span><span class="sxs-lookup"><span data-stu-id="663f7-201">ESP does not run again after the Autopilot for pre-provisioned deployment reseal function.</span></span>
> - <span data-ttu-id="663f7-202">Autopilot 用於預先布建的部署時，未重新命名裝置。</span><span class="sxs-lookup"><span data-stu-id="663f7-202">Device are not being renamed by Autopilot for pre-provisioned deployment.</span></span> <span data-ttu-id="663f7-203">裝置只會在經過 ESP 使用者流程之後重新命名。</span><span class="sxs-lookup"><span data-stu-id="663f7-203">The device will only be renamed after going through the ESP user flow.</span></span>

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a><span data-ttu-id="663f7-204">變更為 Autopilot 和註冊狀態頁面設定</span><span class="sxs-lookup"><span data-stu-id="663f7-204">Change to Autopilot and Enrollment Status Page settings</span></span>

<span data-ttu-id="663f7-205">如果 Microsoft 受管理的電腦所使用的安裝程式不完全符合您的需求，您可以透過系統[管理入口網站](https://portal.azure.com/)來進行支援票證的檔。</span><span class="sxs-lookup"><span data-stu-id="663f7-205">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can  file a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="663f7-206">以下是您可能需要的設定類型的一些範例：</span><span class="sxs-lookup"><span data-stu-id="663f7-206">Here are some examples of the types of configuration you might need:</span></span>

### <a name="autopilot-settings-change"></a><span data-ttu-id="663f7-207">Autopilot 設定變更</span><span class="sxs-lookup"><span data-stu-id="663f7-207">Autopilot settings change</span></span>

<span data-ttu-id="663f7-208">您可能想要要求其他的裝置名稱範本。</span><span class="sxs-lookup"><span data-stu-id="663f7-208">You might want to request a different device name template.</span></span> <span data-ttu-id="663f7-209">不過，您無法變更部署模式、加入 Azure AD As、隱私權設定或使用者帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="663f7-209">You cannot, however, change Deployment Mode, Join to Azure AD As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-settings-change"></a><span data-ttu-id="663f7-210">註冊狀態頁面設定變更</span><span class="sxs-lookup"><span data-stu-id="663f7-210">Enrollment Status Page settings change</span></span>

- <span data-ttu-id="663f7-211">[當安裝時間超過指定的分鐘數] 設定時，會顯示 [錯誤] 的較長分鐘數。</span><span class="sxs-lookup"><span data-stu-id="663f7-211">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="663f7-212">顯示的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="663f7-212">The error message displayed</span></span>
- <span data-ttu-id="663f7-213">新增或移除「封鎖裝置使用之前，請先安裝這些必要的應用程式，否則會指派給使用者/裝置」設定中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="663f7-213">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="663f7-214">必要的應用程式</span><span class="sxs-lookup"><span data-stu-id="663f7-214">Required applications</span></span>

- <span data-ttu-id="663f7-215">您必須以新式的工作場所 *裝置群組* 測試、優先、快速及廣泛的目標為目標應用程式。</span><span class="sxs-lookup"><span data-stu-id="663f7-215">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="663f7-216">必須在「系統」內容中安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="663f7-216">Applications must install in the "System" context.</span></span> <span data-ttu-id="663f7-217">在指派給所有群組之前，請務必先使用 Test 群組中的 ESP 完成測試。</span><span class="sxs-lookup"><span data-stu-id="663f7-217">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="663f7-218">任何應用程式都不應該需要重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="663f7-218">No applications should require the device to restart.</span></span> <span data-ttu-id="663f7-219">建議您在建立應用程式套件時，將應用程式設定為「無任何作用」（如果需要重新開機）。</span><span class="sxs-lookup"><span data-stu-id="663f7-219">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="663f7-220">僅在使用者登入裝置時立即需要的核心應用程式中，才限制必要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="663f7-220">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="663f7-221">保留所有低於 1 GB 的應用程式總大小，以避免應用程式安裝階段超時。</span><span class="sxs-lookup"><span data-stu-id="663f7-221">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="663f7-222">理想狀況下，應用程式不應有任何相依性。</span><span class="sxs-lookup"><span data-stu-id="663f7-222">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="663f7-223">如果您的應用程式 *必須* 有相依性，請務必在 ESP 評估中進行設定、測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="663f7-223">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="663f7-224">不需要 "user" 內容的應用程式 (例如，Teams) 可以包含在 ESP 的公開預覽中。</span><span class="sxs-lookup"><span data-stu-id="663f7-224">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>
