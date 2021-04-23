---
title: Microsoft Defender for Endpoint service 的板載 Windows 伺服器
description: 板載 Windows 伺服器，讓他們可以將感應器資料傳送至 Microsoft Defender for Endpoint 感應器。
keywords: 板載伺服器、伺服器、2012r2、2016、2019、伺服器上架、裝置管理、設定 Microsoft Defender for Endpoint server、板載 Microsoft Defender for endpoint server、板載 Microsoft defender for Endpoint servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 17aca5fb388aef26504902ee63b22410420c8827
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952485"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="d06c5-104">Microsoft Defender for Endpoint service 的板載 Windows 伺服器</span><span class="sxs-lookup"><span data-stu-id="d06c5-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d06c5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d06c5-105">**Applies to:**</span></span>

- <span data-ttu-id="d06c5-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="d06c5-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="d06c5-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d06c5-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="d06c5-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d06c5-108">Windows Server 2016</span></span>
- <span data-ttu-id="d06c5-109">Windows Server (SAC) 版本1803和更新版本</span><span class="sxs-lookup"><span data-stu-id="d06c5-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="d06c5-110">Windows Server 2019 和更新版本</span><span class="sxs-lookup"><span data-stu-id="d06c5-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="d06c5-111">Windows Server 2019 core edition</span><span class="sxs-lookup"><span data-stu-id="d06c5-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="d06c5-112">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d06c5-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d06c5-113">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d06c5-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="d06c5-114">用於端點的 Defender 擴充支援也包含 Windows Server 作業系統。</span><span class="sxs-lookup"><span data-stu-id="d06c5-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="d06c5-115">這種支援透過 Microsoft Defender Security Center 主控台無縫提供高級攻擊偵測和調查功能。</span><span class="sxs-lookup"><span data-stu-id="d06c5-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="d06c5-116">如需有關授權和基礎結構需要採取的實際事項，請參閱 [使用 Defender For Endpoint 保護 Windows server](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="d06c5-117">如需如何下載及使用 Windows server 之 Windows 安全性基準的指導方針，請參閱 [Windows 安全性基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="d06c5-118">Windows Server 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d06c5-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="d06c5-119">您可以使用下列任一選項，將 Windows Server 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016 上架到 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="d06c5-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="d06c5-120">**選項 1**：透過 [安裝及設定 Microsoft MONITORING Agent (MMA) 上的板載](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="d06c5-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="d06c5-121">**選項 2**： [透過 Azure Security Center 的板載](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="d06c5-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="d06c5-122">**選項 3**： [透過 Microsoft 端點管理員版本2002和更新版本的板載版本](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="d06c5-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="d06c5-123">使用任何提供的選項完成上架步驟之後，您將需要 [設定並更新 System Center Endpoint Protection 用戶端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="d06c5-124">需要使用 Defender for Endpoint 獨立伺服器授權（每個節點），以便透過 Microsoft Monitoring Agent (選項 1) 或透過 Microsoft 端點管理員 (選項 3) 將 Windows server 上架。</span><span class="sxs-lookup"><span data-stu-id="d06c5-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="d06c5-125">或者，每個節點需要 Azure Defender for Server 授權，以便透過 Azure Security Center 板載 Windows server (選項 2) ，請參閱 [Azure Defender 中提供的支援功能](https://docs.microsoft.com/azure/security-center/security-center-services)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="d06c5-126">選項1：透過安裝及設定 Microsoft Monitoring Agent (MMA) 上的板載</span><span class="sxs-lookup"><span data-stu-id="d06c5-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="d06c5-127">您將需要安裝及設定 MMA for Windows server，才能將感應器資料包告為端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="d06c5-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="d06c5-128">如需詳細資訊，請參閱 [使用 Azure Log Analytics Agent 收集記錄資料](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="d06c5-129">如果您已在使用 System Center Operations Manager (SCOM) 或 Azure 監視器 (之前稱為 Operations Management Suite (OMS) ) ，請將 Microsoft Monitoring Agent (MMA) ，以透過各核心支援報告您的 Defender for Endpoint workspace。</span><span class="sxs-lookup"><span data-stu-id="d06c5-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="d06c5-130">一般來講，您必須採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d06c5-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="d06c5-131">**會滿足開始之前** 區段中所述的上架需求。</span><span class="sxs-lookup"><span data-stu-id="d06c5-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="d06c5-132">從 Microsoft Defender Security center 開啟伺服器監視。</span><span class="sxs-lookup"><span data-stu-id="d06c5-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="d06c5-133">針對伺服器安裝和設定 MMA，將感應器資料包告給 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d06c5-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="d06c5-134">設定及更新 System Center Endpoint Protection 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d06c5-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="d06c5-135">在裝置上架後，您可以選擇執行偵測測試，以確認它已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="d06c5-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="d06c5-136">如需詳細資訊，請參閱 [在新的架 Defender For endpoint 端點上執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="d06c5-137">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="d06c5-137">Before you begin</span></span>

<span data-ttu-id="d06c5-138">請執行下列步驟來滿足上架需求：</span><span class="sxs-lookup"><span data-stu-id="d06c5-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="d06c5-139">若為 Windows Server 2008 R2 SP1 或 Windows Server 2012 R2，請確定您已安裝下列修復程式：</span><span class="sxs-lookup"><span data-stu-id="d06c5-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="d06c5-140">客戶體驗和診斷遙測的更新</span><span class="sxs-lookup"><span data-stu-id="d06c5-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="d06c5-141">若為 Windows Server 2008 R2 SP1，請確定您符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="d06c5-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="d06c5-142">安裝 [二月份每月更新彙總套件](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="d06c5-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="d06c5-143">安裝 [.net framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更新版本) 或 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="d06c5-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="d06c5-144">如果您使用 SCCM 管理 Windows Server 2008 R2 SP1，則 SCCM 用戶端代理程式會安裝 .Net Framework 4.5.2。</span><span class="sxs-lookup"><span data-stu-id="d06c5-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="d06c5-145">因此，您不需要安裝 .NET framework 4.5 (或更新版本) 。</span><span class="sxs-lookup"><span data-stu-id="d06c5-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="d06c5-146">若為 Windows Server 2008 R2 SP1 和 Windows Server 2012 R2： [設定及更新 System Center Endpoint Protection 用戶端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="d06c5-147">只有當您的組織使用 System Center Endpoint Protection (SCEP) ，且您要上架 Windows Server 2008 R2 SP1 和 Windows Server 2012 R2 時，才需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="d06c5-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="d06c5-148">安裝和設定 Microsoft Monitoring Agent (MMA) ，將感應器資料包告至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d06c5-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="d06c5-149">下載代理程式安裝程式檔案： [Windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603)程式。</span><span class="sxs-lookup"><span data-stu-id="d06c5-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="d06c5-150">使用上一個程式中取得的工作區識別碼和工作區機碼，選擇下列任何安裝方法，在 Windows server 上安裝該代理程式：</span><span class="sxs-lookup"><span data-stu-id="d06c5-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="d06c5-151">[使用安裝程式手動安裝代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="d06c5-152">在 [ **代理程式安裝選項** ] 頁面上，選擇 **[將代理程式連接至 Azure 記錄分析 (OMS])**。</span><span class="sxs-lookup"><span data-stu-id="d06c5-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="d06c5-153">[使用命令列安裝代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="d06c5-154">[使用腳本設定代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="d06c5-155">如果您是 [美國政府客戶](gov.md)，請在「azure 雲端」下，如果使用設定向導，或是使用命令列或腳本-將 "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 參數設定為1，則必須選擇「Azure US 政府」。</span><span class="sxs-lookup"><span data-stu-id="d06c5-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="d06c5-156">視需要設定 Windows server proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="d06c5-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="d06c5-157">如果您的伺服器需要使用 proxy 與 Defender for Endpoint 通訊，請使用下列其中一種方法來設定 MMA 以使用 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="d06c5-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="d06c5-158">設定 MMA 以使用 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="d06c5-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="d06c5-159">設定 Windows 以針對所有連線使用 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="d06c5-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="d06c5-160">如果使用 proxy 或防火牆，請確定伺服器可以直接存取所有的 Microsoft Defender for Endpoint service URLs，而不需要 SSL 截取。</span><span class="sxs-lookup"><span data-stu-id="d06c5-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="d06c5-161">如需詳細資訊，請參閱 [enable access To Defender For Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="d06c5-162">使用 SSL 截取可防止系統與 Defender for Endpoint service 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="d06c5-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="d06c5-163">完成後，您應該會在一小時內看到入口網站中的架 Windows server。</span><span class="sxs-lookup"><span data-stu-id="d06c5-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="d06c5-164">選項2：透過 Azure Security Center 的板載 Windows 伺服器</span><span class="sxs-lookup"><span data-stu-id="d06c5-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="d06c5-165">在 Microsoft Defender 安全性中心導覽窗格中，選取 [**設定**  >  **裝置管理** 上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="d06c5-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="d06c5-166">選取 [ **Windows Server 2008 R2 SP1，2012 R2 and 2016** 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="d06c5-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="d06c5-167">按一下 **Azure Security Center 中的 [上架伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="d06c5-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="d06c5-168">遵循 [適用于 Azure defender 的端點的 Microsoft defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) 中的上架指示，如果您使用 azure ARC，請依照 [啟用 Microsoft defender for endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)中的上架指示進行。</span><span class="sxs-lookup"><span data-stu-id="d06c5-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="d06c5-169">完成上架步驟之後，您將需要 [設定及更新 System Center Endpoint Protection 用戶端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d06c5-170">若要透過 Azure server Defender 的伺服器上架以取得預期的運作，伺服器必須在 Microsoft Monitoring Agent 內設定適當的工作區和金鑰 (MMA) 設定。</span><span class="sxs-lookup"><span data-stu-id="d06c5-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="d06c5-171">設定後，系統會在機器上部署適當的雲端管理元件，而且會部署及開始 (MsSenseS.exe) 的感應器處理常式。</span><span class="sxs-lookup"><span data-stu-id="d06c5-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="d06c5-172">如果伺服器設定為使用 OMS 閘道伺服器做為 proxy，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="d06c5-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="d06c5-173">選項3：透過 Microsoft 端點管理員版本2002和更新版本的板載 Windows 伺服器</span><span class="sxs-lookup"><span data-stu-id="d06c5-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="d06c5-174">您可以使用 Microsoft 端點管理員版本2002和更新版本，將 Windows Server 2012 R2 和 Windows Server 2016 上架在一起。</span><span class="sxs-lookup"><span data-stu-id="d06c5-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="d06c5-175">如需詳細資訊，請參閱 [在 Microsoft 端點管理員的 [目前分支] 中的 Microsoft Defender For Endpoint](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="d06c5-176">完成上架步驟之後，您將需要 [設定及更新 System Center Endpoint Protection 用戶端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="d06c5-177">Windows Server (SAC) 版本1803、Windows Server 2019 及 Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="d06c5-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="d06c5-178">您可以使用下列部署方法，將 Windows Server (SAC) 版本1803、Windows Server 2019 或 Windows Server 2019 Core edition 上架：</span><span class="sxs-lookup"><span data-stu-id="d06c5-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="d06c5-179">本機腳本</span><span class="sxs-lookup"><span data-stu-id="d06c5-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="d06c5-180">群組原則</span><span class="sxs-lookup"><span data-stu-id="d06c5-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="d06c5-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d06c5-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="d06c5-182">System Center Configuration Manager 2012/2012 R2 1511/1602</span><span class="sxs-lookup"><span data-stu-id="d06c5-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="d06c5-183">非持久性裝置的 VDI 上架腳本</span><span class="sxs-lookup"><span data-stu-id="d06c5-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="d06c5-184">透過 Microsoft 端點管理員的 Windows Server 2019 的上架套件目前附帶腳本。</span><span class="sxs-lookup"><span data-stu-id="d06c5-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="d06c5-185">如需如何在 Configuration Manager 中部署腳本的詳細資訊，請參閱 [Configuration manager 中的套件與程式](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="d06c5-186">本機腳本適用于概念證明，但不適用於實際執行部署。</span><span class="sxs-lookup"><span data-stu-id="d06c5-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="d06c5-187">在實際執行部署中，我們建議使用群組原則或 Microsoft 端點 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="d06c5-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="d06c5-188">支援 Windows Server 可深入瞭解伺服器活動、內核和記憶體攻擊偵測的覆蓋率，並啟用回應動作。</span><span class="sxs-lookup"><span data-stu-id="d06c5-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="d06c5-189">使用 Windows 10 裝置的相同工具和方法，在 Windows server 上為端點上架上架設定設定 Defender。</span><span class="sxs-lookup"><span data-stu-id="d06c5-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="d06c5-190">如需詳細資訊，請參閱 [板載 Windows 10 裝置](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="d06c5-191">如果您正在執行協力廠商反惡意程式碼解決方案，則必須套用下列 Microsoft Defender AV 被動模式設定。</span><span class="sxs-lookup"><span data-stu-id="d06c5-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="d06c5-192">確認已正確設定：</span><span class="sxs-lookup"><span data-stu-id="d06c5-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="d06c5-193">設定下列登錄專案：</span><span class="sxs-lookup"><span data-stu-id="d06c5-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="d06c5-194">路徑： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="d06c5-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="d06c5-195">名稱： ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="d06c5-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="d06c5-196">類型： REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="d06c5-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="d06c5-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="d06c5-197">Value: 1</span></span>

    1. <span data-ttu-id="d06c5-198">執行下列 PowerShell 命令，以確認已設定被動式模式：</span><span class="sxs-lookup"><span data-stu-id="d06c5-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="d06c5-199">確認找到一個包含被動模式事件的最近事件：</span><span class="sxs-lookup"><span data-stu-id="d06c5-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![被動模式驗證結果的影像](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="d06c5-201">執行下列命令以檢查是否已安裝 Microsoft Defender AV：</span><span class="sxs-lookup"><span data-stu-id="d06c5-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="d06c5-202">如果結果是「指定的服務不是已安裝的服務」，您將需要安裝 Microsoft Defender AV。</span><span class="sxs-lookup"><span data-stu-id="d06c5-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="d06c5-203">如需詳細資訊，請參閱 [Windows 10 中的 Microsoft Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="d06c5-204">如需如何使用群組原則在 Windows 伺服器上設定及管理 Microsoft Defender 防病毒的詳細資訊，請參閱 [使用群組原則設定來設定及管理 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="d06c5-205">與 Azure Defender 整合</span><span class="sxs-lookup"><span data-stu-id="d06c5-205">Integration with Azure Defender</span></span>

<span data-ttu-id="d06c5-206">Endpoint for Endpoint 可以與 Azure Defender 整合，以提供全面的 Windows server 保護解決方案。</span><span class="sxs-lookup"><span data-stu-id="d06c5-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="d06c5-207">透過這項整合，Azure Defender 可使用端點的 Defender 的功能，為 Windows Server 提供增強的威脅偵測。</span><span class="sxs-lookup"><span data-stu-id="d06c5-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="d06c5-208">此整合中包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="d06c5-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="d06c5-209">自動上架-在架至 Azure Defender 的 Windows Server 上，會自動啟用端點感應器的 Defender。</span><span class="sxs-lookup"><span data-stu-id="d06c5-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="d06c5-210">如需 Azure Defender 上架的詳細資訊，請參閱 [使用整合的 Microsoft Defender For Endpoint 授權](https://docs.microsoft.com/azure/security-center/security-center-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d06c5-211">Azure Defender for Server 和 Microsoft Defender for 端點之間的整合已擴充，可支援 [Windows Server 2019 和 Windows Virtual Desktop (WVD) ](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="d06c5-212">Azure defender 所監控的 Windows 伺服器也會在 Defender for Endpoint 中提供，以透過用戶端和伺服器提供單一視圖，使 Azure Defender 能夠順利連線至 Defender for Endpoint 租使用者。</span><span class="sxs-lookup"><span data-stu-id="d06c5-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="d06c5-213">此外，Azure Defender 主控台也可使用 Defender for Endpoint 警示。</span><span class="sxs-lookup"><span data-stu-id="d06c5-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="d06c5-214">伺服器調查-Azure Defender 客戶可以存取 Microsoft Defender Security Center，以執行詳細調查，以找出可能遭到破壞的範圍。</span><span class="sxs-lookup"><span data-stu-id="d06c5-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="d06c5-215">當您使用 Azure Defender 監控伺服器時，系統會自動為美國使用者建立 (的 Endpoint 租使用者，而歐盟為歐洲和英國使用者) 。</span><span class="sxs-lookup"><span data-stu-id="d06c5-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="d06c5-216">Defender for Endpoint 收集的資料會儲存在提供期間所識別的承租人地理位置。</span><span class="sxs-lookup"><span data-stu-id="d06c5-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="d06c5-217">如果您在使用 Azure Defender 之前使用 Defender for Endpoint，您的資料會儲存在您建立租使用者時所指定的位置，即使您在稍後整合 Azure Defender 時也是如此。</span><span class="sxs-lookup"><span data-stu-id="d06c5-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="d06c5-218">設定後，您就無法變更儲存資料的位置。</span><span class="sxs-lookup"><span data-stu-id="d06c5-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="d06c5-219">如果您需要將資料移至其他位置，您必須聯繫 Microsoft 支援部門以重設租使用者。</span><span class="sxs-lookup"><span data-stu-id="d06c5-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="d06c5-220">已停用 Office 365 GCC 客戶使用此整合的伺服器端點監控功能。</span><span class="sxs-lookup"><span data-stu-id="d06c5-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="d06c5-221">設定及更新 System Center Endpoint Protection 用戶端</span><span class="sxs-lookup"><span data-stu-id="d06c5-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="d06c5-222">與 System Center Endpoint Protection 整合的端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="d06c5-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="d06c5-223">整合可透過 banning 潛在的惡意檔案或可疑惡意程式碼，以查看惡意程式碼偵測，以及停止傳播攻擊。</span><span class="sxs-lookup"><span data-stu-id="d06c5-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="d06c5-224">若要啟用此整合，必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d06c5-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="d06c5-225">[針對 Endpoint Protection 用戶端安裝2017年1月的反惡意程式碼平臺更新](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="d06c5-226">[將 SCEP 用戶端 Cloud Protection Service 成員資格](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 設定為 [ **高級** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="d06c5-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="d06c5-227">Windows server 下架</span><span class="sxs-lookup"><span data-stu-id="d06c5-227">Offboard Windows servers</span></span>

<span data-ttu-id="d06c5-228">您可以使用 Windows 10 用戶端裝置的相同方法，下架 Windows Server (SAC) 、Windows Server 2019 及 Windows Server 2019 Core edition。</span><span class="sxs-lookup"><span data-stu-id="d06c5-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="d06c5-229">若為其他 Windows server 版本，您有兩個選項可讓您從服務下架 Windows server：</span><span class="sxs-lookup"><span data-stu-id="d06c5-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="d06c5-230">卸載 MMA 代理程式</span><span class="sxs-lookup"><span data-stu-id="d06c5-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="d06c5-231">移除用於端點工作區設定的 Defender</span><span class="sxs-lookup"><span data-stu-id="d06c5-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="d06c5-232">脫離會導致 Windows server 停止將感應器資料傳送至入口網站，但是來自 Windows 伺服器的資料（包括對其所做的任何警示參考）將保留最多6個月。</span><span class="sxs-lookup"><span data-stu-id="d06c5-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="d06c5-233">卸載 MMA 代理程式以卸載 Windows server</span><span class="sxs-lookup"><span data-stu-id="d06c5-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="d06c5-234">若要下架 Windows server，您可以從 Windows server 卸載 MMA agent，或將其從報告中拔出至您的 Defender for Endpoint workspace。</span><span class="sxs-lookup"><span data-stu-id="d06c5-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="d06c5-235">脫離代理程式後，Windows server 將不再將感應器資料傳送至端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="d06c5-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="d06c5-236">如需詳細資訊，請參閱 [停用代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="d06c5-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="d06c5-237">移除用於端點工作區設定的 Defender</span><span class="sxs-lookup"><span data-stu-id="d06c5-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="d06c5-238">若要下架 Windows server，您可以使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="d06c5-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="d06c5-239">從 MMA 代理程式中移除 Defender for Endpoint workspace 設定</span><span class="sxs-lookup"><span data-stu-id="d06c5-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="d06c5-240">執行 PowerShell 命令以移除設定</span><span class="sxs-lookup"><span data-stu-id="d06c5-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="d06c5-241">從 MMA 代理程式中移除 Defender for Endpoint workspace 設定</span><span class="sxs-lookup"><span data-stu-id="d06c5-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="d06c5-242">在 [ **Microsoft Monitoring Agent 屬性**] 中，選取 [ **Azure 記錄分析 (OMS)** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d06c5-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="d06c5-243">選取 [Defender for Endpoint workspace]，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="d06c5-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Microsoft Monitoring Agent 屬性的影像](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="d06c5-245">執行 PowerShell 命令以移除設定</span><span class="sxs-lookup"><span data-stu-id="d06c5-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="d06c5-246">取得您的工作區 ID:</span><span class="sxs-lookup"><span data-stu-id="d06c5-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="d06c5-247">在功能窗格中，選取 [**設定**] [上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="d06c5-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="d06c5-248">選取 [ **Windows Server 2008 R2 SP1，2012 R2 and 2016** 做為作業系統並取得您的工作區 ID:</span><span class="sxs-lookup"><span data-stu-id="d06c5-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Windows server 上架的影像](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="d06c5-250&quot;>開啟提升許可權的 PowerShell，並執行下列命令。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d06c5-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;d06c5-251&quot;>使用您取得及取代的工作區識別碼 `WorkspaceID` ：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d06c5-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="d06c5-252">無管理解決方案的上架伺服器</span><span class="sxs-lookup"><span data-stu-id="d06c5-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="d06c5-253">使用群組原則</span><span class="sxs-lookup"><span data-stu-id="d06c5-253">Using Group Policy</span></span>

<span data-ttu-id="d06c5-254">**步驟-1：建立要向外複製到伺服器的必要檔案。**</span><span class="sxs-lookup"><span data-stu-id="d06c5-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="d06c5-255">流覽至 c:\windows\sysvol\domain\scripts (可能需要在其中一個網域控制站上進行變更控制。 ) </span><span class="sxs-lookup"><span data-stu-id="d06c5-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="d06c5-256">建立名為 MMA 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d06c5-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="d06c5-257">下載下列專案並放入 MMA 資料夾：</span><span class="sxs-lookup"><span data-stu-id="d06c5-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="d06c5-258">**(Windows Server 2008 R2 和 Windows Server 2012 R2 的客戶體驗和診斷遙測更新)**</span><span class="sxs-lookup"><span data-stu-id="d06c5-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="d06c5-259">針對 Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="d06c5-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="d06c5-260">針對 Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="d06c5-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="d06c5-261">本文假設您使用 x64 伺服器 (MMA x64 [新 SHA-2 相容版本](https://go.microsoft.com/fwlink/?LinkId=828603)) </span><span class="sxs-lookup"><span data-stu-id="d06c5-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="d06c5-262">**步驟-2：使用 [記事本] 建立檔案名 DeployMMA ()** 將下列行新增至 cmd 檔案。</span><span class="sxs-lookup"><span data-stu-id="d06c5-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="d06c5-263">請注意，您需要您的工作區識別碼和金鑰。</span><span class="sxs-lookup"><span data-stu-id="d06c5-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="d06c5-264">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="d06c5-264">Group Policy Configuration</span></span>

<span data-ttu-id="d06c5-265">為上架裝置（例如 "Microsoft Defender for Endpoint 上架]）專門建立新的群組原則。</span><span class="sxs-lookup"><span data-stu-id="d06c5-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="d06c5-266">建立名為 "c:\windows\MMA" 的群組原則資料夾</span><span class="sxs-lookup"><span data-stu-id="d06c5-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="資料夾":::

    <span data-ttu-id="d06c5-268">**這會在每個取得所套用 GPO 的伺服器（稱為 MMA）上新增一個新的資料夾，並將其儲存在 c:\windows. 中。這會包含 MMA、必要條件及安裝腳本的安裝檔。**</span><span class="sxs-lookup"><span data-stu-id="d06c5-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="d06c5-269">為儲存在 Net logon 中的每個檔案建立「群組原則檔案」首選項。</span><span class="sxs-lookup"><span data-stu-id="d06c5-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="群組原則 image1":::

<span data-ttu-id="d06c5-271">它會將檔案從 DOMAIN\NETLOGON\MMA\filename 複製到 C:\windows\MMA\filename **，使安裝檔案在伺服器上是本機** 的：</span><span class="sxs-lookup"><span data-stu-id="d06c5-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="部署 mma cmd":::

<span data-ttu-id="d06c5-273">針對 Windows Server Nm-winserver-2008r2-2nd/Windows 7 的兩個 Kb (，另一個適用于 Windows server 2012 R2) 重複此程式，但在通用索引標籤上建立專案層級的目標，所以檔案只會複製到範圍中適當的平臺/作業系統版本：</span><span class="sxs-lookup"><span data-stu-id="d06c5-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="目標編輯器":::

- <span data-ttu-id="d06c5-275">若為 Windows Server 2008 R2，您需要 (，而且它只會複製到) Windows 6.1-BJ3080149-x64</span><span class="sxs-lookup"><span data-stu-id="d06c5-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="d06c5-276">若為 Windows Server 2012 R2，您需要 (，而且它只會複製) Windows 8.1-BJ3080149-x64</span><span class="sxs-lookup"><span data-stu-id="d06c5-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="d06c5-277">完成之後，您將需要建立啟動腳本原則：</span><span class="sxs-lookup"><span data-stu-id="d06c5-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="啟動屬性":::

<span data-ttu-id="d06c5-279">要在這裡執行的檔案名 c:\windows\MMA\DeployMMA.cmd。</span><span class="sxs-lookup"><span data-stu-id="d06c5-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="d06c5-280">重新開機伺服器做為啟動程式的一部分之後，它會安裝更新以取得客戶體驗和診斷遙測 KB，然後在設定工作區識別碼和機碼時安裝 MMA 代理程式，而伺服器將會架。</span><span class="sxs-lookup"><span data-stu-id="d06c5-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="d06c5-281">您也可以使用 **立即** 工作來執行 deployMMA，如果您不想要重新開機所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="d06c5-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="d06c5-282">這可分兩個階段完成。</span><span class="sxs-lookup"><span data-stu-id="d06c5-282">This could be done in two phases.</span></span> <span data-ttu-id="d06c5-283">請先 **在 GPO 中建立檔案和資料夾** –請提供系統時間，以確保已套用 gpo，且所有伺服器都有安裝盤案。</span><span class="sxs-lookup"><span data-stu-id="d06c5-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="d06c5-284">然後，新增立即工作。</span><span class="sxs-lookup"><span data-stu-id="d06c5-284">Then, add the immediate task.</span></span> <span data-ttu-id="d06c5-285">這樣就能在不需要重新開機的情況下達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="d06c5-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="d06c5-286">當您已安裝 MMA 時，腳本具有 exit 方法，而且不會重新執行，您也可以使用每日排程的任務，以達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="d06c5-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="d06c5-287">與 Configuration Manager 符合性原則類似，它會每日檢查以確認 MMA 是否存在。</span><span class="sxs-lookup"><span data-stu-id="d06c5-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="排程任務":::

:::image type="content" source="images/newtaskprops.png" alt-text="新任務屬性":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="部署 mma 下載中心 props":::

:::image type="content" source="images/tasksch.png" alt-text="任務排程器":::

<span data-ttu-id="d06c5-292">如您在伺服器 2008 R2 的伺服器上架檔中所述，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="d06c5-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="d06c5-293">若為 Windows Server 2008 R2 PS1，請確定您符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="d06c5-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="d06c5-294">安裝 [每月2018月更新彙總套件](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="d06c5-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="d06c5-295">安裝 [.net framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更新版本) 或 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="d06c5-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="d06c5-296">請先檢查 Kb 是否存在，再上架 Windows Server 2008 R2 此程式可讓您在沒有 Configuration Manager 管理伺服器的情況時，將所有伺服器上架上架。</span><span class="sxs-lookup"><span data-stu-id="d06c5-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d06c5-297">相關主題</span><span class="sxs-lookup"><span data-stu-id="d06c5-297">Related topics</span></span>

- [<span data-ttu-id="d06c5-298">將 Windows 10 裝置上線</span><span class="sxs-lookup"><span data-stu-id="d06c5-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="d06c5-299">將非 Windows 裝置上線</span><span class="sxs-lookup"><span data-stu-id="d06c5-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="d06c5-300">設定 Proxy 和網際網路連接設定</span><span class="sxs-lookup"><span data-stu-id="d06c5-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="d06c5-301">在新的架 Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="d06c5-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="d06c5-302">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="d06c5-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
