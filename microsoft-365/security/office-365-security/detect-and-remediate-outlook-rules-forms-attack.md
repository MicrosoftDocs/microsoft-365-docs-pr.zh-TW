---
title: 偵測並修復 Outlook 規則和自訂表單注入攻擊。
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6e818d05465f7b91268cc44c345c6699e8c6d0ed
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034813"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>偵測並修復 Outlook 規則和自訂表單注入攻擊

**摘要**瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Outlook 規則和自訂表單植入攻擊是什麼？

當攻擊者破壞您租用中的帳戶並取得時，會嘗試並建立一種方式，以在發現及移除之後，繼續進行，或是取得的方式。 這稱為建立持久性機制。 使用 Outlook 規則或將自訂表單插入 Outlook 的兩種方法可以做到這一點。
在這兩種情況下，規則或表單會從雲端服務同步處理至桌面用戶端，因此完整格式化及重新安裝用戶端軟體不會消除插入機制。 這是因為當 Outlook 用戶端軟體重新連接至雲端中的信箱時，它會從雲端重新下載規則和表單。 當規則和表單就緒後，攻擊者會使用它們來執行遠端或自訂程式碼，通常是在本機電腦上安裝惡意程式碼。 惡意程式碼接著重新竊取認證或執行其他非法活動。
以下是一個好的資訊：如果您將用戶端保持在最新版本的補丁，您就不會因為目前的 Outlook 用戶端預設會封鎖這兩種機制，所以威脅不會受到威脅。

攻擊通常遵循下列模式：

**規則會利用**下列專案：

1. 攻擊者竊取其中一個使用者的使用者名稱和密碼。

2. 然後，攻擊者會登入該使用者的 Exchange 信箱。 信箱可以位於 Exchange online 中，也可以位於 Exchange 內部部署中。

3. 然後，攻擊者會在信箱收到符合規則準則的電子郵件時，在觸發的信箱中建立轉移規則。 規則的準則及觸發器電子郵件的內容是針對彼此進行量身定制的。

4. 攻擊者會將觸發器電子郵件傳送至一般使用信箱的使用者。

5. 收到電子郵件時，會觸發規則。 規則的動作通常是在遠端（WebDAV）伺服器上啟動應用程式。

