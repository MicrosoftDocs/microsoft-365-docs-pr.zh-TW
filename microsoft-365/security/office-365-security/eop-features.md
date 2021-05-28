---
title: EOP 功能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 下表提供可在 Exchange Online Protection (EOP) 託管式電子郵件篩選服務中使用的功能清單。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62530a7c5da7ab0b7fd0e8415c8c366a1caafdda
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696451"
---
# <a name="eop-features"></a>EOP 功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)

下表提供 Exchange Online Protection (EOP) 電子郵件篩選服務中可用的功能清單。

> [!TIP]
> [business 藍圖的 Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是用來找出即將推出之新功能之相關資訊的有用資源。 如需深入了解不同的 EOP 訂閱方案可提供什麼功能，請參閱 [Exchange Online Protection 服務描述](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

<br>

****

|功能|描述|
|---|---|
|**Anti-malware protection**||
|多重引擎反惡意程式碼保護|多重的反惡意程式碼引擎可協助隨時自動保護我們的客戶。|
|永遠開啟惡意程式碼篩選|您無法停用惡意程式碼篩選。 我們相信，所有客戶協助提供一致且嚴密的保護層級，是協助保護您電子郵件環境時所需的深度防禦策略中很重要的一部份。 因此，系統會自動為所有客戶啟用惡意程式碼篩選。|
|郵件內文及附件的惡意程式碼檢查|此服務會檢查郵件本文和所有郵件附件中的使用中裝載是否有惡意程式碼。|
|反間諜軟體保護|反惡意程式碼保護內含防毒保護和反間諜軟體保護。|
|惡意程式碼篩選原則|每個組織都有套用至所有收件者的預設反垃圾郵件原則。 為了獲得更多細微性，您可以建立適用于組織中特定使用者、群組或網域的自訂反惡意程式碼原則。 自訂原則永遠套用於預設原則之前，但您可以變更套用自訂原則的順序。 <p> 您可以在反惡意程式碼原則中設定下列設定： <ul><li>**常見附件篩選**：啟用永遠假定為惡意程式碼的自訂檔案類型清單。</li><li>**惡意程式碼的 ZAP**： Retroactively 隔離已傳遞惡意程式碼郵件。 如需詳細資訊，請參閱[Exchange Online 中的零小時自動清除 (ZAP) ](zero-hour-auto-purge.md)。</li><li>**收件者通知**：以無訊息方式隔離郵件或隔離郵件，並將其傳送到包含標準或自訂文字的單一文字檔所取代的所有附件。</li><li>**寄件者通知**：通知寄件者，其郵件被偵測為惡意程式碼。</li><li>系統 **管理員通知**：偵測到內部或外部寄件者的郵件被偵測為惡意程式碼時，請通知系統管理員。</li></ul> <p> 如需詳細資訊，請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。|
|**防網路釣魚保護**||
|防網路釣魚保護|EOP 使用已知的垃圾郵件者所使用的網域清單。|
|反詐騙保護|EOP 中的反網路釣魚防護包括反欺詐防護。 如需詳細資訊，請參閱 [防盜-欺詐防護](anti-spoofing-protection.md)。 <p> Microsoft Defender for Office 365 中的反網路釣魚防護也包含類比保護。 如需詳細資訊，請參閱[適用於 Office 365 的 Microsoft Defender 中的防網路釣魚原則專屬設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。|
|**反垃圾郵件保護**||
|輸入垃圾郵件偵測|如需詳細資訊，請參閱[Microsoft 365 中的反垃圾郵件保護](anti-spam-protection.md)。 <p> 如需混合式環境中所需的其他步驟，請參閱 [CONFIGURE EOP to 將垃圾郵件傳送至混合式環境中的 [垃圾郵件] 資料夾](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。|
|退信攻擊保護|如需詳細資訊，請參閱 [退信攻擊與 EOP](backscatter-messages-and-eop.md)。|
|大宗郵件篩選|EOP 會使用反垃圾郵件原則中大量的投訴 (BCL) 臨界值，將大量電子郵件標記為垃圾郵件。 如需詳細資訊，請參閱下列主題： <ul><li>[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)</li><li>[EOP 中的大量投訴層級 (BCL) ](bulk-complaint-level-values.md)</li><li>[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)</li></ul>|
|惡意 URL 封鎖清單|EOP 使用數個幫助偵測郵件中已知惡意連結的 URL 封鎖清單。|
|**輸出垃圾郵件保護**||
|輸出垃圾郵件偵測|如果您使用該服務來傳送輸出郵件，則會永遠啟用輸出反垃圾郵件保護。 如需詳細資訊，請參閱 [輸出垃圾郵件保護](outbound-spam-controls.md)。|
|輸出垃圾郵件原則|每個組織都有套用至所有收件者的預設輸出垃圾郵件原則。 為了獲得更多細微性，您可以建立適用于組織中特定使用者、群組或網域的自訂反垃圾郵件原則。 自訂原則永遠套用於預設原則之前，但您可以變更套用自訂原則的順序。 <p> 您可以在反垃圾郵件原則中設定下列設定： <ul><li>郵件 **limts**：您可以設定限制，使其低於 **每小時的外部** 收件者、內部收件者 **每小時** 的 [服務預設值](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)，以及每天的收件者 **人數上限**。</li><li>**要對超過限制的使用者採取的動作**：將使用者限制為24小時內，將使用者限制于發行或僅警示。</li><li>**啟用或停用自動外部電子郵件轉發**： [深入瞭解](external-email-forwarding.md)</li><li>**通知或傳送郵件副本給系統管理員**</li></ul> <p> 如需詳細資訊，請參閱 [在 EOP 中設定輸出垃圾郵件篩選](configure-the-outbound-spam-policy.md)。|
|**連線篩選**||
|連接篩選原則|為組織設定 IP 允許清單和 IP 封鎖清單。 如需詳細資訊，請參閱 [Configure connection 篩選](configure-the-connection-filter-policy.md)|
|**垃圾郵件管理**||
|反垃圾郵件原則|每個組織都有套用至所有收件者的預設反垃圾郵件原則。 為了獲得更多細微性，您可以建立適用于組織中特定使用者、群組或網域的自訂反垃圾郵件原則。 自訂原則永遠套用於預設原則之前，但您可以變更套用自訂原則的順序。 <p> 您可以在反垃圾郵件原則中設定下列設定： <ul><li>**垃圾郵件篩選判定的動作**：偵測到郵件時，您可以設定要使用 (刪除，移至 [垃圾郵件] 資料夾、[隔離] 等 ) 以判定為基礎的動作。</li><li>**(ASF) 設定的高級垃圾郵件篩選器**：這些設定會在 [高級垃圾郵件篩選器中說明 (EOP 中的 asf) 設定](advanced-spam-filtering-asf-options.md)</li><li>**網路釣魚和垃圾郵件的 ZAP**： Retroactively 隔離或將已傳遞的郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[Exchange Online 中的零小時自動清除 (ZAP) ](zero-hour-auto-purge.md)。</li><li>**啟用使用者垃圾郵件通知**： [深入瞭解使用者垃圾郵件通知]。 (use-spam-notifications-to-release-and-report-quarantined-messages.md) </li>**允許和封鎖的寄件者和網域**：如需如何安全使用這些清單的重要資訊，請參閱 [建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md) 及 [建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)</li><li>**國際垃圾郵件設定**：根據語言或來源國家/地區封鎖郵件。</li></ul> <p> 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。|
|透過 Outlook 或 Outlook 網頁版 (先前為 Outlook Web 應用程式) 管理垃圾郵件|使用者和系統管理員可以在 Exchange Online 信箱中建立個人安全寄件者清單和封鎖的寄件者清單。 如需詳細資訊，請參閱[關於 Outlook 中的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)。 <p> 如果您是使用 EOP 來協助保護內部部署 Exchange 信箱，請務必使用目錄同步處理，以協助確保這些設定同步處理至服務。 如需詳細資訊，請參閱[使用目錄同步處理來管理郵件使用者](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)。|
|報告對 Microsoft 的誤報和漏報。|如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。|
|在隔離入口網站中查看、尋找及管理郵件。|如需詳細資訊，請參閱 [在 EOP 中管理被隔離的郵件和](manage-quarantined-messages-and-files.md) 檔案，或 [尋找並釋放被隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。|
|查看垃圾郵件隔離的郵件頭|在您查看隔離區中的郵件頭之後，您也可以將標頭文字複製並貼到 [郵件頭分析](https://mha.azurewebsites.net/) 程式，以找出郵件發生了什麼事。|
|**郵件路由和連接器**||
|
|條件式郵件路由|如需詳細資訊，請參閱[案例：條件式郵件路由](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)。|
|隨機或強制 TLS|<ul><li>隨機 TLS 會嘗試 TLS 連線，但是如果 TLS 連線失敗時會使用 SMTP 連線。</li><li>強制 TLS 會強制執行 TLS 連線，這表示如果 TLS 連線失敗，就會拒絕郵件。</li></ul> <p> 如需 TLS、安全性和連接器的詳細資訊，請參閱[Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。|
|地區路由 (流向特定地區的郵件流程限制)|如需詳細資訊，請參閱 [EOP 資料中心](exchange-online-protection-overview.md#eop-datacenters)。|
|SMTP 連線檢查程式工具|如需使用此工具測試郵件流程的詳細資訊，請參閱透過[驗證 Microsoft 365 連接器來測試郵件流程](/exchange/mail-flow-best-practices/test-mail-flow)。|
|符合子網域|如需關於啟用公認的網域之子網域的雙向郵件流程的詳細資訊，請參閱 [EOP 中的郵件流程](mail-flow-in-eop.md)。|
|**郵件流程規則**||
|EOP 中的郵件流程規則|實際上，郵件流程 (規則中所提供的所有條件、例外狀況和動作（也稱為傳輸規則) 在 Exchange Online 中）也可用於獨立 EOP 組織，而不需 Exchange Online 信箱。 如需郵件流程規則的相關資訊，請參閱下列主題： <ul><li>[郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</li><li>[郵件流程規則條件和例外狀況](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</li><li>[郵件流程規則動作](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</li></ul>|
|郵件流程規則案例|使用傳輸規則可提供許多案例。 例如： <ul><li>以 **原則為基礎的篩選和動作**：您可以依網域、關鍵字、檔案名、檔案類型、主旨行、郵件內文、寄件者、收件者、標頭及 IP 位址進行篩選。</li><li>**依文字模式篩選**：郵件流程規則可以使用陣列或正則運算式來符合文字。 您也可以使用單一字串或字串陣列來比對許多郵件屬性，例如地址、主旨、內文或附件名稱。</li><li>**自訂字典**：郵件流程規則可以包含較長的文字和關鍵字清單，提供與自訂字典相同的功能。</li><li>**每個網域原則規則**：您可以自訂郵件流程規則的範圍，以符合寄件者或收件者功能變數名稱、IP 位址範圍、位址關鍵字或模式、群組成員資格及其他條件。</li><li>**附件掃描**：您可以建立郵件流程規則，以掃描電子郵件附件的檔案名、副檔名和內容。</li><li>**將原則規則通知傳送給寄件者**：您可以拒絕郵件，並傳送未傳遞回報 (也稱為 NDR 或退回郵件) 傳送給寄件者的郵件，並透過 [已 **增強的狀態碼**] 動作來 **說明** 或拒絕郵件。</li><li>重新 **導向或複製郵件**：郵件流程規則可以重新導向、新增收件者的抄送或密件副本，只要新增收件者和其他選項。</li><li>**篩選郵件並變更郵件屬性或路由**：您可以根據各種條件篩選郵件，然後將一系列的動作套用至每封郵件。</li><li>**在傳輸中變更郵件的垃圾郵件信賴等級 (SCL)**</li></ul> <p> 如需特定的郵件流程規則案例文章，請參閱 [郵件流程規則程式](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。|
|**系統管理**||
|Web 式管理|您可以使用下列 admin 中心來管理 EOP： <ul><li>[Microsoft 365 的安全性中心](/microsoft-365/security/defender/overview-security-center)</li><li>[Exchange 系統管理中心](/exchange/exchange-admin-center)</li><li>[Microsoft 365 系統管理中心](/microsoft-365/admin/admin-overview/about-the-admin-center)</li></ul>|
|PowerShell|如果您的組織有 Exchange Online 信箱，您可以在[Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)中管理 EOP 功能。 如果您的組織沒有 Exchange Online 信箱，您可以在[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell)中管理 EOP 功能。|
|**回報和記錄**||
|郵件追蹤|系統管理員可以在電子郵件通過服務時追蹤電子郵件。 您可以判斷服務是否已接收、拒絕、延遲或傳遞目標電子郵件。 此舉可讓您有效回答使用者的問題、疑難排解郵件流程問題、驗證原則變更，並減少連絡技術支援尋求協助的需求。 如需詳細資訊，請參閱[安全性與合規性中心內的郵件追蹤](message-trace-scc.md)。|
|Web 式報告|安全性 & 規範中心內的郵件保護報告可提供郵件資料。 例如，您可以監視偵測到多少垃圾郵件和惡意程式碼，或符合郵件流程規則的程度。 透過這些互動式報告，您可以快速取得摘要資料的視覺報告，並深入查看個別郵件的詳細資料，最多可回溯 90 天。 如需詳細資訊，請參閱 [Use mail protection reports，以查看有關惡意程式碼、垃圾郵件和規則](/exchange/monitoring/use-mail-protection-reports)偵測的資料。|
|稽核記錄|如需詳細資訊，請參閱[Exchange Online 中的審計報告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)。|
|**服務等級協定 (SLA) 和支援**||
|垃圾郵件有效性 SLA|\> 99%|
|誤判率 SLA|\< 1:250,000|
|病毒偵測和封鎖 SLA|100% 已知病毒|
|每月執行時間 SLA|99.999%|
|電話和 web 技術支援，每天 24 小時，每週七天|如需 EOP 協助和支援選項的詳細資訊，請參閱 [EOP 的說明和支援](help-and-support-for-eop.md)。|
|**其他功能**||
|異地備援的伺服器全域網路|EOP 執行於資料中心的全球性網路，這些資料中心的設計目的是協助提供最佳的可用性。如需詳細資訊，請參閱 [Exchange Online Protection 概觀](exchange-online-protection-overview.md) 中的「EOP 資料中心」一節。  |
|內部部署伺服器無法接收郵件時，將郵件加入佇列|延期的郵件會在一天內保留在佇列中。 郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。 平均而言，郵件會每隔 5 分鐘重試一次。 如需詳細資訊，請參閱 [EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.yml)。|
|Office 365 郵件加密可以作為附加元件服務使用|如需詳細資訊，請參閱 [Office 365 中的加密](../../compliance/encryption.md)。|
|
