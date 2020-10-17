---
title: 適用于 Microsoft 365 企業版測試環境的裝置合規性原則
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，將 Intune 裝置相容性原則新增至您的 Microsoft 365 企業版測試環境。
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487409"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a247c-103">適用于 Microsoft 365 企業版測試環境的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="a247c-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a247c-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="a247c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a247c-105">本文說明如何將 Windows 10 裝置和 Microsoft 365 應用程式的 Intune 裝置遵循原則，新增至 Microsoft 365 for enterprise test 環境。</span><span class="sxs-lookup"><span data-stu-id="a247c-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="a247c-106">新增 Intune 裝置規範原則包括兩個階段：</span><span class="sxs-lookup"><span data-stu-id="a247c-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="a247c-107">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="a247c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="a247c-108">階段2：建立 Windows 10 裝置的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="a247c-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a247c-110">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a247c-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a247c-111">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="a247c-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a247c-112">如果您想要以最小需求的輕量方式設定 MAM 原則，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="a247c-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a247c-113">如果您想要在模擬的企業中設定 MAM 原則，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a247c-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a247c-114">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="a247c-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a247c-115">它會以選項形式提供，以便您可以測試自動授權和群組成員資格，並在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="a247c-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="a247c-116">階段2：建立 Windows 10 裝置的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="a247c-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="a247c-117">在這個階段中，為 Windows 10 裝置建立裝置符合性原則。</span><span class="sxs-lookup"><span data-stu-id="a247c-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="a247c-118">移至 [microsoft 365 系統管理中心](https://admin.microsoft.com) ，並以全域系統管理員帳戶登入您的 microsoft 365 測試實驗室訂閱。</span><span class="sxs-lookup"><span data-stu-id="a247c-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="a247c-119">在您的瀏覽器的新索引標籤上，開啟 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="a247c-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="a247c-120">在 Azure 入口網站的 [搜尋] 方塊中，輸入 **intune**，然後選取 [ **intune**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="a247c-121">如果您看到 [ **Microsoft Intune** ] 窗格中**沒有啟用 [裝置管理**] 資訊，請選取它。</span><span class="sxs-lookup"><span data-stu-id="a247c-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="a247c-122">在 [行動 **裝置管理授權** ] 窗格中，選取 [ **Intune MDM 核證機關**]，然後選取 **[選擇**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="a247c-123">重新整理瀏覽器索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a247c-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="a247c-124">在左功能窗格中，選取 [ **群組**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="a247c-125">在 [ **群組-所有群組** ] 窗格中，選取 [ **+ 新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="a247c-126">在 [**群組**] 窗格中，選取 [ **Microsoft 365** ] 或 [**群組類型**的**安全性**？]，在 [**名稱**] 中輸入**受管理的 Windows 10 裝置使用者** **，選取 [** 在**成員資格類型**中**指派**]，然後選取 [</span><span class="sxs-lookup"><span data-stu-id="a247c-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="a247c-127">選取 [ **Microsoft Intune**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="a247c-128">在 [ **Microsoft Intune** ] 窗格的 [ **快速作業** ] 清單中，選取 [ **建立符合性原則**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="a247c-129">在 [ **合規性原則設定檔** ] 窗格中，選取 [ **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="a247c-130">在 [ **建立原則** ] 窗格的 [ **名稱**] 中，輸入 **Windows 10**。</span><span class="sxs-lookup"><span data-stu-id="a247c-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="a247c-131">在 [**平臺**] 中，選取 [windows **10 和更新版本**]，在 [ **windows 10 規範原則**] 窗格中選取 **[確定]** ，然後選取 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="a247c-132">選取 [ **相容性原則設定檔**]，然後選取 **Windows 10** 原則名稱。</span><span class="sxs-lookup"><span data-stu-id="a247c-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="a247c-133">在 [ **Windows 10** ] 窗格中，選取 [ **指派**]，然後選取 [ **選取要包含的群組**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="a247c-134">在 [ **選取要包含的群組** ] 窗格中，選取 [ **受管理的 Windows 10 裝置使用者** ] 群組，然後選取 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="a247c-135">選取 [ **儲存**]，選取 **[Microsoft Intune-簡介**]，然後選取左側導覽中的 [ **用戶端應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="a247c-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="a247c-136">在 [ **用戶端應用程式** ] 窗格中，選取 [ **應用程式**]，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="a247c-137">在 [**新增應用程式**] 窗格中，選取 [**應用程式類型**]，然後選取 [ **Microsoft 365 套件**] 底下的**Windows 10** 。</span><span class="sxs-lookup"><span data-stu-id="a247c-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="a247c-138">在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件資訊**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="a247c-139">在 [**應用程式套件資訊**] 窗格中，輸入 [適用于**套件名稱**和套件中的**Microsoft 365 應用程式**]**說明**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a247c-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="a247c-140">在 [ **新增應用程式** ] 窗格中，選取 [ **設定應用程式套件**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a247c-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="a247c-141">在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件設定**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="a247c-142">在 [ **更新通道**] 中，選取 [ **半年 Enterprise**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a247c-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="a247c-143">在 [ **新增應用程式** ] 窗格中，選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="a247c-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="a247c-144">現在，您已具備裝置符合性原則，可用於測試 **Windows 10** 裝置合規性原則中所選取的應用程式，以及 **受管理的 Windows 10 裝置使用者** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a247c-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="a247c-145">請注意，選取 [ **Microsoft 365** ] 做為「群組類型」會建立其他資源。</span><span class="sxs-lookup"><span data-stu-id="a247c-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="a247c-146">下一步</span><span class="sxs-lookup"><span data-stu-id="a247c-146">Next step</span></span>

<span data-ttu-id="a247c-147">在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="a247c-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a247c-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a247c-148">See also</span></span>

<span data-ttu-id="a247c-149">[適用于企業測試實驗室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="a247c-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="a247c-150">在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="a247c-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="a247c-151">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="a247c-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a247c-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="a247c-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
