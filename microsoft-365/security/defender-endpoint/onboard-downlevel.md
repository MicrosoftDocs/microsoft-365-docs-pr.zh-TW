---
title: Microsoft Defender ATP 上的板載 Windows 版本
description: 上架支援的舊版 Windows 裝置，使其可將感應器資料傳送至 Microsoft Defender ATP 感應器
keywords: 板載，windows，7，81，oms，sp1，enterprise，pro，跌層級
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a70826ee6e245f6744d8fc64eaf06e8cd1bdb265
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056828"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="a502f-104">板載舊版 Windows</span><span class="sxs-lookup"><span data-stu-id="a502f-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a502f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a502f-105">**Applies to:**</span></span>
- [<span data-ttu-id="a502f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a502f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a502f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a502f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a502f-108">**平臺**</span><span class="sxs-lookup"><span data-stu-id="a502f-108">**Platforms**</span></span>
- <span data-ttu-id="a502f-109">Windows 7 SP1 企業版</span><span class="sxs-lookup"><span data-stu-id="a502f-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="a502f-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="a502f-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="a502f-111">Windows 8.1 專業版</span><span class="sxs-lookup"><span data-stu-id="a502f-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="a502f-112">Windows 8.1 企業版</span><span class="sxs-lookup"><span data-stu-id="a502f-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="a502f-113">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a502f-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="a502f-114">[註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="a502f-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="a502f-115">用於端點的 Defender 擴充支援，以包含下層作業系統，提供支援的 Windows 版本的高級攻擊偵測和調查功能。</span><span class="sxs-lookup"><span data-stu-id="a502f-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="a502f-116">若要將下層 Windows 用戶端端點上架到 Defender for Endpoint，您必須：</span><span class="sxs-lookup"><span data-stu-id="a502f-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="a502f-117">設定及更新 System Center Endpoint Protection 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a502f-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="a502f-118">安裝和設定 Microsoft Monitoring Agent (MMA) ，以如下所述，向資料點報告感應器資料至 Defender。</span><span class="sxs-lookup"><span data-stu-id="a502f-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="a502f-119">在裝置上架後，您可以選擇執行偵測測試，以確認它已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="a502f-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="a502f-120">如需詳細資訊，請參閱 [在新的架 Defender For endpoint 端點上執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="a502f-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="a502f-121">設定及更新 System Center Endpoint Protection 用戶端</span><span class="sxs-lookup"><span data-stu-id="a502f-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a502f-122">只有當您的組織使用 System Center Endpoint Protection (SCEP) 時，才需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="a502f-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="a502f-123">Defender for Endpoint 會與 System Center Endpoint Protection 整合，以提供惡意程式碼偵測的可見度，並 banning 潛在的惡意檔案或可疑惡意程式碼，以停止傳播您組織中的攻擊。</span><span class="sxs-lookup"><span data-stu-id="a502f-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="a502f-124">若要啟用此整合，必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a502f-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="a502f-125">安裝 [Endpoint Protection 用戶端的2017年1月的反惡意程式碼平臺更新](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="a502f-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="a502f-126">將 SCEP 用戶端 Cloud Protection Service 成員資格設定為 [ **高級** ] 設定</span><span class="sxs-lookup"><span data-stu-id="a502f-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="a502f-127">設定您的網路以允許連線至 Microsoft Defender 防病毒雲端。</span><span class="sxs-lookup"><span data-stu-id="a502f-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="a502f-128">如需詳細資訊，請參閱 [Allow connections to The Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="a502f-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="a502f-129">安裝和設定 Microsoft Monitoring Agent (MMA) ，將感應器資料包告至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a502f-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="a502f-130">開始之前</span><span class="sxs-lookup"><span data-stu-id="a502f-130">Before you begin</span></span>
<span data-ttu-id="a502f-131">請參閱下列詳細資料以驗證最低系統需求：</span><span class="sxs-lookup"><span data-stu-id="a502f-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="a502f-132">安裝 [每月2018月更新彙總套件](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="a502f-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="a502f-133">僅適用于 Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。</span><span class="sxs-lookup"><span data-stu-id="a502f-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="a502f-134">安裝 [客戶體驗和診斷遙測的更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="a502f-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="a502f-135">安裝 [.net framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更新版本) 或 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="a502f-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="a502f-136">僅適用于 Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。</span><span class="sxs-lookup"><span data-stu-id="a502f-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="a502f-137">請勿安裝 .NET Framework 4.0，因為它會否定上述安裝。</span><span class="sxs-lookup"><span data-stu-id="a502f-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="a502f-138">符合 Azure 記錄分析代理程式最低系統需求。</span><span class="sxs-lookup"><span data-stu-id="a502f-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="a502f-139">如需詳細資訊，請參閱 [使用記錄分析從您環境中的電腦收集資料](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="a502f-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="a502f-140">下載代理程式安裝檔： [windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603) 程式或 [windows 32 位代理](https://go.microsoft.com/fwlink/?LinkId=828604)程式。</span><span class="sxs-lookup"><span data-stu-id="a502f-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="a502f-141">取得工作區 ID:</span><span class="sxs-lookup"><span data-stu-id="a502f-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="a502f-142">在 [Defender for Endpoint] 導覽窗格中，選取 [ **設定] > 裝置管理 > 上架**</span><span class="sxs-lookup"><span data-stu-id="a502f-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="a502f-143">選取 **Windows 7 SP1 和 8.1** 做為作業系統</span><span class="sxs-lookup"><span data-stu-id="a502f-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="a502f-144">複製工作區識別碼與工作區機碼</span><span class="sxs-lookup"><span data-stu-id="a502f-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="a502f-145">使用 [工作區識別碼與工作區金鑰] 選擇下列任一安裝方法來安裝代理程式：</span><span class="sxs-lookup"><span data-stu-id="a502f-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="a502f-146">[使用安裝程式手動安裝代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="a502f-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="a502f-147">在「 **代理程式安裝選項** 」頁面上，選取 **[將代理程式連線到 Azure 記錄分析 (OMS)**</span><span class="sxs-lookup"><span data-stu-id="a502f-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="a502f-148">[使用命令列安裝代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="a502f-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="a502f-149">[使用腳本設定代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="a502f-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a502f-150">如果您是 [美國政府客戶](gov.md)，請在「azure 雲端」下，如果使用設定向導，或是使用命令列或腳本-將 "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 參數設定為1，則必須選擇「Azure US 政府」。</span><span class="sxs-lookup"><span data-stu-id="a502f-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="a502f-151">如果您使用 proxy 連線到網際網路，請參閱設定 proxy 設定區段。</span><span class="sxs-lookup"><span data-stu-id="a502f-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="a502f-152">完成後，您應該會在一個小時內看到入口網站中的架端點。</span><span class="sxs-lookup"><span data-stu-id="a502f-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="a502f-153">設定 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="a502f-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="a502f-154">每個 Windows 端點都必須能夠使用 HTTPS 連接至網際網路。</span><span class="sxs-lookup"><span data-stu-id="a502f-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="a502f-155">這種連線可以直接使用 proxy，也可以透過 [OMS 閘道](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)。</span><span class="sxs-lookup"><span data-stu-id="a502f-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="a502f-156">如果一個 proxy 或防火牆預設會封鎖所有流量，而且只允許特定網域透過或 HTTPS 掃描 (已啟用 SSL 檢查) ，請確定您已啟用 [Endpoint service URLs 的存取權](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="a502f-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="a502f-157">下架用戶端端點</span><span class="sxs-lookup"><span data-stu-id="a502f-157">Offboard client endpoints</span></span>
<span data-ttu-id="a502f-158">若要下架，您可以從端點卸載 MMA agent，或將其從報告中拔出至您的 Defender for Endpoint workspace。</span><span class="sxs-lookup"><span data-stu-id="a502f-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="a502f-159">脫離代理程式後，端點就不再將感應器資料傳送至端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="a502f-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="a502f-160">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a502f-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="a502f-161">[註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)。</span><span class="sxs-lookup"><span data-stu-id="a502f-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

