---
title: 在您的 Microsoft 365 中註冊企業測試環境的 iOS/iPadOS 和 Android 裝置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 您可以使用這個測試實驗室指南，在 Microsoft 365 測試環境中註冊裝置，並以遠端方式管理這些裝置。
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367080"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e0255-103">在您的 Microsoft 365 中註冊企業測試環境的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="e0255-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e0255-104">*此測試實驗室指南僅可用於企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="e0255-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e0255-105">本文說明如何針對企業測試環境 Microsoft 365 中的 iOS/iPadOS 和 Android 裝置，註冊及測試基本行動裝置管理功能。</span><span class="sxs-lookup"><span data-stu-id="e0255-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="e0255-106">在測試環境中登記 iOS/iPadOS 和 Android 裝置包含三個階段：</span><span class="sxs-lookup"><span data-stu-id="e0255-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="e0255-107">階段1：組建您的企業測試環境 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0255-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e0255-108">階段2：註冊您的 iOS/iPadOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="e0255-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="e0255-109">階段3：從遠端系統管理您的 iOS/iPadOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="e0255-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="e0255-111">如需適用于企業測試實驗室指南堆疊的 Microsoft 365 中的所有文章的視覺對應，請移至[Microsoft 365 for enterprise test lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="e0255-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e0255-112">階段1：組建您的企業測試環境 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0255-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e0255-113">若要以輕量的方式登記 iOS/iPadOS 和 Android 裝置，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="e0255-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e0255-114">如果您想要在模擬的企業中登記 iOS/iPadOS 和 Android 裝置，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="e0255-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e0255-115">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="e0255-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e0255-116">它會以選項形式提供，以便您可以測試自動授權和群組成員資格，也可以在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="e0255-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="e0255-117">階段2：註冊您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="e0255-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="e0255-118">如果您正在考慮行動裝置管理 (MDM) 解決方案來管理裝置，您可以使用 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="e0255-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="e0255-119">使用任何 MDM 提供者（包括 Intune）時，裝置會「已註冊」。</span><span class="sxs-lookup"><span data-stu-id="e0255-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="e0255-120">當註冊時，他們會收到您設定的功能和設定。</span><span class="sxs-lookup"><span data-stu-id="e0255-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="e0255-121">在 Intune 中，有幾種方式可以註冊您的 iOS/iPadOS 和 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="e0255-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="e0255-122">您可以選擇最適合您組織的註冊選項。</span><span class="sxs-lookup"><span data-stu-id="e0255-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="e0255-123">如需詳細資訊和指導，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="e0255-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="e0255-124">部署指南：在 Microsoft Intune 中登記 iOS 和 iPadOS 裝置</span><span class="sxs-lookup"><span data-stu-id="e0255-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="e0255-125">部署指南：在 Microsoft Intune 中註冊 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="e0255-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="e0255-126">如果您已準備好使用 Intune 進行裝置管理，且想要提供一些指引，下列資訊可能會有所説明：</span><span class="sxs-lookup"><span data-stu-id="e0255-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="e0255-127">裝置管理概述</span><span class="sxs-lookup"><span data-stu-id="e0255-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="e0255-128">教程： Microsoft 端點管理員中的演練 Intune</span><span class="sxs-lookup"><span data-stu-id="e0255-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="e0255-129">部署指南：設定或移至 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e0255-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="e0255-130">階段3：從遠端系統管理您的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="e0255-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="e0255-131">Microsoft Intune 提供遠端鎖定和密碼重設功能。</span><span class="sxs-lookup"><span data-stu-id="e0255-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="e0255-132">如果有人喪失其裝置，您可以遠端鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="e0255-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="e0255-133">如果有人忘記其密碼，您可以從遠端重設密碼。</span><span class="sxs-lookup"><span data-stu-id="e0255-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="e0255-134">若要遠端鎖定 iOS/iPadOS 或 Android 裝置，請參閱 [使用 Intune 遠端鎖定裝置](/mem/intune/remote-actions/device-remote-lock)。</span><span class="sxs-lookup"><span data-stu-id="e0255-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="e0255-135">若要遠端重設密碼，請參閱 [reset or remove device 密碼 In Intune](/mem/intune/remote-actions/device-passcode-reset)。</span><span class="sxs-lookup"><span data-stu-id="e0255-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="e0255-136">如需其他可遠端執行的工作，請參閱 [可用的裝置動作](/mem/intune/remote-actions/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="e0255-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="e0255-137">下一步</span><span class="sxs-lookup"><span data-stu-id="e0255-137">Next step</span></span>

<span data-ttu-id="e0255-138">在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="e0255-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0255-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e0255-139">See Also</span></span>

[<span data-ttu-id="e0255-140">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="e0255-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="e0255-141">適用于企業測試環境 Microsoft 365 的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="e0255-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="e0255-142">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="e0255-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
