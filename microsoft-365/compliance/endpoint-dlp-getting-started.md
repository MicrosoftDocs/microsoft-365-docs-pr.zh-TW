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
description: 設定 Microsoft 365 端點資料遺失防護以監視檔案活動，並對這些端點的文件實作保護動作。
ms.openlocfilehash: 6ba3b83d634f946f818890a732a83166f346162d
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073092"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="2374b-103">開始使用端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="2374b-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="2374b-p101">Microsoft 端點資料外洩防護 (端點 DLP) 是 Microsoft 365 資料外洩防護 (DLP) 套件的一部分，您可以使用這些功能探索並保護整個 Microsoft 365 服務的敏感性項目。如需所有 Microsoft DLP 供應項目的詳細資訊，請參閱[資料外洩防護概觀](data-loss-prevention-policies.md)。若要深入了解端點 DLP，請參閱[深入了解端點資料外洩防護](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="2374b-p101">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services. For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md). To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="2374b-p102">Microsoft 端點 DLP 可讓您監視 Windows 10 裝置，並偵測敏感性項目使用和共用的時機。這可提供您所需的可見度和控制，以確保它們得到正確的使用與保護，並協助防止可能導致威脅入侵的風險行為。</span><span class="sxs-lookup"><span data-stu-id="2374b-p102">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared. This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2374b-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="2374b-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="2374b-110">SKU/訂閱授權</span><span class="sxs-lookup"><span data-stu-id="2374b-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="2374b-p103">開始使用端點 DLP 之前，您應先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何附加元件。若要存取和使用端點 DLP 的功能，您必須擁有下列其中一個訂閱或附加元件。</span><span class="sxs-lookup"><span data-stu-id="2374b-p103">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons. To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="2374b-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2374b-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="2374b-114">Microsoft 365 A5 (教育版)</span><span class="sxs-lookup"><span data-stu-id="2374b-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="2374b-115">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="2374b-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="2374b-116">Microsoft 365 A5 合規性</span><span class="sxs-lookup"><span data-stu-id="2374b-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="2374b-117">Microsoft 365 E5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="2374b-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="2374b-118">Microsoft 365 A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="2374b-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="2374b-119">權限</span><span class="sxs-lookup"><span data-stu-id="2374b-119">Permissions</span></span>

<span data-ttu-id="2374b-120">若要啟用裝置管理，您使用的帳戶必須屬於下列任一角色的成員：</span><span class="sxs-lookup"><span data-stu-id="2374b-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="2374b-121">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-121">Global admin</span></span>
- <span data-ttu-id="2374b-122">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-122">Security admin</span></span>
- <span data-ttu-id="2374b-123">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-123">Compliance admin</span></span>

<span data-ttu-id="2374b-124">如果想要使用自訂帳戶來查看 [裝置管理] 設定，則必須具有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="2374b-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="2374b-125">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-125">Global admin</span></span>
- <span data-ttu-id="2374b-126">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-126">Compliance admin</span></span>
- <span data-ttu-id="2374b-127">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-127">Compliance data admin</span></span>
- <span data-ttu-id="2374b-128">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="2374b-128">Global reader</span></span>

<span data-ttu-id="2374b-129">如果想要使用自訂帳戶來存取上線/離線頁面，則必須具有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="2374b-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="2374b-130">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-130">Global admin</span></span>
- <span data-ttu-id="2374b-131">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-131">Compliance admin</span></span>

<span data-ttu-id="2374b-132">如果想要使用自訂帳戶來開啟/關閉裝置監控，則必須具有下列其中一種角色：</span><span class="sxs-lookup"><span data-stu-id="2374b-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="2374b-133">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-133">Global admin</span></span>
- <span data-ttu-id="2374b-134">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-134">Compliance admin</span></span>

