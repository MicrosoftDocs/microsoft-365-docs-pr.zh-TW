---
title: Microsoft 365 企業版測試環境的 MAM 原則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 若要新增至 Microsoft 365 企業版的 Intune 行動應用程式管理 (MAM) 原則測試環境中使用此測試實驗室指南。
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866748"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bd37b-103">Microsoft 365 企業版測試環境的 MAM 原則</span><span class="sxs-lookup"><span data-stu-id="bd37b-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bd37b-104">本文中的指示，與您新增至 Microsoft 365 企業版的 Intune 行動應用程式管理 (MAM) 原則測試環境。</span><span class="sxs-lookup"><span data-stu-id="bd37b-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="bd37b-106">按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="bd37b-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bd37b-107">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="bd37b-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bd37b-108">如果您只想要設定 MAM 原則的最小需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="bd37b-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="bd37b-109">如果您想要模擬企業中設定 MAM 原則，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="bd37b-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd37b-p101">測試自動化授權和群組成員資格不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="bd37b-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="bd37b-112">階段 2：建立和部署 iOS 和 Android 的裝置的 MAM 原則</span><span class="sxs-lookup"><span data-stu-id="bd37b-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="bd37b-113">在此階段中，您會建立和部署兩個不同的 MAM 原則：一個適用於 iOS 裝置，另一個適用於 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="bd37b-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="bd37b-114">移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 並登入您的 Office 365 試用版訂閱以全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd37b-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="bd37b-115">在瀏覽器的新] 索引標籤上開啟 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="bd37b-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="bd37b-116">Azure 入口網站] 索引標籤上的 Internet Explorer 中，在功能窗格] 中按一下 [**所有服務**、 並輸入**Intune**，然後按一下都 [ **Intune**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="bd37b-p102">如果您看到**尚未啟用尚未裝置管理**訊息**Microsoft Intune** blade 上，按一下它。在**行動裝置管理授權**blade 中，按一下 [ **Intune MDM 授權**、 及 [**選擇**。重新整理您瀏覽器] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bd37b-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="bd37b-120">在左側瀏覽窗格中，按一下 [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd37b-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="bd37b-121">在**群組所有群組**blade 中，按一下 [ **+ 新群組**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="bd37b-122">在**群組**blade 中，選取 [ **Office 365** **群組類型？**、 在 [**名稱**] 中輸入 [**受管理的 iOS 裝置使用者\*\*\*\*成員資格類型**] 中選取 [**已指派**] 和 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="bd37b-123">關閉**群組**blade。</span><span class="sxs-lookup"><span data-stu-id="bd37b-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="bd37b-124">在**群組所有群組**blade 中，按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="bd37b-125">在**群組**blade 中，選取 [ **Office 365** **群組類型？**、 在 [**名稱**] 中輸入**受管理的 Android 裝置使用者\*\*\*\*成員資格類型**] 中選取 [**已指派**] 和 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="bd37b-126">關閉**群組所有群組**blade。</span><span class="sxs-lookup"><span data-stu-id="bd37b-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="bd37b-127">在**Intune** blade、**快速工作**清單中，按一下 [**建立規範原則**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="bd37b-128">在**規範原則設定檔**blade 中，按一下 [**建立原則**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="bd37b-p103">在**建立原則**blade，在 [**名稱**] 輸入**iOS**。在**平台**，選取**iOS**、 上**iOS 規範原則**blade 中，按一下 [**確定]** 和 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="bd37b-131">在**規範原則設定檔**blade 中，按一下 [**建立原則**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="bd37b-p104">在**建立原則**blade，在 [**名稱**] 中，輸入**Android**。在**平台**，選取**Android**、 在**Android 規範原則**blade 中，按一下 [**確定]** 和 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="bd37b-134">按一下 [**規範原則設定檔**blade、 **Android**原則名稱。</span><span class="sxs-lookup"><span data-stu-id="bd37b-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="bd37b-135">**Android-屬性**blade 的左方導覽，按一下 [**工作分派**，和 [**選取群組**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="bd37b-136">在 [**選取群組**blade、 [**受管理的 Android 裝置 users**群組，和 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="bd37b-137">按一下 [**儲存**]，然後關閉 [ **Android-工作分派**blade。</span><span class="sxs-lookup"><span data-stu-id="bd37b-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="bd37b-138">按一下 [**規範原則設定檔**blade、 **iOS**原則名稱。</span><span class="sxs-lookup"><span data-stu-id="bd37b-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="bd37b-139">**IOS-屬性**blade 的左方導覽，按一下 [**工作分派**，和 [**選取群組**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="bd37b-140">在 [**選取群組**blade、 [**受管理 iOS 裝置 users**群組，和 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="bd37b-141">按一下 [**儲存**]，然後關閉 [ **iOS-工作分派**blade。</span><span class="sxs-lookup"><span data-stu-id="bd37b-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="bd37b-142">關閉**規範原則設定檔**blade。</span><span class="sxs-lookup"><span data-stu-id="bd37b-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="bd37b-143">在**Intune** blade 中，按一下 [在左側導覽中的**管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="bd37b-144">在**行動應用程式**blade 中，按一下 [**應用程式**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="bd37b-145">在 [應用程式] 清單中按一下 [ **PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="bd37b-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="bd37b-p105">在**PowerPoint 概觀 （英文)** blade 中，按一下 [**指派 > 選取群組 > 受管理的 iOS 裝置 > 選取**。在 [**類型**] 選取 [**線上**] 和 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="bd37b-148">重複步驟 29 下列應用程式：</span><span class="sxs-lookup"><span data-stu-id="bd37b-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="bd37b-149">Outlook for Android</span><span class="sxs-lookup"><span data-stu-id="bd37b-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="bd37b-150">Word for iOS</span><span class="sxs-lookup"><span data-stu-id="bd37b-150">Word for iOS</span></span>
    
    - <span data-ttu-id="bd37b-151">iOS 版 Excel</span><span class="sxs-lookup"><span data-stu-id="bd37b-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="bd37b-152">iOS 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="bd37b-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="bd37b-153">iOS 版 Microsoft Dynamics CRM (適用於 iPad)</span><span class="sxs-lookup"><span data-stu-id="bd37b-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="bd37b-154">iOS 版 Microsoft Dynamics CRM (適用於 iPhone)</span><span class="sxs-lookup"><span data-stu-id="bd37b-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="bd37b-155">Android 版 Dynamics CRM (適用於手機)</span><span class="sxs-lookup"><span data-stu-id="bd37b-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="bd37b-156">Android 版 Dynamics CRM (適用於平板電腦)</span><span class="sxs-lookup"><span data-stu-id="bd37b-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="bd37b-157">Android 版 Excel</span><span class="sxs-lookup"><span data-stu-id="bd37b-157">Excel for Android</span></span>
    
    - <span data-ttu-id="bd37b-158">Android 版 Word</span><span class="sxs-lookup"><span data-stu-id="bd37b-158">Word for Android</span></span>
    
    - <span data-ttu-id="bd37b-159">iOS 版的 OneNote</span><span class="sxs-lookup"><span data-stu-id="bd37b-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="bd37b-160">關閉**行動應用程式-應用程式**blade。</span><span class="sxs-lookup"><span data-stu-id="bd37b-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="bd37b-161">在**行動應用程式**blade 中，按一下 [**應用程式保護原則**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="bd37b-162">在**應用程式保護原則**blade 中，按一下 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="bd37b-163">在 [**新增原則**blade 中，輸入**iOS**，和 [**選取所需的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="bd37b-164">在**應用程式**blade、 [ **PowerPoint**、 **IPhone 上的 Microsoft Dynamics CRM**、 **Excel**、 **IPhone 上的 Microsoft Dynamics CRM**、 **Word**、 **OneNote**、 及**Outlook**] 和 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="bd37b-165">按一下 [**新增原則**blade、 的 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="bd37b-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="bd37b-166">在**應用程式保護原則**blade 中，按一下 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="bd37b-167">在**新增原則**blade 中，輸入**Android**、 選取 [ **Android** **平台**，及 [**選取所需的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="bd37b-168">在**應用程式**blade 中，按一下 [ **PowerPoint**、**平板電腦的 Dynamics CRM**、 **Excel**、 **Word**、 **Outlook**和**Dynamics CRM 電話**、 及 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="bd37b-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="bd37b-169">按一下 [**新增原則**blade、 的 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="bd37b-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="bd37b-170">您現在有兩個 MAM 原則，一個適用於 iOS 裝置，另一個適用於 Android 裝置，並且都已準備好對選取的應用程式使用測試設定進行試驗。</span><span class="sxs-lookup"><span data-stu-id="bd37b-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="bd37b-171">下一步</span><span class="sxs-lookup"><span data-stu-id="bd37b-171">Next step</span></span>

<span data-ttu-id="bd37b-172">探索其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能與在測試環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="bd37b-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd37b-173">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bd37b-173">See also</span></span>

<span data-ttu-id="bd37b-174">[Microsoft 365 Enterprise 測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="bd37b-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="bd37b-175">在您的 Microsoft 365 企業版測試環境中註冊 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="bd37b-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="bd37b-176">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="bd37b-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bd37b-177">Enterprise 行動性 + 安全性 （EMS）</span><span class="sxs-lookup"><span data-stu-id="bd37b-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
