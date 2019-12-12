---
title: 偵測並修復 Outlook 規則及自訂表單資料隱碼攻擊的 Office 365 中
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
description: 了解如何識別並修復 Outlook 規則及 Office 365 中的自訂表單資料隱碼攻擊
ms.openlocfilehash: d5f4a653463f4105df025bf29679465ca5335098
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970789"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>偵測並修復 Office 365 中 Outlook 規則與自訂表單插入式攻擊

**摘要**了解如何識別並修復 Outlook 規則及 Office 365 中的自訂表單資料隱碼攻擊。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>什麼是 Outlook 規則及自訂表單資料隱碼攻擊？

攻擊者已在您的租用破壞帳戶，並取得之後，那里即將試，並建立的方式來保持連絡或回復之後找出並移除的方式。 這稱為建立持續性的機制。 他們可以執行此作業的兩種方法是藉由利用 Outlook 規則或插入至 Outlook 的自訂表單。
在這兩種情況下，規則] 或 [表單同步處理自雲端服務下桌面用戶端上，以便為完整的格式並重新安裝用戶端軟體不會排除資料隱碼攻擊的機制。 這是因為 Outlook 用戶端軟體重新連線到雲端信箱時它將會重新下載規則與從雲端的表單。 一旦規則及表單中的位置，攻擊者就會使用它們來執行遠端或自訂的程式碼，通常是在本機電腦上安裝惡意程式碼。 惡意程式碼再重新竊取認證，或執行其他非法活動。
好消息是，如果您保留您修補的最新版本的用戶端，您不會為受到為目前的 Outlook 用戶端預設會封鎖這兩個機制。

攻擊通常請依循下列模式：

**利用規則**：

1. 攻擊者竊取的使用者名稱和密碼的其中一個使用者。

2. 攻擊者然後登入該使用者的 Exchange 信箱。 信箱可以是在 Exchange online 或 Exchange 內部部署。

3. 攻擊者然後建立信箱信箱可接收電子郵件符合準則的規則時所觸發的轉寄規則。 規則的條件以及觸發電子郵件的內容是特製彼此。

4. 攻擊者通常使用其信箱的使用者所傳送的觸發電子郵件。

5. 收到電子郵件時，就會觸發規則。 規則的巨集指令通常是以啟動遠端 (WebDAV) 伺服器上的應用程式。

6. 應用程式通常惡意程式碼、 [Powershell 帝國](https://www.powershellempire.com/)，例如在本機上安裝在使用者的電腦。

7. 惡意程式碼讓駭客重新竊取使用者的使用者名稱與密碼或從本機電腦的其他認證，並執行其他惡意活動。

**利用表單**：

1. 攻擊者竊取的使用者名稱和密碼的其中一個使用者。

2. 攻擊者然後登入該使用者的 Exchange 信箱。 信箱可以是在 Exchange online 或 Exchange 內部部署。

3. 攻擊者再建立自訂郵件表單範本，並將它插入該使用者的信箱。 當信箱可接收的電子郵件，需要載入自訂表單的信箱時，就會觸發自訂表單。 自訂表單和電子郵件的格式是特製彼此。
4. 攻擊者會觸發電子郵件傳送給通常使用其信箱的使用者。

5. 載入表單時收到電子郵件時。 表單啟動遠端 (WebDAV) 伺服器上的應用程式。

6. 應用程式通常惡意程式碼、 [Powershell 帝國](https://www.powershellempire.com/)，例如在本機上安裝在使用者的電腦。

7. 惡意程式碼讓駭客重新竊取使用者的使用者名稱與密碼或從本機電腦的其他認證，並執行其他惡意活動。

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>查看規則及自訂表單資料隱碼攻擊看起來會像 Office 365？

這些保存性機制不太可能會注意到您的使用者所且可能在某些情況下偶數會看不到它們。 本文將告訴您如何尋找下面列出任何七個符號 （危害指標）。 如果您發現任何這些，您需要採取補救步驟。

- 規則的指標危害：

  - 規則動作是要啟動的應用程式。

  - 規則參考 EXE、 ZIP 或 URL。

  - 在本機電腦中，尋找 [來自 Outlook PID 的新程序開始。

- 自訂表單的指標危害：

  - 自訂表單存在另存為他們自己的郵件類別。

  - 郵件類別包含可執行程式碼。

  - 通常儲存在個人表單檔案庫] 或 [收件匣] 資料夾中。

  - 表單是名為 IPM。附註。[自訂名稱]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>尋找這類攻擊的跡象，並確認它的步驟

您可以使用下列兩種方法之一來確認攻擊：

- 手動檢查的規則和每個信箱使用 Outlook 用戶端的表單。 這個方法是徹底，但您只能用來檢查信箱使用者一次可以是相當耗時如果您有許多使用者檢查。 它也可能導致您正在執行從存回之電腦的外洩。

- 使用[Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 指令碼來自動傾印轉寄規則與自訂表單的每個使用者在您的租用中的所有郵件。 這是使用最少的額外負荷量的最快和最安全方法。

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>確認規則攻擊使用 Outlook 用戶端

1. 使用者以開啟使用者的 Outlook 用戶端。 使用者可能需要您在檢查其信箱上的規則的協助。

2. 請參閱[使用規則管理電子郵件訊息](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59)文章如何在 Outlook 中開啟的規則介面上的程序。

3. 查詢規則，未建立使用者，或任何未預期的規則或規則的可疑的名稱。

4. 規則動作的規則描述中尋找該開始和應用程式或參照。EXE、。ZIP 檔案，或啟動 URL。

5. 尋找任何新的程序，開始使用 Outlook 處理序識別碼。 若要[尋找的程序識別碼](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)，請參閱。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>若要確認表單的步驟來進行攻擊使用 Outlook 用戶端

1. 使用者以開啟使用者的 Outlook 用戶端。

2. 請遵循使用者的 Outlook 版本中，[顯示 [開發人員] 索引標籤](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45)的步驟。

3. 在 Outlook 中開啟 [現在顯示開發人員] 索引標籤，然後按一下 [**設計表單**。

4. 從 [查詢] 清單**中**，選取 [**收件匣**。 尋找任何自訂表單。 自訂表單很少，如果您有任何自訂表單完全，它是值得更深入的外觀。

5. 調查任何自訂表單、 特別標示為隱藏。

6. 開啟任何自訂表單，並在 [**表單**] 群組中按一下 [**檢視程式碼**，請參閱什麼執行時載入表單時。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>若要確認的規則及表單的步驟來進行攻擊使用 PowerShell

若要驗證規則的最簡單方式或自訂表單攻擊 」 會執行[Get AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 指令碼。 此指令碼連線至租用戶中的每個信箱和傾印的所有規則和表單到兩個.csv 檔案。

#### <a name="pre-requisites"></a>先決條件

您必須擁有的全域系統管理員權限，因為指令碼連線至租用戶讀取的規則及表單中的每個信箱執行指令碼。

1. 登入您要執行的指令碼以本機系統管理員權限的電腦。

2. 下載或從 GitHub Get AllTenantRulesAndForms.ps1 指令碼複製到資料夾，會從中執行它。 指令碼會建立兩個日期加上戳記檔案，這個資料夾、 MailboxFormsExport-yyyy-公釐-dd.csv 及 MailboxRulesExport yyyy-公釐 dd.csv。

3. 開啟身為系統管理員的 PowerShell 執行個體，然後開啟您儲存至指令碼的資料夾。

4. 執行此 PowerShell 命令列，如下所示`.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>解譯輸出

- **MailboxRulesExport-*-yyyy-mm-dd*.csv**： 檢查巨集指令的條件，包括應用程式或可執行檔 （每個資料列的其中一個） 的規則：

  - **ActionType （欄 A）**： 如果您看到 「 ID_ACTION_CUSTOM 」 的值，此規則會可能惡意。

  - **IsPotentiallyMalicious （D 欄）**： 此值為"TRUE"，規則是否可能惡意。

  - **ActionCommand （資料行 G）**： 這會列出應用程式或任何檔具有.exe、.zip 副檔名或參照至的 URL，不應該在那裡，項目規則是否可能惡意。

- **MailboxFormsExport-*-yyyy-mm-dd*.csv**： 在 [一般] 自訂表單的用途是很少見。 如果您發現任何此活頁簿中，您會開啟該使用者的信箱，並檢查表單本身。 如果您的組織沒有不將它放有刻意，很可能是惡意。

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>如何停止和修復 Outlook 規則及表單攻擊

如果您發現這些攻擊的任何辨識項，補救很簡單，只要從信箱中刪除規則] 或 [表單。 您可以利用 Outlook 用戶端或使用遠端 PowerShell 移除的規則來進行此作業。

### <a name="using-outlook"></a>使用 Outlook

1. 識別使用者已與 Outlook 搭配使用的所有裝置。 他們將所有需要的潛在的惡意程式碼會清除。 不允許使用者登入，並使用電子郵件，直到已清除所有的裝置。

2. 請依照下列每個裝置中[刪除規則](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f)的步驟。

3. 如果您不確定相關的其他惡意程式碼存在，您可以設定的格式，並重新安裝在裝置上的所有軟體。 行動裝置的您可以依照製造商以將裝置重設成出廠預設值的影像。

4. 安裝最新版本的 Outlook。 請記住，目前版本的 Outlook 預設會封鎖這兩種此類攻擊。

5. 一旦已經移除所有的信箱的離線複本，重設使用者的密碼 （高品質其中會使用），如果已經尚未啟用 MFA，請遵循[Office 365 使用者設定多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)] 中的步驟。 這可確保使用者的認證，不會公開透過其他方式 （例如網路釣魚或密碼重複使用）。

### <a name="using-powershell"></a>使用 PowerShell

有兩個遠端 PowerShell 指令程式可移除或停用危險的規則。 請按照步驟。

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Exchange 伺服器上的信箱的步驟

1. 連線至 Exchange 伺服器使用遠端 PowerShell。 遵循在 [[連線到 Exchange 伺服器使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)的步驟。

2. 如果您想要完全移除單一規則，多個規則或從信箱的所有規則使用[Remove-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)指令程式。

3. 如果您想要保留規則，並使用[Disable-inboxrule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)指令程式，供進一步調查其內容。

#### <a name="steps-for-mailboxes-in-exchange-online"></a>在 Exchange Online 信箱的步驟

1. 請依照[使用連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中的步驟。

2. 如果您想要完全移除單一規則，多個規則或從信箱的所有規則使用[移除收件匣規則](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)指令程式。

3. 如果您想要保留規則，並使用[Disable-inboxrule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)指令程式，供進一步調查其內容。

## <a name="how-to-minimize-future-attacks"></a>如何減少未來的攻擊

### <a name="first-protect-your-accounts"></a>第一個： 保護您的帳戶

規則與表單攻擊才會使用攻擊之後他們有竊取或破壞您的使用者帳戶的其中一個。 因此，若要避免使用您的組織對這些攻擊的您第一步是積極地保護您的使用者帳戶。 其中一些帳戶會破壞的常用方法是透過網路釣魚或[密碼噴射](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)攻擊。

若要保護您的使用者帳戶，並特別是您系統管理員帳戶，最好是以[設定 Office 365 使用者的多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。 您也應該：

- 監視您的使用者帳戶是[存取和使用](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)的方式。 您可能不會使初始資料外洩，但您將來偵測此類更快速地縮短持續時間和資料外洩的影響。 您可以使用這些[Office 365 雲端 App 安全性原則](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)來監視您的帳戶與上不尋常的活動警訊：

  - **多個失敗的登入**： 這個原則設定檔環境和觸發提醒使用者有關學的比較基準，這可能表示嘗試外洩的單一工作階段中執行多個失敗的登入活動時。

  - **Impossible 旅行**： 這個原則設定檔環境和活動從相同的使用者在不同位置中偵測到兩個位置之間的預期的旅行時間較短的期間內時，會觸發警示。 這可能表示不同的使用者使用相同的認證。 偵測這個異常行為區間初始學習一段期間它可學習新使用者的活動模式的七天。

  - **不尋常模擬活動 （依使用者）**： 此原則設定檔環境和使用者執行多個模擬的活動相對於基線學會，在單一工作階段中這可能表示嘗試外洩時，會觸發警示。

- 利用[Office 365 安全分數](https://securescore.office.com/)若要管理帳戶的安全性組態與行為這類的工具。

### <a name="second-keep-your-outlook-clients-current"></a>第二個： 您的 Outlook 用戶端維持最新狀態

根據預設，完全更新及修補版本的 Outlook 2013 和 2016年停用 「 啟動應用程式 」 規則] / [表單動作。 這可確保，即使攻擊破壞帳戶，規則] 和 [表單動作會被封鎖。 您可以藉由遵循[安裝 Office](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5)更新的安裝最新的更新與安全性修補程式。

以下是 Outlook 2013 和 2016年用戶端的修補程式版本：

- **Outlook 2016**: 16.0.4534.1001 或更高版本。

- **Outlook 2013**: 15.0.4937.1000 或更新版本。

如需有關個別安全性修補程式的詳細資訊，請參閱：

- [Outlook 2016 安全性修補程式](https://support.microsoft.com/help/3191883)

- [Outlook 2013 安全性修補程式](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>第三個： 監視您的 Outlook 用戶端

請注意，即使與修補程式安裝的更新，它是以變更本機電腦設定若要重新啟用 「 啟動應用程式 」 行為攻擊者可能。 您可以使用[進階群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)來監視及強制執行您的用戶端上的本機電腦原則。

您可以查看是否 「 啟動應用程式 」 已重新啟用透過覆寫登錄中所使用的資訊[如何檢視使用 64 位元版本的 Windows 系統登錄](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows)中。 請檢查這些子機碼：

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

機碼 EnableUnsafeClientMailRules 外觀。 如果它有且設為 1，已覆寫 Outlook 安全性修補程式和電腦很容易表單讀規則攻擊。 如果值為 0，會停用的 「 啟動應用程式 」 巨集指令。 如果已安裝的 Outlook 更新及修補版本，而且此登錄機碼不存在，則系統不會受到攻擊。

與內部部署 Exchange 安裝的客戶應該考慮封鎖舊版 Outlook 沒有可用的修補程式。 可以[設定 Outlook 用戶端封鎖](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)」 文件中找到此程序的詳細資訊。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>像網路安全專業人員一般保護 Office 365

您的 Office 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。 使用[Office 365 安全性藍圖的 30 天、 前 90 天及過後的頂端優先順序](security-roadmap.md)來實作 Microsoft 建議的最佳作法為保護您的 Office 365 租用戶。

- 要在前 30 天內完成的工作。 這些工作會有立即的影響，而且對您的使用者影響較低。

- 要在 90 天內完成的工作。 這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。

- 90 天之後。 這些增強功能會在您的前 90 天工作內建置。

## <a name="see-also"></a>請參閱：

- [惡意 Outlook 規則](https://silentbreaksecurity.com/malicious-outlook-rules/)的相關規則向量 SilentBreak 安全性文章提供如何詳細的檢閱 Outlook 規則。

- 關於 Mailrule Pwnage Sensepost 部落格上的[MAPI over HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)討論工具，稱為尺規，可讓您利用透過 Outlook 規則的信箱。

- [Outlook 表單與 shell](https://sensepost.com/blog/2017/outlook-forms-and-shells/)關於表單威脅向量 Sensepost 部落格上。

- [尺規程式碼基底](https://github.com/sensepost/ruler)

- [尺規指標的危害](https://github.com/sensepost/notruler/blob/master/iocs.md)
