---
title: 在環中部署 Microsoft Defender for Endpoint
description: 瞭解如何在環中為端點部署 Microsoft Defender
keywords: 部署、震鈴、評估、試驗、內幕人士快速、內幕人士緩慢、安裝程式、板載、階段、部署、部署、採用、設定
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8123bdf610b30407e5d262296f9c3639bc21b12f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893482"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="bd3a0-104">在環中部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd3a0-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd3a0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd3a0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bd3a0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bd3a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd3a0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bd3a0-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bd3a0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bd3a0-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="bd3a0-110">您可以使用以環為基礎的部署方法來部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="bd3a0-111">部署週期可用於下列案例：</span><span class="sxs-lookup"><span data-stu-id="bd3a0-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="bd3a0-112">新部署</span><span class="sxs-lookup"><span data-stu-id="bd3a0-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="bd3a0-113">現有部署</span><span class="sxs-lookup"><span data-stu-id="bd3a0-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="bd3a0-114">新部署</span><span class="sxs-lookup"><span data-stu-id="bd3a0-114">New deployments</span></span>

![部署環的影像](images/deployment-rings.png)


<span data-ttu-id="bd3a0-116">震鈴方法是一種方法，可將一組端點識別成板載，並確認符合特定準則，然後再繼續將服務部署到一組較大的裝置。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="bd3a0-117">您可以為每個震鈴定義結束準則，並在移動至下一環之前確定已完成。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="bd3a0-118">採用以震鈴的部署可協助減少在推出服務時可能發生的潛在問題。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="bd3a0-119">透過試驗特定數目的裝置，您可以識別潛在問題，並減輕可能發生的潛在風險。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="bd3a0-120">表1提供您可能使用的部署環範例。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="bd3a0-121">**表1**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-121">**Table 1**</span></span>

