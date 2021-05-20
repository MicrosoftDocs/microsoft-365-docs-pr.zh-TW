---
title: 在 Microsoft Defender for Endpoint 中對裝置採取回應動作
description: 在裝置（例如隔離裝置、收集調查套件、管理標記、執行 av 掃描及限制應用程式執行）上採取回應動作。
keywords: 回應、隔離、隔離裝置、收集調查套件、動作中心、限制、管理標記、av 掃描、限制應用程式
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
ms.openlocfilehash: ae8b08ce3d5bcc34e91f031223108fca053348ce
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572390"
---
# <a name="take-response-actions-on-a-device"></a>在裝置上採取回應動作

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-respondmachine-abovefoldlink) 

透過隔離裝置或收集調查套件，快速回應偵測到的攻擊。 對裝置採取動作後，您可以在「行動中心」查看活動詳細資料。

回應動作會沿著特定裝置頁面的頂端執行，並包含：

- 管理標籤
- 啟動自動調查
- 啟動 Live Response Session
- 收集調查套件
- 執行防毒掃描
- 限制應用程式執行
- 隔離裝置
- 諮詢威脅專家
- 控制中心

[![回應動作 ](images/response-actions.png) 的影像](images/response-actions.png#lightbox)

 您可以從下列任何一種視圖中尋找裝置頁面：

- **安全性作業儀表板** -從危險卡的裝置中選取裝置名稱。
- **警示佇列** - 從警示佇列中選取裝置圖示旁邊的裝置名稱。
- **裝置清單** -從 [裝置] 清單中選取裝置名稱的標題。
- **搜尋方塊** - 從下拉式功能表中選取裝置並輸入裝置名稱。

>[!IMPORTANT]
> - 這些回應動作只適用于 Windows 10 版本1703或更新版本上的裝置。 
> - 針對非 Windows 的平臺，回應功能 (如裝置隔離) 取決於協力廠商功能。

## <a name="manage-tags"></a>管理標籤

新增或管理標記以建立邏輯群組從屬關係。 裝置標籤支援網路的正確對應，使您能够附加不同的標籤以擷取内容，並作為事件的一部分啟用動態清單建立。

如需裝置標記的詳細資訊，請參閱 [Create and manage device tags](machine-tags.md)。

## <a name="initiate-automated-investigation"></a>啟動自動調查

您可以視需要在裝置上啟動新的一般用途自動調查。 在執行調查時，系統會將從裝置產生的任何其他警示新增至進行中的自動調查，直到完成調查為止。 此外，如果在其他裝置上看到相同威脅，就會將這些裝置新增至調查。

如需自動調查的詳細資訊，請參閱 [自動化調查的概述](automated-investigations.md)。

## <a name="initiate-live-response-session"></a>啟動 Live Response Session

Live response 是一種可讓您透過遠端命令介面連線對裝置進行暫態存取的功能。 這可讓您在深入調查工作中進行工作，並立即採取回應動作，及時包含已識別的威脅（即時）。

Live response 的設計目的是讓您可以收集法律調查資料、執行腳本、傳送可疑實體以進行分析、修正威脅，以及主動搜尋新興威脅。

如需即時回應的詳細資訊，請參閱 [使用即時回應調查裝置上的實體](live-response.md)。

## <a name="collect-investigation-package-from-devices"></a>從裝置收集調查套件

作為調查或回應程式的一部分，您可以從裝置收集調查套件。 透過收集調查套件，您可以識別目前的裝置狀態，並進一步瞭解攻擊者所使用的工具和技術。

若要下載封裝 (Zip 檔案) 並調查裝置上發生的事件

1. 從 [裝置] 頁面頂端的 [回應] 動作列中，選取 [ **收集調查套件** ]。
2. 在文字方塊中指定您要執行此動作的原因。 選取 [確認 **]**。
3. 將下載 zip 檔案

另一種方法：

1. 從 [裝置] 頁面的 [回應動作] 區段中，選取 [ **操作中心** ]。

    ![動作中心按鈕的圖像](images/action-center-package-collection.png)

3. 在 [動作中心] 飛出中，選取 [ **套件集合套件可供** 下載 zip 檔案]。
  
    ![下載套件按鈕的影像](images/collect-package.png)

套件包含下列資料夾：

| 資料夾 | 描述 |
|:---|:---------|
|Autoruns | 包含一組檔案，每一組檔案都代表已知自動啟動進入點之登錄的內容， (ASEP) 協助識別攻擊者在裝置上的 persistency。 </br></br> <div class="alert"><b>附注：</b> 如果找不到登錄機碼，該檔案會包含下列訊息：「錯誤：系統找不到指定的登錄機碼或值」。</div>                                                                                                                                |
|已安裝程式 | 此 .CSV 檔案包含已安裝程式的清單，可協助識別裝置上目前已安裝的元件。 如需詳細資訊，請參閱 [Win32_Product 類別](https://go.microsoft.com/fwlink/?linkid=841509)。                                                                                  |
|網路連線 | 此資料夾包含一組與連線資訊相關的資料點，可協助識別可疑 URLs 的連線、攻擊者的命令和控制 (C&C) 基礎結構、任何橫向移動或遠端連線。</br></br> -ActiveNetConnections.txt –顯示通訊協定統計資料和目前 TCP/IP 網路連線。 可讓您尋找處理常式所進行的可疑連線能力。 </br></br> -Arp.txt –顯示所有介面 (ARP) 快取表的目前位址解析通訊協定。 </br></br> ARP 快取可以在網路上顯示已遭破壞或可疑系統可能已被用來執行內部攻擊的其他主機。</br></br> -DnsCache.txt-顯示 DNS 用戶端解析程式快取的內容，該快取包括從本機主機檔案預先載入的專案，以及電腦所解析之名稱查詢的任何最近取得的資源記錄。 這可協助識別可疑的連線。 </br></br> -IpConfig.txt –顯示所有配接器的完整 TCP/IP 設定。 配接器可以代表實體介面（如已安裝的網路介面卡）或邏輯介面，例如撥號連線。 </br></br> -FirewallExecutionLog.txt 和 pfirewall .log                                                                                  |
| 預回遷檔| Windows預回遷檔案的設計目的是要加速應用程式啟動程式。 可用於追蹤系統最近使用過的所有檔案，並尋找可能已遭刪除但仍可在 [回遷檔] 清單中找到之應用程式的追蹤。 </br></br> -預回遷資料夾–包含預先回遷檔案的複本 `%SystemRoot%\Prefetch` 。 附注：建議下載預回遷檔案檢視器以查看預回遷檔。 </br></br> -PrefetchFilesList.txt –包含所有已複製檔案的清單，這些檔案可用於追蹤回遷資料夾是否有任何複製失敗。                                                                                                      |
| 過程| 包含列出執行中進程的 .CSV 檔案，該檔案可用於識別裝置上所執行的當前進程。 這在識別可疑程式及其狀態時非常有用。                                                                                                                                                                                                       |
| 排程任務| 包含的 .CSV 檔案會列出排程的任務，可用來識別在選取的裝置上自動執行的常式，以尋找設定為自動執行的可疑代碼。                                                                                                                                                                                                      |
| 安全性事件記錄檔| 包含安全性事件記錄檔，其中包含登入或登出活動的記錄，或系統的「審核」原則所指定的其他安全相關事件。 </br></br><div class="alert"><b>附注：</b> 使用 [事件檢視器] 開啟事件記錄檔。</div>                                                                                    |
| 服務| 包含列出服務及其狀態的 .CSV 檔案。                                                                                      |
| Windows伺服器消息區塊 (SMB) 會話 | 列出網路上的各節點之間的檔案、印表機、序列埠及其他通訊的共用存取。 這可協助識別資料 exfiltration 或側向移動。 </br></br> 包含 SMBInboundSessions 和 SMBOutboundSession 的檔案。 </br></br> <div class="alert"><b>附注：</b> 如果沒有會話 (輸入或外寄) ，您會收到文字檔，告訴您找不到任何 SMB 會話。</div>                                                                                                                          |
| 系統資訊| 包含 SystemInformation.txt 檔，其中會列出作業系統版本和網卡等系統資訊。                                                                                     |
| 臨時目錄| 包含一組文字檔，其中列出系統中每位使用者的% Temp% 檔案。 </br></br> 這可協助追蹤攻擊者可能已在系統上丟棄的可疑檔案。 </br></br> <div class="alert"><b>附注：</b> 如果檔案包含下列郵件：「系統找不到指定的路徑」，表示此使用者沒有任何 temp 目錄，可能是因為使用者未登入系統。</div>                                                                                                                                         |
| 使用者和群組| 提供每個檔案的清單，每個檔案都代表一個群組及其成員。                                                                                                                   |
|WdSupportLogs| 提供 MpCmdRunLog.txt 和 MPSupportFiles.cab  </br></br> <div class="alert"><b>附注：</b>此資料夾只會在2月2020更新彙總套件或更新所安裝的 Windows 10 版本1709或更新版本上建立：</br> Win10 1709 (RS3) 組建16299.1717： [KB4537816](https://support.microsoft.com/en-us/help/4537816/windows-10-update-kb4537816) </br> Win10 1803 (RS4) 組建17134.1345： [KB4537795](https://support.microsoft.com/en-us/help/4537795/windows-10-update-kb4537795) </br> Win10 1809 (RS5) 組建17763.1075： [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818) </br> Win10 1903/1909 (19h1/19h2) 組建18362.693 及18363.693： [KB4535996](https://support.microsoft.com/en-us/help/4535996/windows-10-update-kb4535996) </div>                                                                                                                    |
| CollectionSummaryReport.xls| 此檔案是調查套件集合的摘要，它包含資料點清單、用於提取資料的命令、執行狀態，以及失敗時的錯誤代碼。 您可以使用此報告來追蹤套件是否包含所有預期的資料，並識別是否有任何錯誤。 |

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>在裝置上執行 Microsoft Defender 防毒軟體掃描

在調查或回應程式中，您可以從遠端啟動防病毒掃描，以協助識別和修正受損裝置上可能會出現的惡意程式碼。

>[!IMPORTANT]
>- 此動作可用於 Windows 10 版本1709或更新版本的裝置。
>- Microsoft Defender 防毒軟體 (microsoft defender av) 掃描可與其他防病毒方案一起執行，不論 microsoft defender AV 是否使用中防病毒解決方案。 Microsoft Defender AV 可以是被動模式。 如需詳細資訊，請參閱[Microsoft Defender 防毒軟體相容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md)。

您已選取 [ **執行防病毒掃描**]，請選取您想要執行的掃描類型 (快速或完整) 並在確認掃描之前新增批註。

![選取 [快速掃描] 或 [完全掃描] 及 [新增批註] 的通知圖像](images/run-antivirus.png)

動作中心會顯示掃描資訊，裝置時程表會包含新的事件，反映已在裝置上提交掃描動作。 Microsoft Defender AV 警示會反映在掃描期間所呈現的任何偵測。

>[!NOTE]
>使用 Defender for Endpoint response 動作觸發掃描時，Microsoft Defender 防毒程式 ' ScanAvgCPULoadFactor ' 值仍會套用，並限制掃描的 CPU 影響。<br> 如果未設定 ScanAvgCPULoadFactor，則預設值為在掃描期間最多50% 的 CPU 負載限制。<br>
>如需詳細資訊，請參閱 [configure-advanced-掃描類型-microsoft-defender-防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus)。

## <a name="restrict-app-execution"></a>限制應用程式執行

除了透過停止惡意程式以外，您也可以鎖定裝置，並防止後續惡意程式的後續嘗試執行。

>[!IMPORTANT]
> - 此動作可用於 Windows 10 版本1709或更新版本的裝置。
> - 如果您的組織使用 Microsoft Defender 防毒軟體，便可使用此功能。
> - 此巨集指令需要符合 Windows Defender 的應用程式控制代碼完整性原則格式及簽署需求。 如需詳細資訊，請參閱程式 [代碼完整性原則格式及簽署](https://docs.microsoft.com/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing)。

若要限制應用程式的執行，則會套用程式碼完整性原則，只允許檔案以 Microsoft 簽發的憑證簽署。 這種限制方式可協助防止攻擊者控制已受損的裝置，並進一步執行惡意活動。

>[!NOTE]
>您可以在任何時間，撤銷應用程式的限制，使其無法執行。 [裝置] 頁面上的按鈕將變更為 [ **移除應用程式限制**]，然後您可以採取與限制應用程式執行相同的步驟。

當您選取 [限制裝置上的 **應用程式執行** ] 頁面時，輸入注釋並選取 [ **確認**]。 動作中心會顯示掃描資訊，裝置時程表會包含新的事件。

![應用程式限制通知影像](images/restrict-app-execution.png)

**在裝置使用者上的通知**：</br>
當應用程式受到限制時，會顯示下列通知，以告知使用者已限制應用程式執行：

![應用程式限制的影像](images/atp-app-restriction.png)

## <a name="isolate-devices-from-the-network"></a>將裝置與網路隔離

根據攻擊的嚴重性和裝置的靈敏度，您可能想要將裝置與網路隔離。 此巨集指令可協助防止攻擊者控制已遭破壞的裝置，以及執行其他活動，例如資料 exfiltration 及橫向移動。

>[!IMPORTANT]
>- Windows 10 版本1703上的裝置均可使用完整隔離。
>- 在 Windows 10，版本1709或更新版本上，裝置可以使用選擇性隔離。
>- 當隔離裝置時，只允許某些程式和目的地。 因此，在隔離裝置之前，已完全 VPN 隧道後的裝置將無法到達 Microsoft Defender for Endpoint cloud service。 我們建議您針對 Microsoft Defender for Endpoint 使用分割隧道 VPN，並 Microsoft Defender 防毒軟體雲端型保護相關流量。

此裝置隔離功能會中斷已受損的裝置與網路的連線，並保留與 Defender for Endpoint service 的連線，進而繼續監視裝置。

在 Windows 10，版本1709或更新版本中，您將可以進一步控制網路隔離層級。 您也可以選擇啟用 Outlook、Microsoft Teams 及商務用 Skype 連線 (a ' 選擇性隔離」 ) 。

>[!NOTE]
>您可以隨時將裝置重新連線到網路。 裝置頁面上的按鈕將變更為 [ **從隔離釋放**]，然後您可以採取與隔離裝置相同的步驟。

在 [裝置] 頁面上選取 [ **隔離裝置** ] 之後，輸入注釋並選取 [ **確認**]。 動作中心會顯示掃描資訊，裝置時程表會包含新的事件。

![隔離裝置的影像](images/isolate-device.png)

>[!NOTE]
>即使它是與網路隔離的，裝置仍會保持連線至的 Defender for Endpoint service。 如果您已選擇啟用 Outlook 和商務用 Skype 通訊，則在隔離裝置時，您就可以與使用者通訊。

**在裝置使用者上的通知**：</br>
在隔離裝置時，會顯示下列通知，以告知使用者已從網路隔離裝置：

![沒有網路連線的影像](images/atp-notification-isolate.png)

## <a name="consult-a-threat-expert"></a>諮詢威脅專家

您可以參閱 Microsoft 威脅專家，以取得有關可能已遭破壞裝置或已受損裝置的更深入資訊。 Microsoft 威脅專家可以直接從 Microsoft Defender 資訊安全中心內直接參與，以進行及時且準確的回應。 專家不僅針對可能受到損害的裝置提供深入資訊，也能更好地瞭解複雜的威脅、您取得的目標攻擊通知，或者您需要有關提醒的詳細資訊，或是您在入口網站儀表板上看到的威脅情報內容。

如需詳細資訊，請參閱查看 [Microsoft 威脅專家](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) 。


## <a name="check-activity-details-in-action-center"></a>檢查控制中心的活動詳細資料

「 **行動中心** 」提供對裝置或檔案所採取動作的資訊。 您將可以查看下列詳細資料：

- 調查套件集合
- 防病毒掃描
- 應用程式限制
- 裝置隔離

也會顯示所有其他相關詳細資料，例如提交日期/時間、提交使用者，以及動作成功或失敗。

![包含資訊的動作中心影像](images/action-center-details.png)

## <a name="related-topic"></a>相關主題
- [對檔案採取回應動作](respond-file-alerts.md)
- [報表 inaccuracy](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
