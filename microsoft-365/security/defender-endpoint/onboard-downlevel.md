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
ms.openlocfilehash: b180e7555bb3339324d3b99956d8f8ad73dc13c3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186386"
---
# <a name="onboard-previous-versions-of-windows"></a>板載舊版 Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平臺**
- Windows 7 SP1 企業版
- Windows 7 SP1 Pro
- Windows 8.1 專業版
- Windows 8.1 企業版


>想要體驗 Defender for Endpoint？ [註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)。

用於端點的 Defender 擴充支援，以包含下層作業系統，提供支援的 Windows 版本的高級攻擊偵測和調查功能。

若要將下層 Windows 用戶端端點上架到 Defender for Endpoint，您必須：
- 設定及更新 System Center Endpoint Protection 用戶端。
- 安裝和設定 Microsoft Monitoring Agent (MMA) ，以如下所述，向資料點報告感應器資料至 Defender。

> [!TIP]
> 在裝置上架後，您可以選擇執行偵測測試，以確認它已正確架至服務。 如需詳細資訊，請參閱 [在新的架 Defender For endpoint 端點上執行偵測測試](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>設定及更新 System Center Endpoint Protection 用戶端
> [!IMPORTANT]
> 只有當您的組織使用 System Center Endpoint Protection (SCEP) 時，才需要此步驟。

Defender for Endpoint 會與 System Center Endpoint Protection 整合，以提供惡意程式碼偵測的可見度，並 banning 潛在的惡意檔案或可疑惡意程式碼，以停止傳播您組織中的攻擊。 

若要啟用此整合，必須執行下列步驟： 
- 安裝 [Endpoint Protection 用戶端的2017年1月的反惡意程式碼平臺更新](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- 將 SCEP 用戶端 Cloud Protection Service 成員資格設定為 [ **高級** ] 設定
- 設定您的網路以允許連線至 Microsoft Defender 防病毒雲端。 如需詳細資訊，請參閱 [Allow connections to The Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>安裝和設定 Microsoft Monitoring Agent (MMA) ，將感應器資料包告至 Microsoft Defender for Endpoint

### <a name="before-you-begin"></a>開始之前
請參閱下列詳細資料以驗證最低系統需求：
- 安裝 [每月2018月更新彙總套件](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > 僅適用于 Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。 

- 安裝 [客戶體驗和診斷遙測的更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- 安裝 [.net framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更新版本) 或 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > 僅適用于 Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。
    > 請勿安裝 .NET Framework 4.0，因為它會否定上述安裝。

- 符合 Azure 記錄分析代理程式最低系統需求。 如需詳細資訊，請參閱 [使用記錄分析從您環境中的電腦收集資料](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. 下載代理程式安裝檔： [windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603) 程式或 [windows 32 位代理](https://go.microsoft.com/fwlink/?LinkId=828604)程式。

2. 取得工作區 ID:
   - 在 [Defender for Endpoint] 導覽窗格中，選取 [ **設定] > 裝置管理 > 上架**
   - 選取 **Windows 7 SP1 和 8.1** 做為作業系統
   - 複製工作區識別碼與工作區機碼

3. 使用 [工作區識別碼與工作區金鑰] 選擇下列任一安裝方法來安裝代理程式：
    - [使用安裝程式手動安裝代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。 <br>
      在「 **代理程式安裝選項** 」頁面上，選取 **[將代理程式連線到 Azure 記錄分析 (OMS)**
    - [使用命令列安裝代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [使用腳本設定代理程式](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 如果您是 [美國政府客戶](gov.md)，請在「azure 雲端」下，如果使用設定向導，或是使用命令列或腳本-將 "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 參數設定為1，則必須選擇「Azure US 政府」。

4. 如果您使用 proxy 連線到網際網路，請參閱設定 proxy 設定區段。

完成後，您應該會在一個小時內看到入口網站中的架端點。

### <a name="configure-proxy-and-internet-connectivity-settings"></a>設定 proxy 和網際網路連線設定
 
- 每個 Windows 端點都必須能夠使用 HTTPS 連接至網際網路。 這種連線可以直接使用 proxy，也可以透過 [OMS 閘道](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)。
- 如果一個 proxy 或防火牆預設會封鎖所有流量，而且只允許特定網域透過或 HTTPS 掃描 (已啟用 SSL 檢查) ，請確定您已啟用 [Endpoint service URLs 的存取權](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

## <a name="offboard-client-endpoints"></a>下架用戶端端點
若要下架，您可以從端點卸載 MMA agent，或將其從報告中拔出至您的 Defender for Endpoint workspace。 脫離代理程式後，端點就不再將感應器資料傳送至端點的 Defender。 

> 想要體驗 Defender for Endpoint？ [註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)。

