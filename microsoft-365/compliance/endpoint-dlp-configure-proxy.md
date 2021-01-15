---
title: 為端點 DLP 設定裝置 Proxy 和網際網路連線設定
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
ms.openlocfilehash: 1e723adfbf16ba1180558e34b0fe4867e6337c57
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841605"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a>為端點 DLP 設定裝置 Proxy 和網際網路連線設定

Microsoft 端點 DLP 使用 Microsoft Windows HTTP (WinHTTP) 報告資料並與 Microsoft 端點雲端服務通訊。 內嵌的端點 DLP 以 LocalSystem 帳戶在系統內容執行。

> [!TIP]
> 對於使用 正向 Proxy 作為網際網路閘道的組織，可以使用網路保護來調查 Proxy 背後的情況。 有關詳細資訊，請參閱[調查正向 Proxy 背後發生的連線事件](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy)。

WinHTTP 組態設定與 Windows 網際網路 (WinINet) 網際網路流覽 proxy 設定無關，且只能使用下列自動探索方法來探索 proxy 伺服器：

- 透明Proxy
- 網頁 Proxy 自動探索通訊協定（WPAD）

> [!NOTE]
> 如果在網路拓撲中使用透明 proxy 或 WPAD，則不需要特殊的組態設定。 有關 Proxy 中適用於端點的 Defender URL 排除的更多資訊，請參閱[在 Proxy 伺服器中啟用對適用於端點的 Defender 雲端服務 URL 的存取](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)。

- 手動靜態 Proxy 組態：
    - 基於登錄的設定
    - 使用 netsh 命令設定的 WinHTTP – 僅適用於穩定拓撲中的桌面 (例如：同一 Proxy 後公司網路中的桌面)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器

對於不允許連線至網際網路的端點裝置，需要設定基於登錄的靜態 Proxy。 您需要將其設定為僅允許 Microsoft 端點 DLP 報告診斷資料並與 Microsoft 端點雲端服務通訊。

靜態 Proxy 可以透過群組原則 (GP) 設定。 可以在以下位置找到群組原則：

1. 開啟 **[系統管理範本] > [Windows 元件] > [資料收集和預覽組建] > [為連線的使用者體驗與遙測服務設定已驗證 Proxy]**

2. 將其設定為 **[啟用]**，然後選取 **[停用已驗證的 Proxy]**： 

![群組原則設定 1 的圖片](../media/atp-gpo-proxy1.png)
 
3. 開啟 **[系統管理範本] > [Windows 元件] > [資料收集和預覽組建] > [設定連線的使用者體驗與遙測]**：

 設定 Proxy

![群組原則設置 2 的圖片](../media/atp-gpo-proxy2.png)

原則將登錄機碼 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的兩個登錄值 `TelemetryProxyServer` 設定為 REG\u SZ，`DisableEnterpriseAuthProxy` 設定為 REG\u DWORD。

登錄值 TelemetryProxyServer 的格式為：\<server name or ip\>\<port\>。 例如：**10.0.0.6:8080**

此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>使用「netsh」命令手動設定 Proxy 伺服器

使用 netsh 設定全系統的靜態 Proxy。

> [!NOTE]
> 這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。 - 正在改變拓撲的膝上型電腦 (例如：從辦公室到家) 將出現 netsh 故障。 使用基於登錄的靜態 Proxy 設定。

1. 開啟提高權限的命令列：
    1. 轉至 **[開始]** 並輸入 **「cmd」**
    1. 以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。
2.  輸入以下命令，再按 **Enter**：

    `netsh winhttp set proxy <proxy>:<port>`

    例如：**netsh winhttp set proxy 10.0.0.6:8080**

3. 要重設 winhttpProxy，請輸入以下命令並按 **Enter** 鍵：

     `netsh winhttp reset proxy`

若要瞭解詳細資訊。，請參見 [Netsh 命令語法、上下文和格式](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts)。


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a>在 Proxy 伺服器中啟用對端點 DLP 雲端服務 URL 的存取

