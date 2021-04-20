---
title: 設定裝置 proxy 和網際網路連線設定
description: 設定 Microsoft Defender for Endpoint proxy 和 internet 設定，以啟用與雲端服務之間的通訊。
keywords: 設定、proxy、internet、internet 連線、設定、proxy 設定、netsh、winHTTP、proxy 伺服器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ebfff7721bc61012811a66146079ac9758889594
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893598"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="ffa4a-104">設定裝置 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="ffa4a-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ffa4a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ffa4a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ffa4a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ffa4a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ffa4a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffa4a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ffa4a-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ffa4a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ffa4a-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="ffa4a-110">您必須使用 Microsoft Windows HTTP (WinHTTP) 來報告感應器資料，並與 Defender for Endpoint service 進行通訊，才能使用該 Endpoint 感應器的 Defender。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="ffa4a-111">內嵌的 Defender for Endpoint 感應器會在使用 LocalSystem 帳戶的系統內容中執行。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="ffa4a-112">感應器會使用 Microsoft Windows HTTP 服務 (WinHTTP) 來啟用與 Defender for Endpoint cloud service 的通訊。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="ffa4a-113">對於使用 正向 Proxy 作為網際網路閘道的組織，可以使用網路保護來調查 Proxy 背後的情況。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="ffa4a-114">有關詳細資訊，請參閱[調查正向 Proxy 背後發生的連線事件](investigate-behind-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="ffa4a-115">WinHTTP 設定設定與 Windows Internet (WinINet) Internet 流覽 proxy 設定無關，而且只能使用下列探索方法來探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="ffa4a-116">自動探索方法：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="ffa4a-117">透明Proxy</span><span class="sxs-lookup"><span data-stu-id="ffa4a-117">Transparent proxy</span></span>
  - <span data-ttu-id="ffa4a-118">網頁 Proxy 自動探索通訊協定（WPAD）</span><span class="sxs-lookup"><span data-stu-id="ffa4a-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="ffa4a-119">如果您的網路拓撲中使用的是透明 proxy 或 WPAD，您不需要特殊的設定。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="ffa4a-120">如需 proxy 中的端點 URL 排除的相關資訊，請參閱 [Enable access To Defender For endpoint service URLs in proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="ffa4a-121">手動靜態 Proxy 組態：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="ffa4a-122">基於登錄的設定</span><span class="sxs-lookup"><span data-stu-id="ffa4a-122">Registry based configuration</span></span>
  - <span data-ttu-id="ffa4a-123">使用 netsh 命令設定的 WinHTTP – 僅適用於穩定拓撲中的桌面 (例如：同一 Proxy 後公司網路中的桌面)</span><span class="sxs-lookup"><span data-stu-id="ffa4a-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="ffa4a-124">使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="ffa4a-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="ffa4a-125">設定登錄型靜態 proxy，只允許當電腦不允許連線至網際網路時，僅限 Defender for Endpoint 感應器報告診斷資料，並與 Defender for Endpoint service 通訊。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

> [!NOTE]
> - <span data-ttu-id="ffa4a-126">在 Windows 10 或 Windows Server 2019 上使用此選項時，建議您在下列 (或更新版本) 組建和累計更新彙總套件：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span></br>
> <span data-ttu-id="ffa4a-127">Windows 10，版本 1909- https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="ffa4a-127">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span></br>
> <span data-ttu-id="ffa4a-128">Windows 10，版本 2004- https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="ffa4a-128">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="ffa4a-129">Windows 10，版本 20H2- https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="ffa4a-129">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="ffa4a-130">這些更新會改善 CnC (命令和控制) 通道的連線和可靠性。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-130">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span></br>

<span data-ttu-id="ffa4a-131">靜態 Proxy 可以透過群組原則 (GP) 設定。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-131">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="ffa4a-132">可以在以下位置找到群組原則：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-132">The group policy can be found under:</span></span>

- <span data-ttu-id="ffa4a-133">系統管理範本 > Windows 元件 > 資料收集和預覽組建 > 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用狀況</span><span class="sxs-lookup"><span data-stu-id="ffa4a-133">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="ffa4a-134">將其設定為 [ **啟用** ]，然後選取 [ **停用已驗證的 Proxy 使用**：] ![ 群組原則 setting1 的影像](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="ffa4a-134">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="ffa4a-135">系統 **管理範本 > Windows 元件 > 資料收集和預覽組建 > 設定連線的使用者經驗和遙測**：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-135">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="ffa4a-136">設定 proxy：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-136">Configure the proxy:</span></span><br>
    <span data-ttu-id="ffa4a-137">![群組原則 setting2 的影像](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="ffa4a-137">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="ffa4a-138">原則將登錄機碼 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的兩個登錄值 `TelemetryProxyServer` 設定為 REG\u SZ，`DisableEnterpriseAuthProxy` 設定為 REG\u DWORD。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-138">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="ffa4a-139">登錄值 `TelemetryProxyServer` 採用下列字串格式：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-139">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="ffa4a-140">例如：10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="ffa4a-140">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="ffa4a-141">此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-141">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="ffa4a-142">使用 netsh 命令手動設定 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="ffa4a-142">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="ffa4a-143">使用 netsh 設定全系統的靜態 Proxy。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-143">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="ffa4a-144">這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-144">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="ffa4a-145">變更拓撲的膝上型電腦 (例如：從 office 到 home) ，將無法使用 netsh。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-145">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="ffa4a-146">使用基於登錄的靜態 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-146">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="ffa4a-147">開啟提高權限的命令列：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-147">Open an elevated command-line:</span></span>

    <span data-ttu-id="ffa4a-148">a.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-148">a.</span></span> <span data-ttu-id="ffa4a-149">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-149">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="ffa4a-150">b.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-150">b.</span></span> <span data-ttu-id="ffa4a-151">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="ffa4a-152">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="ffa4a-153">例如：netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="ffa4a-153">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="ffa4a-154">若要重設 winHTTP proxy，請輸入下列命令，然後按 **enter**</span><span class="sxs-lookup"><span data-stu-id="ffa4a-154">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="ffa4a-155">若要瞭解詳細資訊。，請參見 [Netsh 命令語法、上下文和格式](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts)。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-155">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="ffa4a-156">在 proxy 伺服器中啟用 Microsoft Defender for Endpoint service URLs 的存取權</span><span class="sxs-lookup"><span data-stu-id="ffa4a-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="ffa4a-157">如果 Proxy 或防火牆在預設情況下封鎖所有流量，並且只允許特定網域通過，請將可下載工作表中列出的網域新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="ffa4a-158">下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="ffa4a-159">您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取，否則您可能需要為他們建立一個 *允許* 規則。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="ffa4a-160">**網域清單的試算表**</span><span class="sxs-lookup"><span data-stu-id="ffa4a-160">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="ffa4a-161">**描述**</span><span class="sxs-lookup"><span data-stu-id="ffa4a-161">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | <span data-ttu-id="ffa4a-163">服務位置、地理位置和作業系統的特定 DNS 記錄試算表。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="ffa4a-164">在這裡下載試算表。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="ffa4a-165">如果 Proxy 或防火牆啟用了 HTTPS 掃描 (SSL 檢查)，則從 HTTPS 掃描中排除上表中列出的網域。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="ffa4a-166">settings-win.data.microsoft.com 只有在您有執行版本1803或更早版本的 Windows 10 裝置時才需要。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="ffa4a-167">只有當您有執行版本1803或更新版本的 Windows 10 裝置時，才需要在其中包含 v20 的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="ffa4a-168">例如， ```us-v20.events.data.microsoft.com``` 在執行版本1803或更新版本的 Windows 10 裝置，以及架至 US Data Storage region 時，是必要的。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-168">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="ffa4a-169">如果您在環境中使用 Microsoft Defender 防病毒，請參閱 [設定 Microsoft Defender 防病毒雲端服務的網路](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)連線。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="ffa4a-170">如果 proxy 或防火牆封鎖匿名流量，則在端點感應器的 Defender 是從系統內容連線時，請確定先前所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="ffa4a-171">適用于舊版 Windows 用戶端或 Windows Server 的 Microsoft Monitoring Agent (MMA) proxy 及防火牆需求</span><span class="sxs-lookup"><span data-stu-id="ffa4a-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="ffa4a-172">下表列出與 Log Analytics 代理程式通訊所需的 proxy 及防火牆設定資訊 (通常稱為 Windows 7 SP1、Windows 8.1、Windows Server 2008 R2、Windows Server 2012 R2 和 Windows Server 2016 等舊版 Windows 的 Microsoft Monitoring Agent) 。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="ffa4a-173">代理人資源</span><span class="sxs-lookup"><span data-stu-id="ffa4a-173">Agent Resource</span></span>|<span data-ttu-id="ffa4a-174">連接埠</span><span class="sxs-lookup"><span data-stu-id="ffa4a-174">Ports</span></span> |<span data-ttu-id="ffa4a-175">方向</span><span class="sxs-lookup"><span data-stu-id="ffa4a-175">Direction</span></span> |<span data-ttu-id="ffa4a-176">略過 HTTPS 檢查</span><span class="sxs-lookup"><span data-stu-id="ffa4a-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="ffa4a-177">ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="ffa4a-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="ffa4a-178">埠443</span><span class="sxs-lookup"><span data-stu-id="ffa4a-178">Port 443</span></span> |<span data-ttu-id="ffa4a-179">出境</span><span class="sxs-lookup"><span data-stu-id="ffa4a-179">Outbound</span></span>|<span data-ttu-id="ffa4a-180">是</span><span class="sxs-lookup"><span data-stu-id="ffa4a-180">Yes</span></span> |  
|<span data-ttu-id="ffa4a-181">oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="ffa4a-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="ffa4a-182">埠443</span><span class="sxs-lookup"><span data-stu-id="ffa4a-182">Port 443</span></span> |<span data-ttu-id="ffa4a-183">出境</span><span class="sxs-lookup"><span data-stu-id="ffa4a-183">Outbound</span></span>|<span data-ttu-id="ffa4a-184">是</span><span class="sxs-lookup"><span data-stu-id="ffa4a-184">Yes</span></span> |  
|<span data-ttu-id="ffa4a-185">blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="ffa4a-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="ffa4a-186">埠443</span><span class="sxs-lookup"><span data-stu-id="ffa4a-186">Port 443</span></span> |<span data-ttu-id="ffa4a-187">出境</span><span class="sxs-lookup"><span data-stu-id="ffa4a-187">Outbound</span></span>|<span data-ttu-id="ffa4a-188">是</span><span class="sxs-lookup"><span data-stu-id="ffa4a-188">Yes</span></span> |
|<span data-ttu-id="ffa4a-189">azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="ffa4a-189">\*.azure-automation.net</span></span> |<span data-ttu-id="ffa4a-190">埠443</span><span class="sxs-lookup"><span data-stu-id="ffa4a-190">Port 443</span></span> |<span data-ttu-id="ffa4a-191">出境</span><span class="sxs-lookup"><span data-stu-id="ffa4a-191">Outbound</span></span>|<span data-ttu-id="ffa4a-192">是</span><span class="sxs-lookup"><span data-stu-id="ffa4a-192">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="ffa4a-193">作為雲端式解決方案，IP 範圍可能會變更。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="ffa4a-194">建議您移至 DNS 解析設定。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="ffa4a-195">確認 Microsoft Monitoring Agent (MMA) 服務 URL 需求</span><span class="sxs-lookup"><span data-stu-id="ffa4a-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="ffa4a-196">使用舊版 Windows 的 Microsoft Monitoring Agent (MMA) 時，請參閱下列指導，以消除特定環境的萬用字元 ( \* ) 需求。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="ffa4a-197">使用 Microsoft Monitoring Agent (MMA) 到 Endpoint for Endpoint (的先前作業系統如需詳細資訊，請參閱在 Defender for Endpoint 和[板載 windows server](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)[上的板載舊版 Windows](https://go.microsoft.com/fwlink/p/?linkid=2010326) 。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="ffa4a-198">確定已成功將機器報告至 Microsoft Defender Security Center 入口網站。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="ffa4a-199">從「C:\Program Files\Microsoft 監控 Agent\Agent] 中執行 TestCloudConnection.exe 工具，以驗證連線能力，並查看特定工作區的必要 URLs。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="ffa4a-200">在 [Microsoft Defender for Endpoint URLs] 清單中檢查您地區的完整需求清單 (請參閱服務 URLs [試算表](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)) 。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![Windows PowerShell 中的系統管理員影像](images/admin-powershell.png)

<span data-ttu-id="ffa4a-202">Ods.opinsights.azure.com、oms.opinsights.azure.com 和 \*. agentsvc.azure-automation.net URL 端點中所用的萬用字元 ( \* ) 可以取代為您的特定 Workspace 識別碼。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="ffa4a-203">工作區識別碼是針對您的環境和工作區所特有，可在您的租使用者的 Microsoft Defender 安全中心入口網站中的 [上架] 區段中找到。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="ffa4a-204">您可以使用測試結果的「防火牆 Rule： blob.core.windows.net」區段中所示的 URLs，取代 blob.core.windows.net URL 端點。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="ffa4a-205">在透過 Azure Security Center 上架的情況下 (ASC) 中，可能會使用多個工作區。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-205">In the case of onboarding via Azure Security Center (ASC), multiple workspaces maybe used.</span></span> <span data-ttu-id="ffa4a-206">您必須在每個工作區的架電腦上執行上述 TestCloudConnection.exe 程式 (，以判斷是否) 工作區之間的 blob.core.windows.net URLs 的任何變更。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="ffa4a-207">驗證 Endpoint service URLs 的用戶端與 Microsoft Defender 的連線能力</span><span class="sxs-lookup"><span data-stu-id="ffa4a-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="ffa4a-208">驗證 Proxy 設定是否成功完成，WinHTTP 是否可以在您的環境中發現 Proxy 伺服器並透過 Proxy 伺服器進行通訊，以及 Proxy 伺服器是否允許到適用於端點的 Defender 服務 URL 的通訊息。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="ffa4a-209">將 [MDATP 用戶端 Analyzer 工具](https://aka.ms/mdatpanalyzer) 下載至執行 Endpoint 感應器所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="ffa4a-210">擷取裝置上 MDATPClientAnalyzer.zip 的內容。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="ffa4a-211">開啟提高權限的命令列：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-211">Open an elevated command-line:</span></span>

    <span data-ttu-id="ffa4a-212">a.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-212">a.</span></span> <span data-ttu-id="ffa4a-213">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-213">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="ffa4a-214">b.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-214">b.</span></span>  <span data-ttu-id="ffa4a-215">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-215">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="ffa4a-216">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-216">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="ffa4a-217">例如，用下載 MDATPClientAnalyzer 工具的路徑取代 *HardDrivePath*</span><span class="sxs-lookup"><span data-stu-id="ffa4a-217">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="ffa4a-218">在 *HardDrivePath* 中使用的資料夾中，解壓縮工具所建立的 *MDATPClientAnalyzerResult.zip* 檔案。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-218">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="ffa4a-219">開啟 *MDATPClientAnalyzerResult.txt* 並驗證是否已執行 Proxy 設定步驟以啟用伺服器發現和對服務 URL 的存取。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-219">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="ffa4a-220">該工具檢查適用於端點的 Defender 用戶端設定為與之互動的適用於端點的 Defender 服務 URL 的連線性。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-220">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="ffa4a-221">然後，它將結果列印到每個可能用於與適用於端點的 Defender 服務進行通訊之 URL 的 *MDATPClientAnalyzerResult.txt* 文件中。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-221">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="ffa4a-222">例如：</span><span class="sxs-lookup"><span data-stu-id="ffa4a-222">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="ffa4a-223">如果至少有一個連線選項退回 (200) 適用於端點的 Defender 用戶端可以使用此連線方法與測試的 URL 正確通訊。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-223">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="ffa4a-224">但是，如果連線檢查結果顯示失敗，則會顯示 HTTP 錯誤 (請參閱 HTTP 狀態碼)。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-224">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="ffa4a-225">然後，您可以在 proxy 伺服器中，使用 [ [啟用 Endpoint To Defender For Endpoint service URLs](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)] 中所示的表格中所示的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-225">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="ffa4a-226">您將使用的 URLs 取決於上架程式期間所選取的區域。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-226">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="ffa4a-227">連線分析程式工具與 ASR 規則不相容[封鎖源自 PSExec 和 WMI 命令的流程建立](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-227">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="ffa4a-228">需要暫時停用此規則才能執行連線工具。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-228">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="ffa4a-229">設定 TelemetryProxyServer 時，在 [登錄] 或 [透過群組原則] 中，當其無法存取定義的 proxy 時，它會回復為 [直屬]。</span><span class="sxs-lookup"><span data-stu-id="ffa4a-229">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ffa4a-230">相關主題</span><span class="sxs-lookup"><span data-stu-id="ffa4a-230">Related topics</span></span>

- [<span data-ttu-id="ffa4a-231">將 Windows 10 裝置上線</span><span class="sxs-lookup"><span data-stu-id="ffa4a-231">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="ffa4a-232">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="ffa4a-232">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