|<span data-ttu-id="bd3a0-122">**部署環**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-122">**Deployment ring**</span></span>|<span data-ttu-id="bd3a0-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="bd3a0-124">Evaluate</span><span class="sxs-lookup"><span data-stu-id="bd3a0-124">Evaluate</span></span> | <span data-ttu-id="bd3a0-125">Ring 1：識別試驗測試的50系統</span><span class="sxs-lookup"><span data-stu-id="bd3a0-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="bd3a0-126">試驗</span><span class="sxs-lookup"><span data-stu-id="bd3a0-126">Pilot</span></span> | <span data-ttu-id="bd3a0-127">Ring 2：在實際執行環境中識別下50-100 端點</span><span class="sxs-lookup"><span data-stu-id="bd3a0-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="bd3a0-128">完整部署</span><span class="sxs-lookup"><span data-stu-id="bd3a0-128">Full deployment</span></span> | <span data-ttu-id="bd3a0-129">震鈴3：以較大的增量向環境中的其他環境推出服務</span><span class="sxs-lookup"><span data-stu-id="bd3a0-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="bd3a0-130">退出準則</span><span class="sxs-lookup"><span data-stu-id="bd3a0-130">Exit criteria</span></span>
<span data-ttu-id="bd3a0-131">這些震鈴的一組出口準則範例包括：</span><span class="sxs-lookup"><span data-stu-id="bd3a0-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="bd3a0-132">裝置庫存清單中顯示裝置</span><span class="sxs-lookup"><span data-stu-id="bd3a0-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="bd3a0-133">在儀表板中顯示警示</span><span class="sxs-lookup"><span data-stu-id="bd3a0-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="bd3a0-134">執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="bd3a0-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="bd3a0-135">在裝置上執行模擬的攻擊</span><span class="sxs-lookup"><span data-stu-id="bd3a0-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="bd3a0-136">Evaluate</span><span class="sxs-lookup"><span data-stu-id="bd3a0-136">Evaluate</span></span>
<span data-ttu-id="bd3a0-137">識別您環境中的少量測試電腦，以在服務上架。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="bd3a0-138">理想情況下，這些機器會少於50端點。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="bd3a0-139">試驗</span><span class="sxs-lookup"><span data-stu-id="bd3a0-139">Pilot</span></span>
<span data-ttu-id="bd3a0-140">Microsoft Defender for Endpoint 支援您可以在服務上架的各種端點。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="bd3a0-141">在此震鈴中，根據您所定義的允出準則，識別多個裝置，並決定繼續進行下一個部署環。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="bd3a0-142">下表顯示支援的端點，以及您可以用於板載裝置裝置至服務的對應工具。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="bd3a0-143">端點</span><span class="sxs-lookup"><span data-stu-id="bd3a0-143">Endpoint</span></span>     | <span data-ttu-id="bd3a0-144">部署工具</span><span class="sxs-lookup"><span data-stu-id="bd3a0-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="bd3a0-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-145">**Windows**</span></span>  |  [<span data-ttu-id="bd3a0-146">本機腳本 (最多10個裝置) </span><span class="sxs-lookup"><span data-stu-id="bd3a0-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="bd3a0-147">附注：如果您想要在實際執行環境中部署超過10個裝置，請改用「群組原則」方法或下列所列的其他支援工具。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="bd3a0-148">群組原則</span><span class="sxs-lookup"><span data-stu-id="bd3a0-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="bd3a0-149">Microsoft 端點管理員/行動裝置管理員</span><span class="sxs-lookup"><span data-stu-id="bd3a0-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="bd3a0-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bd3a0-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="bd3a0-151">VDI 腳本</span><span class="sxs-lookup"><span data-stu-id="bd3a0-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="bd3a0-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-152">**macOS**</span></span>    | [<span data-ttu-id="bd3a0-153">本機腳本</span><span class="sxs-lookup"><span data-stu-id="bd3a0-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="bd3a0-154">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="bd3a0-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="bd3a0-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="bd3a0-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="bd3a0-156">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="bd3a0-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="bd3a0-157">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-157">**Linux Server**</span></span> | [<span data-ttu-id="bd3a0-158">本機腳本</span><span class="sxs-lookup"><span data-stu-id="bd3a0-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="bd3a0-159">木偶</span><span class="sxs-lookup"><span data-stu-id="bd3a0-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="bd3a0-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="bd3a0-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="bd3a0-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-161">**iOS**</span></span>      | [<span data-ttu-id="bd3a0-162">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="bd3a0-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="bd3a0-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-163">**Android**</span></span>  | [<span data-ttu-id="bd3a0-164">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="bd3a0-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="bd3a0-165">完整部署</span><span class="sxs-lookup"><span data-stu-id="bd3a0-165">Full deployment</span></span>
<span data-ttu-id="bd3a0-166">在此階段中，您可以使用 [計畫部署](deployment-strategy.md) 材料來協助您規劃部署。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="bd3a0-167">使用下列材料，為最適合您組織的端點架構選取適當的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="bd3a0-168">**Item**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-168">**Item**</span></span>|<span data-ttu-id="bd3a0-169">**描述**</span><span class="sxs-lookup"><span data-stu-id="bd3a0-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd3a0-170">[![Microsoft Defender for Endpoint 部署策略的縮圖影像](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="bd3a0-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="bd3a0-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="bd3a0-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="bd3a0-172">架構材料可協助您規劃下列架構的部署：</span><span class="sxs-lookup"><span data-stu-id="bd3a0-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="bd3a0-173">雲端-原生</span><span class="sxs-lookup"><span data-stu-id="bd3a0-173">Cloud-native</span></span> </li><li> <span data-ttu-id="bd3a0-174">共同管理</span><span class="sxs-lookup"><span data-stu-id="bd3a0-174">Co-management</span></span> </li><li> <span data-ttu-id="bd3a0-175">內部部署</span><span class="sxs-lookup"><span data-stu-id="bd3a0-175">On-premise</span></span></li><li><span data-ttu-id="bd3a0-176">評估與本機上架</span><span class="sxs-lookup"><span data-stu-id="bd3a0-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="bd3a0-177">現有部署</span><span class="sxs-lookup"><span data-stu-id="bd3a0-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="bd3a0-178">Windows 端點</span><span class="sxs-lookup"><span data-stu-id="bd3a0-178">Windows endpoints</span></span>
<span data-ttu-id="bd3a0-179">若為 Windows 和/或 Windows Server，您可以使用 **安全性更新驗證計畫 (SUVP)**，選取要提前測試的幾部電腦，以在 patch 星期二) 之前 (。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="bd3a0-180">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="bd3a0-180">For more information, see:</span></span>
- [<span data-ttu-id="bd3a0-181">何謂安全性更新驗證程式</span><span class="sxs-lookup"><span data-stu-id="bd3a0-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="bd3a0-182">軟體更新驗證計畫和 Microsoft 惡意程式碼保護中心 TwC 互動式時程表第4部分</span><span class="sxs-lookup"><span data-stu-id="bd3a0-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="bd3a0-183">非 Windows 端點</span><span class="sxs-lookup"><span data-stu-id="bd3a0-183">Non-Windows endpoints</span></span>
<span data-ttu-id="bd3a0-184">使用 macOS 和 Linux，您可以使用一些系統，並在 "InsidersFast" 通道中執行。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-184">With macOS and Linux, you could take a couple of systems and run in the "InsidersFast" channel.</span></span>

>[!NOTE]
><span data-ttu-id="bd3a0-185">理想情況下，至少有一個安全性管理員和一個開發人員，這樣您就能在組建進入「生產」通道之前找到相容性、效能和可靠性問題。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the "Production" channel.</span></span>

<span data-ttu-id="bd3a0-186">通道選擇會決定提供給裝置的更新類型及頻率。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="bd3a0-187">在內部版本中的裝置快用的第一種方法是接收更新及新功能，然後是上一個程式-速度慢，最後透過生產。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-187">Devices in insiders-fast are the first ones to receive updates and new features, followed later by insiders-slow and lastly by prod.</span></span>

![內幕用環的影像](images/insider-rings.png)

<span data-ttu-id="bd3a0-189">為了預覽新功能並提供及早的意見反應，建議您將企業中的部分裝置設定為使用預覽人員-快或內部的速度緩慢。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either insiders-fast or insiders-slow.</span></span>

>[!WARNING]
><span data-ttu-id="bd3a0-190">初次安裝後切換通道需要重新安裝產品。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="bd3a0-191">若要切換產品通道，請執行下列動作：卸載現有的套件、重新設定裝置以使用新通道，然後依照此檔中的步驟，從新位置安裝套件。</span><span class="sxs-lookup"><span data-stu-id="bd3a0-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
