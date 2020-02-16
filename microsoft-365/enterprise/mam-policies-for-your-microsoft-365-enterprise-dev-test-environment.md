---
title: 裝置合規性原則，您的 Microsoft 365 企業版測試環境
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
description: 使用此測試實驗室指南來新增 Intune 裝置合規性原則，以您的 Microsoft 365 企業版測試環境。
ms.openlocfilehash: b0b8bd2d76a3959bbcca749545d9a16e50491d20
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066910"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0cd1a-103">裝置合規性原則，您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="0cd1a-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0cd1a-104">*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="0cd1a-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="0cd1a-105">透過本文中的指示，您可以新增 Windows 10 裝置和 Office 365 專業增強版的 Intune 裝置合規性原則至 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Office 365 ProPlus to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="0cd1a-107">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0cd1a-108">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="0cd1a-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0cd1a-109">如果您只想以具有最小需求的輕量型方式設定 MAM 原則，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0cd1a-110">如果您想要在模擬的企業中設定的 MAM 原則，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0cd1a-111">測試自動授權和群組成員資格不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0cd1a-112">它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="0cd1a-113">階段 2： 建立 Windows 10 裝置的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="0cd1a-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="0cd1a-114">在這個階段，您會建立 Windows 10 裝置的裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="0cd1a-115">移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 並登入您的 Office 365 測試實驗室訂閱，以全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="0cd1a-116">在瀏覽器的新] 索引標籤上開啟 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="0cd1a-117">從 Azure 入口網站] 索引標籤瀏覽器中，在 [搜尋] 方塊中，輸入**Intune** ，然後按一下 [ **Intune**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="0cd1a-118">如果您看到**您尚未啟用尚未裝置管理**訊息在**Microsoft Intune** ] 窗格中的，按一下它。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="0cd1a-119">在 [**行動裝置管理授權**] 窗格中，按一下 [ **Intune MDM 授權單位**，，然後按一下 [**選擇**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="0cd1a-120">重新整理您的瀏覽器索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="0cd1a-121">在左側瀏覽窗格中，按一下 [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="0cd1a-122">在 [**群組-所有群組**] 窗格中，按一下 [ **+ 新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="0cd1a-123">在 [**群組**] 窗格中，選取 [ **Office 365**或**安全性\*\*\*\*群組類型？**，在 [**名稱**] 中，輸入**受管理的 Windows 10 裝置使用者**在 [**成員資格類型**] 中，選取 [**已指派**，然後按一下 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="0cd1a-124">按一下 [ **Microsoft Intune**]。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="0cd1a-125">在**Microsoft Intune** ] 窗格中，在 [**快速工作**] 清單中，按一下 [**建立合規性政策**]。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="0cd1a-126">在 [**合規性政策設定檔**] 窗格中，按一下 [**建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="0cd1a-127">在 [**建立原則**] 窗格中，在 [**名稱**] 中，輸入**Windows 10**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="0cd1a-128">在 [**平台**，選取 [ **Windows 10 和更新版本**在**Windows 10 合規性原則**] 窗格中，按一下 [**確定]** ，然後按一下 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="0cd1a-129">按一下**合規性政策設定檔**、，然後按一下 [ **Windows 10**原則名稱。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="0cd1a-130">在**Windows 10** ] 窗格中，按一下 [**工作分派**，，然後按一下 [**選取要包含的群組**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="0cd1a-131">在 [**選取要加入群組**] 窗格中，按一下 [**管理 Windows 10 裝置使用者**] 群組中，，然後按一下 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="0cd1a-132">按一下 [**儲存**]，請按一下 [ **Microsoft Intune 概觀**，和 [**用戶端應用程式**在左側導覽窗格中。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="0cd1a-133">在**用戶端應用程式**] 窗格中，按一下 [**應用程式**，，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="0cd1a-134">在 [**新增應用程式**] 窗格中，選取**應用程式類型**]，然後選取 [ **Office 365 套件**] 下的**Windows 10** 。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="0cd1a-135">在 [**新增應用程式**] 窗格中，選取 [**應用程式套件資訊**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="0cd1a-136">在 [**應用程式套件資訊**] 窗格中，輸入**Office 365 專業增強版**在**套件名稱**] 和 [**套件描述**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-136">In the **App Suite Information** pane, type **Office 365 ProPlus** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="0cd1a-137">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-137">Click OK.</span></span>

19. <span data-ttu-id="0cd1a-138">在 [**新增應用程式**] 窗格中，選取 [**設定應用程式套件**，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="0cd1a-139">在 [**新增應用程式**] 窗格中，選取 [**應用程式套件設定**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="0cd1a-140">**更新通道**，選取**半年**，然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-140">For **Update Channel**, select **Semi-Annual**, and then click **OK**.</span></span>

22. <span data-ttu-id="0cd1a-141">在 [**新增應用程式**] 窗格中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="0cd1a-142">您現在可以在**Windows 10**裝置合規性原則中進行測試選取的應用程式和**受管理的 Windows 10 裝置的使用者**群組的成員裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="0cd1a-143">請注意，選取 [Office 365，因為群組類型會建立額外的資源。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="0cd1a-144">下一步</span><span class="sxs-lookup"><span data-stu-id="0cd1a-144">Next step</span></span>

<span data-ttu-id="0cd1a-145">瀏覽其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能及測試環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cd1a-146">請參閱</span><span class="sxs-lookup"><span data-stu-id="0cd1a-146">See also</span></span>

<span data-ttu-id="0cd1a-147">[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="0cd1a-148">註冊 iOS 和 Android 裝置，Microsoft 365 企業版測試環境中</span><span class="sxs-lookup"><span data-stu-id="0cd1a-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="0cd1a-149">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="0cd1a-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0cd1a-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="0cd1a-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