<span data-ttu-id="2374b-p104">可在[活動總管](data-classification-activity-explorer.md)中檢視來自端點 DLP 的資料。有四個角色可以將權限授與活動總管，您用來存取資料的帳戶必須是其中任一的成員。</span><span class="sxs-lookup"><span data-stu-id="2374b-p104">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="2374b-137">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-137">Global admin</span></span>
- <span data-ttu-id="2374b-138">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-138">Compliance admin</span></span>
- <span data-ttu-id="2374b-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-139">Security admin</span></span>
- <span data-ttu-id="2374b-140">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="2374b-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="2374b-141">準備您的端點</span><span class="sxs-lookup"><span data-stu-id="2374b-141">Prepare your endpoints</span></span>

<span data-ttu-id="2374b-142">請確認您計畫部署端點 DLP 的 Windows 10 裝置符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="2374b-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="2374b-143">必須執行 Windows 10 x64 組建 1809 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="2374b-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="2374b-p105">反惡意程式碼用戶端版本為 4.18.2009.7 或更新版本。開啟 Windows 安全性應用程式，選取 [設定] 圖示，然後選取 [關於]，以查看您目前的版本。版本號碼會列在 [反惡意程式碼用戶端版本] 底下。安裝 Windows Update KB4052623 以更新至最新的反惡意程式碼用戶端版本。附註：Windows 安全性元件不需為作用中，您即可以不依賴 Windows 安全性狀態而執行端點 DLP。</span><span class="sxs-lookup"><span data-stu-id="2374b-p105">Antimalware Client Version is 4.18.2009.7 or newer. Check your current version by opening Windows Security app, select the Settings icon, and then select About. The version number is listed under Antimalware Client Version. Update to the latest Antimalware Client Version by installing Windows Update KB4052623. Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="2374b-p106">已安裝下列 Windows 更新。附註：這些更新不是將裝置上線至端點 DLP 的先決條件，但包含重要問題的修正，因此必須先安裝，才能使用產品。</span><span class="sxs-lookup"><span data-stu-id="2374b-p106">The following Windows Updates are installed. Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="2374b-151">若為 Windows 10 1809 - KB4559003、KB4577069、KB4580390</span><span class="sxs-lookup"><span data-stu-id="2374b-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="2374b-152">若為 Windows 10 1903 或 1909 - KB4559004、KB4577062、KB4580386</span><span class="sxs-lookup"><span data-stu-id="2374b-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="2374b-153">若為 Windows 10 2004 - KB4568831、KB4577063</span><span class="sxs-lookup"><span data-stu-id="2374b-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="2374b-154">若為執行 Office 2016 的裝置 (不是任何其他 Office 版本) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="2374b-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="2374b-155">所有裝置都必須[加入 Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) 或加入混合式 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="2374b-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="2374b-p107">在端點裝置上安裝 Microsoft Chromium Edge 瀏覽器，以強制執行上傳至雲端活動的原則動作。請參閱[下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。</span><span class="sxs-lookup"><span data-stu-id="2374b-p107">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity. See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="2374b-p108">如果您使用的是 Microsoft 365 Apps 版本 2004-2008 的每月企業頻道，則存在端點 DLP 對 Office 內容進行分類的已知問題，且您需要更新為版本 2009 或更新版本。請參閱 [Microsoft 365 Apps 的更新歷程記錄 (依日期列出)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) 以取得目前d 版本。若要深入了解有關此問題的更多資訊，請參閱 [2020 年目前通道版本的版本資訊](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27)中的 Office 套件一節。</span><span class="sxs-lookup"><span data-stu-id="2374b-p108">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later. See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions. To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="2374b-161">將裝置上線至裝置管理</span><span class="sxs-lookup"><span data-stu-id="2374b-161">Onboarding devices into device management</span></span>

