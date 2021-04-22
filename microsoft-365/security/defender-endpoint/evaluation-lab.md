---
title: Microsoft Defender for Endpoint 評估實驗室
description: 深入瞭解 Microsoft Defender for Endpoint 功能、執行攻擊模擬，並查看其如何防止、偵測和 remediates 威脅。
keywords: 評估 Microsoft Defender for Endpoint，評估，實驗室，模擬，windows 10，windows server 2019，評估實驗室
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
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ed2165c0102170256f50964180a550d8eccbce8c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932784"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="47804-104">Microsoft Defender for Endpoint 評估實驗室</span><span class="sxs-lookup"><span data-stu-id="47804-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47804-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="47804-105">**Applies to:**</span></span>
- [<span data-ttu-id="47804-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="47804-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="47804-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47804-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="47804-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="47804-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47804-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="47804-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="47804-110">進行完整的安全性產品評估可能是複雜的程式，需要很繁瑣的環境和裝置設定，才能實際執行端對端的攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="47804-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="47804-111">新增至複雜性是追蹤評估期間反映類比活動、警示和結果的難度。</span><span class="sxs-lookup"><span data-stu-id="47804-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="47804-112">Microsoft Defender for Endpoint 評估實驗室的設計是為了消除裝置和環境設定的複雜性，使您能夠專注于評估平臺的功能、執行模擬，以及查看動作中的預防、偵測和修正功能。</span><span class="sxs-lookup"><span data-stu-id="47804-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="47804-113">使用簡化的設定體驗，您可以將重點放在執行您自己的測試案例和預先類比，以查看如何執行的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="47804-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="47804-114">您將擁有平臺強大功能的完整存取權，例如自動化調查、高級搜尋和威脅分析，可讓您測試已提供的 Defender for Endpoint 的綜合保護堆疊。</span><span class="sxs-lookup"><span data-stu-id="47804-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="47804-115">您可以將預先設定的 Windows 10 或 Windows Server 2019 裝置，新增至適當的作業系統版本和正確的安全性元件，以及已安裝的 Office 2019 Standard。</span><span class="sxs-lookup"><span data-stu-id="47804-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="47804-116">您也可以安裝威脅模擬器。</span><span class="sxs-lookup"><span data-stu-id="47804-116">You can also install threat simulators.</span></span> <span data-ttu-id="47804-117">Defender for Endpoint 已與業界領先的威脅類比平臺合作，協助您測試用於端點功能的 Defender，而不需要離開入口網站。</span><span class="sxs-lookup"><span data-stu-id="47804-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="47804-118">安裝您慣用的模擬器、在評估實驗室內執行案例，並立即查看平臺的執行方式-所有可方便您免費取得，而不需要額外成本。</span><span class="sxs-lookup"><span data-stu-id="47804-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="47804-119">您也可以輕鬆存取您可以從模擬目錄存取及執行的大量類比。</span><span class="sxs-lookup"><span data-stu-id="47804-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="47804-120">開始之前</span><span class="sxs-lookup"><span data-stu-id="47804-120">Before you begin</span></span>
<span data-ttu-id="47804-121">您將需要履行 [授權需求](minimum-requirements.md#licensing-requirements) ，或擁有 Microsoft Defender for Endpoint 的試用存取權，才能存取評估實驗室。</span><span class="sxs-lookup"><span data-stu-id="47804-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="47804-122">您必須具有「 **管理安全性設定** 」許可權，才能執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="47804-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="47804-123">建立實驗室</span><span class="sxs-lookup"><span data-stu-id="47804-123">Create the lab</span></span>
- <span data-ttu-id="47804-124">建立裝置</span><span class="sxs-lookup"><span data-stu-id="47804-124">Create devices</span></span>
- <span data-ttu-id="47804-125">重設密碼</span><span class="sxs-lookup"><span data-stu-id="47804-125">Reset password</span></span>
- <span data-ttu-id="47804-126">建立模擬</span><span class="sxs-lookup"><span data-stu-id="47804-126">Create simulations</span></span> 
 
<span data-ttu-id="47804-127">如果您已啟用角色型存取控制 (RBAC) 並建立至少一部機器群組，使用者必須能夠存取所有機器群組。</span><span class="sxs-lookup"><span data-stu-id="47804-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="47804-128">如需詳細資訊，請參閱 [Create and manage roles](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="47804-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="47804-129">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="47804-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47804-130">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="47804-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="47804-131">開始使用實驗室</span><span class="sxs-lookup"><span data-stu-id="47804-131">Get started with the lab</span></span>
<span data-ttu-id="47804-132">您可以從功能表存取 lab。</span><span class="sxs-lookup"><span data-stu-id="47804-132">You can access the lab from the menu.</span></span> <span data-ttu-id="47804-133">在 [流覽] 功能表中，選取 [ **評估與示教 > 評估實驗室**]。</span><span class="sxs-lookup"><span data-stu-id="47804-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![功能表上評估實驗室的影像](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="47804-135">視您所選取的環境結構類型而定，裝置會在啟用後的指定時數內使用。</span><span class="sxs-lookup"><span data-stu-id="47804-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="47804-136">每個環境都配有一組有限的測試裝置。</span><span class="sxs-lookup"><span data-stu-id="47804-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="47804-137">當您已使用已布建的裝置時，不會提供任何新裝置。</span><span class="sxs-lookup"><span data-stu-id="47804-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="47804-138">已刪除的裝置不會重新整理可用的測試裝置計數。</span><span class="sxs-lookup"><span data-stu-id="47804-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="47804-139">當資源已使用中時，您將無法再使用實驗。</span><span class="sxs-lookup"><span data-stu-id="47804-139">You can no longer use the lab when the resources have been used up.</span></span> <span data-ttu-id="47804-140">它不會重設或重新整理。</span><span class="sxs-lookup"><span data-stu-id="47804-140">It does not reset nor refresh.</span></span>
>- <span data-ttu-id="47804-141">建議您謹慎使用資源。實驗室資源有限。</span><span class="sxs-lookup"><span data-stu-id="47804-141">It is advisable to use the resources carefully.The lab resources are limited.</span></span> <span data-ttu-id="47804-142">它們不會重設或重新整理。</span><span class="sxs-lookup"><span data-stu-id="47804-142">They will not reset nor refresh.</span></span> 

<span data-ttu-id="47804-143">已經有實驗室？</span><span class="sxs-lookup"><span data-stu-id="47804-143">Already have a lab?</span></span> <span data-ttu-id="47804-144">請務必啟用新的威脅模擬器，並具有作用中裝置。</span><span class="sxs-lookup"><span data-stu-id="47804-144">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="47804-145">設定評估實驗室</span><span class="sxs-lookup"><span data-stu-id="47804-145">Setup the evaluation lab</span></span>

1. <span data-ttu-id="47804-146">在功能窗格中，選取 [**評估與教程**  >  **評估實驗室**]，然後選取 [**安裝實驗室**]。</span><span class="sxs-lookup"><span data-stu-id="47804-146">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![評估實驗室歡迎頁面的圖像](images/evaluation-lab-setup.png)

2. <span data-ttu-id="47804-148">視您的評估需求而定，您可以選擇在較短的期間內使用較少的裝置來設定環境，而不是更長的時間。</span><span class="sxs-lookup"><span data-stu-id="47804-148">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="47804-149">選取您偏好的實驗室設定，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="47804-149">Select your preferred lab configuration then select **Next**.</span></span>

    ![實驗室配置選項的影像](images/lab-creation-page.png) 


3. <span data-ttu-id="47804-151"> (選用) 您可以選擇在實驗室中安裝威脅模擬器。</span><span class="sxs-lookup"><span data-stu-id="47804-151">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![安裝模擬器代理程式的影像](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="47804-153">您必須先接受並提供條款和資訊共用語句的同意。</span><span class="sxs-lookup"><span data-stu-id="47804-153">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="47804-154">選取您要使用的威脅模擬代理程式，並輸入您的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="47804-154">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="47804-155">您也可以選擇稍後安裝威脅模擬器。</span><span class="sxs-lookup"><span data-stu-id="47804-155">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="47804-156">如果您選擇在實驗室設定期間安裝威脅模擬代理程式，您可以享受在所加入的裝置上輕鬆安裝的優點。</span><span class="sxs-lookup"><span data-stu-id="47804-156">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![摘要頁面的圖像](images/lab-setup-summary.png)

5.  <span data-ttu-id="47804-158">查看摘要，然後選取 [ **安裝實驗室**]。</span><span class="sxs-lookup"><span data-stu-id="47804-158">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="47804-159">實驗室安裝程式完成後，您可以新增裝置和執行模擬。</span><span class="sxs-lookup"><span data-stu-id="47804-159">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="47804-160">新增裝置</span><span class="sxs-lookup"><span data-stu-id="47804-160">Add devices</span></span>
<span data-ttu-id="47804-161">當您在環境中新增裝置時，終結點會設定具有連線詳細資料的完善設定裝置。</span><span class="sxs-lookup"><span data-stu-id="47804-161">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="47804-162">您可以新增 Windows 10 或 Windows Server 2019 裝置。</span><span class="sxs-lookup"><span data-stu-id="47804-162">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="47804-163">裝置會設定為最新版本的作業系統和 Office 2019 Standard，以及其他應用程式，例如 JAVA、Python 和 SysIntenals。</span><span class="sxs-lookup"><span data-stu-id="47804-163">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="47804-164">您的實驗室中需要更多裝置？</span><span class="sxs-lookup"><span data-stu-id="47804-164">Need more devices in your lab?</span></span> <span data-ttu-id="47804-165">提交支援票證，以供 Endpoint 小組的 Defender 檢查要求。</span><span class="sxs-lookup"><span data-stu-id="47804-165">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="47804-166">如果您選擇在實驗室設定期間新增威脅模擬器，所有裝置都會在您新增的裝置中安裝威脅模擬器代理程式。</span><span class="sxs-lookup"><span data-stu-id="47804-166">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="47804-167">裝置將會自動架至您的租使用者，並將建議的 Windows 安全性元件開啟和稽核模式-無需任何工作。</span><span class="sxs-lookup"><span data-stu-id="47804-167">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="47804-168">在測試裝置中預先設定下列安全性元件：</span><span class="sxs-lookup"><span data-stu-id="47804-168">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="47804-169">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="47804-169">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="47804-170">第一次看到的封鎖</span><span class="sxs-lookup"><span data-stu-id="47804-170">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="47804-171">受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="47804-171">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="47804-172">入侵防護</span><span class="sxs-lookup"><span data-stu-id="47804-172">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="47804-173">網路保護</span><span class="sxs-lookup"><span data-stu-id="47804-173">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="47804-174">可能有害的應用程式偵測</span><span class="sxs-lookup"><span data-stu-id="47804-174">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="47804-175">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="47804-175">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="47804-176">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="47804-176">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="47804-177">Microsoft Defender 防病毒會在 (不是在審計模式) 中。</span><span class="sxs-lookup"><span data-stu-id="47804-177">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="47804-178">如果 Microsoft Defender 防病毒封鎖您執行類比，您可以透過 Windows 安全性關閉裝置上的即時保護。</span><span class="sxs-lookup"><span data-stu-id="47804-178">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="47804-179">如需詳細資訊，請參閱 [Configure always on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="47804-179">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="47804-180">自動調查設定會因租使用者設定而異。</span><span class="sxs-lookup"><span data-stu-id="47804-180">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="47804-181">預設會將其設定為半自動。</span><span class="sxs-lookup"><span data-stu-id="47804-181">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="47804-182">如需詳細資訊，請參閱 [自動化調查的概述](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="47804-182">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="47804-183">使用 RDP 進行與測試裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="47804-183">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="47804-184">請確定您的防火牆設定允許 RDP 連線。</span><span class="sxs-lookup"><span data-stu-id="47804-184">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="47804-185">從儀表板中，選取 [ **新增裝置**]。</span><span class="sxs-lookup"><span data-stu-id="47804-185">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="47804-186">選擇要新增的裝置類型。</span><span class="sxs-lookup"><span data-stu-id="47804-186">Choose the type of device to add.</span></span> <span data-ttu-id="47804-187">您可以選擇新增 Windows 10 或 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="47804-187">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![具有裝置選項的實驗室設定映射](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="47804-189">如果在建立裝置時出現問題，您將會收到通知，您必須提交新的要求。</span><span class="sxs-lookup"><span data-stu-id="47804-189">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="47804-190">如果裝置建立失敗，不會將它計入總允許配額。</span><span class="sxs-lookup"><span data-stu-id="47804-190">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="47804-191">隨即會顯示連線詳細資料。</span><span class="sxs-lookup"><span data-stu-id="47804-191">The connection details are displayed.</span></span> <span data-ttu-id="47804-192">選取 [ **複製** ]，以儲存裝置的密碼。</span><span class="sxs-lookup"><span data-stu-id="47804-192">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="47804-193">密碼只會顯示一次。</span><span class="sxs-lookup"><span data-stu-id="47804-193">The password is only displayed once.</span></span> <span data-ttu-id="47804-194">請務必將其儲存以供日後使用。</span><span class="sxs-lookup"><span data-stu-id="47804-194">Be sure to save it for later use.</span></span>

    ![以連線詳細資料新增裝置的影像](images/add-machine-eval-lab.png)

4. <span data-ttu-id="47804-196">裝置設定開始。</span><span class="sxs-lookup"><span data-stu-id="47804-196">Device set up begins.</span></span> <span data-ttu-id="47804-197">這可能需要大約30分鐘。</span><span class="sxs-lookup"><span data-stu-id="47804-197">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="47804-198">選取 [ **裝置** ] 索引標籤，查看測試裝置的狀態、風險和暴露程度，以及模擬程式安裝的狀態。</span><span class="sxs-lookup"><span data-stu-id="47804-198">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![[裝置影像] 索引標籤](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="47804-200">在 [ **模擬器狀態** ] 欄中，您可以將游標移到資訊圖示上，以瞭解代理程式的安裝狀態。</span><span class="sxs-lookup"><span data-stu-id="47804-200">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="47804-201">類比攻擊案例</span><span class="sxs-lookup"><span data-stu-id="47804-201">Simulate attack scenarios</span></span>
<span data-ttu-id="47804-202">透過連線來執行您自己的攻擊模擬，以使用測試裝置。</span><span class="sxs-lookup"><span data-stu-id="47804-202">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="47804-203">您可以使用下列方式模擬攻擊案例：</span><span class="sxs-lookup"><span data-stu-id="47804-203">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="47804-204">「 [自行執行它」攻擊案例](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="47804-204">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="47804-205">威脅模擬器</span><span class="sxs-lookup"><span data-stu-id="47804-205">Threat simulators</span></span>

<span data-ttu-id="47804-206">您也可以使用 [高級搜尋](advanced-hunting-query-language.md) 查詢資料和 [威脅分析](threat-analytics.md) ，以查看有關新興威脅的報告。</span><span class="sxs-lookup"><span data-stu-id="47804-206">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="47804-207">自行攻擊案例</span><span class="sxs-lookup"><span data-stu-id="47804-207">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="47804-208">如果您正在尋找預先類比，您可以使用我們「 [自己動手」的攻擊案例](https://securitycenter.windows.com/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="47804-208">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="47804-209">這些腳本是安全、有記錄且便於使用。</span><span class="sxs-lookup"><span data-stu-id="47804-209">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="47804-210">這些案例會反映 Defender 的端點功能，並引導您完成調查經驗。</span><span class="sxs-lookup"><span data-stu-id="47804-210">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="47804-211">使用 RDP 進行與測試裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="47804-211">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="47804-212">請確定您的防火牆設定允許 RDP 連線。</span><span class="sxs-lookup"><span data-stu-id="47804-212">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="47804-213">選取 **[** 連線]，以連線至您的裝置並執行攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="47804-213">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![測試裝置的 [連接] 按鈕影像](images/test-machine-table.png)

2. <span data-ttu-id="47804-215">選取 [連線 **]** 以儲存 RDP 檔案並加以啟動。</span><span class="sxs-lookup"><span data-stu-id="47804-215">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![遠端桌面連線的影像](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="47804-217">如果您沒有在初始設定期間儲存的密碼複本，您可以從功能表中選取 [ **重設密碼** ] 以重設密碼： ![ 重設密碼的影像](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="47804-217">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="47804-218">裝置會將其狀態變更為「執行重新設定密碼」，然後您會在幾分鐘內看到新的密碼。</span><span class="sxs-lookup"><span data-stu-id="47804-218">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="47804-219">輸入在裝置建立步驟中顯示的密碼。</span><span class="sxs-lookup"><span data-stu-id="47804-219">Enter the password that was displayed during the device creation step.</span></span> 

   ![輸入認證的視窗影像](images/enter-password.png)

4. <span data-ttu-id="47804-221">在裝置上執行自行攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="47804-221">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="47804-222">威脅模擬案例</span><span class="sxs-lookup"><span data-stu-id="47804-222">Threat simulator scenarios</span></span>
<span data-ttu-id="47804-223">如果您選擇在實驗室設定期間安裝任何受支援的威脅模擬器，您可以在評估實驗室裝置上執行內建模擬。</span><span class="sxs-lookup"><span data-stu-id="47804-223">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="47804-224">使用協力廠商平臺執行威脅模擬是一種很好的方法，可以在實驗室環境的範圍內評估 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="47804-224">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="47804-225">在您可以執行模擬之前，請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="47804-225">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="47804-226">裝置必須新增至評估實驗室</span><span class="sxs-lookup"><span data-stu-id="47804-226">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="47804-227">威脅模擬器必須安裝在評估實驗室中</span><span class="sxs-lookup"><span data-stu-id="47804-227">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="47804-228">從入口網站選取 [ **建立類比**]。</span><span class="sxs-lookup"><span data-stu-id="47804-228">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="47804-229">選取威脅模擬器。</span><span class="sxs-lookup"><span data-stu-id="47804-229">Select a threat simulator.</span></span>

    ![威脅模擬器選取專案的影像](images/select-simulator.png)

3. <span data-ttu-id="47804-231">選擇類比或查看類比圖庫，以流覽可用模擬。</span><span class="sxs-lookup"><span data-stu-id="47804-231">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="47804-232">您可以從下列專案進入類比庫：</span><span class="sxs-lookup"><span data-stu-id="47804-232">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="47804-233">**模擬一覽表** 磚中的主要評估儀表板或</span><span class="sxs-lookup"><span data-stu-id="47804-233">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="47804-234">透過流覽流覽窗格 **評估與示教**  >  **類比 & 教學** 課程，然後選取 [**模擬目錄**]。</span><span class="sxs-lookup"><span data-stu-id="47804-234">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="47804-235">選取您要在其中執行模擬的裝置。</span><span class="sxs-lookup"><span data-stu-id="47804-235">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="47804-236">選取 [ **建立類比**]。</span><span class="sxs-lookup"><span data-stu-id="47804-236">Select **Create simulation**.</span></span>

6. <span data-ttu-id="47804-237">選取 [ **模擬** ] 索引標籤，以查看模擬的進度。查看類比狀態、作用中警示和其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="47804-237">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![模擬的影像索引標籤](images/simulations-tab.png)
    
<span data-ttu-id="47804-239">執行模擬後，我們鼓勵您逐步完成實驗室進度列，並探索 **Microsoft Defender For Endpoint 會觸發自動調查和修正**。</span><span class="sxs-lookup"><span data-stu-id="47804-239">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="47804-240">查看由功能收集及分析的證據。</span><span class="sxs-lookup"><span data-stu-id="47804-240">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="47804-241">使用豐富的查詢語言和原始遙測，並查看在威脅分析中所記錄的一些世界範圍威脅，以透過「高級搜尋」搜尋攻擊證據。</span><span class="sxs-lookup"><span data-stu-id="47804-241">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="47804-242">類比圖庫</span><span class="sxs-lookup"><span data-stu-id="47804-242">Simulation gallery</span></span>
<span data-ttu-id="47804-243">Microsoft Defender for Endpoint 已與各種威脅模擬平臺產生合作，讓您能輕鬆地從入口網站中測試平臺的功能。</span><span class="sxs-lookup"><span data-stu-id="47804-243">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="47804-244">從功能表移至 [**類比] 和 [教程**  >  **模擬] 目錄**，以查看所有可用的模擬。</span><span class="sxs-lookup"><span data-stu-id="47804-244">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="47804-245">列出支援的協力廠商威脅模擬代理程式清單，並在目錄上提供特定類型的模擬，以及詳細描述。</span><span class="sxs-lookup"><span data-stu-id="47804-245">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="47804-246">您可以從目錄輕鬆執行任何可用的類比。</span><span class="sxs-lookup"><span data-stu-id="47804-246">You can conveniently run any available simulation right from the catalog.</span></span>  


![模擬目錄的影像](images/simulations-catalog.png)

<span data-ttu-id="47804-248">每個類比都具有攻擊案例的深入描述，如使用的 MITRE 攻擊技術和您執行的高級搜尋查詢範例。</span><span class="sxs-lookup"><span data-stu-id="47804-248">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="47804-249">**範例：** 
 ![模擬描述 details1 的影像](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="47804-249">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![模擬描述 details2 的影像](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="47804-251">評估報告</span><span class="sxs-lookup"><span data-stu-id="47804-251">Evaluation report</span></span>
<span data-ttu-id="47804-252">實驗室報告會摘要在裝置上進行模擬的結果。</span><span class="sxs-lookup"><span data-stu-id="47804-252">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![評估報告的影像](images/eval-report.png)

<span data-ttu-id="47804-254">您很快就能看到：</span><span class="sxs-lookup"><span data-stu-id="47804-254">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="47804-255">觸發的事件</span><span class="sxs-lookup"><span data-stu-id="47804-255">Incidents that were triggered</span></span>
- <span data-ttu-id="47804-256">產生的提醒</span><span class="sxs-lookup"><span data-stu-id="47804-256">Generated alerts</span></span>
- <span data-ttu-id="47804-257">針對公開層級的評估</span><span class="sxs-lookup"><span data-stu-id="47804-257">Assessments on exposure level</span></span> 
- <span data-ttu-id="47804-258">觀測威脅類別</span><span class="sxs-lookup"><span data-stu-id="47804-258">Threat categories observed</span></span>
- <span data-ttu-id="47804-259">偵測來源</span><span class="sxs-lookup"><span data-stu-id="47804-259">Detection sources</span></span>
- <span data-ttu-id="47804-260">自動化調查</span><span class="sxs-lookup"><span data-stu-id="47804-260">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="47804-261">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="47804-261">Provide feedback</span></span>
<span data-ttu-id="47804-262">您的意見反應可協助我們從高級攻擊中保護您的環境。</span><span class="sxs-lookup"><span data-stu-id="47804-262">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="47804-263">與產品功能和評估結果共用您的經驗與印象。</span><span class="sxs-lookup"><span data-stu-id="47804-263">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="47804-264">您可以選擇 [ **提供意見** 反應]，讓我們知道您的想法。</span><span class="sxs-lookup"><span data-stu-id="47804-264">Let us know what you think, by selecting **Provide feedback**.</span></span>

![提供意見反應的影像](images/send-us-feedback-eval-lab.png)
