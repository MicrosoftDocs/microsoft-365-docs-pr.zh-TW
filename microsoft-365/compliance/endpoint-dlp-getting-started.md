---
title: 開始使用 Microsoft 365 端點資料外洩防護
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 設定 Microsoft 365 端點資料外洩防護以監視檔案活動，並對這些端點的檔案實作保護動作。
ms.openlocfilehash: 0410d4d09354ca716c83a63da9c1fdd22eda8551
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114111"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="93637-103">開始使用端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="93637-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="93637-104">Microsoft 端點資料外洩防護 (端點 DLP) 是 Microsoft 365 資料外洩防護 (DLP) 套件的一部分，您可以使用這些功能探索並保護整個 Microsoft 365 服務的敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="93637-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="93637-105">如需所有 Microsoft DLP 供應項目的詳細資訊，請參閱[了解資料外洩防護](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="93637-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="93637-106">若要深入了解端點 DLP，請參閱 [深入了解端點資料外洩防護](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="93637-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="93637-107">Microsoft 端點 DLP 可讓您監視 Windows 10 裝置，並偵測敏感性項目使用和共用的時間。</span><span class="sxs-lookup"><span data-stu-id="93637-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="93637-108">這可提供您所需的可見度和控制，以確保它們得到正確的使用與保護，並協助防治可能導致威脅入侵的風險行為。</span><span class="sxs-lookup"><span data-stu-id="93637-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="93637-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="93637-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="93637-110">SKU/訂閱授權</span><span class="sxs-lookup"><span data-stu-id="93637-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="93637-111">開始使用端點 DLP 之前，您應先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何附加元件。</span><span class="sxs-lookup"><span data-stu-id="93637-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="93637-112">若要存取和使用端點 DLP 的功能，您必須擁有下列其中一個訂閱或附加元件。</span><span class="sxs-lookup"><span data-stu-id="93637-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="93637-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="93637-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="93637-114">Microsoft 365 A5 (教育版)</span><span class="sxs-lookup"><span data-stu-id="93637-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="93637-115">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="93637-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="93637-116">Microsoft 365 A5 合規性</span><span class="sxs-lookup"><span data-stu-id="93637-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="93637-117">Microsoft 365 E5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="93637-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="93637-118">Microsoft 365 A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="93637-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="93637-119">權限</span><span class="sxs-lookup"><span data-stu-id="93637-119">Permissions</span></span>

<span data-ttu-id="93637-120">若要啟用裝置管理，您使用的帳戶必須屬於下列任一角色的成員：</span><span class="sxs-lookup"><span data-stu-id="93637-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="93637-121">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-121">Global admin</span></span>
- <span data-ttu-id="93637-122">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-122">Security admin</span></span>
- <span data-ttu-id="93637-123">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-123">Compliance admin</span></span>

<span data-ttu-id="93637-124">如果想要使用自訂帳戶來查看 [裝置管理] 設定，則必須具有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="93637-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="93637-125">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-125">Global admin</span></span>
- <span data-ttu-id="93637-126">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-126">Compliance admin</span></span>
- <span data-ttu-id="93637-127">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-127">Compliance data admin</span></span>
- <span data-ttu-id="93637-128">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="93637-128">Global reader</span></span>

<span data-ttu-id="93637-129">如果想要使用自訂帳戶來存取上線/離線頁面，則必須具有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="93637-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="93637-130">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-130">Global admin</span></span>
- <span data-ttu-id="93637-131">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-131">Compliance admin</span></span>

<span data-ttu-id="93637-132">如果想要使用自訂帳戶來開啟/關閉裝置監控，則必須具有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="93637-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="93637-133">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-133">Global admin</span></span>
- <span data-ttu-id="93637-134">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-134">Compliance admin</span></span>

<span data-ttu-id="93637-135">可在 [[活動總管]](data-classification-activity-explorer.md)中檢視來自端點 DLP 的資料。</span><span class="sxs-lookup"><span data-stu-id="93637-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="93637-136">有四個角色可以將權限授與活動總管，您用來存取資料的帳戶必須是其中任一的成員。</span><span class="sxs-lookup"><span data-stu-id="93637-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="93637-137">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-137">Global admin</span></span>
- <span data-ttu-id="93637-138">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-138">Compliance admin</span></span>
- <span data-ttu-id="93637-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-139">Security admin</span></span>
- <span data-ttu-id="93637-140">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="93637-140">Compliance data admin</span></span>
- <span data-ttu-id="93637-141">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="93637-141">Global reader</span></span>
- <span data-ttu-id="93637-142">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="93637-142">Security reader</span></span>
- <span data-ttu-id="93637-143">報告讀取者</span><span class="sxs-lookup"><span data-stu-id="93637-143">Reports reader</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="93637-144">準備您的端點</span><span class="sxs-lookup"><span data-stu-id="93637-144">Prepare your endpoints</span></span>

<span data-ttu-id="93637-145">請確認您計畫部署端點 DLP 的 Windows 10 裝置符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="93637-145">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="93637-146">必須執行 Windows 10 x64 組建 1809 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="93637-146">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="93637-147">反惡意程式碼用戶端版本為 4.18.2009.7 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="93637-147">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="93637-148">開啟 Windows 安全性應用程式，選取 [設定] 圖示，然後選取 [關於]，以查看您目前的版本。</span><span class="sxs-lookup"><span data-stu-id="93637-148">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="93637-149">版本號碼會列在 [反惡意程式碼用戶端版本] 底下。</span><span class="sxs-lookup"><span data-stu-id="93637-149">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="93637-150">安裝 Windows Update KB4052623 以更新至最新的反惡意程式碼用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="93637-150">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="93637-151">Windows 安全性元件不需為作用中，您即可以不依賴 Windows 安全性狀態而執行端點 DLP，但必須啟用[即時防護與行為監視](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="93637-151">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="93637-152">已安裝下列 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="93637-152">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="93637-153">這些更新不是將裝置上線至端點 DLP 的先決條件，但包含重要問題的修正，因此必須先安裝，才能使用產品。</span><span class="sxs-lookup"><span data-stu-id="93637-153">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="93637-154">若為 Windows 10 1809 - KB4559003、KB4577069、KB4580390</span><span class="sxs-lookup"><span data-stu-id="93637-154">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="93637-155">若為 Windows 10 1903 或 1909 - KB4559004、KB4577062、KB4580386</span><span class="sxs-lookup"><span data-stu-id="93637-155">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="93637-156">若為 Windows 10 2004 - KB4568831、KB4577063</span><span class="sxs-lookup"><span data-stu-id="93637-156">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="93637-157">若為執行 Office 2016 的裝置 (不是任何其他 Office 版本) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="93637-157">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="93637-158">所有裝置都必須[加入 Azure Active Directory (Azure AD)](/azure/active-directory/devices/concept-azure-ad-join) 或加入混合式 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="93637-158">All devices must be [Azure Active Directory (Azure AD) joined](/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="93637-159">在端點裝置上安裝 Microsoft Chromium Edge 瀏覽器，以強制執行上傳至雲端活動的原則動作。</span><span class="sxs-lookup"><span data-stu-id="93637-159">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="93637-160">請參閱[下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。</span><span class="sxs-lookup"><span data-stu-id="93637-160">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="93637-161">如果您使用的是 Microsoft 365 Apps 版本 2004-2008 的每月企業頻道，則存在端點 DLP 對 Office 內容進行分類的已知問題，您需要更新到 2009 版或更高版本。</span><span class="sxs-lookup"><span data-stu-id="93637-161">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="93637-162">請參閲目前版本的 [Microsoft 365 Apps 的更新歷程記錄 (依日期列出)](/officeupdates/update-history-microsoft365-apps-by-date)。</span><span class="sxs-lookup"><span data-stu-id="93637-162">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="93637-163">深入了解有關此問題的更多資訊，請參閱 [2020 年目前通道版本的版本資訊](/officeupdates/current-channel#version-2010-october-27) 中的 Office 套件一節。</span><span class="sxs-lookup"><span data-stu-id="93637-163">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="93637-164">如果您有使用裝置 proxy 連線至網際網路的端點，請按照 [為端點 DLP 設定裝置 proxy 和網際網路連線設定](endpoint-dlp-configure-proxy.md) 中的程式。</span><span class="sxs-lookup"><span data-stu-id="93637-164">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="93637-165">將裝置上線至裝置管理</span><span class="sxs-lookup"><span data-stu-id="93637-165">Onboarding devices into device management</span></span>

<span data-ttu-id="93637-166">您必須先啟用裝置監控與上線端點，才能監視與防護裝置上的敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="93637-166">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="93637-167">這兩個動作都是在 Microsoft 365 合規性入口網站中完成。</span><span class="sxs-lookup"><span data-stu-id="93637-167">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="93637-168">當您想要將尚未上線的的裝置進行上線時，您將會下載適當的指令碼，並將它部署到這些裝置。</span><span class="sxs-lookup"><span data-stu-id="93637-168">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="93637-169">請按照[上線裝置程序](endpoint-dlp-getting-started.md#onboarding-devices)。</span><span class="sxs-lookup"><span data-stu-id="93637-169">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="93637-170">如果您的裝置已上線至 [適用於端點的 Microsoft Defender](/windows/security/threat-protection/)，這些裝置原本就會出現在 [受管理的裝置] 清單中。</span><span class="sxs-lookup"><span data-stu-id="93637-170">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="93637-171">請按照 [[裝置已上線至適用於端點的 Microsoft Defender] 的程序操作](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="93637-171">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="93637-172">上線裝置</span><span class="sxs-lookup"><span data-stu-id="93637-172">Onboarding devices</span></span>

<span data-ttu-id="93637-173">在此部署案例中，您將上線尚未上線的裝置，且您只要監視並保護來自 Windows 10 裝置上無意間共用的敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="93637-173">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="93637-174">開啟 [Microsoft 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="93637-174">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="93637-175">開啟 [合規性中心] 設定頁面，然後選擇 **[上線裝置]**。</span><span class="sxs-lookup"><span data-stu-id="93637-175">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93637-176">![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="93637-176">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="93637-177">通常啟用裝置上線需要 60 秒的時間，但請等候最多 30 分鐘的時間再與 Microsoft 支援服務聯絡以取得協助。</span><span class="sxs-lookup"><span data-stu-id="93637-177">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="93637-178">選擇 **[裝置管理]** 以開啟 **[裝置]** 清單。</span><span class="sxs-lookup"><span data-stu-id="93637-178">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="93637-179">在您的裝置上線之前，此清單會是空白。</span><span class="sxs-lookup"><span data-stu-id="93637-179">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="93637-180">選擇 **[上線]** 開始上線程序。</span><span class="sxs-lookup"><span data-stu-id="93637-180">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="93637-181">選擇您想要從 **[部署方法]** 清單中部署至這些其他裝置的方式，然後 **[下載套件]**。</span><span class="sxs-lookup"><span data-stu-id="93637-181">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93637-182">![部署方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="93637-182">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="93637-183">按照 [Windows 10 電腦的上線工具和方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的適當程序。</span><span class="sxs-lookup"><span data-stu-id="93637-183">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="93637-184">此連結會帶您前往一個登陸頁面，讓您存取適用於端點的 Microsoft Defender 且符合您在步驟 5 中選取的部署套件的程序：</span><span class="sxs-lookup"><span data-stu-id="93637-184">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="93637-185">使用群組原則上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-185">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="93637-186">使用 Microsoft Endpoint Configuration Manager 來上線 Windows 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-186">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="93637-187">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-187">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="93637-188">使用本機指令碼上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-188">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="93637-189">上線非永續性 Virtual Desktop Infrastructure (VDI) 電腦。</span><span class="sxs-lookup"><span data-stu-id="93637-189">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="93637-190">一旦完成且端點上線後，端點會顯示在裝置清單中，並開始向 [活動總管] 回報音訊活動記錄。</span><span class="sxs-lookup"><span data-stu-id="93637-190">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="93637-191">這項體驗屬於授權強制執行。</span><span class="sxs-lookup"><span data-stu-id="93637-191">This experience is under license enforcement.</span></span> <span data-ttu-id="93637-192">若無所需授權，資料將不會顯示或無法存取。</span><span class="sxs-lookup"><span data-stu-id="93637-192">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="93637-193">若裝置已上線至適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="93637-193">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="93637-194">在這種情況下，適用於端點的 Microsoft Defender 已經部署，且已有回報中的端點。</span><span class="sxs-lookup"><span data-stu-id="93637-194">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="93637-195">所有這些端點都會出現在 [受管理的裝置] 清單中。</span><span class="sxs-lookup"><span data-stu-id="93637-195">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="93637-196">您可以繼續使用 [[上線裝置程序]](endpoint-dlp-getting-started.md#onboarding-devices) 將新裝置上線至端點 DLP 中，以拓展涵蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="93637-196">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="93637-197">開啟 [Microsoft 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="93637-197">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="93637-198">開啟 [合規性中心] 設定頁面，然後選擇 **[啟用裝置監控]**。</span><span class="sxs-lookup"><span data-stu-id="93637-198">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="93637-199">選擇 **[裝置管理]** 以開啟 **[裝置]** 清單。</span><span class="sxs-lookup"><span data-stu-id="93637-199">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="93637-200">您應該會看到已向適用於端點的 Microsoft Defender 回報的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="93637-200">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93637-201">![裝置管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="93637-201">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="93637-202">如果您需要上線其他裝置，請選擇 **[上線]**。</span><span class="sxs-lookup"><span data-stu-id="93637-202">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="93637-203">選擇您想要從 **[部署方法]** 清單中部署至這些其他裝置的方式，然後 **[下載套件]**。</span><span class="sxs-lookup"><span data-stu-id="93637-203">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="93637-204">按照 [Windows 10 電腦的上線工具和方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的適當程序。</span><span class="sxs-lookup"><span data-stu-id="93637-204">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="93637-205">此連結會帶您前往一個登陸頁面，讓您存取適用於端點的 Microsoft Defender 且符合您在步驟 5 中選取的部署套件的程序：</span><span class="sxs-lookup"><span data-stu-id="93637-205">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="93637-206">使用群組原則上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-206">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="93637-207">使用 Microsoft Endpoint Configuration Manager 來上線 Windows 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-207">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="93637-208">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-208">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="93637-209">使用本機指令碼上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="93637-209">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="93637-210">上線非永續性 Virtual Desktop Infrastructure (VDI) 電腦。</span><span class="sxs-lookup"><span data-stu-id="93637-210">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="93637-211">一旦完成且端點上線後，端點會顯示在 **[裝置]** 表格下，並開始向 **[活動總管]** 回報音訊記錄。</span><span class="sxs-lookup"><span data-stu-id="93637-211">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="93637-212">這項體驗屬於授權強制執行。</span><span class="sxs-lookup"><span data-stu-id="93637-212">This experience is under license enforcement.</span></span> <span data-ttu-id="93637-213">若無所需授權，資料將不會顯示或無法存取。</span><span class="sxs-lookup"><span data-stu-id="93637-213">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="93637-214">在 DLP 警示管理儀表板中檢視端點 DLP 警示</span><span class="sxs-lookup"><span data-stu-id="93637-214">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="93637-215">在 Microsoft 365 合規性中心開啟 [資料外洩防護] 頁面，並選擇 [警示]。</span><span class="sxs-lookup"><span data-stu-id="93637-215">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="93637-216">請參閱[如何設定和檢視 DLP 原則的警示](dlp-configure-view-alerts-policies.md)中的程序，以檢視您端點 DLP 原則的警示。</span><span class="sxs-lookup"><span data-stu-id="93637-216">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="93637-217">檢視 [活動總管] 中的端點 DLP 資料</span><span class="sxs-lookup"><span data-stu-id="93637-217">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="93637-218">在 Microsoft 365 合規性中心開啟您網域的 [[資料分類] 頁面](https://compliance.microsoft.com/dataclassification?viewid=overview)，然後選擇 [活動總管]。</span><span class="sxs-lookup"><span data-stu-id="93637-218">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="93637-219">請參閱 [開始使用活動總管](data-classification-activity-explorer.md) 中的程序，以存取及篩選您端裝置的所有資料。</span><span class="sxs-lookup"><span data-stu-id="93637-219">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93637-220">![端點裝置的活動總管篩選](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="93637-220">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="93637-221">後續步驟</span><span class="sxs-lookup"><span data-stu-id="93637-221">Next steps</span></span>
<span data-ttu-id="93637-222">現在您擁有已上線的裝置，且可以在 [活動總管] 中檢視活動資料，您已準備好開始建立可保護您敏感性項目之 DLP 原則的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="93637-222">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="93637-223">使用端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="93637-223">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="93637-224">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93637-224">See also</span></span>

- [<span data-ttu-id="93637-225">深入了解端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="93637-225">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="93637-226">使用端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="93637-226">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="93637-227">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="93637-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="93637-228">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="93637-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="93637-229">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="93637-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="93637-230">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="93637-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- <span data-ttu-id="93637-231">[Windows 10 電腦上線的工具及方法 ](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="93637-231">[Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="93637-232">Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="93637-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="93637-233">加入 Azure AD 的裝置</span><span class="sxs-lookup"><span data-stu-id="93637-233">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- <span data-ttu-id="93637-234">[下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。</span><span class="sxs-lookup"><span data-stu-id="93637-234">[Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)</span></span>