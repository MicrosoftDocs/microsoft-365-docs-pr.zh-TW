---
title: 為端點 DLP 設定裝置 Proxy 和網際網路連線設定
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 瞭解如何為端點 DLP 設定裝置 Proxy 和網際網路連線設定。
ms.openlocfilehash: f2a62b5c7913b6f41c414310a97ab5f072f59642
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538612"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="7cfde-103">為端點 DLP 設定裝置 Proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="7cfde-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="7cfde-104">Microsoft 端點 DLP 使用 Microsoft Windows HTTP (WinHTTP) 報告資料並與 Microsoft 端點雲端服務通訊。</span><span class="sxs-lookup"><span data-stu-id="7cfde-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="7cfde-105">內嵌的端點 DLP 以 LocalSystem 帳戶在系統內容執行。</span><span class="sxs-lookup"><span data-stu-id="7cfde-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="7cfde-106">對於使用 正向 Proxy 作為網際網路閘道的組織，可以使用網路保護來調查 Proxy 背後的情況。</span><span class="sxs-lookup"><span data-stu-id="7cfde-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="7cfde-107">有關詳細資訊，請參閱[調查正向 Proxy 背後發生的連線事件](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy)。</span><span class="sxs-lookup"><span data-stu-id="7cfde-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="7cfde-108">WinHTTP 組態設定與 Windows 網際網路 (WinINet) 網際網路流覽 proxy 設定無關，且只能使用下列自動探索方法來探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="7cfde-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="7cfde-109">透明Proxy</span><span class="sxs-lookup"><span data-stu-id="7cfde-109">Transparent proxy</span></span>
- <span data-ttu-id="7cfde-110">網頁 Proxy 自動探索通訊協定（WPAD）</span><span class="sxs-lookup"><span data-stu-id="7cfde-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="7cfde-111">如果在網路拓撲中使用透明 proxy 或 WPAD，則不需要特殊的組態設定。</span><span class="sxs-lookup"><span data-stu-id="7cfde-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="7cfde-112">有關 Proxy 中適用於端點的 Defender URL 排除的更多資訊，請參閱[在 Proxy 伺服器中啟用對適用於端點的 Defender 雲端服務 URL 的存取](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="7cfde-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="7cfde-113">手動靜態 Proxy 組態：</span><span class="sxs-lookup"><span data-stu-id="7cfde-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="7cfde-114">基於登錄的設定</span><span class="sxs-lookup"><span data-stu-id="7cfde-114">Registry-based configuration</span></span>
    - <span data-ttu-id="7cfde-115">使用 netsh 命令設定的 WinHTTP – 僅適用於穩定拓撲中的桌面 (例如：同一 Proxy 後公司網路中的桌面)</span><span class="sxs-lookup"><span data-stu-id="7cfde-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="7cfde-116">使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="7cfde-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="7cfde-117">對於不允許連線至網際網路的端點裝置，需要設定基於登錄的靜態 Proxy。</span><span class="sxs-lookup"><span data-stu-id="7cfde-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="7cfde-118">您需要將其設定為僅允許 Microsoft 端點 DLP 報告診斷資料並與 Microsoft 端點雲端服務通訊。</span><span class="sxs-lookup"><span data-stu-id="7cfde-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="7cfde-119">靜態 Proxy 可以透過群組原則 (GP) 設定。</span><span class="sxs-lookup"><span data-stu-id="7cfde-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="7cfde-120">可以在以下位置找到群組原則：</span><span class="sxs-lookup"><span data-stu-id="7cfde-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="7cfde-121">開啟 **[系統管理範本] > [Windows 元件] > [資料收集和預覽組建] > [為連線的使用者體驗與遙測服務設定已驗證 Proxy]**</span><span class="sxs-lookup"><span data-stu-id="7cfde-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="7cfde-122">將其設定為 **[啟用]**，然後選取 **[停用已驗證的 Proxy]**：</span><span class="sxs-lookup"><span data-stu-id="7cfde-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![群組原則設定 1 的圖片](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="7cfde-124">開啟 **[系統管理範本] > [Windows 元件] > [資料收集和預覽組建] > [設定連線的使用者體驗與遙測]**：</span><span class="sxs-lookup"><span data-stu-id="7cfde-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="7cfde-125">設定 Proxy</span><span class="sxs-lookup"><span data-stu-id="7cfde-125">Configure the proxy</span></span>

![群組原則設置 2 的圖片](../media/atp-gpo-proxy2.png)

<span data-ttu-id="7cfde-127">原則將登錄機碼 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的兩個登錄值 `TelemetryProxyServer` 設定為 REG\u SZ，`DisableEnterpriseAuthProxy` 設定為 REG\u DWORD。</span><span class="sxs-lookup"><span data-stu-id="7cfde-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="7cfde-128">登錄值 TelemetryProxyServer 的格式為：\<server name or ip\>\<port\>。</span><span class="sxs-lookup"><span data-stu-id="7cfde-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="7cfde-129">例如：**10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="7cfde-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="7cfde-130">此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。</span><span class="sxs-lookup"><span data-stu-id="7cfde-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="7cfde-131">使用「netsh」命令手動設定 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="7cfde-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="7cfde-132">使用 netsh 設定全系統的靜態 Proxy。</span><span class="sxs-lookup"><span data-stu-id="7cfde-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="7cfde-133">這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="7cfde-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="7cfde-134">- 正在改變拓撲的膝上型電腦 (例如：從辦公室到家) 將出現 netsh 故障。</span><span class="sxs-lookup"><span data-stu-id="7cfde-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="7cfde-135">使用基於登錄的靜態 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="7cfde-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="7cfde-136">開啟提高權限的命令列：</span><span class="sxs-lookup"><span data-stu-id="7cfde-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="7cfde-137">轉至 **[開始]** 並輸入 **「cmd」**</span><span class="sxs-lookup"><span data-stu-id="7cfde-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="7cfde-138">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="7cfde-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="7cfde-139">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="7cfde-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="7cfde-140">例如：**netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="7cfde-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="7cfde-141">要重設 winhttpProxy，請輸入以下命令並按 **Enter** 鍵：</span><span class="sxs-lookup"><span data-stu-id="7cfde-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="7cfde-142">若要瞭解詳細資訊。，請參見 [Netsh 命令語法、上下文和格式](/windows-server/networking/technologies/netsh/netsh-contexts)。</span><span class="sxs-lookup"><span data-stu-id="7cfde-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="7cfde-143">在 Proxy 伺服器中啟用對端點 DLP 雲端服務 URL 的存取</span><span class="sxs-lookup"><span data-stu-id="7cfde-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="7cfde-144">如果 Proxy 或防火牆在預設情況下封鎖所有流量，並且只允許特定網域通過，請將可下載工作表中列出的網域新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="7cfde-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="7cfde-145">此[可下載的試算表](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)列出了網路必須能夠連線至的服務及其關聯的 URL。</span><span class="sxs-lookup"><span data-stu-id="7cfde-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="7cfde-146">應該確保沒有防火牆或網路篩選規則會拒絕存取這些 URL，或者可能需要專門為它們建立允許規則。</span><span class="sxs-lookup"><span data-stu-id="7cfde-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="7cfde-147">如果 Proxy 或防火牆啟用了 HTTPS 掃描 (SSL 檢查)，則從 HTTPS 掃描中排除上表中列出的網域。</span><span class="sxs-lookup"><span data-stu-id="7cfde-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="7cfde-148">如果 Proxy 或防火牆封鎖匿名流量，因為端點 DLP 是從系統内容連線的，請確保前面列出的 URL 中允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="7cfde-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="7cfde-149">驗證用戶端與 Microsoft 雲端服務 URL 的連線</span><span class="sxs-lookup"><span data-stu-id="7cfde-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="7cfde-150">驗證 Proxy 設定是否成功完成，WinHTTP 是否可以在您的環境中發現 Proxy 伺服器並透過 Proxy 伺服器進行通訊，以及 Proxy 伺服器是否允許到適用於端點的 Defender 服務 URL 的通訊息。</span><span class="sxs-lookup"><span data-stu-id="7cfde-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="7cfde-151">將 [MDATP 用戶端分析器工具](https://aka.ms/mdatpanalyzer)下載到執行端點 DLP 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="7cfde-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="7cfde-152">擷取裝置上 MDATPClientAnalyzer.zip 的內容。</span><span class="sxs-lookup"><span data-stu-id="7cfde-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="7cfde-153">開啟提高權限的命令列：</span><span class="sxs-lookup"><span data-stu-id="7cfde-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="7cfde-154">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="7cfde-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="7cfde-155">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="7cfde-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="7cfde-156">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="7cfde-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="7cfde-157">例如，用下載 MDATPClientAnalyzer 工具的路徑取代 *HardDrivePath*</span><span class="sxs-lookup"><span data-stu-id="7cfde-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="7cfde-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="7cfde-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="7cfde-159">在 _HardDrivePath\* 中使用的資料夾中擷取由工具建立的 **MDATPClientAnalyzerResult.zip** _ 文件。</span><span class="sxs-lookup"><span data-stu-id="7cfde-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="7cfde-160">開啟 **MDATPClientAnalyzerResult.txt** 並驗證是否已執行 Proxy 設定步驟以啟用伺服器發現和對服務 URL 的存取。</span><span class="sxs-lookup"><span data-stu-id="7cfde-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="7cfde-161">該工具檢查適用於端點的 Defender 用戶端設定為與之互動的適用於端點的 Defender 服務 URL 的連線性。</span><span class="sxs-lookup"><span data-stu-id="7cfde-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="7cfde-162">然後，它將結果列印到每個可能用於與適用於端點的 Defender 服務進行通訊之 URL 的 **MDATPClientAnalyzerResult.txt** 文件中。</span><span class="sxs-lookup"><span data-stu-id="7cfde-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="7cfde-163">例如：</span><span class="sxs-lookup"><span data-stu-id="7cfde-163">For example:</span></span>

    <span data-ttu-id="7cfde-164">**測試 URL：https://xxx.microsoft.com/xxx</br>1 - 預設 Proxy：成功 (200) </br>2 - Proxy 自動探索 (WPAD)：成功 (200) </br> 3 - 停用 Proxy：成功 (200) </br> 4 - 指定的 Proxy：不存在 </br> 5 - 命令列 Proxy：不存在**</span><span class="sxs-lookup"><span data-stu-id="7cfde-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="7cfde-165">如果至少有一個連線選項退回 (200) 適用於端點的 Defender 用戶端可以使用此連線方法與測試的 URL 正確通訊。</span><span class="sxs-lookup"><span data-stu-id="7cfde-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="7cfde-166">但是，如果連線檢查結果顯示失敗，則會顯示 HTTP 錯誤 (請參閱 HTTP 狀態碼)。</span><span class="sxs-lookup"><span data-stu-id="7cfde-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="7cfde-167">然後可以使用[啟用對端點 DLP 雲端服務 URL 的存取](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)中所示的表中的 URL。</span><span class="sxs-lookup"><span data-stu-id="7cfde-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="7cfde-168">您將使用的 URL 將取決於上線過程中選取的區域。</span><span class="sxs-lookup"><span data-stu-id="7cfde-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="7cfde-169">連線分析程式工具與 ASR 規則不相容[封鎖源自 PSExec 和 WMI 命令的流程建立](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="7cfde-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="7cfde-170">需要暫時停用此規則才能執行連線工具。</span><span class="sxs-lookup"><span data-stu-id="7cfde-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="7cfde-171">在登錄中或透過群組原則設定 TelemetryProxyServer 時，如果適用於端點的 Defender 無法存取定義的 Proxy，它將回復至 direct。</span><span class="sxs-lookup"><span data-stu-id="7cfde-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="7cfde-172">相關主題 • 上線 Windows 10 裝置 • Microsoft 端點 DLP 上線問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="7cfde-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="7cfde-173">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7cfde-173">See also</span></span>

- [<span data-ttu-id="7cfde-174">深入了解端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="7cfde-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="7cfde-175">使用端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="7cfde-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="7cfde-176">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="7cfde-176">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="7cfde-177">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7cfde-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="7cfde-178">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="7cfde-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="7cfde-179">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7cfde-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- <span data-ttu-id="7cfde-180">[Windows 10 電腦上線的工具及方法 ](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="7cfde-180">[Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="7cfde-181">Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="7cfde-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="7cfde-182">加入 Azure AD 的裝置</span><span class="sxs-lookup"><span data-stu-id="7cfde-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- <span data-ttu-id="7cfde-183">[下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。</span><span class="sxs-lookup"><span data-stu-id="7cfde-183">[Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)</span></span>