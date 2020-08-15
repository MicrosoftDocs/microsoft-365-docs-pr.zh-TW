---
title: 在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此測試實驗室指南，可在 Microsoft 365 測試環境中註冊裝置，並以遠端方式管理這些裝置。
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686007"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="20ade-103">在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="20ade-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="20ade-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="20ade-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="20ade-105">遵循本文所提供的指示，您可以在 Microsoft 365 for enterprise 測試環境中，為 iOS 和 Android 裝置登錄並測試基本行動裝置管理功能。</span><span class="sxs-lookup"><span data-stu-id="20ade-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="20ade-107">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="20ade-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="20ade-108">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="20ade-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="20ade-109">如果您只想以輕量的方式登記 iOS 和 Android 裝置，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="20ade-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="20ade-110">如果您想要在模擬的企業中登記 iOS 和 Android 裝置，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="20ade-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="20ade-111">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="20ade-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="20ade-112">這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="20ade-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="20ade-113">階段2：註冊您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="20ade-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="20ade-114">首先，使用 [安裝和登入公司入口網站](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 中的指示，為您的測試環境自訂 Microsoft Intune 公司入口網站應用程式。</span><span class="sxs-lookup"><span data-stu-id="20ade-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="20ade-115">接下來，使用 [設定您公司資源的存取權](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 來註冊 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="20ade-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="20ade-116">接下來，使用在 [Intune 中註冊您的 android 裝置](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 中的指示來註冊 android 裝置。</span><span class="sxs-lookup"><span data-stu-id="20ade-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="20ade-117">階段3：從遠端系統管理您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="20ade-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="20ade-118">Microsoft Intune 提供遠端鎖定和密碼重設功能。</span><span class="sxs-lookup"><span data-stu-id="20ade-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="20ade-119">如果有人遺失他們的裝置，您可以從遠端鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="20ade-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="20ade-120">如果有人忘記其密碼，您可以遠端重設密碼。</span><span class="sxs-lookup"><span data-stu-id="20ade-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="20ade-121">若要從遠端鎖定 iOS 或 Android 裝置：</span><span class="sxs-lookup"><span data-stu-id="20ade-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="20ade-122">[https://portal.azure.com](https://portal.azure.com)使用全域系統管理員帳戶的認證登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="20ade-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="20ade-123">在瀏覽器的 [Azure 入口網站] 索引標籤上，在搜尋方塊中輸入 **Intune** ，然後按一下 [ **intune**]。</span><span class="sxs-lookup"><span data-stu-id="20ade-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="20ade-124">按一下 [ **裝置 > 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="20ade-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="20ade-125">在裝置清單中，按一下 [iOS] 或 [Android] 裝置，然後按一下 [ **遠端鎖定** ] 動作。</span><span class="sxs-lookup"><span data-stu-id="20ade-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="20ade-126">若要從遠端重設密碼︰</span><span class="sxs-lookup"><span data-stu-id="20ade-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="20ade-127">如有需要，以 [https://portal.azure.com](https://portal.azure.com) 全域系統管理員帳戶的認證登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="20ade-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="20ade-128">在瀏覽器的 [Azure 入口網站] 索引標籤上，在搜尋方塊中輸入 **Intune** ，然後按一下 [ **intune**]。</span><span class="sxs-lookup"><span data-stu-id="20ade-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="20ade-129">按一下 [ **裝置 > 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="20ade-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="20ade-130">從您管理的裝置清單中，按一下 [iOS] 或 [Android] 裝置，然後選擇 [...]。 **其他**。</span><span class="sxs-lookup"><span data-stu-id="20ade-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="20ade-131">然後選擇 [ **移除密碼** 裝置遠端] 動作。</span><span class="sxs-lookup"><span data-stu-id="20ade-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="20ade-132">如需其他實驗，請參閱 [可用的裝置動作](https://docs.microsoft.com/intune/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="20ade-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="20ade-133">下一步</span><span class="sxs-lookup"><span data-stu-id="20ade-133">Next step</span></span>

<span data-ttu-id="20ade-134">在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="20ade-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="20ade-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="20ade-135">See Also</span></span>

[<span data-ttu-id="20ade-136">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="20ade-136">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="20ade-137">適用于 Microsoft 365 企業版測試環境的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="20ade-137">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="20ade-138">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="20ade-138">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

