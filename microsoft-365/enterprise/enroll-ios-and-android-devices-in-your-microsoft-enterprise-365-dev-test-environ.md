---
title: 註冊 iOS 和 Android 裝置，Microsoft 365 企業版測試環境中
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此測試實驗室指南來註冊 Microsoft 365 測試環境中的裝置，並從遠端管理。
ms.openlocfilehash: e653b3e6cafb6ee2eb492709a2d060c7b92a6904
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281244"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3ccb9-103">註冊 iOS 和 Android 裝置，Microsoft 365 企業版測試環境中</span><span class="sxs-lookup"><span data-stu-id="3ccb9-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3ccb9-104">藉由遵循本文中提供的指示，您將能夠註冊，並在 Microsoft 365 企業版測試環境中測試 for iOS 和 Android 裝置的基本的行動裝置管理功能。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="3ccb9-106">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3ccb9-107">階段 1： 建置 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="3ccb9-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3ccb9-108">如果您只想以具有最小需求的輕量型方式註冊 iOS 和 Android 裝置，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3ccb9-109">如果您想要註冊 iOS 和 Android 裝置模擬的企業中，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3ccb9-110">測試自動授權和群組成員資格不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3ccb9-111">它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="3ccb9-112">階段 2： 註冊 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="3ccb9-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="3ccb9-113">首先，使用中的指示[安裝並登入公司入口網站應用程式](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)來自訂您的測試環境的 Microsoft Intune 公司入口網站應用程式。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="3ccb9-114">接下來，使用中[設定您的公司資源的存取權](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)的指示，註冊 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="3ccb9-115">接下來，使用中[註冊您的 Android 裝置，在 Intune 中](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)的指示，註冊 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="3ccb9-116">階段 3： 您的 iOS 和 Android 裝置從遠端管理</span><span class="sxs-lookup"><span data-stu-id="3ccb9-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="3ccb9-117">Microsoft Intune 提供遠端鎖定和密碼重設功能。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="3ccb9-118">如果有人遺失他們的裝置，您可以從遠端鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="3ccb9-119">如果有人忘記其密碼，您可以從遠端重。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="3ccb9-120">若要從遠端鎖定 iOS 或 Android 裝置︰</span><span class="sxs-lookup"><span data-stu-id="3ccb9-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="3ccb9-121">登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="3ccb9-122">按一下 [**所有服務**]，輸入**Intune**，，然後都按一下 [ **Intune**。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="3ccb9-123">按一下 [**裝置 > 所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="3ccb9-124">在裝置清單中，按一下 [iOS 或 Android 裝置，，，然後按一下 [**遠端鎖定**巨集指令。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="3ccb9-125">若要從遠端重設密碼︰</span><span class="sxs-lookup"><span data-stu-id="3ccb9-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="3ccb9-126">如有需要登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="3ccb9-127">按一下 [**所有服務**]，輸入**Intune**，，然後都按一下 [ **Intune**。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="3ccb9-128">按一下 [**裝置 > 所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="3ccb9-129">從裝置清單您可以管理、 按一下 iOS 或 Android 裝置，並選擇 **...]多個**。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="3ccb9-130">然後選擇 [**移除密碼**裝置遠端巨集指令。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="3ccb9-131">其他試驗，請參閱[可用的裝置的動作](https://docs.microsoft.com/intune/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="3ccb9-132">下一步</span><span class="sxs-lookup"><span data-stu-id="3ccb9-132">Next step</span></span>

<span data-ttu-id="3ccb9-133">瀏覽其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能及測試環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="3ccb9-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ccb9-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3ccb9-134">See Also</span></span>

[<span data-ttu-id="3ccb9-135">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="3ccb9-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="3ccb9-136">裝置合規性原則，您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="3ccb9-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="3ccb9-137">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="3ccb9-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3ccb9-138">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="3ccb9-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
