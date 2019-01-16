---
title: Microsoft 365 企業版的裝置規範遵守原則測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 若要新增至 Microsoft 365 企業版的 Intune 裝置規範遵守原則測試環境中使用此測試實驗室指南。
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866748"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f140a-103">Microsoft 365 企業版的裝置規範遵守原則測試環境</span><span class="sxs-lookup"><span data-stu-id="f140a-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f140a-104">使用本文中的指示，您可以將 Intune 裝置規範原則新增至 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="f140a-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f140a-106">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="f140a-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f140a-107">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="f140a-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f140a-108">如果您只想要設定 MAM 原則的最小需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="f140a-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f140a-109">如果您想要模擬企業中設定 MAM 原則，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="f140a-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f140a-p101">測試自動化授權和群組成員資格不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="f140a-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="f140a-112">階段 2： 建立 Windows 10 裝置的裝置規範原則</span><span class="sxs-lookup"><span data-stu-id="f140a-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="f140a-113">在此階段中，您會建立 Windows 10 裝置的裝置規範原則。</span><span class="sxs-lookup"><span data-stu-id="f140a-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="f140a-114">移至 [Office 入口網站 ([https://office.com](https://office.com)) 並登入您的 Office 365 試用版訂閱以全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="f140a-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="f140a-115">在瀏覽器的新] 索引標籤上開啟 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="f140a-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="f140a-116">在 Azure 的入口網站] 索引標籤中瀏覽器中，在功能窗格] 中按一下 [**所有服務**、 並輸入**Intune**，然後按一下都 [ **Intune**。</span><span class="sxs-lookup"><span data-stu-id="f140a-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="f140a-p102">如果您看到**尚未啟用尚未裝置管理**訊息**Microsoft Intune** blade 上，按一下它。在**行動裝置管理授權**blade 中，按一下 [ **Intune MDM 授權**、 及 [**選擇**。重新整理您瀏覽器] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f140a-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="f140a-120">在左側瀏覽窗格中，按一下 [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f140a-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="f140a-121">在**群組所有群組**blade 中，按一下 [ **+ 新群組**。</span><span class="sxs-lookup"><span data-stu-id="f140a-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="f140a-122">在**群組**blade 中，選取 [ **Office 365** **群組類型？**、 在 [**名稱**] 中輸入**受管理的 Windows 10 裝置的使用者**在**成員資格類型**] 中選取 [**已指派**] 和 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="f140a-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="f140a-123">關閉**群組**blade。</span><span class="sxs-lookup"><span data-stu-id="f140a-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="f140a-124">關閉**群組所有群組**blade。</span><span class="sxs-lookup"><span data-stu-id="f140a-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="f140a-125">在**Microsoft Intune** blade、**快速工作**清單中，按一下 [**建立規範原則**。</span><span class="sxs-lookup"><span data-stu-id="f140a-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="f140a-126">在**規範原則設定檔**blade 中，按一下 [**建立原則**。</span><span class="sxs-lookup"><span data-stu-id="f140a-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="f140a-p103">在**建立原則**blade，在 [**名稱**] 輸入**Windows 10**。**平台**，在選取**10 及更新版本的 Windows**、 在**Windows 10 規範原則**blade 中，按一下 [**確定]** 和 [**建立**。關閉**Windows 10** blade。</span><span class="sxs-lookup"><span data-stu-id="f140a-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="f140a-130">在**規範原則設定檔**blade 中，按一下 [ **Windows 10**原則名稱。</span><span class="sxs-lookup"><span data-stu-id="f140a-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="f140a-131">在**Windows 10** blade 中，按一下 [**工作分派**，及 [**選取要包含的群組**。</span><span class="sxs-lookup"><span data-stu-id="f140a-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="f140a-132">**選取要包含的群組**blade，在 [**受管理的 Windows 10 裝置 users**群組，和 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="f140a-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="f140a-133">按一下 [**儲存**]，然後關閉 [ **Windows 10-工作分派**blade。</span><span class="sxs-lookup"><span data-stu-id="f140a-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="f140a-134">關閉**規範原則設定檔**blade。</span><span class="sxs-lookup"><span data-stu-id="f140a-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="f140a-135">在**Microsoft Intune** blade 中，按一下 [在左側導覽中的**用戶端應用程式**。</span><span class="sxs-lookup"><span data-stu-id="f140a-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="f140a-136">在**用戶端應用程式**blade 中，按一下 [**應用程式**，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="f140a-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="f140a-137">在**新增應用程式**blade 中，選取**類型的應用程式**]，然後選取 [ **Office 365 套裝軟體** **Windows 10** 。</span><span class="sxs-lookup"><span data-stu-id="f140a-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="f140a-138">按一下 [**設定應用程式套件**，並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="f140a-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="f140a-139">按一下 [**應用程式套件資訊**、 輸入**套件名稱**] 中**的 Windows 10 Office 應用程式\*\*\*\*套件描述**] 中，在**Office 應用程式的 Windows 10** ，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="f140a-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="f140a-140">按一下 [**應用程式套件設定**、 選取**分號每年次**中**更新通道**，並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="f140a-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="f140a-141">在**新增 app** blade 中，按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="f140a-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="f140a-142">您現在有裝置規範原則中的**Windows 10**裝置規範原則測試所選的應用程式與**受管理的 Windows 10 裝置的使用者**群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f140a-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="f140a-143">下一步</span><span class="sxs-lookup"><span data-stu-id="f140a-143">Next step</span></span>

<span data-ttu-id="f140a-144">探索其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能與在測試環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="f140a-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f140a-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f140a-145">See also</span></span>

<span data-ttu-id="f140a-146">[Microsoft 365 Enterprise 測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="f140a-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="f140a-147">在您的 Microsoft 365 企業版測試環境中註冊 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="f140a-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="f140a-148">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="f140a-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f140a-149">Enterprise 行動性 + 安全性 （EMS）</span><span class="sxs-lookup"><span data-stu-id="f140a-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
