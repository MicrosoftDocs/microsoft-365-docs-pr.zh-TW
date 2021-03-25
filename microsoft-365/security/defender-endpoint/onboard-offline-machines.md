---
title: 沒有網際網路存取 Microsoft Defender for Endpoint 的板載裝置
ms.reviewer: ''
description: 沒有網際網路存取的板載裝置，使其可將感應器資料傳送至 Microsoft Defender ATP 感應器
keywords: 板載、伺服器、vm、內部部署、oms 閘道、記錄分析、azure 記錄分析、mma
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
ms.openlocfilehash: b31705a4e6dc8cdd480c8b43c2154a2d6ddacddd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186938"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="aa585-104">沒有網際網路存取 Microsoft Defender for Endpoint 的板載裝置</span><span class="sxs-lookup"><span data-stu-id="aa585-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aa585-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="aa585-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa585-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aa585-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa585-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa585-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aa585-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="aa585-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa585-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="aa585-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="aa585-110">若沒有網際網路存取的板載裝置，您必須採取下列一般步驟：</span><span class="sxs-lookup"><span data-stu-id="aa585-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="aa585-111">下列步驟僅適用于執行舊版 Windows 的裝置，例如： Windows Server 2016 和更新版本或 Windows 8.1 及更早版本。</span><span class="sxs-lookup"><span data-stu-id="aa585-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="aa585-112">在透過 ' TelemetryProxyServer ' 登錄或 GPO 進行設定時，OMS 閘道伺服器不能做為中斷連線 Windows 10 或 Windows Server 2019 裝置的 proxy。</span><span class="sxs-lookup"><span data-stu-id="aa585-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="aa585-113">若為 Windows 10 或 Windows Server 2019-當您可以使用 TelemetryProxyServer 時，必須指向標準 proxy 裝置或裝置。</span><span class="sxs-lookup"><span data-stu-id="aa585-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="aa585-114">此外，在中斷連線的環境中，Windows 10 或 Windows Server 2019 必須能夠透過內部檔案或網頁伺服器離線更新憑證信任清單。</span><span class="sxs-lookup"><span data-stu-id="aa585-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="aa585-115">如需離線更新 Ctl 的詳細資訊，請參閱 [Configure a file or web server To CONFIGURE CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)。</span><span class="sxs-lookup"><span data-stu-id="aa585-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="aa585-116">如需上架方法的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="aa585-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="aa585-117">板載舊版 Windows</span><span class="sxs-lookup"><span data-stu-id="aa585-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="aa585-118">Microsoft Defender for Endpoint service 的板載伺服器</span><span class="sxs-lookup"><span data-stu-id="aa585-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="aa585-119">設定裝置 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="aa585-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="aa585-120">內部部署裝置</span><span class="sxs-lookup"><span data-stu-id="aa585-120">On-premise devices</span></span>

- <span data-ttu-id="aa585-121">安裝 Azure Log Analytics (以前稱為 OMS 閘道) ，可充當 proxy 或 hub：</span><span class="sxs-lookup"><span data-stu-id="aa585-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="aa585-122">Azure 記錄分析代理程式</span><span class="sxs-lookup"><span data-stu-id="aa585-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="aa585-123">[安裝和設定 Microsoft Monitoring Agent (MMA) ](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) 指向 Defender 以取得端點工作區金鑰 & 識別碼</span><span class="sxs-lookup"><span data-stu-id="aa585-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="aa585-124">相同網路的 Azure 記錄分析中的離線裝置</span><span class="sxs-lookup"><span data-stu-id="aa585-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="aa585-125">將 MMA 設定為指向：</span><span class="sxs-lookup"><span data-stu-id="aa585-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="aa585-126">Azure Log Analytics IP 為 proxy</span><span class="sxs-lookup"><span data-stu-id="aa585-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="aa585-127">用於端點的 Defender 工作區金鑰 & 識別碼</span><span class="sxs-lookup"><span data-stu-id="aa585-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="aa585-128">Azure 虛擬機器</span><span class="sxs-lookup"><span data-stu-id="aa585-128">Azure virtual machines</span></span>
- <span data-ttu-id="aa585-129">設定及啟用 [Azure 記錄分析工作區](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="aa585-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="aa585-130">安裝 Azure Log Analytics 閘道 (（以前稱為 OMS 閘道) 以充當 proxy 或 hub）：</span><span class="sxs-lookup"><span data-stu-id="aa585-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="aa585-131">Azure 記錄分析閘道</span><span class="sxs-lookup"><span data-stu-id="aa585-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="aa585-132">[安裝和設定 Microsoft Monitoring Agent (MMA) ](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) 指向 Defender 以取得端點工作區金鑰 & 識別碼</span><span class="sxs-lookup"><span data-stu-id="aa585-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="aa585-133">在不同的 OMS 閘道網路中的離線 Azure Vm</span><span class="sxs-lookup"><span data-stu-id="aa585-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="aa585-134">將 Azure Log Analytics IP 設定為 proxy</span><span class="sxs-lookup"><span data-stu-id="aa585-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="aa585-135">Azure 記錄分析的工作區機碼 & 識別碼</span><span class="sxs-lookup"><span data-stu-id="aa585-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="aa585-136">Azure Security Center (ASC) </span><span class="sxs-lookup"><span data-stu-id="aa585-136">Azure Security Center (ASC)</span></span>
      - [<span data-ttu-id="aa585-137">安全性原則 \> 記錄分析工作區</span><span class="sxs-lookup"><span data-stu-id="aa585-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="aa585-138">威脅偵測 \> 允許 Endpoint To Endpoint 存取我的資料</span><span class="sxs-lookup"><span data-stu-id="aa585-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="aa585-139">如需詳細資訊，請參閱使用 [安全性原則](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)。</span><span class="sxs-lookup"><span data-stu-id="aa585-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
