---
title: 設定 Microsoft Defender for Endpoint 部署
description: 瞭解如何設定 Microsoft Defender for Endpoint 的部署
keywords: 部署、安裝、授權驗證、租使用者設定、網路設定
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636191"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="403e5-104">設定 Microsoft Defender for Endpoint 部署</span><span class="sxs-lookup"><span data-stu-id="403e5-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="403e5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="403e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="403e5-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="403e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="403e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="403e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="403e5-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="403e5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="403e5-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="403e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="403e5-110">為端點部署 Defender 是三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="403e5-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="403e5-111">[![部署階段-準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="403e5-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="403e5-112">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="403e5-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![部署階段-安裝程式](images/phase-diagrams/setup.png)<br><span data-ttu-id="403e5-114">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="403e5-114">Phase 2: Setup</span></span> | <span data-ttu-id="403e5-115">[![部署階段-板載](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="403e5-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="403e5-116">第 3 階段：導入</span><span class="sxs-lookup"><span data-stu-id="403e5-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="403e5-117">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="403e5-117">*You are here!*</span></span>||

<span data-ttu-id="403e5-118">您目前在設定階段。</span><span class="sxs-lookup"><span data-stu-id="403e5-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="403e5-119">在此部署案例中，您將會逐步指導您執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="403e5-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="403e5-120">授權驗證</span><span class="sxs-lookup"><span data-stu-id="403e5-120">Licensing validation</span></span>
- <span data-ttu-id="403e5-121">租用戶設定</span><span class="sxs-lookup"><span data-stu-id="403e5-121">Tenant configuration</span></span>
- <span data-ttu-id="403e5-122">網路設定</span><span class="sxs-lookup"><span data-stu-id="403e5-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="403e5-123">為便於您透過一般部署，此案例只會涵蓋 Microsoft Endpoint Configuration Manager 的使用。</span><span class="sxs-lookup"><span data-stu-id="403e5-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="403e5-124">Defender for Endpoint 支援使用其他上架工具，但不涵蓋部署指南中的那些案例。</span><span class="sxs-lookup"><span data-stu-id="403e5-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="403e5-125">如需詳細資訊，請參閱 [在 Microsoft Defender For Endpoint 中的板載裝置](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="403e5-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="403e5-126">檢查授權狀態</span><span class="sxs-lookup"><span data-stu-id="403e5-126">Check license state</span></span>