<span data-ttu-id="2374b-p109">您必須先啟用裝置監控與上線端點，才能監視與防護裝置上的敏感性項目。這兩個動作都是在 Microsoft 365 合規性入口網站中完成。</span><span class="sxs-lookup"><span data-stu-id="2374b-p109">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device. Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="2374b-p110">當您想要將尚未上線的裝置進行上線時，您將會下載適當的指令碼，並將它部署到這些裝置。請遵循[上線裝置程序](endpoint-dlp-getting-started.md#onboarding-devices)。</span><span class="sxs-lookup"><span data-stu-id="2374b-p110">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices. Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="2374b-p111">如果您的裝置已上線至[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)，這些裝置就會出現在受管理的裝置清單中。請遵循[若裝置已上線至適用於端點的 Microsoft Defender](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint)。</span><span class="sxs-lookup"><span data-stu-id="2374b-p111">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list. Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="2374b-168">上線裝置</span><span class="sxs-lookup"><span data-stu-id="2374b-168">Onboarding devices</span></span>

<span data-ttu-id="2374b-169">在此部署案例中，您將上線尚未上線的裝置，且您只要監視並保護來自 Windows 10 裝置上無意間共用的敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="2374b-169">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="2374b-170">開啟 [Microsoft 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2374b-170">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="2374b-171">開啟 [合規性中心] 設定頁面，然後選擇 **[上線裝置]**。</span><span class="sxs-lookup"><span data-stu-id="2374b-171">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2374b-172">![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="2374b-172">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="2374b-173">通常啟用裝置上線需要 60 秒的時間，但請等候最多 30 分鐘的時間，再與 Microsoft 支援服務連絡以取得協助。</span><span class="sxs-lookup"><span data-stu-id="2374b-173">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="2374b-p112">選擇 [裝置管理 **]** 以開啟 [裝置 **]** 清單。在您的裝置上線之前，此清單會是空白。</span><span class="sxs-lookup"><span data-stu-id="2374b-p112">Choose **Device management** to open the **Devices** list. The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="2374b-176">選擇 [上線 **]** 開始上線程序。</span><span class="sxs-lookup"><span data-stu-id="2374b-176">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="2374b-177">選擇您想要從 **[部署方法]** 清單中部署至這些其他裝置的方式，然後 **[下載套件]**。</span><span class="sxs-lookup"><span data-stu-id="2374b-177">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2374b-178">![部署方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="2374b-178">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="2374b-p113">遵循 [Windows 10 電腦的上線工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的適當程序。此連結會將您帶到一個登陸頁面，讓您存取適用於端點的 Microsoft Defender 且符合您在步驟 5 中選取的部署套件的程序：</span><span class="sxs-lookup"><span data-stu-id="2374b-p113">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="2374b-181">使用群組原則上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-181">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="2374b-182">使用 Microsoft Endpoint Configuration Manager 來上線 Windows 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-182">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="2374b-183">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-183">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="2374b-184">使用本機指令碼上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-184">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="2374b-185">上線非永續性 Virtual Desktop Infrastructure (VDI) 電腦。</span><span class="sxs-lookup"><span data-stu-id="2374b-185">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="2374b-186">一旦完成且端點上線後，端點會顯示在裝置清單中，並開始向活動總管報告稽核活動記錄。</span><span class="sxs-lookup"><span data-stu-id="2374b-186">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="2374b-p114">這項體驗屬於授權強制執行。若無所需授權，資料將不會顯示或無法存取。</span><span class="sxs-lookup"><span data-stu-id="2374b-p114">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="2374b-189">若裝置已上線至適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2374b-189">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="2374b-p115">在這種情況下，適用於端點的 Microsoft Defender 已經部署，且已有回報中的端點。所有這些端點都會出現在 [受管理的裝置] 清單中。您可以繼續使用[上線裝置程序](endpoint-dlp-getting-started.md#onboarding-devices)，將新裝置上線至端點 DLP 中，以拓展涵蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="2374b-p115">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in. All these endpoints will appear in the managed devices list. You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="2374b-193">開啟 [Microsoft 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2374b-193">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="2374b-194">開啟合規性中心設定頁面，然後選擇 [啟用裝置監控 **]**。</span><span class="sxs-lookup"><span data-stu-id="2374b-194">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="2374b-p116">選擇 [裝置管理 **]** 以開啟 [裝置 **]** 清單。您應該會看到已向適用於端點的 Microsoft Defender 報告的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="2374b-p116">Choose **Device management** to open the **Devices** list. You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2374b-197">![裝置管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="2374b-197">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="2374b-198">如果您需要上線其他裝置，請選擇 **[上線]**。</span><span class="sxs-lookup"><span data-stu-id="2374b-198">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="2374b-199">選擇您想要從 [部署方法 **]** 清單中部署至這些其他裝置的方式，然後 [下載套件 **]**。</span><span class="sxs-lookup"><span data-stu-id="2374b-199">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="2374b-p117">遵循 [Windows 10 電腦的上線工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的適當程序。此連結會將您帶到一個登陸頁面，讓您存取適用於端點的 Microsoft Defender 且符合您在步驟 5 中選取的部署套件的程序：</span><span class="sxs-lookup"><span data-stu-id="2374b-p117">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="2374b-202">使用群組原則上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-202">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="2374b-203">使用 Microsoft Endpoint Configuration Manager 來上線 Windows 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-203">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="2374b-204">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-204">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="2374b-205">使用本機指令碼上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="2374b-205">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="2374b-206">上線非永續性 Virtual Desktop Infrastructure (VDI) 電腦。</span><span class="sxs-lookup"><span data-stu-id="2374b-206">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="2374b-207">一旦完成且端點上線後，端點會顯示在 [裝置 **]** 表格下，並開始向 [活動總管 **]** 報告稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="2374b-207">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="2374b-p118">這項體驗屬於授權強制執行。若無所需授權，資料將不會顯示或無法存取。</span><span class="sxs-lookup"><span data-stu-id="2374b-p118">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="2374b-210">在 DLP 警示管理儀表板中檢視端點 DLP 警示</span><span class="sxs-lookup"><span data-stu-id="2374b-210">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="2374b-211">在 Microsoft 365 合規性中心開啟 [資料外洩防護] 頁面，並選擇 [警示]。</span><span class="sxs-lookup"><span data-stu-id="2374b-211">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="2374b-212">請參閱[如何設定和檢視 DLP 原則的警示](dlp-configure-view-alerts-policies.md)中的程序，以檢視您端點 DLP 原則的警示。</span><span class="sxs-lookup"><span data-stu-id="2374b-212">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="2374b-213">在活動總管中檢視端點 DLP 資料</span><span class="sxs-lookup"><span data-stu-id="2374b-213">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="2374b-214">在 Microsoft 365 合規性中心開啟您網域的 [[資料分類] 頁面](https://compliance.microsoft.com/dataclassification?viewid=overview)，然後選擇 [活動總管]。</span><span class="sxs-lookup"><span data-stu-id="2374b-214">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="2374b-215">請參閱 [開始使用活動總管](data-classification-activity-explorer.md) (英文) 中的程序，以存取及篩選您端裝置的所有資料。</span><span class="sxs-lookup"><span data-stu-id="2374b-215">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2374b-216">![端點裝置的活動總管篩選](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="2374b-216">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="2374b-217">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2374b-217">Next steps</span></span>
<span data-ttu-id="2374b-218">現在您擁有已上線的裝置，且可以在 [活動總管] 中檢視活動資料，您已準備好開始建立可保護您敏感性項目之 DLP 原則的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="2374b-218">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="2374b-219">使用端點資料外洩防護 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="2374b-219">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="2374b-220">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2374b-220">See also</span></span>

- [<span data-ttu-id="2374b-221">深入了解端點資料外洩防護 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="2374b-221">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="2374b-222">使用端點資料外洩防護 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="2374b-222">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- <span data-ttu-id="2374b-223">[資料外洩防護概觀](data-loss-prevention-policies.md) (英文)</span><span class="sxs-lookup"><span data-stu-id="2374b-223">[Overview of data loss prevention](data-loss-prevention-policies.md)</span></span>
- [<span data-ttu-id="2374b-224">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2374b-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="2374b-225">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="2374b-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="2374b-226">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2374b-226">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- <span data-ttu-id="2374b-227">[Windows 10 電腦上線的工具及方法 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="2374b-227">[Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="2374b-228">Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="2374b-228">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="2374b-229">加入 Azure AD 的裝置</span><span class="sxs-lookup"><span data-stu-id="2374b-229">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- <span data-ttu-id="2374b-230">[下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。</span><span class="sxs-lookup"><span data-stu-id="2374b-230">[Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)</span></span>
