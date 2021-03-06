---
title: 偵測並修復 Outlook 規則和自訂表單注入攻擊。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203653"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>偵測和修正 Outlook 規則和自訂表單注入攻擊

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**摘要** 瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Outlook 規則和自訂表單植入攻擊是什麼？

在攻擊者取得組織的存取權之後，他們會嘗試建立 foothold，以在發現之後繼續進行，或回復。 此活動稱為 *建立持續性機制*。 攻擊者可使用 Outlook 建立持續性機制的方式有兩種：

- 利用 Outlook 規則。
- 將自訂表單插入 Outlook。

重新安裝 Outlook，或甚至為受影響的人員提供新電腦將不會有説明。 Outlook 的全新安裝會連接至信箱時，所有的規則和表單都會從雲端進行同步處理。 規則或表單通常是用來執行遠端程式碼，並在本機電腦上安裝惡意程式碼。 惡意程式碼會竊取認證或執行其他非法活動。

好消息是：如果您將 Outlook 用戶端保持在最新版本的狀態，您就不會受到威脅成為目前的威脅 Outlook 用戶端預設會封鎖這兩種機制。

攻擊通常遵循下列模式：

**規則會利用** 下列專案：

1. 攻擊者竊取使用者的認證。

2. 攻擊者會登入該使用者的 Exchange 信箱 (Exchange Online 或內部部署 Exchange) 。

3. 攻擊者會在信箱中建立轉接收件匣規則。 當信箱收到符合規則條件的特定郵件時，就會觸發轉寄規則。 規則條件和郵件格式是針對彼此進行量身定制的。

4. 攻擊者會將觸發器電子郵件傳送至已遭破壞的信箱，而該信箱仍是由使用者無意中使用。

5. 當信箱收到符合規則條件的郵件時，就會套用規則的動作。 一般來說，規則動作是要在遠端 (WebDAV) 伺服器上啟動應用程式。