<span data-ttu-id="403e5-127">檢查授權狀態以及是否已正確布建，可透過系統管理中心或透過 **Microsoft Azure 入口網站** 進行。</span><span class="sxs-lookup"><span data-stu-id="403e5-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="403e5-128">若要查看您的授權，請移至 **Microsoft Azure 入口網站**，並流覽至「 [Microsoft Azure 入口網站授權」一節](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="403e5-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 授權頁面影像](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="403e5-130">或者，在系統管理中心中，流覽至 [**帳單**] [  >  **訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="403e5-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="403e5-131">在螢幕上，您會看到所有已布建的授權及其目前的 **狀態**。</span><span class="sxs-lookup"><span data-stu-id="403e5-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![計費授權影像](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="403e5-133">雲端服務提供者驗證</span><span class="sxs-lookup"><span data-stu-id="403e5-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="403e5-134">若要存取您公司所提供的授權，以及檢查授權的狀態，請移至系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="403e5-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="403e5-135">從 **夥伴入口網站** 中，選取 [**管理服務] > Office 365**]。</span><span class="sxs-lookup"><span data-stu-id="403e5-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="403e5-136">按一下 [ **合作夥伴入口網站** ] 連結時，將會自行開啟 [ **管理員** ] 選項，並可讓您存取客戶系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="403e5-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![O365 管理入口網站的影像](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="403e5-138">租使用者設定</span><span class="sxs-lookup"><span data-stu-id="403e5-138">Tenant Configuration</span></span>
<span data-ttu-id="403e5-139">上架至 Microsoft Defender for Endpoint 非常簡單。</span><span class="sxs-lookup"><span data-stu-id="403e5-139">Onboarding to Microsoft Defender for Endpoint is easy.</span></span> <span data-ttu-id="403e5-140">從 [流覽] 功能表中，選取 [端點] 區段下的任何專案，或任何 Microsoft 365 的 Defender 功能（例如事件、搜尋、動作中心或威脅分析）以啟動上架處理常式。</span><span class="sxs-lookup"><span data-stu-id="403e5-140">From the navigation menu, select any item under the Endpoints section, or any Microsoft 365 Defender feature such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span>

<span data-ttu-id="403e5-141">在網頁瀏覽器中，流覽至 [ [Microsoft 365 的安全性中心](https://security.microsoft.com)]。</span><span class="sxs-lookup"><span data-stu-id="403e5-141">From a web browser, navigate to the [Microsoft 365 Security Center](https://security.microsoft.com).</span></span>

## <a name="network-configuration"></a><span data-ttu-id="403e5-142">網路設定</span><span class="sxs-lookup"><span data-stu-id="403e5-142">Network configuration</span></span>
<span data-ttu-id="403e5-143">如果組織不需要端點使用 Proxy 來存取網際網路，請略過本節。</span><span class="sxs-lookup"><span data-stu-id="403e5-143">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="403e5-144">適用於端點的 Microsoft Defender 感應器需要 Microsoft Windows HTTP (WinHTTP) 回報感應器資料，並與適用於端點的 Microsoft Defender 服務通訊。</span><span class="sxs-lookup"><span data-stu-id="403e5-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="403e5-145">內嵌的 Microsoft Defender for Endpoint 感應器會在使用 LocalSystem 帳戶的系統上下文中執行。</span><span class="sxs-lookup"><span data-stu-id="403e5-145">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="403e5-146">感應器使用 Microsoft Windows HTTP Services （WinHTTP）來啟用與適用於端點的 Microsoft Defender 雲端服務的通訊。</span><span class="sxs-lookup"><span data-stu-id="403e5-146">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="403e5-147">WinHTTP 設定設定與 Windows internet (WinINet) Internet 流覽 proxy 設定無關，而且只能使用下列探索方法來探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="403e5-147">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="403e5-148">**自動探索方法：**</span><span class="sxs-lookup"><span data-stu-id="403e5-148">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="403e5-149">透明Proxy</span><span class="sxs-lookup"><span data-stu-id="403e5-149">Transparent proxy</span></span>

-   <span data-ttu-id="403e5-150">Web Proxy 自動探索通訊協定 (WPAD) </span><span class="sxs-lookup"><span data-stu-id="403e5-150">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="403e5-151">如果已在網路拓撲中執行透明 proxy 或 WPAD，則不需要特殊的設定。</span><span class="sxs-lookup"><span data-stu-id="403e5-151">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="403e5-152">如需 proxy 中 Microsoft Defender for Endpoint URL 排除專案的詳細資訊，請參閱本檔中的 [Proxy 服務 URLs](production-deployment.md#proxy-service-urls) 一節，以取得 URLs 允許清單或 [設定裝置 Proxy 和網際網路連線設定](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="403e5-152">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="403e5-153">**手動靜態 Proxy 組態：**</span><span class="sxs-lookup"><span data-stu-id="403e5-153">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="403e5-154">基於登錄的設定</span><span class="sxs-lookup"><span data-stu-id="403e5-154">Registry-based configuration</span></span>

-   <span data-ttu-id="403e5-155">使用 netsh 命令設定 WinHTTP</span><span class="sxs-lookup"><span data-stu-id="403e5-155">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="403e5-156">僅適用于穩定拓撲中的桌上型電腦 (例如，公司網路中位於相同 proxy 的桌面) </span><span class="sxs-lookup"><span data-stu-id="403e5-156">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="403e5-157">使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="403e5-157">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="403e5-158">設定登錄型靜態 proxy，只允許 Microsoft Defender for Endpoint 感應器報告診斷資料，並在電腦不允許連線至網際網路時，與 Microsoft Defender 的端點服務通訊。</span><span class="sxs-lookup"><span data-stu-id="403e5-158">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="403e5-159">靜態 Proxy 可以透過群組原則 (GP) 設定。</span><span class="sxs-lookup"><span data-stu-id="403e5-159">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="403e5-160">可以在以下位置找到群組原則：</span><span class="sxs-lookup"><span data-stu-id="403e5-160">The group policy can be found under:</span></span>

 - <span data-ttu-id="403e5-161">系統管理範本 \> Windows 元件 \> 資料收集和預覽版本 \> 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用方式</span><span class="sxs-lookup"><span data-stu-id="403e5-161">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="403e5-162">設定為 **啟用** ，並選取 [ **停用已驗證的 Proxy 使用**</span><span class="sxs-lookup"><span data-stu-id="403e5-162">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="403e5-163">開啟 [群組原則管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="403e5-163">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="403e5-164">建立原則，或根據組織的作法來編輯現有的原則。</span><span class="sxs-lookup"><span data-stu-id="403e5-164">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="403e5-165">編輯群組原則並流覽至 [系統 **管理範本] \> Windows 元件 \> 資料收集和預覽組建 \> 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用方式**。</span><span class="sxs-lookup"><span data-stu-id="403e5-165">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="403e5-166">![群組原則設定的影像](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="403e5-166">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="403e5-167">選取 **已啟用**。</span><span class="sxs-lookup"><span data-stu-id="403e5-167">Select **Enabled**.</span></span>
5. <span data-ttu-id="403e5-168">選取 [ **停用已驗證的 Proxy 使用**]。</span><span class="sxs-lookup"><span data-stu-id="403e5-168">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="403e5-169">流覽至系統 **管理範本 \> Windows 元件 \> 資料收集和預覽版本 \> 設定連線使用者經驗和遙測**。</span><span class="sxs-lookup"><span data-stu-id="403e5-169">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="403e5-170">![群組原則設定設定的影像](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="403e5-170">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="403e5-171">選取 **已啟用**。</span><span class="sxs-lookup"><span data-stu-id="403e5-171">Select **Enabled**.</span></span>
8. <span data-ttu-id="403e5-172">輸入 **Proxy 伺服器名稱**。</span><span class="sxs-lookup"><span data-stu-id="403e5-172">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="403e5-173">原則將登錄機碼 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的兩個登錄值 `TelemetryProxyServer` 設定為 REG\u SZ，`DisableEnterpriseAuthProxy` 設定為 REG\u DWORD。</span><span class="sxs-lookup"><span data-stu-id="403e5-173">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="403e5-174">登錄值 `TelemetryProxyServer` 採用下列字串格式：</span><span class="sxs-lookup"><span data-stu-id="403e5-174">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="403e5-175">例如：10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="403e5-175">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="403e5-176">此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。</span><span class="sxs-lookup"><span data-stu-id="403e5-176">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="403e5-177">使用 netsh 命令手動設定 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="403e5-177">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="403e5-178">使用 netsh 設定全系統的靜態 Proxy。</span><span class="sxs-lookup"><span data-stu-id="403e5-178">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="403e5-179">這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="403e5-179">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="403e5-180">變更拓撲的膝上型電腦 (例如：從 office 到 home) ，將無法使用 netsh。</span><span class="sxs-lookup"><span data-stu-id="403e5-180">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="403e5-181">使用基於登錄的靜態 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="403e5-181">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="403e5-182">開啟提高權限的命令列：</span><span class="sxs-lookup"><span data-stu-id="403e5-182">Open an elevated command line:</span></span>

    1. <span data-ttu-id="403e5-183">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="403e5-183">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="403e5-184">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="403e5-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="403e5-185">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="403e5-185">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="403e5-186">例如：netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="403e5-186">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="403e5-187">底層裝置的 Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="403e5-187">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="403e5-188">Down-Level 裝置包含 Windows 7 SP1 和 Windows 8.1 工作站，以及 Windows server CB 1803 之前 Windows Server 2012 server 2008 R2、Windows Server 2012、Windows Server 2016 r2 及 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="403e5-188">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="403e5-189">這些作業系統會將 proxy 設定為 Microsoft Management Agent 的一部分，以處理從端點到 Azure 的通訊。</span><span class="sxs-lookup"><span data-stu-id="403e5-189">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="403e5-190">如需如何在這些裝置上設定 proxy 的詳細資訊，請參閱《 Microsoft Management Agent Fast Deployment 指南》。</span><span class="sxs-lookup"><span data-stu-id="403e5-190">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="403e5-191">Proxy 服務 URLs</span><span class="sxs-lookup"><span data-stu-id="403e5-191">Proxy Service URLs</span></span>
<span data-ttu-id="403e5-192">只有當您具有 Windows 10、版本1803或更新版本的裝置時，才需要在其中包含 v20 的 URLs。</span><span class="sxs-lookup"><span data-stu-id="403e5-192">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="403e5-193">例如， ```us-v20.events.data.microsoft.com``` 只有在裝置位於 Windows 10，版本1803或更新版本時才需要。</span><span class="sxs-lookup"><span data-stu-id="403e5-193">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="403e5-194">如果 proxy 或防火牆封鎖匿名流量，當 Microsoft Defender for Endpoint 感應器從系統內容連線時，請確定所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="403e5-194">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="403e5-195">下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。</span><span class="sxs-lookup"><span data-stu-id="403e5-195">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="403e5-196">確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權，否則您可能需要建立專用的 *allow* 規則。</span><span class="sxs-lookup"><span data-stu-id="403e5-196">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="403e5-197">**網域清單的試算表**</span><span class="sxs-lookup"><span data-stu-id="403e5-197">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="403e5-198">**描述**</span><span class="sxs-lookup"><span data-stu-id="403e5-198">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | <span data-ttu-id="403e5-200">服務位置、地理位置和作業系統的特定 DNS 記錄試算表。</span><span class="sxs-lookup"><span data-stu-id="403e5-200">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="403e5-201">在這裡下載試算表。</span><span class="sxs-lookup"><span data-stu-id="403e5-201">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="403e5-202">Microsoft Defender for Endpoint service 後端 IP 範圍</span><span class="sxs-lookup"><span data-stu-id="403e5-202">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="403e5-203">如果您的網路裝置不支援以 DNS 為基礎的規則，請改為使用 IP 範圍。</span><span class="sxs-lookup"><span data-stu-id="403e5-203">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="403e5-204">已于 Azure cloud 中建立端點 for Endpoint，部署于下列地區：</span><span class="sxs-lookup"><span data-stu-id="403e5-204">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="403e5-205">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="403e5-205">AzureCloud.eastus</span></span>
- <span data-ttu-id="403e5-206">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="403e5-206">AzureCloud.eastus2</span></span>
- <span data-ttu-id="403e5-207">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="403e5-207">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="403e5-208">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="403e5-208">AzureCloud.northeurope</span></span>
- <span data-ttu-id="403e5-209">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="403e5-209">AzureCloud.westeurope</span></span>
- <span data-ttu-id="403e5-210">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="403e5-210">AzureCloud.uksouth</span></span>
- <span data-ttu-id="403e5-211">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="403e5-211">AzureCloud.ukwest</span></span>

<span data-ttu-id="403e5-212">您可以在 [AZURE Ip 範圍和服務標記–公用雲端](https://www.microsoft.com/download/details.aspx?id=56519)中找到 azure ip 範圍。</span><span class="sxs-lookup"><span data-stu-id="403e5-212">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="403e5-213">作為雲端式解決方案，IP 位址範圍可能會變更。</span><span class="sxs-lookup"><span data-stu-id="403e5-213">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="403e5-214">建議您移至以 DNS 為基礎的規則。</span><span class="sxs-lookup"><span data-stu-id="403e5-214">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="403e5-215">如果您是美國政府客戶，請參閱適用于 US 政府頁面的 [Defender For Endpoint](gov.md#service-backend-ip-ranges) 中的對應章節。</span><span class="sxs-lookup"><span data-stu-id="403e5-215">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="403e5-216">下一步</span><span class="sxs-lookup"><span data-stu-id="403e5-216">Next step</span></span>

<span data-ttu-id="403e5-217">![* * 階段3：板載 * *](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="403e5-217">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="403e5-218">[階段3：板載](onboarding.md)：對服務的板載裝置，使 Microsoft Defender for Endpoint service 可以從這些裝置取得感應器資料。</span><span class="sxs-lookup"><span data-stu-id="403e5-218">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
