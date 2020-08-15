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
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686751"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="69ca9-103">適用于 Microsoft 365 企業版測試環境的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="69ca9-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="69ca9-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="69ca9-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="69ca9-105">透過本文中的指示，您可以將 Windows 10 裝置和 Microsoft 365 應用程式 enterprise 的 Intune 裝置符合性原則，新增至 Microsoft 365 for enterprise test 環境。</span><span class="sxs-lookup"><span data-stu-id="69ca9-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="69ca9-107">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="69ca9-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="69ca9-108">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="69ca9-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="69ca9-109">如果您只想以輕量的方式設定 MAM 原則，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="69ca9-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="69ca9-110">如果您想要在模擬的企業中設定 MAM 原則，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="69ca9-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="69ca9-111">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="69ca9-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="69ca9-112">這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="69ca9-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="69ca9-113">階段2：建立 Windows 10 裝置的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="69ca9-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="69ca9-114">在此階段中，您會為 Windows 10 裝置建立裝置符合性原則。</span><span class="sxs-lookup"><span data-stu-id="69ca9-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="69ca9-115">移至 [microsoft 365 系統管理中心](https://admin.microsoft.com) ，並以全域系統管理員帳戶登入您的 microsoft 365 測試實驗室訂閱。</span><span class="sxs-lookup"><span data-stu-id="69ca9-115">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="69ca9-116">在您的瀏覽器的新索引標籤上，開啟 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="69ca9-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="69ca9-117">從瀏覽器的 [Azure 入口網站] 索引標籤中，于搜尋方塊中輸入 **Intune** ，然後按一下 [ **intune**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="69ca9-118">如果您看到 [ **Microsoft Intune** ] 窗格中**沒有啟用 [裝置管理**] 的訊息，請按一下該窗格。</span><span class="sxs-lookup"><span data-stu-id="69ca9-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="69ca9-119">在 [行動 **裝置管理授權** ] 窗格中，按一下 [ **Intune MDM 核證機關**]，然後按一下 **[選擇**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="69ca9-120">重新整理瀏覽器索引標籤。</span><span class="sxs-lookup"><span data-stu-id="69ca9-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="69ca9-121">在左側瀏覽窗格中，按一下 [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69ca9-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="69ca9-122">在 [ **群組-所有群組** ] 窗格中，按一下 [ **+ 新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="69ca9-123">在 [**群組**] 窗格中，選取 [ **Microsoft 365** Or **Group type**的**安全性**]，並在 [**名稱**] 中輸入**Managed Windows 10 device users** ，選取 [在**成員資格類型**中**指派**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-123">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="69ca9-124">按一下 [ **Microsoft Intune**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="69ca9-125">在 [ **Microsoft Intune** ] 窗格的 [ **快速作業** ] 清單中，按一下 [ **建立符合性原則**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="69ca9-126">在 [ **合規性原則設定檔** ] 窗格中，按一下 [ **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="69ca9-127">在 [ **建立原則** ] 窗格的 [ **名稱**] 中，輸入 **Windows 10**。</span><span class="sxs-lookup"><span data-stu-id="69ca9-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="69ca9-128">在 [**平臺**] 中，選取 [ **windows 10 和更新版本**]，在**windows 10 符合性原則**窗格中按一下 **[確定]** ，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="69ca9-129">按一下 [ **合規性原則設定檔**]，然後按一下 **Windows 10** 原則名稱。</span><span class="sxs-lookup"><span data-stu-id="69ca9-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="69ca9-130">在 [ **Windows 10** ] 窗格中，按一下 [ **指派**]，然後按一下 [ **選取要包含的群組**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="69ca9-131">在 [ **選取要包含的群組** ] 窗格中，按一下 [ **受管理的 Windows 10 裝置使用者** ] 群組，然後按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="69ca9-132">按一下 [ **儲存**]，按一下 **[Microsoft Intune-簡介**]，然後按一下左側導覽中的 [ **用戶端應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="69ca9-133">在 [ **用戶端應用程式** ] 窗格中，按一下 [ **應用程式**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="69ca9-134">在 [**新增應用程式**] 窗格中，選取 [**應用程式類型**]，然後選取 [ **Microsoft 365 套件**] 底下的**Windows 10** 。</span><span class="sxs-lookup"><span data-stu-id="69ca9-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>

17. <span data-ttu-id="69ca9-135">在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件資訊**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="69ca9-136">在 [**應用程式套件資訊**] 窗格中，輸入「適用于**套件名稱**和套件的**Microsoft 365 應用程式**」**描述**。</span><span class="sxs-lookup"><span data-stu-id="69ca9-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="69ca9-137">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-137">Click OK.</span></span>

19. <span data-ttu-id="69ca9-138">在 [ **新增應用程式** ] 窗格中，選取 [ **設定應用程式套件**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="69ca9-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="69ca9-139">在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件設定**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="69ca9-140">在 [ **更新通道**] 中，選取 [ **半年 Enterprise**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="69ca9-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="69ca9-141">在 [ **新增應用程式** ] 窗格中，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="69ca9-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="69ca9-142">現在，您已具備裝置符合性原則，可用於測試 **Windows 10** 裝置合規性原則中所選取的應用程式，以及 **受管理的 Windows 10 裝置使用者** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="69ca9-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="69ca9-143">請注意，選取 [Microsoft 365] 做為群組類型將會建立其他資源。</span><span class="sxs-lookup"><span data-stu-id="69ca9-143">Please note that selecting Microsoft 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="69ca9-144">下一步</span><span class="sxs-lookup"><span data-stu-id="69ca9-144">Next step</span></span>

<span data-ttu-id="69ca9-145">在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="69ca9-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="69ca9-146">請參閱</span><span class="sxs-lookup"><span data-stu-id="69ca9-146">See also</span></span>

<span data-ttu-id="69ca9-147">[適用于企業測試實驗室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="69ca9-147">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="69ca9-148">在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="69ca9-148">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="69ca9-149">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="69ca9-149">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="69ca9-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="69ca9-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
