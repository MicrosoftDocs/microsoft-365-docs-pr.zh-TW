---
title: 使用 Microsoft Endpoint Configuration Manager 上架
description: 瞭解如何使用 Microsoft 端點 Configuration Manager 在 Microsoft Defender for Endpoint 上進行板載
keywords: 上架、設定、部署、部署、端點設定管理員、mdatp、高級威脅防護、集合建立、端點偵測回應、下一代保護、攻擊面減少、microsoft 端點 configuration manager
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
ms.openlocfilehash: 31c946ccad84aca3b2fc86c95655cea9e66e182f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186398"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="87989-104">使用 Microsoft Endpoint Configuration Manager 上架</span><span class="sxs-lookup"><span data-stu-id="87989-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="87989-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="87989-105">**Applies to:**</span></span>
- [<span data-ttu-id="87989-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="87989-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87989-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87989-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="87989-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="87989-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="87989-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="87989-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="87989-110">本文是部署指南的一部分，可做為上架方法的範例。</span><span class="sxs-lookup"><span data-stu-id="87989-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="87989-111">在 [規劃](deployment-strategy.md) 主題中，有數種方法可提供給板載裝置給服務。</span><span class="sxs-lookup"><span data-stu-id="87989-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="87989-112">本主題涵蓋共同管理架構。</span><span class="sxs-lookup"><span data-stu-id="87989-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="87989-113">![環境架構之雲端原生架構 ](images/co-management-architecture.png)
 *圖表* 的影像</span><span class="sxs-lookup"><span data-stu-id="87989-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="87989-114">當 Defender for Endpoint 支援各種端點和工具的上架時，本文並未涵蓋這類功能。</span><span class="sxs-lookup"><span data-stu-id="87989-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="87989-115">如需使用其他支援部署工具及方法的一般上架資訊，請參閱上 [架一覽](onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="87989-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="87989-116">本主題指導使用者：</span><span class="sxs-lookup"><span data-stu-id="87989-116">This topic guides users in:</span></span>
- <span data-ttu-id="87989-117">步驟1：將 Windows 裝置上架至服務</span><span class="sxs-lookup"><span data-stu-id="87989-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="87989-118">步驟2：設定用於端點功能的 Defender</span><span class="sxs-lookup"><span data-stu-id="87989-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="87989-119">此上架指引會逐步引導您使用 Microsoft 端點設定管理員時，您必須採取下列基本步驟：</span><span class="sxs-lookup"><span data-stu-id="87989-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="87989-120">**在 Microsoft 端點 Configuration Manager 中建立集合**</span><span class="sxs-lookup"><span data-stu-id="87989-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="87989-121">**使用 Microsoft Endpoint Configuration Manager 設定 Microsoft Defender for Endpoint 功能**</span><span class="sxs-lookup"><span data-stu-id="87989-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="87989-122">在此範例部署中只涵蓋 Windows 裝置。</span><span class="sxs-lookup"><span data-stu-id="87989-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="87989-123">步驟1：使用 Microsoft 端點 Configuration Manager 的板載 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="87989-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="87989-124">集合建立</span><span class="sxs-lookup"><span data-stu-id="87989-124">Collection creation</span></span>
<span data-ttu-id="87989-125">若要使用 Microsoft 端點設定管理員對 Windows 10 裝置進行板載部署，部署可以針對現有集合，也可以建立新的集合以供測試。</span><span class="sxs-lookup"><span data-stu-id="87989-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="87989-126">使用群組原則或手動方法的工具上架不會在系統上安裝任何代理程式。</span><span class="sxs-lookup"><span data-stu-id="87989-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="87989-127">在 Microsoft 端點 Configuration Manager 主控台內，上架過程會設定為主控台中的規範設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="87989-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="87989-128">只要 Configuration Manager 用戶端繼續從管理點接收此原則，任何接收此必要設定的系統都會維護該設定。</span><span class="sxs-lookup"><span data-stu-id="87989-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="87989-129">請遵循下列步驟，使用 Microsoft 端點 Configuration Manager 進行板載端點。</span><span class="sxs-lookup"><span data-stu-id="87989-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="87989-130">在 Microsoft 端點 Configuration Manager 主控台中，流覽至 **[資產] 和 [合規性 \> 一覽表] \> 裝置集合**。</span><span class="sxs-lookup"><span data-stu-id="87989-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Microsoft 端點 Configuration Manager 的圖像 wizard1](images/configmgr-device-collections.png)

2. <span data-ttu-id="87989-132">以滑鼠右鍵按一下 [ **裝置集合** ]，然後選取 [ **建立裝置集合**]。</span><span class="sxs-lookup"><span data-stu-id="87989-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="87989-134">提供 **名稱** 及 **限制集合**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87989-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="87989-136">選取 [ **新增規則** ]，然後選擇 [ **查詢規則**]。</span><span class="sxs-lookup"><span data-stu-id="87989-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="87989-138">在 [**直屬成員資格] 嚮導** 中按 **[下一步**]，然後按一下 [**編輯查詢語句**]</span><span class="sxs-lookup"><span data-stu-id="87989-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Microsoft 端點 Configuration Manager 的圖像 wizard5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="87989-140">選取 [ **準則** ]，然後選擇星形圖示。</span><span class="sxs-lookup"><span data-stu-id="87989-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Microsoft 端點 Configuration Manager 的圖像 wizard6](images/configmgr-criteria.png)