如果 Proxy 或防火牆在預設情況下封鎖所有流量，並且只允許特定網域通過，請將可下載工作表中列出的網域新增到允許的網域清單中。

此[可下載的試算表](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/security/threat-protection/microsoft-defender-atp/downloads/mdatp-urls.xlsx)列出了網路必須能夠連線至的服務及其關聯的 URL。 應該確保沒有防火牆或網路篩選規則會拒絕存取這些 URL，或者可能需要專門為它們建立允許規則。

如果 Proxy 或防火牆啟用了 HTTPS 掃描 (SSL 檢查)，則從 HTTPS 掃描中排除上表中列出的網域。
如果 Proxy 或防火牆封鎖匿名流量，因為端點 DLP 是從系統内容連線的，請確保前面列出的 URL 中允許匿名流量。

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a>驗證用戶端與 Microsoft 雲端服務 URL 的連線

驗證 Proxy 設定是否成功完成，WinHTTP 是否可以在您的環境中發現 Proxy 伺服器並透過 Proxy 伺服器進行通訊，以及 Proxy 伺服器是否允許到適用於端點的 Defender 服務 URL 的通訊息。

1. 將 [MDATP 用戶端分析器工具](https://aka.ms/mdatpanalyzer)下載到執行端點 DLP 的電腦上。
2. 擷取裝置上 MDATPClientAnalyzer.zip 的內容。
3. 開啟提高權限的命令列：
    1. 轉至 **[開始]** 並鍵入 **「cmd」**。
    1. 以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。
4.  輸入以下命令，再按 **Enter**：
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

例如，用下載 MDATPClientAnalyzer 工具的路徑取代 *HardDrivePath*
    
**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**


5.  在 _HardDrivePath* 中使用的資料夾中擷取由工具建立的 **MDATPClientAnalyzerResult.zip** _ 文件。

6.  開啟 **MDATPClientAnalyzerResult.txt** 並驗證是否已執行 Proxy 設定步驟以啟用伺服器發現和對服務 URL 的存取。  該工具檢查適用於端點的 Defender 用戶端設定為與之互動的適用於端點的 Defender 服務 URL 的連線性。 然後，它將結果列印到每個可能用於與適用於端點的 Defender 服務進行通訊之 URL 的 **MDATPClientAnalyzerResult.txt** 文件中。 例如：

    **測試 URL：https://xxx.microsoft.com/xxx</br>1 - 預設 Proxy：成功 (200) </br>2 - Proxy自動發現 (WPAD)：成功 (200) </br> 3 - 停用 Proxy：成功 (200) </br> 4 - 命名的 Proxy：不存在 </br> 5 - 命令列 Proxy：不存在**</br>


如果至少有一個連線選項退回 (200) 適用於端點的 Defender 用戶端可以使用此連線方法與測試的 URL 正確通訊。 

但是，如果連線檢查結果顯示失敗，則會顯示 HTTP 錯誤 (請參閱 HTTP 狀態碼)。 然後可以使用[啟用對端點 DLP 雲端服務 URL 的存取](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)中所示的表中的 URL。 您將使用的 URL 將取決於上線過程中選取的區域。
[!NOTE]連線分析程式工具與 ASR 規則不相容[封鎖源自 PSExec 和 WMI 命令的流程建立](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。 需要暫時停用此規則才能執行連線工具。

[!NOTE] 在登錄中或透過群組原則設定 TelemetryProxyServer 時，如果適用於端點的 Defender 無法存取定義的 Proxy，它將回復至 direct。
相關主題 • 上線 Windows 10 裝置 • Microsoft 端點 DLP 上線問題疑難排解





## <a name="see-also"></a>另請參閱

- [深入了解端點資料外洩防護](endpoint-dlp-learn-about.md)
- [使用端點資料外洩防護](endpoint-dlp-using.md)
- [資料外洩防護概觀](data-loss-prevention-policies.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [開始使用活動總管](data-classification-activity-explorer.md)
- [適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 電腦上線的工具及方法 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。
- [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [加入 Azure AD 的裝置](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。
