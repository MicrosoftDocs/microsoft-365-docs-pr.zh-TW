---
title: 使用 Microsoft 端點管理員上線
description: 瞭解如何使用 Microsoft 端點管理員對端點的 Microsoft Defender 進行上架
keywords: 上架、設定、部署、部署、端點管理員、Microsoft Defender for Endpoint、集合建立、端點偵測回應、下一代保護、攻擊面減少、Microsoft 端點管理員
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f3442528f6d9239219f0b4638f75758a055717de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842635"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="df475-104">使用 Microsoft 端點管理員上線</span><span class="sxs-lookup"><span data-stu-id="df475-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="df475-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="df475-105">**Applies to:**</span></span>
- [<span data-ttu-id="df475-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df475-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="df475-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df475-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="df475-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="df475-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="df475-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="df475-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="df475-110">本文是部署指南的一部分，可做為上架方法的範例。</span><span class="sxs-lookup"><span data-stu-id="df475-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="df475-111">在 [規劃](deployment-strategy.md) 主題中，有數種方法可提供給板載裝置給服務。</span><span class="sxs-lookup"><span data-stu-id="df475-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="df475-112">本主題涵蓋雲端原生架構。</span><span class="sxs-lookup"><span data-stu-id="df475-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="df475-113">![環境架構之雲端原生架構 ](images/cloud-native-architecture.png)
 *圖表* 的影像</span><span class="sxs-lookup"><span data-stu-id="df475-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="df475-114">當 Defender for Endpoint 支援各種端點和工具的上架時，本文並未涵蓋這類功能。</span><span class="sxs-lookup"><span data-stu-id="df475-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="df475-115">如需使用其他支援部署工具及方法的一般上架資訊，請參閱上 [架一覽](onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="df475-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="df475-116">[Microsoft 端點管理員](/mem/endpoint-manager-overview)是一種可統一數種服務的方案平臺。</span><span class="sxs-lookup"><span data-stu-id="df475-116">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="df475-117">它包含雲端式裝置管理的[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) 。</span><span class="sxs-lookup"><span data-stu-id="df475-117">It includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="df475-118">本主題指導使用者：</span><span class="sxs-lookup"><span data-stu-id="df475-118">This topic guides users in:</span></span>
- <span data-ttu-id="df475-119">步驟1：將裝置加入服務，方法是在 Microsoft 端點管理員中建立群組 (MEM) 指派設定</span><span class="sxs-lookup"><span data-stu-id="df475-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="df475-120">步驟2：使用 Microsoft 端點管理員設定用 Defender 做為端點功能</span><span class="sxs-lookup"><span data-stu-id="df475-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="df475-121">此上架指引會逐步引導您使用 Microsoft 端點管理員時，您必須採取下列基本步驟：</span><span class="sxs-lookup"><span data-stu-id="df475-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="df475-122">識別目標裝置或使用者</span><span class="sxs-lookup"><span data-stu-id="df475-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="df475-123"> (使用者或裝置建立 Azure Active Directory 組) </span><span class="sxs-lookup"><span data-stu-id="df475-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="df475-124">建立設定檔</span><span class="sxs-lookup"><span data-stu-id="df475-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="df475-125">在 Microsoft 端點管理員中，我們將引導您為每個功能建立個別的原則。</span><span class="sxs-lookup"><span data-stu-id="df475-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="df475-126">資源</span><span class="sxs-lookup"><span data-stu-id="df475-126">Resources</span></span>


<span data-ttu-id="df475-127">以下是您將在其餘程式中所需的連結：</span><span class="sxs-lookup"><span data-stu-id="df475-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="df475-128">MEM 入口網站</span><span class="sxs-lookup"><span data-stu-id="df475-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="df475-129">安全中心</span><span class="sxs-lookup"><span data-stu-id="df475-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="df475-130">Intune 安全性基準</span><span class="sxs-lookup"><span data-stu-id="df475-130">Intune Security baselines</span></span>](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="df475-131">如需 Microsoft 端點管理員的詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="df475-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="df475-132">Microsoft 端點管理員頁面</span><span class="sxs-lookup"><span data-stu-id="df475-132">Microsoft Endpoint Manager page</span></span>](/mem/)
- [<span data-ttu-id="df475-133">Intune 和 ConfigMgr 的結合的博客文章</span><span class="sxs-lookup"><span data-stu-id="df475-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="df475-134">有關 MEM 的簡介影片</span><span class="sxs-lookup"><span data-stu-id="df475-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="df475-135">步驟1：板載裝置，方法是在要指派設定的 MEM 中建立群組</span><span class="sxs-lookup"><span data-stu-id="df475-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="df475-136">識別目標裝置或使用者</span><span class="sxs-lookup"><span data-stu-id="df475-136">Identify target devices or users</span></span>
<span data-ttu-id="df475-137">在本節中，我們將建立測試群組，以將您的設定指派給您。</span><span class="sxs-lookup"><span data-stu-id="df475-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="df475-138">Intune 使用 Azure Active Directory (Azure AD) 群組來管理裝置和使用者。</span><span class="sxs-lookup"><span data-stu-id="df475-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="df475-139">作為 Intune 系統管理員，您可以設定群組以符合您的組織需求。</span><span class="sxs-lookup"><span data-stu-id="df475-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="df475-140">如需詳細資訊，請參閱 [新增群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="df475-140">For more information, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="df475-141">建立群組</span><span class="sxs-lookup"><span data-stu-id="df475-141">Create a group</span></span>

1.  <span data-ttu-id="df475-142">開啟 MEM 入口網站。</span><span class="sxs-lookup"><span data-stu-id="df475-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="df475-143">**> 新群組** 中開啟群組。</span><span class="sxs-lookup"><span data-stu-id="df475-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-144">![Microsoft 端點管理員 portal1 的影像](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="df475-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="df475-145">輸入詳細資料，並建立新的群組。</span><span class="sxs-lookup"><span data-stu-id="df475-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-146">![Microsoft 端點管理員 portal2 的影像](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="df475-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="df475-147">新增您的測試使用者或裝置。</span><span class="sxs-lookup"><span data-stu-id="df475-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="df475-148">從 [ **群組 > 所有群組** ] 窗格中，開啟新的群組。</span><span class="sxs-lookup"><span data-stu-id="df475-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="df475-149">Select  **members > Add members**。</span><span class="sxs-lookup"><span data-stu-id="df475-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="df475-150">尋找您的測試使用者或裝置，並加以選取。</span><span class="sxs-lookup"><span data-stu-id="df475-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-151">![Microsoft 端點管理員 portal3 的影像](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="df475-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="df475-152">您的測試群組現在有一個要測試的成員。</span><span class="sxs-lookup"><span data-stu-id="df475-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="df475-153">步驟2：建立設定原則以設定 Microsoft Defender for Endpoint 功能</span><span class="sxs-lookup"><span data-stu-id="df475-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="df475-154">在下一節中，您將建立許多設定原則。</span><span class="sxs-lookup"><span data-stu-id="df475-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="df475-155">首先是設定原則，以選取哪些使用者或裝置群組將會架至 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="df475-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="df475-156">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="df475-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="df475-157">接著，您會建立數種不同類型的端點安全性原則，以繼續執行：</span><span class="sxs-lookup"><span data-stu-id="df475-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="df475-158">新一代保護</span><span class="sxs-lookup"><span data-stu-id="df475-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="df475-159">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="df475-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="df475-160">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="df475-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="df475-161">開啟 MEM 入口網站。</span><span class="sxs-lookup"><span data-stu-id="df475-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="df475-162">流覽至 **端點安全性 > 端點偵測和回應**。</span><span class="sxs-lookup"><span data-stu-id="df475-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="df475-163">按一下 [ **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="df475-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-164">![Microsoft 端點管理員 portal4 的影像](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="df475-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="df475-165">在 [平臺] 底下，**選取 [Windows 10 和更新版本]。 > 建立設定檔端點偵測和回應**。</span><span class="sxs-lookup"><span data-stu-id="df475-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="df475-166">輸入名稱和描述，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-167">![Microsoft 端點管理員 portal5 的影像](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="df475-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="df475-168">選取 [必要時設定]，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-169">![Microsoft 端點管理員 portal6 的影像](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="df475-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="df475-170">在此範例中，這已自動填入，因為已將 Defender 的 Endpoint 已整合至已與 Intune 整合。</span><span class="sxs-lookup"><span data-stu-id="df475-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="df475-171">如需整合的詳細資訊，請參閱 [在 Intune 中啟用 Microsoft Defender For Endpoint](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)。</span><span class="sxs-lookup"><span data-stu-id="df475-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="df475-172">下列圖像是 Microsoft Defender for Endpoint 未與 Intune 整合時所看到之內容的範例：</span><span class="sxs-lookup"><span data-stu-id="df475-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Microsoft 端點管理員 portal7 的影像](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="df475-174">必要時新增範圍標籤，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-175">![Microsoft 端點管理員 portal8 的影像](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="df475-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="df475-176">按一下 [ **選取要包含的群組** ] 並選擇您的群組，然後選取  **[下一步]**，以新增測試群組。</span><span class="sxs-lookup"><span data-stu-id="df475-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-177">![Microsoft 端點管理員 portal9 的影像](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="df475-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="df475-178">複查並接受，然後選取 [  **建立**]。</span><span class="sxs-lookup"><span data-stu-id="df475-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-179">![Microsoft 端點管理員 portal10 的影像](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="df475-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="df475-180">您可以查看已完成的原則。</span><span class="sxs-lookup"><span data-stu-id="df475-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-181">![Microsoft 端點管理員 portal11 的影像](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="df475-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="df475-182">新一代保護</span><span class="sxs-lookup"><span data-stu-id="df475-182">Next-generation protection</span></span>

1.  <span data-ttu-id="df475-183">開啟 MEM 入口網站。</span><span class="sxs-lookup"><span data-stu-id="df475-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="df475-184">流覽至 **端點安全性 > 防病毒 > 建立原則**。</span><span class="sxs-lookup"><span data-stu-id="df475-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-185">![Microsoft 端點管理員 portal12 的影像](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="df475-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="df475-186">選取 [**平臺-Windows 10 和更新版本-Windows 和設定檔– Microsoft Defender 防毒軟體 > 建立**]。</span><span class="sxs-lookup"><span data-stu-id="df475-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="df475-187">輸入名稱和描述，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-188">![Microsoft 端點管理員 portal13 的影像](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="df475-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="df475-189">在 [設定 **設定] 頁面** 中，設定 Microsoft Defender 防毒軟體所需的設定 (Cloud Protection，排除，Real-Time 保護和修正) 。</span><span class="sxs-lookup"><span data-stu-id="df475-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-190">![Microsoft 端點管理員 portal14 的影像](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="df475-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="df475-191">必要時新增範圍標籤，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-192">![Microsoft 端點管理員 portal15 的影像](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="df475-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="df475-193">選取要包含的群組、指派至您的測試群組，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-194">![Microsoft 端點管理員 portal16 的影像](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="df475-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="df475-195">檢查並建立，然後選取 [  **建立**]。</span><span class="sxs-lookup"><span data-stu-id="df475-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-196">![Microsoft 端點管理員 portal17 的影像](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="df475-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="df475-197">您將會看到您建立的設定原則。</span><span class="sxs-lookup"><span data-stu-id="df475-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-198">![Microsoft 端點管理員 portal18 的影像](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="df475-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="df475-199">攻擊面減少–攻擊面減少的原則</span><span class="sxs-lookup"><span data-stu-id="df475-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="df475-200">開啟 MEM 入口網站。</span><span class="sxs-lookup"><span data-stu-id="df475-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="df475-201">流覽至 **端點安全性 > 攻擊面降減**。</span><span class="sxs-lookup"><span data-stu-id="df475-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="df475-202">選取 [  **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="df475-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="df475-203">選取 [**平臺-Windows 10 和更新版本–設定檔-> 建立的攻擊面降減規則**。</span><span class="sxs-lookup"><span data-stu-id="df475-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-204">![Microsoft 端點管理員 portal19 的影像](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="df475-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="df475-205">輸入名稱和描述，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-206">![Microsoft 端點管理員 portal20 的影像](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="df475-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="df475-207">在 [ **設定設定] 頁面** 上：設定攻擊面降低規則所需的設定，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df475-208">我們將設定所有攻擊面降減規則，以進行審核。</span><span class="sxs-lookup"><span data-stu-id="df475-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="df475-209">如需詳細資訊，請參閱 [攻擊面降減規則](attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="df475-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-210">![Microsoft 端點管理員 portal21 的影像](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="df475-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="df475-211">視需要新增範圍標記，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-212">![Microsoft 端點管理員 portal22 的影像](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="df475-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="df475-213">選取 [要包含的群組並指派給 test group]，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-214">![Microsoft 端點管理員 portal23 的影像](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="df475-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="df475-215">查看詳細資料，然後選取 [  **建立**]。</span><span class="sxs-lookup"><span data-stu-id="df475-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-216">![Microsoft 端點管理員 portal24 的影像](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="df475-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="df475-217">查看原則。</span><span class="sxs-lookup"><span data-stu-id="df475-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-218">![Microsoft 端點管理員 portal25 的影像](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="df475-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="df475-219">攻擊面減少– Web 保護</span><span class="sxs-lookup"><span data-stu-id="df475-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="df475-220">開啟 MEM 入口網站。</span><span class="sxs-lookup"><span data-stu-id="df475-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="df475-221">流覽至 **端點安全性 > 攻擊面降減**。</span><span class="sxs-lookup"><span data-stu-id="df475-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="df475-222">選取 [  **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="df475-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="df475-223">選取 [ **Windows 10 和更新版本– > 建立 Web 保護**]。</span><span class="sxs-lookup"><span data-stu-id="df475-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-224">![Microsoft 端點管理員 portal26 的影像](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="df475-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="df475-225">輸入名稱和描述，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-226">![Microsoft 端點管理員 portal27 的影像](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="df475-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="df475-227">在 [設定 **設定] 頁面** 上：設定 Web 保護所需的設定，然後選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df475-228">我們正在設定網頁防護以封鎖。</span><span class="sxs-lookup"><span data-stu-id="df475-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="df475-229">如需詳細資訊，請參閱 [Web 保護](web-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="df475-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-230">![Microsoft 端點管理員 portal28 的影像](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="df475-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="df475-231">**> 下一步將範圍標記** 新增至必要。</span><span class="sxs-lookup"><span data-stu-id="df475-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-232">![Microsoft 端點管理員 portal29 的影像](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="df475-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="df475-233">選取 **[指派至測試組 > 下一步]**。</span><span class="sxs-lookup"><span data-stu-id="df475-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-234">![Microsoft 端點管理員 portal30 的影像](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="df475-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="df475-235">選取 [ **複查]，建立 > 建立**]。</span><span class="sxs-lookup"><span data-stu-id="df475-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-236">![Microsoft 端點管理員 portal31 的影像](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="df475-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="df475-237">查看原則。</span><span class="sxs-lookup"><span data-stu-id="df475-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-238">![Microsoft 端點管理員 portal32 的影像](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="df475-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="df475-239">驗證設定</span><span class="sxs-lookup"><span data-stu-id="df475-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="df475-240">確認已套用的原則</span><span class="sxs-lookup"><span data-stu-id="df475-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="df475-241">指派好設定原則之後，將需要一些時間才能套用。</span><span class="sxs-lookup"><span data-stu-id="df475-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="df475-242">如需有關計時的資訊，請參閱 [Intune 設定資訊](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)。</span><span class="sxs-lookup"><span data-stu-id="df475-242">For information on timing, see [Intune configuration information](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="df475-243">若要確認已將設定原則套用至測試裝置，請針對每個設定原則遵循下列程式。</span><span class="sxs-lookup"><span data-stu-id="df475-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="df475-244">開啟 MEM 入口網站，並流覽至相關步驟中所示的相關原則。</span><span class="sxs-lookup"><span data-stu-id="df475-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="df475-245">下列範例會顯示下一代保護設定。</span><span class="sxs-lookup"><span data-stu-id="df475-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-246">[![Microsoft 端點管理員 portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png) 的影像](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="df475-247">選取設定 **原則** ，以查看原則狀態。</span><span class="sxs-lookup"><span data-stu-id="df475-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-248">[![Microsoft 端點管理員 portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png) 的影像](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="df475-249">選取 [  **裝置狀態** ] 以查看狀態。</span><span class="sxs-lookup"><span data-stu-id="df475-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-250">[![Microsoft 端點管理員 portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png) 的影像](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="df475-251">選取 [  **使用者狀態** ] 以查看狀態。</span><span class="sxs-lookup"><span data-stu-id="df475-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-252">[![Microsoft 端點管理員 portal36 ](images/4e965749ff71178af8873bc91f9fe525.png) 的影像](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="df475-253">選取 [  **每一設定狀態** ] 以查看狀態。</span><span class="sxs-lookup"><span data-stu-id="df475-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="df475-254">此視圖非常適合識別與其他原則衝突的任何設定。</span><span class="sxs-lookup"><span data-stu-id="df475-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-255">[![Microsoft 端點管理員 portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png) 的影像](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="df475-256">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="df475-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="df475-257">套用此設定之前，不應該啟動 Endpoint Protection 的 Defender for service。</span><span class="sxs-lookup"><span data-stu-id="df475-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-258">[![服務的圖像 panel1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="df475-259">套用設定後，應啟動 Endpoint Protection 服務的 Defender。</span><span class="sxs-lookup"><span data-stu-id="df475-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-260">[![服務的圖像 panel2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="df475-261">在裝置上執行服務後，裝置會出現在 Microsoft Defender 資訊安全中心中。</span><span class="sxs-lookup"><span data-stu-id="df475-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-262">[![Microsoft Defender 資訊安全中心 ](images/df0c64001b9219cfbd10f8f81a273190.png) 的影像](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="df475-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="df475-263">新一代保護</span><span class="sxs-lookup"><span data-stu-id="df475-263">Next-generation protection</span></span>

1.  <span data-ttu-id="df475-264">在測試裝置上套用原則之前，您應該可以手動管理設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="df475-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-265">![設定 page1 的影像](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="df475-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="df475-266">套用原則之後，您應該無法手動管理設定。</span><span class="sxs-lookup"><span data-stu-id="df475-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df475-267">在下列影像中， **開啟雲端傳送保護** ，並 **開啟即時保護** 顯示為受管理。</span><span class="sxs-lookup"><span data-stu-id="df475-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df475-268">![設定 page2 的影像](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="df475-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="df475-269">攻擊面減少–攻擊面減少的原則</span><span class="sxs-lookup"><span data-stu-id="df475-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="df475-270">在測試裝置上套用此原則之前，請先將該原則套用至 PowerShell 視窗，然後輸入 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="df475-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="df475-271">這應該會以下列沒有內容的行回應：</span><span class="sxs-lookup"><span data-stu-id="df475-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="df475-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="df475-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="df475-273">AttackSurfaceReductionRules_Actions：</span><span class="sxs-lookup"><span data-stu-id="df475-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="df475-274">AttackSurfaceReductionRules_Ids：</span><span class="sxs-lookup"><span data-stu-id="df475-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![命令 line1 的圖像](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="df475-276">在測試裝置上套用原則之後，請開啟 PowerShell Windows 並輸入 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="df475-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="df475-277">這應該會以下列包含內容的行來回應，如下所示：</span><span class="sxs-lookup"><span data-stu-id="df475-277">This should respond with the following lines with content as shown below:</span></span>

    ![命令 line2 的影像](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="df475-279">攻擊面減少– Web 保護</span><span class="sxs-lookup"><span data-stu-id="df475-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="df475-280">在測試裝置上，開啟 PowerShell Windows 並輸入 `(Get-MpPreference).EnableNetworkProtection` 。</span><span class="sxs-lookup"><span data-stu-id="df475-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="df475-281">這應該會以0做回應，如下所示。</span><span class="sxs-lookup"><span data-stu-id="df475-281">This should respond with a 0 as shown below.</span></span>

    ![命令 line3 的影像](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="df475-283">套用原則之後，請開啟 PowerShell Windows 並輸入 `(Get-MpPreference).EnableNetworkProtection` 。</span><span class="sxs-lookup"><span data-stu-id="df475-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="df475-284">這應該會以如下所示的1回應。</span><span class="sxs-lookup"><span data-stu-id="df475-284">This should respond with a 1 as shown below.</span></span>

    ![命令 line4 的影像](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