7. <span data-ttu-id="87989-142">將條件類型保留為 **簡單值**，請選擇 [目標為： **作業系統組建編號**]，運算子為 **大於或等於** 和值 **14393** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="87989-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard7](images/configmgr-simple-value.png)

8. <span data-ttu-id="87989-144">選取 **[下一步] 和 [** **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="87989-144">Select **Next** and **Close**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="87989-146">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="87989-146">Select **Next**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard9](images/configmgr-confirm.png)


<span data-ttu-id="87989-148">完成此工作之後，您現在有一個裝置集合，具有環境中所有 Windows 10 端點。</span><span class="sxs-lookup"><span data-stu-id="87989-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="87989-149">步驟2：設定 Microsoft Defender for Endpoint 功能</span><span class="sxs-lookup"><span data-stu-id="87989-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="87989-150">本節會引導您使用 Windows 裝置上的 Microsoft Endpoint Configuration Manager 來設定下列功能：</span><span class="sxs-lookup"><span data-stu-id="87989-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="87989-151">**端點偵測及回應**</span><span class="sxs-lookup"><span data-stu-id="87989-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="87989-152">**下一代保護**</span><span class="sxs-lookup"><span data-stu-id="87989-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="87989-153">**受攻擊面縮小**</span><span class="sxs-lookup"><span data-stu-id="87989-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="87989-154">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="87989-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="87989-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="87989-155">Windows 10</span></span>
<span data-ttu-id="87989-156">在 Microsoft Defender Security Center 中，您可以下載可用於在 System Center Configuration Manager 中建立原則的「. 上架」原則，並將該原則部署至 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="87989-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="87989-157">從 Microsoft Defender Security Center 入口網站，選取 [設定]，然後按 [上 [架](https://securitycenter.windows.com/preferences2/onboarding)]。</span><span class="sxs-lookup"><span data-stu-id="87989-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="87989-158">在 [部署方法] 底下，選取支援的 **Microsoft 端點 Configuration Manager** 版本。</span><span class="sxs-lookup"><span data-stu-id="87989-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Microsoft Defender for Endpoint 上架 wizard10 的影像](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="87989-160">選取 [ **下載套件**]。</span><span class="sxs-lookup"><span data-stu-id="87989-160">Select **Download package**.</span></span>

    ![Microsoft Defender for Endpoint 上架 wizard11 的影像](images/mdatp-download-package.png)

4. <span data-ttu-id="87989-162">將套件儲存至可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="87989-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="87989-163">在 [Microsoft 端點設定管理員] 中，流覽至：「 **資產和合規性 > 概述 > Endpoint Protection > Microsoft DEFENDER ATP 原則**。</span><span class="sxs-lookup"><span data-stu-id="87989-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="87989-164">以滑鼠右鍵按一下 [ **Microsoft DEFENDER Atp 原則** ]，然後選取 [ **建立 Microsoft defender atp 原則**]。</span><span class="sxs-lookup"><span data-stu-id="87989-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard12](images/configmgr-create-policy.png)

7. <span data-ttu-id="87989-166">輸入名稱和描述，確認已選取 [上 **架** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87989-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 wizard13](images/configmgr-policy-name.png)


8. <span data-ttu-id="87989-168">按一下 [瀏覽]。</span><span class="sxs-lookup"><span data-stu-id="87989-168">Click **Browse**.</span></span>

9. <span data-ttu-id="87989-169">流覽至上述步驟4下載檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="87989-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="87989-170">按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="87989-170">Click **Next**.</span></span>
11. <span data-ttu-id="87989-171">以適當的範例設定代理 (**無** 或 **所有檔案類型**) 。</span><span class="sxs-lookup"><span data-stu-id="87989-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![設定 settings1 的影像](images/configmgr-config-settings.png)

