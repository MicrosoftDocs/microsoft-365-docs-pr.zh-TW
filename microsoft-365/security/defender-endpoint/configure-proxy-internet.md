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
ms.openlocfilehash: 0de55eefe2f7dd8c9f891fbe126a68a49699ecd3
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594094"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="3c912-104">設定裝置 Proxy 和網際網路連線能力設定</span><span class="sxs-lookup"><span data-stu-id="3c912-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c912-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3c912-105">**Applies to:**</span></span>
- [<span data-ttu-id="3c912-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3c912-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c912-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c912-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3c912-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3c912-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3c912-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3c912-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="3c912-110">Defender for endpoint 感應器需要 Microsoft Windows HTTP (WinHTTP) 才能報告感應器資料，並與 defender for Endpoint service 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3c912-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="3c912-111">內嵌的 Defender for Endpoint 感應器會在使用 LocalSystem 帳戶的系統內容中執行。</span><span class="sxs-lookup"><span data-stu-id="3c912-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="3c912-112">感應器會使用 Microsoft Windows HTTP 服務 (WinHTTP) 來啟用與 Defender for Endpoint cloud service 的通訊。</span><span class="sxs-lookup"><span data-stu-id="3c912-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="3c912-113">對於使用 正向 Proxy 作為網際網路閘道的組織，可以使用網路保護來調查 Proxy 背後的情況。</span><span class="sxs-lookup"><span data-stu-id="3c912-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="3c912-114">有關詳細資訊，請參閱[調查正向 Proxy 背後發生的連線事件](investigate-behind-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="3c912-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="3c912-115">WinHTTP 設定設定與 Windows internet (WinINet) Internet 流覽 proxy 設定無關，而且只能使用下列探索方法來探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="3c912-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="3c912-116">自動探索方法：</span><span class="sxs-lookup"><span data-stu-id="3c912-116">Auto-discovery methods:</span></span>

  - <span data-ttu-id="3c912-117">透明Proxy</span><span class="sxs-lookup"><span data-stu-id="3c912-117">Transparent proxy</span></span>

  - <span data-ttu-id="3c912-118">網頁 Proxy 自動探索通訊協定（WPAD）</span><span class="sxs-lookup"><span data-stu-id="3c912-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="3c912-119">如果您的網路拓撲中使用的是透明 proxy 或 WPAD，您不需要特殊的設定。</span><span class="sxs-lookup"><span data-stu-id="3c912-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="3c912-120">如需 proxy 中的端點 URL 排除的相關資訊，請參閱 [Enable access To Defender For endpoint service URLs in proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="3c912-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="3c912-121">手動靜態 Proxy 組態：</span><span class="sxs-lookup"><span data-stu-id="3c912-121">Manual static proxy configuration:</span></span>

  - <span data-ttu-id="3c912-122">基於登錄的設定</span><span class="sxs-lookup"><span data-stu-id="3c912-122">Registry based configuration</span></span>

  - <span data-ttu-id="3c912-123">使用 netsh 命令設定的 WinHTTP – 僅適用於穩定拓撲中的桌面 (例如：同一 Proxy 後公司網路中的桌面)</span><span class="sxs-lookup"><span data-stu-id="3c912-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="3c912-124">使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="3c912-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="3c912-125">設定登錄型靜態 proxy，只允許當電腦不允許連線至網際網路時，僅限 Defender for Endpoint 感應器報告診斷資料，並與 Defender for Endpoint service 通訊。</span><span class="sxs-lookup"><span data-stu-id="3c912-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not permitted to connect to the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="3c912-126">在 Windows 10 或 Windows Server 2019 上使用此選項時，建議使用下列 (或更新版本) 產生及累計更新彙總套件：</span><span class="sxs-lookup"><span data-stu-id="3c912-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span>
>
> - <span data-ttu-id="3c912-127">Windows 10，版本1809或 Windows Server 2019-https://support.microsoft.com/kb/5001384</span><span class="sxs-lookup"><span data-stu-id="3c912-127">Windows 10, version 1809 or Windows Server 2019 - https://support.microsoft.com/kb/5001384</span></span>
> - <span data-ttu-id="3c912-128">Windows 10，版本 1909-https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="3c912-128">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span>
> - <span data-ttu-id="3c912-129">Windows 10，版本 2004-https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="3c912-129">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span>
> - <span data-ttu-id="3c912-130">Windows 10，版本 20H2-https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="3c912-130">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span>
>
> <span data-ttu-id="3c912-131">這些更新會改善 CnC (命令和控制) 通道的連線和可靠性。</span><span class="sxs-lookup"><span data-stu-id="3c912-131">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span>

<span data-ttu-id="3c912-132">靜態 Proxy 可以透過群組原則 (GP) 設定。</span><span class="sxs-lookup"><span data-stu-id="3c912-132">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="3c912-133">可以在以下位置找到群組原則：</span><span class="sxs-lookup"><span data-stu-id="3c912-133">The group policy can be found under:</span></span>

- <span data-ttu-id="3c912-134">**系統管理範本 > Windows 元件 > 資料收集和預覽版本 > 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用狀況**</span><span class="sxs-lookup"><span data-stu-id="3c912-134">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

  <span data-ttu-id="3c912-135">設定為 [ **已啟用** ]，然後選取 [ **停用已驗證的 Proxy 使用**]。</span><span class="sxs-lookup"><span data-stu-id="3c912-135">Set it to **Enabled** and select **Disable Authenticated Proxy usage**.</span></span>

  ![群組原則 setting1 的影像](images/atp-gpo-proxy1.png)

- <span data-ttu-id="3c912-137">系統 **管理範本 > Windows 元件 > 資料收集和預覽版本 > 設定連線使用者體驗和遙測**：</span><span class="sxs-lookup"><span data-stu-id="3c912-137">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

  <span data-ttu-id="3c912-138">設定 Proxy</span><span class="sxs-lookup"><span data-stu-id="3c912-138">Configure the proxy</span></span>

  ![群組原則 setting2 的影像](images/atp-gpo-proxy2.png)

  <span data-ttu-id="3c912-140">原則會設定兩個登錄值， `TelemetryProxyServer` REG_SZ 和 REG_DWORD，都是登錄機 `DisableEnterpriseAuthProxy` 碼底下 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 。</span><span class="sxs-lookup"><span data-stu-id="3c912-140">The policy sets two registry values, `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD, under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

  <span data-ttu-id="3c912-141">登錄值 `TelemetryProxyServer` 採用下列字串格式：</span><span class="sxs-lookup"><span data-stu-id="3c912-141">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

  ```text
  <server name or ip>:<port>
  ```

  <span data-ttu-id="3c912-142">例如：10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="3c912-142">For example: 10.0.0.6:8080</span></span>

  <span data-ttu-id="3c912-143">此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。</span><span class="sxs-lookup"><span data-stu-id="3c912-143">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="3c912-144">使用 netsh 命令手動設定 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="3c912-144">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="3c912-145">使用 netsh 設定全系統的靜態 Proxy。</span><span class="sxs-lookup"><span data-stu-id="3c912-145">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="3c912-146">這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="3c912-146">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="3c912-147">變更拓撲的膝上型電腦 (例如：從 office 到 home) ，將無法使用 netsh。</span><span class="sxs-lookup"><span data-stu-id="3c912-147">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="3c912-148">使用基於登錄的靜態 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="3c912-148">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="3c912-149">開啟提高權限的命令列：</span><span class="sxs-lookup"><span data-stu-id="3c912-149">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="3c912-150">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="3c912-150">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="3c912-151">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="3c912-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="3c912-152">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="3c912-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="3c912-153">例如：`netsh winhttp set proxy 10.0.0.6:8080`</span><span class="sxs-lookup"><span data-stu-id="3c912-153">For example: `netsh winhttp set proxy 10.0.0.6:8080`</span></span>

<span data-ttu-id="3c912-154">要重設 winhttpProxy，請輸入以下命令並按 **Enter** 鍵：</span><span class="sxs-lookup"><span data-stu-id="3c912-154">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="3c912-155">若要瞭解詳細資訊。，請參見 [Netsh 命令語法、上下文和格式](/windows-server/networking/technologies/netsh/netsh-contexts)。</span><span class="sxs-lookup"><span data-stu-id="3c912-155">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="3c912-156">在 proxy 伺服器中啟用 Microsoft Defender for Endpoint service URLs 的存取權</span><span class="sxs-lookup"><span data-stu-id="3c912-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="3c912-157">如果 Proxy 或防火牆在預設情況下封鎖所有流量，並且只允許特定網域通過，請將可下載工作表中列出的網域新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="3c912-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="3c912-158">下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。</span><span class="sxs-lookup"><span data-stu-id="3c912-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="3c912-159">您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取，否則您可能需要為他們建立一個 *允許* 規則。</span><span class="sxs-lookup"><span data-stu-id="3c912-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


| <span data-ttu-id="3c912-160">網域清單的試算表</span><span class="sxs-lookup"><span data-stu-id="3c912-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="3c912-161">描述</span><span class="sxs-lookup"><span data-stu-id="3c912-161">Description</span></span> |
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | <span data-ttu-id="3c912-163">服務位置、地理位置和作業系統的特定 DNS 記錄試算表。</span><span class="sxs-lookup"><span data-stu-id="3c912-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="3c912-164">在這裡下載試算表。</span><span class="sxs-lookup"><span data-stu-id="3c912-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="3c912-165">如果 Proxy 或防火牆啟用了 HTTPS 掃描 (SSL 檢查)，則從 HTTPS 掃描中排除上表中列出的網域。</span><span class="sxs-lookup"><span data-stu-id="3c912-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="3c912-166">settings-win.data.microsoft.com 只有 Windows 10 在執行版本1803或更早版本的裝置時才需要。</span><span class="sxs-lookup"><span data-stu-id="3c912-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="3c912-167">只有當您具有執行版本1803或更新版本的 Windows 10 裝置時，才需要在其中包含 v20 的 URLs。</span><span class="sxs-lookup"><span data-stu-id="3c912-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="3c912-168">例如， `us-v20.events.data.microsoft.com` 在執行版本1803或更新版本的 Windows 10 裝置，以及架至 US 資料儲存體地區時，是必要的。</span><span class="sxs-lookup"><span data-stu-id="3c912-168">For example, `us-v20.events.data.microsoft.com` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="3c912-169">如果您在環境中使用 Microsoft Defender 防毒軟體，請參閱[設定 Microsoft Defender 防毒軟體雲端服務的網路](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)連線。</span><span class="sxs-lookup"><span data-stu-id="3c912-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="3c912-170">如果 proxy 或防火牆封鎖匿名流量，則在端點感應器的 Defender 是從系統內容連線時，請確定先前所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="3c912-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="3c912-171">Microsoft Monitoring Agent (MMA) -舊版本 Windows 用戶端或 Windows 伺服器的 proxy 和防火牆需求</span><span class="sxs-lookup"><span data-stu-id="3c912-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="3c912-172">下表列出與 Log Analytics 代理程式通訊所需的 proxy 及防火牆設定資訊 (通常稱為 Microsoft Monitoring Agent) 舊版 Windows，例如 Windows 7 SP1、Windows 8.1 Windows Server 2008 R2、Windows Server 2012 R2 及 Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="3c912-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="3c912-173">代理人資源</span><span class="sxs-lookup"><span data-stu-id="3c912-173">Agent Resource</span></span>|<span data-ttu-id="3c912-174">連接埠</span><span class="sxs-lookup"><span data-stu-id="3c912-174">Ports</span></span> |<span data-ttu-id="3c912-175">方向</span><span class="sxs-lookup"><span data-stu-id="3c912-175">Direction</span></span> |<span data-ttu-id="3c912-176">略過 HTTPS 檢查</span><span class="sxs-lookup"><span data-stu-id="3c912-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="3c912-177">ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="3c912-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="3c912-178">埠443</span><span class="sxs-lookup"><span data-stu-id="3c912-178">Port 443</span></span> |<span data-ttu-id="3c912-179">出境</span><span class="sxs-lookup"><span data-stu-id="3c912-179">Outbound</span></span>|<span data-ttu-id="3c912-180">是</span><span class="sxs-lookup"><span data-stu-id="3c912-180">Yes</span></span> |  
|<span data-ttu-id="3c912-181">oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="3c912-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="3c912-182">埠443</span><span class="sxs-lookup"><span data-stu-id="3c912-182">Port 443</span></span> |<span data-ttu-id="3c912-183">出境</span><span class="sxs-lookup"><span data-stu-id="3c912-183">Outbound</span></span>|<span data-ttu-id="3c912-184">是</span><span class="sxs-lookup"><span data-stu-id="3c912-184">Yes</span></span> |  
|<span data-ttu-id="3c912-185">blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="3c912-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="3c912-186">埠443</span><span class="sxs-lookup"><span data-stu-id="3c912-186">Port 443</span></span> |<span data-ttu-id="3c912-187">出境</span><span class="sxs-lookup"><span data-stu-id="3c912-187">Outbound</span></span>|<span data-ttu-id="3c912-188">是</span><span class="sxs-lookup"><span data-stu-id="3c912-188">Yes</span></span> |
|<span data-ttu-id="3c912-189">azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="3c912-189">\*.azure-automation.net</span></span> |<span data-ttu-id="3c912-190">埠443</span><span class="sxs-lookup"><span data-stu-id="3c912-190">Port 443</span></span> |<span data-ttu-id="3c912-191">出境</span><span class="sxs-lookup"><span data-stu-id="3c912-191">Outbound</span></span>|<span data-ttu-id="3c912-192">是</span><span class="sxs-lookup"><span data-stu-id="3c912-192">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="3c912-193">作為雲端式解決方案，IP 範圍可能會變更。</span><span class="sxs-lookup"><span data-stu-id="3c912-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="3c912-194">建議您移至 DNS 解析設定。</span><span class="sxs-lookup"><span data-stu-id="3c912-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="3c912-195">確認 Microsoft Monitoring Agent (MMA) 服務 URL 需求</span><span class="sxs-lookup"><span data-stu-id="3c912-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="3c912-196">使用舊版) 的 Microsoft Monitoring Agent (MMA Windows 時，請參閱下列指導，以消除特定環境的萬用字元 ( \* ) 需求。</span><span class="sxs-lookup"><span data-stu-id="3c912-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="3c912-197">使用 Microsoft Monitoring Agent (MMA) 的舊版作業系統 (如需詳細資訊，請參閱[在 defender 上的上架先前版本 Windows](https://go.microsoft.com/fwlink/p/?linkid=2010326)和[板載 Windows server](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="3c912-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="3c912-198">確定機器已成功地報告 Microsoft Defender 資訊安全中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="3c912-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="3c912-199">從 "C:\Program Files \ Microsoft Monitoring Agent \Agent] 執行 TestCloudConnection.exe 工具，以驗證連線，並查看特定工作區所需的 URLs。</span><span class="sxs-lookup"><span data-stu-id="3c912-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="3c912-200">在 [Microsoft Defender for Endpoint URLs] 清單中檢查您地區的完整需求清單 (請參閱服務 URLs [試算表](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)) 。</span><span class="sxs-lookup"><span data-stu-id="3c912-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

    ![Windows PowerShell 中的系統管理員影像](images/admin-powershell.png)

<span data-ttu-id="3c912-202">Ods.opinsights.azure.com、oms.opinsights.azure.com 和 \*. agentsvc.azure-automation.net URL 端點中所用的萬用字元 ( \* ) 可以取代為您的特定 Workspace 識別碼。</span><span class="sxs-lookup"><span data-stu-id="3c912-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="3c912-203">工作區識別碼是針對您的環境和工作區所特有，可在 Microsoft Defender 資訊安全中心入口網站的承租人內架區段中找到。</span><span class="sxs-lookup"><span data-stu-id="3c912-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="3c912-204">您可以使用測試結果的「防火牆 Rule： blob.core.windows.net」區段中所示的 URLs，取代 blob.core.windows.net URL 端點。</span><span class="sxs-lookup"><span data-stu-id="3c912-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="3c912-205">在使用 Azure Defender 進行上架時，可能會使用多個工作區。</span><span class="sxs-lookup"><span data-stu-id="3c912-205">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="3c912-206">您必須在每個工作區的架電腦上執行上述 TestCloudConnection.exe 程式 (，以判斷是否) 工作區之間的 blob.core.windows.net URLs 的任何變更。</span><span class="sxs-lookup"><span data-stu-id="3c912-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="3c912-207">驗證 Endpoint service URLs 的用戶端與 Microsoft Defender 的連線能力</span><span class="sxs-lookup"><span data-stu-id="3c912-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="3c912-208">驗證 Proxy 設定是否成功完成，WinHTTP 是否可以在您的環境中發現 Proxy 伺服器並透過 Proxy 伺服器進行通訊，以及 Proxy 伺服器是否允許到適用於端點的 Defender 服務 URL 的通訊息。</span><span class="sxs-lookup"><span data-stu-id="3c912-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="3c912-209">將[MDATP Client Analyzer 工具](https://aka.ms/mdatpanalyzer)下載至執行 Endpoint for Endpoint 感應器的電腦。</span><span class="sxs-lookup"><span data-stu-id="3c912-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="3c912-210">擷取裝置上 MDATPClientAnalyzer.zip 的內容。</span><span class="sxs-lookup"><span data-stu-id="3c912-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="3c912-211">開啟提高權限的命令列：</span><span class="sxs-lookup"><span data-stu-id="3c912-211">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="3c912-212">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="3c912-212">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="3c912-213">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="3c912-213">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="3c912-214">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="3c912-214">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="3c912-215">以 MDATPClientAnalyzer 工具下載所在的路徑取代 *HardDrivePath* ，例如：</span><span class="sxs-lookup"><span data-stu-id="3c912-215">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example:</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="3c912-216">在 *HardDrivePath* 中使用的資料夾中，解壓縮工具所建立的 *MDATPClientAnalyzerResult.zip* 檔案。</span><span class="sxs-lookup"><span data-stu-id="3c912-216">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="3c912-217">開啟 *MDATPClientAnalyzerResult.txt* 並驗證是否已執行 Proxy 設定步驟以啟用伺服器發現和對服務 URL 的存取。</span><span class="sxs-lookup"><span data-stu-id="3c912-217">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>

   <span data-ttu-id="3c912-218">該工具檢查適用於端點的 Defender 用戶端設定為與之互動的適用於端點的 Defender 服務 URL 的連線性。</span><span class="sxs-lookup"><span data-stu-id="3c912-218">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="3c912-219">然後，它將結果列印到每個可能用於與適用於端點的 Defender 服務進行通訊之 URL 的 *MDATPClientAnalyzerResult.txt* 文件中。</span><span class="sxs-lookup"><span data-stu-id="3c912-219">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="3c912-220">例如：</span><span class="sxs-lookup"><span data-stu-id="3c912-220">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="3c912-221">如果至少有一個連線選項退回 (200) 適用於端點的 Defender 用戶端可以使用此連線方法與測試的 URL 正確通訊。</span><span class="sxs-lookup"><span data-stu-id="3c912-221">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span>

<span data-ttu-id="3c912-222">但是，如果連線檢查結果顯示失敗，則會顯示 HTTP 錯誤 (請參閱 HTTP 狀態碼)。</span><span class="sxs-lookup"><span data-stu-id="3c912-222">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="3c912-223">然後，您可以在 proxy 伺服器中，使用 [ [啟用 Endpoint To Defender For Endpoint service URLs](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)] 中所示的表格中所示的 URLs。</span><span class="sxs-lookup"><span data-stu-id="3c912-223">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="3c912-224">您將使用的 URLs 取決於上架程式期間所選取的區域。</span><span class="sxs-lookup"><span data-stu-id="3c912-224">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="3c912-225">連線分析程式工具與 ASR 規則不相容[封鎖源自 PSExec 和 WMI 命令的流程建立](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="3c912-225">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="3c912-226">需要暫時停用此規則才能執行連線工具。</span><span class="sxs-lookup"><span data-stu-id="3c912-226">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="3c912-227">設定 TelemetryProxyServer 時，在 [登錄] 或 [透過群組原則] 中，當其無法存取定義的 proxy 時，它會回復為 [直屬]。</span><span class="sxs-lookup"><span data-stu-id="3c912-227">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c912-228">相關主題</span><span class="sxs-lookup"><span data-stu-id="3c912-228">Related topics</span></span>

- [<span data-ttu-id="3c912-229">將 Windows 10 裝置上線</span><span class="sxs-lookup"><span data-stu-id="3c912-229">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="3c912-230">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="3c912-230">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
