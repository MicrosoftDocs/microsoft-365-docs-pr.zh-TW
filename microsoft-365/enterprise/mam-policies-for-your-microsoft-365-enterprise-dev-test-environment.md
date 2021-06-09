---
title: 適用于企業測試環境 Microsoft 365 的裝置合規性原則
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，將 Intune 裝置相容性原則新增至您的企業測試環境 Microsoft 365。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367092"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="74d7e-103">適用于企業測試環境 Microsoft 365 的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="74d7e-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="74d7e-104">*此測試實驗室指南僅可用於企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="74d7e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="74d7e-105">本文說明如何為 Windows 10 裝置新增 Intune 裝置符合性原則，以及 Microsoft 365 Apps 企業版企業測試環境的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="74d7e-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="74d7e-106">新增 Intune 裝置規範原則包括兩個階段：</span><span class="sxs-lookup"><span data-stu-id="74d7e-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="74d7e-107">階段1：組建您的企業測試環境 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74d7e-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="74d7e-108">階段2：建立 Windows 10 裝置的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="74d7e-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="74d7e-110">如需適用于企業測試實驗室指南堆疊的 Microsoft 365 中的所有文章的視覺對應，請移至[Microsoft 365 for enterprise test lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="74d7e-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="74d7e-111">階段1：組建您的企業測試環境 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74d7e-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="74d7e-112">如果您想要以最小需求的輕量方式設定 MAM 原則，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="74d7e-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="74d7e-113">如果您想要在模擬的企業中設定 MAM 原則，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="74d7e-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="74d7e-114">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="74d7e-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="74d7e-115">它會以選項形式提供，以便您可以測試自動授權和群組成員資格，並在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="74d7e-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="74d7e-116">階段2：建立 Windows 10 裝置的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="74d7e-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="74d7e-117">在此階段中，您會為 Windows 10 裝置建立裝置符合性原則。</span><span class="sxs-lookup"><span data-stu-id="74d7e-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="74d7e-118">此階段使用 Microsoft Intune 和[Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)新增群組，並建立符合性原則。</span><span class="sxs-lookup"><span data-stu-id="74d7e-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="74d7e-119">移至[Microsoft 365 系統管理中心](https://admin.microsoft.com)，並以全域系統管理員帳戶登入您的 Microsoft 365 測試實驗室訂閱。</span><span class="sxs-lookup"><span data-stu-id="74d7e-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="74d7e-120">選取 [**端點管理員** 系統管理中心]。</span><span class="sxs-lookup"><span data-stu-id="74d7e-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="74d7e-121">[端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="74d7e-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="74d7e-122">如果已顯示類似 **您未啟用 [裝置管理** ] 的郵件，請選取 [Intune] 做為 MDM 授權。</span><span class="sxs-lookup"><span data-stu-id="74d7e-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="74d7e-123">如需特定步驟，請參閱 [Set the mobile device management 機關](/mem/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="74d7e-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="74d7e-124">端點管理員系統管理中心著重于裝置管理及應用程式管理。</span><span class="sxs-lookup"><span data-stu-id="74d7e-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="74d7e-125">如需此系統管理中心的導覽，請參閱 Microsoft 端點管理員中的[教學課程：逐步 Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。</span><span class="sxs-lookup"><span data-stu-id="74d7e-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="74d7e-126">在 **[群組**] 中，使用 **指派** 的成員資格類型，新增名為 **Managed Windows 10 裝置使用者** 的新 **Microsoft 365** 或 **安全** 組。</span><span class="sxs-lookup"><span data-stu-id="74d7e-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="74d7e-127">在後續步驟中，您會將您的相容性原則指派給此群組。</span><span class="sxs-lookup"><span data-stu-id="74d7e-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="74d7e-128">如需特定步驟，以及 **Microsoft 365** 或 **安全性** 群組的詳細資訊，請參閱 [新增群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="74d7e-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="74d7e-129">在 [**裝置**] 中，建立 Windows 10 合規性原則。</span><span class="sxs-lookup"><span data-stu-id="74d7e-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="74d7e-130">將此原則指派給您建立的 **受管理的 Windows 10 裝置使用者** 群組。</span><span class="sxs-lookup"><span data-stu-id="74d7e-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="74d7e-131">在您的原則中，您可以封鎖簡單密碼、需要防火牆、需要執行 Microsoft Defender 反惡意程式碼服務，等等。</span><span class="sxs-lookup"><span data-stu-id="74d7e-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="74d7e-132">規範原則通常會包含基本設定或每個裝置應該具備的最低基本設定。</span><span class="sxs-lookup"><span data-stu-id="74d7e-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="74d7e-133">如需特定步驟，以及您可以設定之可用之相容性設定的資訊，請參閱 [Use 合規性原則設定您管理之裝置的規則](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="74d7e-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="74d7e-134">完成時，您會有裝置規範原則，可用於測試 **Managed Windows 10 裝置使用者** 群組中的成員。</span><span class="sxs-lookup"><span data-stu-id="74d7e-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="74d7e-135">下一步</span><span class="sxs-lookup"><span data-stu-id="74d7e-135">Next step</span></span>

<span data-ttu-id="74d7e-136">在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="74d7e-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="74d7e-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="74d7e-137">See also</span></span>

<span data-ttu-id="74d7e-138">[適用于企業測試實驗室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="74d7e-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="74d7e-139">在您的 Microsoft 365 中註冊企業測試環境的 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="74d7e-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="74d7e-140">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="74d7e-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="74d7e-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="74d7e-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
