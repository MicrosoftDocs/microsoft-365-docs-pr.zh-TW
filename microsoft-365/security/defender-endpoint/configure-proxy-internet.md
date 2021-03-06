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
ms.openlocfilehash: 6a3bbc46bb5859743d5170451b0d1c68793f93bf
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338706"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>設定裝置 Proxy 和網際網路連線能力設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Defender for endpoint 感應器需要 Microsoft Windows HTTP (WinHTTP) 才能報告感應器資料，並與 defender for Endpoint service 進行通訊。

內嵌的 Defender for Endpoint 感應器會在使用 LocalSystem 帳戶的系統內容中執行。 感應器會使用 Microsoft Windows HTTP 服務 (WinHTTP) 來啟用與 Defender for Endpoint cloud service 的通訊。

> [!TIP]
> 對於使用 正向 Proxy 作為網際網路閘道的組織，可以使用網路保護來調查 Proxy 背後的情況。 有關詳細資訊，請參閱[調查正向 Proxy 背後發生的連線事件](investigate-behind-proxy.md)。

WinHTTP 設定設定與 Windows internet (WinINet) Internet 流覽 proxy 設定無關，而且只能使用下列探索方法來探索 proxy 伺服器：

- 自動探索方法：

  - 透明Proxy

  - 網頁 Proxy 自動探索通訊協定（WPAD）

    > [!NOTE]
    > 如果您的網路拓撲中使用的是透明 proxy 或 WPAD，您不需要特殊的設定。 如需 proxy 中的端點 URL 排除的相關資訊，請參閱 [Enable access To Defender For endpoint service URLs in proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

- 手動靜態 Proxy 組態：

  - 基於登錄的設定

  - 使用 netsh 命令設定的 WinHTTP – 僅適用於穩定拓撲中的桌面 (例如：同一 Proxy 後公司網路中的桌面)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器

設定登錄型靜態 proxy，只允許當電腦不允許連線至網際網路時，僅限 Defender for Endpoint 感應器報告診斷資料，並與 Defender for Endpoint service 通訊。

> [!NOTE]
> 在 Windows 10 或 Windows Server 2019 上使用此選項時，建議使用下列 (或更新版本) 產生及累計更新彙總套件：
>
> - Windows 10 版本1809或 Windows 伺服器 2019-https://support.microsoft.com/kb/5001384
> - Windows 10，版本 1909-https://support.microsoft.com/kb/4601380
> - Windows 10，版本 2004-https://support.microsoft.com/kb/4601382
> - Windows 10，版本 20H2-https://support.microsoft.com/kb/4601382
>
> 這些更新會改善 CnC (命令和控制) 通道的連線和可靠性。

靜態 Proxy 可以透過群組原則 (GP) 設定。 可以在以下位置找到群組原則：

- **系統管理範本 > Windows 元件 > 資料收集和預覽版本 > 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用狀況**

  設定為 [ **已啟用** ]，然後選取 [ **停用已驗證的 Proxy 使用**]。

  ![群組原則 setting1 的影像](images/atp-gpo-proxy1.png)

- 系統 **管理範本 > Windows 元件 > 資料收集和預覽版本 > 設定連線使用者體驗和遙測**：

  設定 Proxy

  ![群組原則 setting2 的影像](images/atp-gpo-proxy2.png)

  原則會設定兩個登錄值， `TelemetryProxyServer` REG_SZ 和 REG_DWORD，都是登錄機 `DisableEnterpriseAuthProxy` 碼底下 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 。

  登錄值 `TelemetryProxyServer` 採用下列字串格式：

  ```text
  <server name or ip>:<port>
  ```

  例如：10.0.0.6:8080

  此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>使用 netsh 命令手動設定 proxy 伺服器

使用 netsh 設定全系統的靜態 Proxy。

> [!NOTE]
>
> - 這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。</br>
> - 變更拓撲的膝上型電腦 (例如：從 office 到 home) ，將無法使用 netsh。 使用基於登錄的靜態 Proxy 設定。

1. 開啟提高權限的命令列：

   1. 轉至 **[開始]** 並鍵入 **「cmd」**。

   1. 以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

2. 輸入以下命令，再按 **Enter**：

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例如：`netsh winhttp set proxy 10.0.0.6:8080`

要重設 winhttpProxy，請輸入以下命令並按 **Enter** 鍵：

```PowerShell
netsh winhttp reset proxy
```

若要瞭解詳細資訊。，請參見 [Netsh 命令語法、上下文和格式](/windows-server/networking/technologies/netsh/netsh-contexts)。

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>在 proxy 伺服器中啟用 Microsoft Defender for Endpoint service URLs 的存取權

如果 Proxy 或防火牆在預設情況下封鎖所有流量，並且只允許特定網域通過，請將可下載工作表中列出的網域新增到允許的網域清單中。

下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。 您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取，否則您可能需要為他們建立一個 *允許* 規則。

| 網域清單的試算表 | 描述 |
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | 服務位置、地理位置和作業系統的特定 DNS 記錄試算表。 <br><br>[在這裡下載試算表。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

如果 Proxy 或防火牆啟用了 HTTPS 掃描 (SSL 檢查)，則從 HTTPS 掃描中排除上表中列出的網域。

> [!NOTE]
> settings-win.data.microsoft.com 只有 Windows 10 在執行版本1803或更早版本的裝置時才需要。<br>
>
> 只有當您具有執行版本1803或更新版本的 Windows 10 裝置時，才需要在其中包含 v20 的 URLs。 例如， `us-v20.events.data.microsoft.com` 在執行版本1803或更新版本的 Windows 10 裝置，以及架至 US 資料儲存體地區時，是必要的。
>
> 如果您在環境中使用 Microsoft Defender 防毒軟體，請參閱[設定 Microsoft Defender 防毒軟體雲端服務的網路](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)連線。

如果 proxy 或防火牆封鎖匿名流量，則在端點感應器的 Defender 是從系統內容連線時，請確定先前所列的 URLs 允許匿名流量。

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) -舊版本 Windows 用戶端或 Windows 伺服器的 proxy 和防火牆需求

下表列出與 Log Analytics 代理程式通訊所需的 proxy 及防火牆設定資訊 (通常稱為 Microsoft Monitoring Agent) 舊版 Windows，例如 Windows 7 SP1、Windows 8.1 Windows Server 2008 R2、Windows Server 2012 R2 及 Windows Server 2016。

|代理程式資源|連接埠 |方向 |略過 HTTPS 檢查|
|------|---------|--------|--------|
|*.ods.opinsights.azure.com |連接埠 443 |出埠|是 |  
|*.oms.opinsights.azure.com |連接埠 443 |出埠|是 |  
|*.blob.core.windows.net |連接埠 443 |出埠|是 |
|*.azure-automation.net |連接埠 443 |出埠|是 |  

> [!NOTE]
> 作為雲端式解決方案，IP 範圍可能會變更。 建議您移至 DNS 解析設定。

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>確認 Microsoft Monitoring Agent (MMA) 服務 URL 需求 

使用舊版) 的 Microsoft Monitoring Agent (MMA Windows 時，請參閱下列指導，以消除特定環境的萬用字元 ( * ) 需求。

1. 使用 Microsoft Monitoring Agent (MMA) 的舊版作業系統 (如需詳細資訊，請參閱[在 defender 上的上架先前版本 Windows](https://go.microsoft.com/fwlink/p/?linkid=2010326)和[板載 Windows server](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。

2. 確定機器已成功地報告 Microsoft 365 Defender 入口網站。

3. 從 "C:\Program Files \ Microsoft Monitoring Agent \Agent] 執行 TestCloudConnection.exe 工具，以驗證連線，並查看特定工作區所需的 URLs。

4. 在 [Microsoft Defender for Endpoint URLs] 清單中檢查您地區的完整需求清單 (請參閱服務 URLs [試算表](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)) 。

    ![Windows PowerShell 中的系統管理員影像](images/admin-powershell.png)

\* \* Ods.opinsights.azure.com、oms.opinsights.azure.com 及 agentsvc.azure-automation.net URL 端點中所用的)  (萬用字元， \* \* 都可以取代為您特定的工作區識別碼。 工作區識別碼是針對您的環境和工作區所特有，可在 Microsoft 365 Defender 入口網站的承租人內架區段中找到。

\*BLOB.CORE.WINDOWS.NET URL 端點可以取代為測試結果的「防火牆規則： \* blob.core.windows.net」一節中所示的 URLs。

> [!NOTE]
> 在使用 Azure Defender 進行上架時，可能會使用多個工作區。 您必須在每個工作區的架電腦上執行上述 TestCloudConnection.exe 程式 (，以判斷是否) 工作區之間的 blob.core.windows.net URLs 的任何變更。

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>驗證 Endpoint service URLs 的用戶端與 Microsoft Defender 的連線能力

驗證 Proxy 設定是否成功完成，WinHTTP 是否可以在您的環境中發現 Proxy 伺服器並透過 Proxy 伺服器進行通訊，以及 Proxy 伺服器是否允許到適用於端點的 Defender 服務 URL 的通訊息。

1. 將 [MDATP 用戶端 Analyzer 工具](https://aka.ms/mdatpanalyzer) 下載至執行 Endpoint 感應器所在的電腦。

2. 擷取裝置上 MDATPClientAnalyzer.zip 的內容。

3. 開啟提高權限的命令列：

   1. 轉至 **[開始]** 並鍵入 **「cmd」**。

   1. 以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

4. 輸入以下命令，再按 **Enter**：

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    以 MDATPClientAnalyzer 工具下載所在的路徑取代 *HardDrivePath* ，例如：

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. 在 *HardDrivePath* 中使用的資料夾中，解壓縮工具所建立的 *MDATPClientAnalyzerResult.zip* 檔案。

6. 開啟 *MDATPClientAnalyzerResult.txt* 並驗證是否已執行 Proxy 設定步驟以啟用伺服器發現和對服務 URL 的存取。

   該工具檢查適用於端點的 Defender 用戶端設定為與之互動的適用於端點的 Defender 服務 URL 的連線性。 然後，它將結果列印到每個可能用於與適用於端點的 Defender 服務進行通訊之 URL 的 *MDATPClientAnalyzerResult.txt* 文件中。 例如：

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

如果至少有一個連線選項退回 (200) 適用於端點的 Defender 用戶端可以使用此連線方法與測試的 URL 正確通訊。

但是，如果連線檢查結果顯示失敗，則會顯示 HTTP 錯誤 (請參閱 HTTP 狀態碼)。 然後，您可以在 proxy 伺服器中，使用 [ [啟用 Endpoint To Defender For Endpoint service URLs](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)] 中所示的表格中所示的 URLs。 您將使用的 URLs 取決於上架程式期間所選取的區域。

> [!NOTE]
> 連線分析程式工具與 ASR 規則不相容[封鎖源自 PSExec 和 WMI 命令的流程建立](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。 需要暫時停用此規則才能執行連線工具。
>
> 設定 TelemetryProxyServer 時，在 [登錄] 或 [透過群組原則] 中，當其無法存取定義的 proxy 時，它會回復為 [直屬]。

## <a name="related-topics"></a>相關主題

- [將 Windows 10 裝置上線](configure-endpoints.md)
- [疑難排解 Microsoft Defender 的端點上架問題](troubleshoot-onboarding.md)