6. 應用程式通常會在使用者的電腦上，以本機方式安裝惡意程式碼，例如[Powershell Empire](https://www.powershellempire.com/)。

7. 惡意程式碼可讓攻擊者重新竊取使用者的使用者名稱和密碼，或從本機機器重新竊取其他認證，以及執行其他惡意活動。

**表單利用**方式：

1. 攻擊者竊取其中一個使用者的使用者名稱和密碼。

2. 然後，攻擊者會登入該使用者的 Exchange 信箱。 信箱可以位於 Exchange online 中，也可以位於 Exchange 內部部署中。

3. 然後，攻擊者會建立自訂的郵件表單範本，並將其插入使用者的信箱。 當信箱收到需要信箱載入自訂表單的電子郵件時，就會觸發自訂表單。 自訂表單和電子郵件的格式是針對彼此進行量身定制。
4. 攻擊者會將觸發器電子郵件傳送給使用者，該使用者一般會使用其信箱。

5. 當接收到電子郵件時，就會載入表單。 表單會在遠端（WebDAV）伺服器上啟動應用程式。

6. 應用程式通常會在使用者的電腦上，以本機方式安裝惡意程式碼，例如[Powershell Empire](https://www.powershellempire.com/)。

7. 惡意程式碼可讓攻擊者重新竊取使用者的使用者名稱和密碼，或從本機機器重新竊取其他認證，以及執行其他惡意活動。

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>規則和自訂表單植入攻擊可能類似于 Office 365？

您的使用者可能會注意到這些持續性機制，但在某些情況下，您可能會看不到這些功能。 本文將告訴您如何尋找下列列出的七個符號（有損損）中的任何一個。 如果您找到上述任一項，您必須採取補救步驟。

- 規則受損的指標：

  - 規則動作是要啟動應用程式。

  - 規則參照 EXE、ZIP 或 URL。

  - 在本機電腦上，尋找來自 Outlook P&ID 的新進程開始。

- 自訂表單受損的指標：

  - 顯示的自訂表單會另存為自己的郵件類別。

  - 郵件類別包含可執行程式碼。

  - 通常儲存在個人表單庫或 [收件匣] 資料夾中。

  - 表單命名為 IPM。注意。[custom name]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>尋找此攻擊之徵兆及確認的步驟

您可以使用下列兩種方法之一來確認攻擊：

- 使用 Outlook 用戶端，手動檢查每個信箱的規則和表單。 這種方法是完整的，但是您一次只能檢查信箱使用者，如果您有許多使用者可供檢查，就會非常耗費時間。 也可能會造成您正在執行檢查的電腦遭到破壞。

- 使用 PowerShell [Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1)腳本可自動為您租使用者中的所有使用者轉儲所有的郵件轉寄規則和自訂表單。 這是最快且最安全的方法，最少量的開銷。

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>使用 Outlook 用戶端確認規則攻擊

1. 以使用者身分開啟使用者 Outlook 用戶端。 使用者可能需要協助您檢查其信箱上的規則。

2. 如需如何在 Outlook 中開啟規則介面的程式，請參閱[使用規則文章管理電子郵件訊息](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59)。

3. 尋找使用者未建立的規則，或任何未預期的規則或具有可疑名稱的規則。

4. 請參閱規則描述，以取得啟動和應用程式或參考的規則動作。Exe。ZIP 檔或啟動 URL。

5. 尋找任何開始使用 Outlook 進程識別碼的新程式。 請參閱[尋找進程識別碼](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>使用 Outlook 用戶端確認表單攻擊的步驟

1. 以使用者身分開啟使用者 Outlook 用戶端。

2. 遵循中的步驟，顯示 Outlook 使用者版本的[[開發人員]](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45)索引標籤。

3. 開啟 Outlook 中的 [now visible developer] 索引標籤，然後按一下 [**設計表單**]。

4. 從 [**查找範圍**] 清單中選取 [**收件**匣]。 尋找任何自訂表單。 自訂表單非常少見，如果您有任何自訂表單，則需要更深入的外觀。

5. 調查任何自訂表單，尤其是標示為隱藏的表單。

6. 開啟任何自訂表單，然後在**表單**群組中按一下 [ **View Code** ] （查看表單載入時執行的功能）。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>使用 PowerShell 確認規則和表單攻擊的步驟

驗證規則或自訂表單攻擊的最簡單方法，就是執行[Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script。 此腳本會連線至您租使用者中的每個信箱，並將所有規則和表單轉儲成兩個 .csv 檔案。

#### <a name="pre-requisites"></a>先決條件

您必須具有全域系統管理員許可權，才能執行腳本，因為腳本會連線至租用中的每個信箱，以讀取規則和表單。

1. 以本機系統管理員許可權登入您將執行腳本的電腦。

2. 將 Get-AllTenantRulesAndForms 腳本從 GitHub 下載或複製到要從中執行它的資料夾。 腳本會建立兩個日期戳檔案至此資料夾、MailboxFormsExport-yyyy-mm-dd 及 MailboxRulesExport-yyyy-mm-dd。

3. 以系統管理員身分開啟 PowerShell 實例，然後開啟您用來儲存腳本的資料夾。

4. 以 .\Get-AllTenantRulesAndForms.ps1 的方式`.\Get-AllTenantRulesAndForms.ps1`執行此 PowerShell 命令列

#### <a name="interpreting-the-output"></a>解讀輸出

- **MailboxRulesExport-*yyyy-dd***：檢查規則（每列一個）是否有包含應用程式或可執行檔的動作條件：

  - **ActionType （資料行 A）**：如果看到值 "ID_ACTION_CUSTOM"，該規則可能是惡意的。

  - **IsPotentiallyMalicious （欄 D）**：如果此值為 "TRUE"，則此規則可能是惡意的。

  - **ActionCommand （Column G）**：如果這會列出應用程式或任何副檔名為 .exe、.zip 副檔名的專案，或是參照 URL 的專案，則該規則可能是惡意的。

- **MailboxFormsExport-*yyyy-yyyy***：一般說來，使用自訂表單非常少見。 如果您在此活頁簿中找到任何的，請開啟該使用者的信箱，並檢查該表單本身。 如果您的組織未有意放入該組織，可能是惡意的。

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>如何停止和修復 Outlook 規則和表單攻擊

如果您發現其中任何一種攻擊的證據，修正很簡單，只需要從信箱中刪除規則或表單即可。 您可以使用 Outlook 用戶端或使用遠端 PowerShell 來移除規則。

### <a name="using-outlook"></a>使用 Outlook

1. 識別使用者已用於 Outlook 的所有裝置。 所有的潛在惡意程式碼都必須清除。 不允許使用者登入並使用電子郵件，直到所有裝置都已清除為止。

2. 依照刪除每個裝置的[規則](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f)中的步驟進行。

3. 如果您不確定是否存在其他惡意程式碼，您可以格式化及重新安裝裝置上的所有軟體。 針對行動裝置，您可以遵循製造商的步驟，將裝置重設為出廠影像。

4. 安裝最新版本的 Outlook。 請記住，目前的 Outlook 版本會封鎖這兩種攻擊類型的預設值。

5. 移除信箱的所有離線副本之後，請重設使用者的密碼（使用高品質的密碼），並依照[設定多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)中的步驟進行，如果尚未啟用 MFA。 這可確保使用者的認證不會透過其他方式公開（例如網路釣魚或密碼重複使用）。

### <a name="using-powershell"></a>使用 PowerShell

您可以使用兩個遠端 PowerShell Cmdlet 來移除或停用危險的規則。 只需遵循步驟。

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Exchange 伺服器上的信箱步驟

1. 使用遠端 PowerShell 連接至 Exchange 伺服器。 依照[[使用遠端 PowerShell 連線到 Exchange 伺服器]](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)中的步驟進行。

2. 如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用[Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule) Cmdlet。

3. 如果您想要保留規則及其內容以進行進一步調查，請使用[Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) Cmdlet。

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Exchange Online 中的信箱步驟

1. 依照[[使用 PowerShell 連線到 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中的步驟進行。

2. 如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用 [[移除收件匣規則](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)] Cmdlet。

3. 如果您想要保留規則及其內容以進行進一步調查，請使用[Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) Cmdlet。

## <a name="how-to-minimize-future-attacks"></a>如何最小化未來的攻擊

### <a name="first-protect-your-accounts"></a>第一種：保護您的帳戶

只有在竊取或破壞使用者的帳戶之後，攻擊者才會使用這些規則和表單攻擊。 因此，避免對您的組織使用這些入侵的第一步，是要積極保護您的使用者帳戶。 一些最常見的帳戶破壞方式是透過網路釣魚或[密碼 spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)攻擊。

保護使用者帳戶的最佳方法（特別是管理員帳戶）是為[使用者設定多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。 您也應該：

- 監視如何[存取及使用](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)您的使用者帳戶。 您可能不會防止初始遭到破壞，但是您會儘早偵測，以縮短破壞的持續時間和破壞影響。 您可以使用這些[Office 365 雲端 App 安全性原則](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)，監控不尋常活動的帳戶和警示：

  - **多個失敗的登入嘗試**：這個原則設定檔您的環境，當使用者在與所學的基準相關的單一會話中執行多個失敗的登入活動時，便會觸發警示，這可能表示企圖遭到破壞。

  - 不**可能的旅行**：這項原則會在不同位置的相同使用者中偵測到活動時，在兩個位置之間的時間範圍內，以短于預期的旅行時間。 這可能表示不同的使用者使用相同的認證。 偵測到這種反常行為時，會有七天的初始學習週期，以瞭解新使用者的活動模式。

  - 不**尋常的模仿活動（依使用者）**：這項原則會在使用者執行多個模擬活動時，在與基線相關的單一會話中執行多個模擬活動，這可能表示企圖遭到破壞。

- 利用類似[Office 365 安全分數](https://securescore.office.com/)的工具來管理帳戶安全性設定和行為。

### <a name="second-keep-your-outlook-clients-current"></a>第二：讓 Outlook 用戶端保持最新

完全更新及修補的 Outlook 2013 版本，而2016預設會停用「啟動應用程式」規則/表單動作。 這可確保即使攻擊者破壞帳戶，規則和表單動作也會遭到封鎖。 您可以遵循[安裝 Office 更新](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5)中的步驟，安裝最新的更新及安全性修補程式。

以下是 Outlook 2013 和2016用戶端的修補程式版本：

- **Outlook 2016**：16.0.4534.1001 或更新版本。

- **Outlook 2013**：15.0.4937.1000 或更新版本。

如需個別安全性修補程式的詳細資訊，請參閱：

- [Outlook 2016 安全性修補程式](https://support.microsoft.com/help/3191883)

- [Outlook 2013 安全性修補程式](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>第三：監控 Outlook 用戶端

請注意，即使已安裝修補程式和更新，攻擊者還是可以變更本機電腦設定，以重新啟用「啟動應用程式」行為。 您可以使用[高級群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)，在用戶端上監視及強制執行本機電腦原則。

您可以使用[Windows 的64位版本](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows)資訊，查看是否已透過登錄中的覆寫方式重新啟用 [啟動應用程式]。 請檢查下列子項：

- **Outlook 2016**：`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**：`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

尋找機碼 EnableUnsafeClientMailRules。 如果已存在，且已設定為1，Outlook 安全性修補程式已被取代，且電腦受到表單/規則攻擊的影響。 如果值為0，就會停用「啟動應用程式」動作。 如果已安裝更新及修補的 Outlook 版本，但此登錄機碼不存在，系統就不會受到攻擊。

使用內部部署 Exchange 安裝的客戶應考慮封鎖舊版本的 Outlook，但沒有可用的修補程式。 有關此程式的詳細資訊，請參閱[設定 Outlook 用戶端封鎖](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)一文。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>像網路安全專業人員一般保護 Microsoft 365

您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。 使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。

- 要在前 30 天內完成的工作。 這些工作會有立即的影響，而且對您的使用者影響較低。

- 要在 90 天內完成的工作。 這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。

- 90 天之後。 這些增強功能會在您的前 90 天工作內建置。

## <a name="see-also"></a>另請參閱：

- [惡意的 Outlook 規則](https://silentbreaksecurity.com/malicious-outlook-rules/)SilentBreak 安全性文章關於規則向量可提供 Outlook 規則的詳細評論。

- [MAPI OVER HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) On the Sensepost Blog On Mailrule Pwnage 討論稱為尺規的工具，可讓您透過 Outlook 規則利用信箱。

- Sensepost 博客上有關表單威脅向量的[Outlook 表單及 shell](https://sensepost.com/blog/2017/outlook-forms-and-shells/) 。

- [尺規基本代碼](https://github.com/sensepost/ruler)

- [尺規指標洩露](https://github.com/sensepost/notruler/blob/master/iocs.md)
