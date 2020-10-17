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
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487693"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7af8f-103">在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="7af8f-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7af8f-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="7af8f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7af8f-105">本文說明如何針對企業版測試環境365中的 iOS 和 Android 裝置，註冊及測試基本行動裝置管理功能。</span><span class="sxs-lookup"><span data-stu-id="7af8f-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="7af8f-106">在測試環境中登記 iOS 和 Android 裝置包含三個階段：</span><span class="sxs-lookup"><span data-stu-id="7af8f-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="7af8f-107">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="7af8f-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="7af8f-108">階段2：註冊您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="7af8f-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="7af8f-109">階段3：從遠端系統管理您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="7af8f-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="7af8f-111">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="7af8f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7af8f-112">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="7af8f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7af8f-113">若要以輕量的方式註冊 iOS 和 Android 裝置，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="7af8f-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7af8f-114">如果您想要在模擬的企業中登記 iOS 和 Android 裝置，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="7af8f-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7af8f-115">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="7af8f-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7af8f-116">它會以選項形式提供，以便您可以測試自動授權和群組成員資格，也可以在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="7af8f-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="7af8f-117">階段2：註冊您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="7af8f-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="7af8f-118">首先，使用 [安裝和登入公司入口網站](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 中的指示，為您的測試環境自訂 Microsoft Intune 公司入口網站應用程式。</span><span class="sxs-lookup"><span data-stu-id="7af8f-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="7af8f-119">接下來，使用 [設定您公司資源的存取權](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 來註冊 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="7af8f-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="7af8f-120">接下來，使用在 [Intune 中註冊您的 android 裝置](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 中的指示來註冊 android 裝置。</span><span class="sxs-lookup"><span data-stu-id="7af8f-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="7af8f-121">階段3：從遠端系統管理您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="7af8f-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="7af8f-122">Microsoft Intune 提供遠端鎖定和密碼重設功能。</span><span class="sxs-lookup"><span data-stu-id="7af8f-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="7af8f-123">如果有人喪失其裝置，您可以遠端鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="7af8f-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="7af8f-124">如果有人忘記其密碼，您可以從遠端重設密碼。</span><span class="sxs-lookup"><span data-stu-id="7af8f-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="7af8f-125">若要遠端鎖定 iOS 或 Android 裝置：</span><span class="sxs-lookup"><span data-stu-id="7af8f-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="7af8f-126">[https://portal.azure.com](https://portal.azure.com)使用全域系統管理員帳戶的認證登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="7af8f-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="7af8f-127">在 Azure 入口網站中，于搜尋方塊中輸入 **intune** ，然後選取 [ **intune**]。</span><span class="sxs-lookup"><span data-stu-id="7af8f-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="7af8f-128">按一下 [ **裝置 > 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="7af8f-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="7af8f-129">在裝置清單中，選取 [iOS] 或 [Android] 裝置，然後選取 [ **遠端鎖定** ] 動作。</span><span class="sxs-lookup"><span data-stu-id="7af8f-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="7af8f-130">若要遠端重設密碼：</span><span class="sxs-lookup"><span data-stu-id="7af8f-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="7af8f-131">如有需要，以 [https://portal.azure.com](https://portal.azure.com) 全域系統管理員帳戶的認證登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="7af8f-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="7af8f-132">在 Azure 入口網站中，于搜尋方塊中輸入 **intune** ，然後選取 [ **intune**]。</span><span class="sxs-lookup"><span data-stu-id="7af8f-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="7af8f-133">選取 [**裝置**  >  **所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="7af8f-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="7af8f-134">從您管理的裝置清單中，選取 iOS 或 Android 裝置，選取 [ **...]更多**，然後選取 [ **移除密碼** 裝置遠端動作]。</span><span class="sxs-lookup"><span data-stu-id="7af8f-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="7af8f-135">如需其他實驗，請參閱 [可用的裝置動作](https://docs.microsoft.com/intune/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="7af8f-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="7af8f-136">下一步</span><span class="sxs-lookup"><span data-stu-id="7af8f-136">Next step</span></span>

<span data-ttu-id="7af8f-137">在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="7af8f-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7af8f-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7af8f-138">See Also</span></span>

[<span data-ttu-id="7af8f-139">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="7af8f-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="7af8f-140">適用于 Microsoft 365 企業版測試環境的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="7af8f-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="7af8f-141">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="7af8f-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
