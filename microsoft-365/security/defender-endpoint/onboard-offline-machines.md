---
title: 沒有網際網路存取 Microsoft Defender for Endpoint 的板載裝置
ms.reviewer: ''
description: 沒有網際網路存取的板載裝置，使其可將感應器資料傳送至 Microsoft Defender for Endpoint 感應器
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
ms.openlocfilehash: 73110d89c39319825cc8dc8e347d137de52a510a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028376"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>沒有網際網路存取 Microsoft Defender for Endpoint 的板載裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


若沒有網際網路存取的板載裝置，您必須採取下列一般步驟：

> [!IMPORTANT] 
> 下列步驟僅適用于執行舊版 Windows 的裝置，例如： Windows Server 2016 及更早版本或 Windows 8.1 和更舊版本。

> [!NOTE]
> - 在透過 ' TelemetryProxyServer ' 登錄或 GPO 進行設定時，不能將 OMS 閘道伺服器當做 proxy 用於中斷連線 Windows 10 或 Windows 伺服器2019裝置。
> - 若為 Windows 10 或 Windows 伺服器 2019-當您可以使用 TelemetryProxyServer 時，必須指向標準 proxy 裝置或裝置。
> - 此外，在中斷連線環境中 Windows 10 或 Windows 伺服器2019必須能夠透過內部檔案或網頁伺服器離線更新憑證信任清單。
> - 如需離線更新 Ctl 的詳細資訊，請參閱 [Configure a file or web server To CONFIGURE CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)。

如需上架方法的詳細資訊，請參閱下列文章：
- [將上一版 Windows 上線](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Microsoft Defender for Endpoint service 的板載伺服器](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [設定裝置 Proxy 和網際網路連線能力設定](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premises-devices"></a>內部部署裝置

- 安裝 Azure Log Analytics (以前稱為 OMS 閘道) ，可充當 proxy 或 hub：
  - [Azure 記錄分析代理程式](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [安裝和設定 Microsoft Monitoring Agent (MMA) ](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)指向 Defender，& 識別碼的端點工作區金鑰

- 相同網路的 Azure 記錄分析中的離線裝置
  -  將 MMA 設定為指向：
     - Azure Log Analytics IP 為 proxy
     - 用於端點的 Defender 工作區金鑰 & 識別碼

## <a name="azure-virtual-machines"></a>Azure 虛擬機器
- 設定及啟用 [Azure 記錄分析工作區](/azure/azure-monitor/platform/gateway)

    - 安裝 Azure Log Analytics 閘道 (（以前稱為 OMS 閘道) 以充當 proxy 或 hub）：
      - [Azure 記錄分析閘道](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [安裝和設定 Microsoft Monitoring Agent (MMA) ](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)指向 Defender，& 識別碼的端點工作區金鑰
    - 在不同的 OMS 閘道網路中的離線 Azure Vm
      - 將 Azure Log Analytics IP 設定為 proxy
      - Azure 記錄分析的工作區機碼 & 識別碼

    - Azure Defender
      - [安全性原則 \> 記錄分析工作區](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [威脅偵測 \> 允許 Endpoint To Endpoint 存取我的資料](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        如需詳細資訊，請參閱使用 [安全性原則](/azure/security-center/tutorial-security-policy)。