12. <span data-ttu-id="87989-173">選取適當的遙測 (**Normal** 或 **加急**) 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87989-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![設定 settings2 的影像](images/configmgr-telemetry.png)

14. <span data-ttu-id="87989-175">確認設定，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87989-175">Verify the configuration, then click **Next**.</span></span>

     ![設定 settings3 的影像](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="87989-177">當嚮導完成時，按一下 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="87989-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="87989-178">在 Microsoft 端點 Configuration Manager 主控台中，以滑鼠右鍵按一下您剛才建立的 Defender for Endpoint 原則，然後選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="87989-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![設定 settings4 的影像](images/configmgr-deploy.png)

17. <span data-ttu-id="87989-180">在右窗格中，選取先前建立的集合，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="87989-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![設定 settings5 的影像](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="87989-182">舊版本的 Windows 用戶端 (Windows 7 和 Windows 8.1) </span><span class="sxs-lookup"><span data-stu-id="87989-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="87989-183">請遵循下列步驟來識別用於上架舊版 Windows 的 Defender 工作區識別碼和工作區金鑰。</span><span class="sxs-lookup"><span data-stu-id="87989-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="87989-184">從 Microsoft Defender Security Center 入口網站中，選取 [ **設定] > 上架**。</span><span class="sxs-lookup"><span data-stu-id="87989-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="87989-185">在 [作業系統] 底下，選擇 [ **Windows 7 SP1 和 8.1**。</span><span class="sxs-lookup"><span data-stu-id="87989-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="87989-186">複製 **工作區識別碼** 和 **工作區機碼** ，並加以儲存。</span><span class="sxs-lookup"><span data-stu-id="87989-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="87989-187">這些程式將在稍後的程式中使用。</span><span class="sxs-lookup"><span data-stu-id="87989-187">They will be used later in the process.</span></span>

    ![上架影像](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="87989-189">安裝 Microsoft Monitoring Agent (MMA) 。</span><span class="sxs-lookup"><span data-stu-id="87989-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="87989-190">MMA 目前 (到2019年1月為止，在下列 Windows 作業系統上支援) ：</span><span class="sxs-lookup"><span data-stu-id="87989-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="87989-191">伺服器 SKUs： Windows Server 2008 SP1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="87989-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="87989-192">用戶端 SKUs： Windows 7 SP1 和更新版本</span><span class="sxs-lookup"><span data-stu-id="87989-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="87989-193">MMA 代理程式將需要安裝在 Windows 裝置上。</span><span class="sxs-lookup"><span data-stu-id="87989-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="87989-194">若要安裝代理程式，有些系統將需要下載 [客戶經驗的更新和診斷遙測](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) ，以便使用 MMA 收集資料。</span><span class="sxs-lookup"><span data-stu-id="87989-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="87989-195">這些系統版本包括（但不限於）：</span><span class="sxs-lookup"><span data-stu-id="87989-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="87989-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="87989-196">Windows 8.1</span></span>

    -   <span data-ttu-id="87989-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="87989-197">Windows 7</span></span>

    -   <span data-ttu-id="87989-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="87989-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="87989-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="87989-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="87989-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="87989-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="87989-201">具體說來，針對 Windows 7 SP1，必須安裝下列修補程式：</span><span class="sxs-lookup"><span data-stu-id="87989-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="87989-202">安裝 [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="87989-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="87989-203">安裝 [.net Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更新版本) **或** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)。</span><span class="sxs-lookup"><span data-stu-id="87989-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="87989-204">請勿在同一系統上安裝兩者。</span><span class="sxs-lookup"><span data-stu-id="87989-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="87989-205">如果您使用 proxy 連線到網際網路，請參閱設定 proxy 設定區段。</span><span class="sxs-lookup"><span data-stu-id="87989-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="87989-206">完成後，您應該會在一個小時內看到入口網站中的架端點。</span><span class="sxs-lookup"><span data-stu-id="87989-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="87989-207">下一代保護</span><span class="sxs-lookup"><span data-stu-id="87989-207">Next generation protection</span></span> 
<span data-ttu-id="87989-208">Microsoft Defender 防毒軟體是一套內建的反惡意程式碼解決方案，為電腦、可攜式電腦，以及伺服器提供下一代保護。</span><span class="sxs-lookup"><span data-stu-id="87989-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="87989-209">在 Microsoft 端點 Configuration Manager 主控台中，流覽至 **[資產和合規性 \> 一覽表] \> Endpoint Protection \> 反惡意** 代碼原則，然後選擇 [ **建立反惡意程式碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="87989-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![反惡意軟體原則的影像](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="87989-211">選取 [**排程掃描**]、[**掃描設定**]、[**預設動作**]、[**即時保護**]、[**排除設定**]、[**高級**]、[**威脅覆寫** **]、[** **Cloud protection Service** ] 和 [**安全性智慧更新**</span><span class="sxs-lookup"><span data-stu-id="87989-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![下一代保護 pane1 的影像](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="87989-213">在某些行業或某些選取的企業客戶可能對防病毒設定方式有特殊需求。</span><span class="sxs-lookup"><span data-stu-id="87989-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="87989-214">快速掃描與完整掃描及自訂掃描</span><span class="sxs-lookup"><span data-stu-id="87989-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="87989-215">如需詳細資訊，請參閱 [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="87989-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![下一代保護 pane2 的影像](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![下一代保護 pane3 的影像](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![下一代保護 pane4 的影像](images/a28afc02c1940d5220b233640364970c.png)

    ![下一代保護 pane5 的影像](images/5420a8790c550f39f189830775a6d4c9.png)

    ![下一代保護 pane6 的影像](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![下一代保護 pane7 的影像](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![下一代保護 pane8 的影像](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![下一代保護 pane9 的影像](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="87989-224">在新建立的反惡意軟體原則上按一下滑鼠右鍵，然後選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="87989-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![下一代保護 pane10 的影像](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="87989-226">將新的反惡意軟體原則設定為您的 Windows 10 集合，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="87989-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![下一代保護 pane11 的影像](images/configmgr-select-collection.png)

<span data-ttu-id="87989-228">完成此工作之後，您現在已成功設定 Windows Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="87989-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="87989-229">受攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="87989-229">Attack surface reduction</span></span>
<span data-ttu-id="87989-230">Pillar 的 Defender for Endpoint 的攻擊面減少包含可在 Exploit Guard 下使用的功能集。</span><span class="sxs-lookup"><span data-stu-id="87989-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="87989-231">攻擊面減少 (ASR) 規則、受控資料夾存取、網路保護和 Exploit Protection。</span><span class="sxs-lookup"><span data-stu-id="87989-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="87989-232">所有這些功能都會提供一個稽核模式和封鎖模式。</span><span class="sxs-lookup"><span data-stu-id="87989-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="87989-233">在審計模式中，不會影響使用者。</span><span class="sxs-lookup"><span data-stu-id="87989-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="87989-234">所有的功能都是收集其他遙測，並使其可在 Microsoft Defender Security Center 中使用。</span><span class="sxs-lookup"><span data-stu-id="87989-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="87989-235">部署的目標在於逐步將安全性控制措施移至區塊模式。</span><span class="sxs-lookup"><span data-stu-id="87989-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="87989-236">若要在審計模式中設定 ASR 規則：</span><span class="sxs-lookup"><span data-stu-id="87989-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="87989-237">在 Microsoft 端點 Configuration Manager 主控台中，流覽至 **[資產和合規性 \> 一覽] [ \> Endpoint Protection \> Windows Defender 利用防護** ]，然後選擇 [ **建立 Exploit Guard 原則**]。</span><span class="sxs-lookup"><span data-stu-id="87989-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Microsoft 端點 Configuration Manager 的圖像 console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="87989-239">選取 [ **攻擊面減少**]。</span><span class="sxs-lookup"><span data-stu-id="87989-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="87989-240">設定要 **審核** 的規則，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87989-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Microsoft 端點 Configuration Manager 主控台的影像](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="87989-242">按一下 **[下一步]**，確認新的 Exploit Guard 原則。</span><span class="sxs-lookup"><span data-stu-id="87989-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 console2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="87989-244">建立原則之後，按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="87989-244">Once the policy is created click **Close**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Microsoft 端點管理員主控台的影像](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="87989-247">在新建立的原則上按一下滑鼠右鍵，然後選擇 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="87989-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Microsoft 端點 Configuration Manager 的圖像 console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="87989-249">將原則設定為新建立的 Windows 10 集合，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="87989-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Microsoft 端點 Configuration Manager 的圖像 console5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="87989-251">完成此工作之後，您現在已在稽核模式中成功設定 ASR 規則。</span><span class="sxs-lookup"><span data-stu-id="87989-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="87989-252">以下是驗證 ASR 規則是否正確套用至端點的其他步驟。</span><span class="sxs-lookup"><span data-stu-id="87989-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="87989-253"> (可能需要幾分鐘的時間) </span><span class="sxs-lookup"><span data-stu-id="87989-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="87989-254">在網頁瀏覽器中，流覽至 <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="87989-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="87989-255">從左側功能表中選取 [設定 **管理** ]。</span><span class="sxs-lookup"><span data-stu-id="87989-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="87989-256">在 [攻擊面管理] 面板中，按一下 [ **移至攻擊介面管理** ]。</span><span class="sxs-lookup"><span data-stu-id="87989-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![攻擊面管理的影像](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="87989-258">按一下 **攻擊** 面減少規則報告中的 [設定] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="87989-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="87989-259">它會在每個裝置上顯示 ASR 規則的設定概述和 ASR 規則狀態。</span><span class="sxs-lookup"><span data-stu-id="87989-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![攻擊面降低規則 reports1 的螢幕擷取畫面](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="87989-261">按一下每個裝置會顯示 ASR 規則的設定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="87989-261">Click each device shows configuration details of ASR rules.</span></span>

    ![攻擊面降低規則 reports2 的螢幕擷取畫面](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="87989-263">如需詳細資訊，請參閱 [優化 ASR 規則部署和](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   偵測。</span><span class="sxs-lookup"><span data-stu-id="87989-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="87989-264">在稽核模式中設定網路保護規則：</span><span class="sxs-lookup"><span data-stu-id="87989-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="87989-265">在 Microsoft 端點 Configuration Manager 主控台中，流覽至 **[資產和合規性 \> 一覽] [ \> Endpoint Protection \> Windows Defender 利用防護** ]，然後選擇 [ **建立 Exploit Guard 原則**]。</span><span class="sxs-lookup"><span data-stu-id="87989-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![螢幕擷取畫面 System Center 設定 Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="87989-267">選取 [ **網路保護**]。</span><span class="sxs-lookup"><span data-stu-id="87989-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="87989-268">將設定設定為「 **審核** 」，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87989-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![螢幕擷取畫面 System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="87989-270">按 **[下一步]**，確認新的 Exploit Guard 原則。</span><span class="sxs-lookup"><span data-stu-id="87989-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![螢幕擷取畫面利用防護 policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="87989-272">建立原則之後，按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="87989-272">Once the policy is created click on **Close**.</span></span>

    ![螢幕擷取畫面利用防護 policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="87989-274">在新建立的原則上按一下滑鼠右鍵，然後選擇 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="87989-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![螢幕擷取畫面 Microsoft 端點設定 Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="87989-276">選取新建立的 Windows 10 集合的原則，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="87989-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![螢幕擷取畫面 Microsoft 端點設定 Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="87989-278">完成這項工作之後，您現在已經成功設定了稽核模式中的網路保護。</span><span class="sxs-lookup"><span data-stu-id="87989-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="87989-279">若要設定稽核模式中的受控資料夾存取規則：</span><span class="sxs-lookup"><span data-stu-id="87989-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="87989-280">在 Microsoft 端點 Configuration Manager 主控台中，流覽至 **[資產和合規性 \> 一覽] [ \> Endpoint Protection \> Windows Defender 利用防護** ]，然後選擇 [ **建立 Exploit Guard 原則**]。</span><span class="sxs-lookup"><span data-stu-id="87989-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Microsoft 端點設定 Manager3 的螢幕擷取畫面](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="87989-282">選取 [ **受管理的資料夾存取**]。</span><span class="sxs-lookup"><span data-stu-id="87989-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="87989-283">將設定設定為 [ **審計** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87989-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Microsoft 端點設定 Manager4 的螢幕擷取畫面](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="87989-285">按一下 **[下一步]**，確認新的 Exploit Guard 原則。</span><span class="sxs-lookup"><span data-stu-id="87989-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Microsoft 端點設定 Manager5 的螢幕擷取畫面](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="87989-287">建立原則之後，按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="87989-287">Once the policy is created click on **Close**.</span></span>

    ![Microsoft 端點設定 Manager6 的螢幕擷取畫面](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="87989-289">在新建立的原則上按一下滑鼠右鍵，然後選擇 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="87989-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Microsoft 端點設定 Manager7 的螢幕擷取畫面](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="87989-291">將原則設定為新建立的 Windows 10 集合，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="87989-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Microsoft 端點設定 Manager8 的螢幕擷取畫面](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="87989-293">您現在已成功設定稽核模式中的「控制資料夾存取」。</span><span class="sxs-lookup"><span data-stu-id="87989-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="87989-294">相關主題</span><span class="sxs-lookup"><span data-stu-id="87989-294">Related topic</span></span>
- [<span data-ttu-id="87989-295">使用 Microsoft 端點管理員上架</span><span class="sxs-lookup"><span data-stu-id="87989-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