6. 通常，應用程式會在使用者的電腦上安裝惡意程式碼 (例如， [PowerShell Empire](https://www.powershellempire.com/)) 。

7. 惡意程式碼可讓攻擊者) 使用者的使用者名稱和密碼或本機電腦上的其他認證，以及執行其他惡意活動，以竊取 (或竊取。

**表單利用** 方式：

1. 攻擊者竊取使用者的認證。

2. 攻擊者會登入該使用者的 Exchange 信箱 (Exchange Online 或內部部署 Exchange) 。

3. 攻擊者會將自訂的郵件表單範本插入使用者的信箱。 當信箱從需要信箱載入自訂表單的攻擊者接收特定郵件時，就會觸發自訂表單。 自訂表單和郵件格式是針對彼此進行量身定制。

4. 攻擊者會將觸發器電子郵件傳送至已遭破壞的信箱，而該信箱仍是由使用者無意中使用。

5. 當信箱收到郵件時，信箱會載入所需的表單。 表單會在遠端 (WebDAV) 伺服器上啟動應用程式。

6. 通常，應用程式會在使用者的電腦上安裝惡意程式碼 (例如， [PowerShell Empire](https://www.powershellempire.com/)) 。

7. 惡意程式碼可讓攻擊者) 使用者的使用者名稱和密碼或本機電腦上的其他認證，以及執行其他惡意活動，以竊取 (或竊取。

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>規則和自訂表單植入攻擊的外觀可能如 Office 365 所示？

您的使用者可能會注意到這些持續性機制，但在某些情況下，您可能會看不到這些功能。 本文將告訴您如何在下面列出的任何 (的威脅) 中尋找7號徵兆。 如果您找到上述任一項，您必須採取補救步驟。

- **規則受損的** 指標：
  - 規則動作是要啟動應用程式。
  - 規則參照 EXE、ZIP 或 URL。
  - 在本機電腦上，尋找來自 Outlook PID 的新進程開始。

- **自訂表單受損的** 指標：
  - 顯示的自訂表單會另存為自己的郵件類別。
  - 郵件類別包含可執行程式碼。
  - 通常，惡意表單會儲存在個人表單文件庫或 [收件匣] 資料夾中。
  - 表單命名為 IPM。注意。[custom name]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>尋找此攻擊之徵兆及確認的步驟

您可以使用下列其中一種方法來確認攻擊：

- 使用 Outlook 用戶端，手動檢查每個信箱的規則和表單。 這個方法是完整的，但是您一次只能檢查一個信箱。 如果您有許多使用者要檢查，而且也可能會感染您所使用的電腦，則此方法可能會非常耗時。

- 使用 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 腳本自動為您租使用者中的所有使用者轉儲所有的郵件轉寄規則和自訂表單。 這是最快且最安全的方法，最少量的開銷。

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>使用 Outlook 用戶端確認規則攻擊

1. 以使用者身分開啟使用者 Outlook 用戶端。 使用者可能需要協助您檢查其信箱上的規則。

2. 如需如何在 Outlook 中開啟規則介面的程式，請參閱[使用規則文章管理電子郵件訊息](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。

3. 尋找使用者未建立的規則，或任何未預期的規則或具有可疑名稱的規則。

4. 請參閱規則描述，以取得啟動和應用程式的規則動作，或參考 .EXE、.ZIP 檔案或啟動 URL。

5. 尋找任何開始使用 Outlook 進程識別碼的新程式。 請參閱 [尋找進程識別碼](/windows-hardware/drivers/debugger/finding-the-process-id)。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>使用 Outlook 用戶端確認表單攻擊的步驟

1. 以使用者身分開啟使用者 Outlook 用戶端。

2. 遵循中的步驟，顯示使用者 Outlook 版本的[[開發人員]](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)索引標籤。

3. 在 Outlook 中開啟 [目前可見的開發人員] 索引標籤，然後按一下 [**設計表單**]

4. 從 [**查找範圍**] 清單中選取 [**收件** 匣]。 尋找任何自訂表單。 自訂表單非常少見，如果您有任何自訂表單，則需要更深入的外觀。

5. 調查任何自訂表單，尤其是標示為隱藏的表單。

6. 開啟任何自訂表單，然後在 **表單** 群組中按一下 [ **View Code** ] （查看表單載入時執行的功能）。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>使用 PowerShell 確認規則和表單攻擊的步驟

驗證規則或自訂表單攻擊的最簡單方法，就是執行 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script。 此腳本會連接至您租使用者中的每個信箱，並將所有規則和表單轉儲成兩個 .csv 檔案。

#### <a name="pre-requisites"></a>先決條件

您必須具有全域系統管理員許可權，才能執行腳本，因為腳本會連接到租用中的每個信箱，以讀取規則和表單。

1. 以本機系統管理員許可權登入您將執行腳本的電腦。

2. 將 Get-AllTenantRulesAndForms.ps1 腳本從 GitHub 下載或複製到要從中執行它的資料夾。 腳本會為此資料夾建立兩個日期戳檔案，MailboxFormsExport-yyyy-mm-dd.csv 和 MailboxRulesExport-yyyy-mm-dd.csv。

3. 以系統管理員身分開啟 PowerShell 實例，然後開啟您用來儲存腳本的資料夾。

4. 依下列方式執行此 PowerShell 命令列 `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>解讀輸出

- **MailboxRulesExport-*年月*.csv**：檢查每個資料列 (一個規則，) 包含應用程式或可執行檔的動作條件：

  - **ActionType (欄位 A)**：如果看到值 "ID_ACTION_CUSTOM"，該規則可能是惡意的。

  - **IsPotentiallyMalicious (欄)**：如果此值為 "TRUE"，則此規則可能是惡意的。

  - **ActionCommand (Column G)**：如果此欄列出的應用程式或任何具有 .exe 或 .zip 副檔名的檔案，或是參照 URL 的未知專案，則該規則可能是惡意的。

- **MailboxFormsExport-*yyyy*.csv**：一般說來，使用自訂表單非常少見。 如果您在此活頁簿中找到任何的，請開啟該使用者的信箱，並檢查該表單本身。 如果您的組織未有意放入該組織，可能是惡意的。

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>如何停止和修正 Outlook 規則和表單攻擊

如果您發現其中任何一種攻擊的證據，修正很簡單，只需要從信箱中刪除規則或表單即可。 您可以使用 Outlook 用戶端或使用遠端 PowerShell 來移除規則。

### <a name="using-outlook"></a>使用 Outlook

1. 識別使用者與 Outlook 搭配使用的所有裝置。 所有的潛在惡意程式碼都必須清除。 不允許使用者登入並使用電子郵件，直到所有裝置都已清除為止。

2. 依照刪除每個裝置的 [規則](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) 中的步驟進行。

3. 如果您不確定是否存在其他惡意程式碼，您可以格式化及重新安裝裝置上的所有軟體。 若為行動裝置，您可以依照製造商的步驟，將裝置重設為出廠影像。

4. 安裝最新版本的 Outlook。 請記住，目前的 Outlook 版本會封鎖這兩種攻擊類型的預設值。

5. 移除信箱的所有離線副本之後，請重設使用者的密碼 (使用高品質的) ，然後在 [未啟用 MFA 的情況下，依照 [設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) ] 中的步驟進行。 這可確保使用者的認證不會透過其他方式公開 (例如網路釣魚或密碼重複使用) 。

### <a name="using-powershell"></a>使用 PowerShell

您可以使用兩個遠端 PowerShell Cmdlet 來移除或停用危險的規則。 只需遵循步驟。

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Exchange server 上之信箱的步驟

1. 使用遠端 PowerShell 連線至 Exchange 伺服器。 遵循[連線 Exchange 使用遠端 PowerShell 來伺服器](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)的步驟。

2. 如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用 [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) Cmdlet。

3. 如果您想要保留規則及其內容以進行進一步調查，請使用 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) Cmdlet。

#### <a name="steps-for-mailboxes-in-exchange-online"></a>信箱在 Exchange Online 中的步驟

1. 遵循[連線 Exchange Online 使用 PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中所述的步驟。

2. 如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用 [ [移除收件匣規則](/powershell/module/exchange/Remove-InboxRule) ] Cmdlet。

3. 如果您想要保留規則及其內容以進行進一步調查，請使用 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) Cmdlet。

## <a name="how-to-minimize-future-attacks"></a>如何最小化未來的攻擊

### <a name="first-protect-your-accounts"></a>第一種：保護您的帳戶

只有在竊取或破壞使用者的帳戶之後，攻擊者才會使用這些規則和表單攻擊。 因此，避免對您的組織使用這些入侵的第一步，是要積極保護您的使用者帳戶。 一些最常見的帳戶破壞方式是透過網路釣魚或 [密碼噴塗攻擊](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)。

保護使用者帳戶的最佳方法（特別是管理員帳戶）是為 [使用者設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。 您也應該：

- 監視如何 [存取及使用](/azure/active-directory/active-directory-view-access-usage-reports)您的使用者帳戶。 您可能不會防止初始遭到破壞，但是您會儘早偵測，以縮短破壞的持續時間和破壞影響。 您可以使用這些[Office 365 雲端 App 安全性原則](/cloud-app-security/what-is-cloud-app-security)，在不尋常的活動上監視帳戶及警示：

  - **多個失敗的登入嘗試**：這個原則設定檔您的環境，當使用者在與所學的基準相關的單一會話中執行多個失敗的登入活動時，便會觸發警示，這可能表示企圖遭到破壞。

  - 不 **可能的旅行**：這項原則會在不同位置的相同使用者中偵測到活動時，在兩個位置之間的時間範圍內，以短于預期的旅行時間。 這可能表示不同的使用者使用相同的認證。 偵測到這種反常行為時，會有七天的初始學習週期，以瞭解新使用者的活動模式。

  - **由使用者) 所 (的特殊模擬活動**：此原則設定檔您的環境，當使用者在與基線獲知相關的單一會話中執行多個類比活動時，便會觸發警示，這可能表示企圖遭到破壞。

- 使用類似[Office 365 安全評分](https://securescore.office.com/)的工具來管理帳戶安全性設定和行為。

### <a name="second-keep-your-outlook-clients-current"></a>第二：讓 Outlook 的用戶端保持在最新

完全更新及修補的 Outlook 2013 版本，2016預設會停用「啟動應用程式」規則/表單動作。 這可確保即使攻擊者破壞帳戶，規則和表單動作也會遭到封鎖。 您可以遵循[安裝 Office 更新](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)中的步驟，安裝最新的更新及安全性修補程式。

以下是 Outlook 2013 和2016用戶端的修補程式版本：

- **Outlook 2016**：16.0.4534.1001 或更新版本。

- **Outlook 2013**：15.0.4937.1000 或更新版本。

如需個別安全性修補程式的詳細資訊，請參閱：

- [Outlook 2016安全性修補程式](https://support.microsoft.com/help/3191883)

- [Outlook 2013 安全性修補程式](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>第三：監視您的 Outlook 用戶端

請注意，即使已安裝修補程式和更新，攻擊者還是可以變更本機電腦設定，以重新啟用「啟動應用程式」行為。 您可以使用 [高級群組原則管理](/microsoft-desktop-optimization-pack/agpm/) ，在用戶端上監視及強制執行本機電腦原則。

您可以使用[64 位版本的 Windows](https://support.microsoft.com/help/305097)，查看是否已透過登錄中的覆寫重新啟用「啟動應用程式」的資訊。 請檢查下列子項：

- **Outlook 2016**：`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**：`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

尋找機碼 EnableUnsafeClientMailRules。 如果已存在，且已設定為1，則 Outlook 的安全性修補程式已被取代，且電腦受到表單/規則攻擊的影響。 如果值為0，就會停用「啟動應用程式」動作。 如果已安裝更新及修補的 Outlook 版本，但此登錄機碼不存在，系統就不會受到這些攻擊。

使用內部部署 Exchange 安裝的客戶應考慮封鎖沒有可用修補程式的舊 Outlook 版本。 有關此程式的詳細資訊，請參閱[設定 Outlook 用戶端封鎖](/exchange/configure-outlook-client-blocking-exchange-2013-help)的文章。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>像網路安全專業人員一般保護 Microsoft 365

您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。 使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。

- 要在前 30 天內完成的工作。 這類功能會立即生效，對您的使用者影響很小。

- 要在 90 天內完成的工作。 這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。

- 90 天之後。 這些增強功能會在您的前 90 天工作內建置。

## <a name="see-also"></a>另請參閱：

- [惡意 Outlook 規則](https://silentbreaksecurity.com/malicious-outlook-rules/)SilentBreak 的安全性公告關於規則向量可提供 Outlook 規則的詳細評論。

- [MAPI over HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog on Mailrule Pwnage 討論稱為尺規的工具，可讓您透過 Outlook 規則來利用信箱。

- Sensepost 博客上有關表單威脅向量的[Outlook 表單和外殼](https://sensepost.com/blog/2017/outlook-forms-and-shells/)。

- [尺規基本代碼](https://github.com/sensepost/ruler)

- [尺規指標洩露](https://github.com/sensepost/notruler/blob/master/iocs.md)