---
title: EOP 功能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 下表提供可在 Exchange Online Protection (EOP) 託管式電子郵件篩選服務中使用的功能清單。
ms.openlocfilehash: f69b1772a6eddb6cb85441e52c470cf0bb506a3a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638425"
---
# <a name="eop-features"></a>EOP 功能

下表提供可在 Exchange Online Protection (EOP) 託管式電子郵件篩選服務中使用的功能清單。

> [!TIP]
> [Microsoft 365 for business 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是找出即將推出之新功能之相關資訊的有用資源。如需更多有關不同 EOP 訂閱計畫可用之功能的詳細資訊，請參閱[Exchange Online Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

|||
|---|---|
|**功能**|**描述**|
|**反垃圾郵件保護**||
|輸入垃圾郵件偵測|輸入反垃圾郵件保護永遠啟用，而且無法停用。您可以透過連線篩選和內容篩選原則來進行自訂設定。  <br/><br/> 若為 EOP 獨立版客戶：EOP 內容篩選預設會將偵測到的垃圾郵件傳送至每位收件者的 [垃圾郵件] 資料夾。 不過，為了協助確保 **[將郵件移至垃圾郵件資料夾]** 動作能夠在內部部署信箱中運作，您必須在內部部署伺服器上設定兩項 Exchange 流程規則 (也稱為傳輸規則)，以偵測由 EOP 新增的垃圾郵件標頭。 如需詳細資訊，請參閱[設定獨立版 EOP 將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。|
|輸出垃圾郵件偵測|如果您使用服務傳送輸出電子郵件，藉此幫助保護使用服務的組織和其預期的收件者，一定會啟用輸出反垃圾郵件保護。 和輸入篩選相似，輸出垃圾郵件篩選由連線篩選和內容篩選組成。 輸出垃圾郵件篩選設定無法進行設定，但是有輸出垃圾郵件原則，可讓您用來設定可疑和已封鎖輸出郵件的系統管理員通知。 如需詳細資訊，請參閱[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)。|
|NDR 退信攻擊保護|如需 NDR 退信攻擊的詳細資訊，請參閱[Office 365 中的高級垃圾郵件篩選（ASF）設定](advanced-spam-filtering-asf-options.md)中的 [NDR 退信攻擊] 設定，以及[退信攻擊郵件和 EOP](backscatter-messages-and-eop.md)。|
|大宗郵件篩選|EOP 已經增強偵測方法來識別大宗的電子郵件。 您可以透過使用者介面將服務設定為標記大宗電子郵件。 您也可以建立郵件流程規則，以更積極地藉由搜尋大量郵件標頭戳記來篩選大量郵件。 如需有關大宗電子郵件的詳細資訊，請參閱[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md) 和相關聯的副主題。|
|惡意 URL 封鎖清單|EOP 使用數個幫助偵測郵件中已知惡意連結的 URL 封鎖清單。|
|反網路釣魚保護|EOP 包括 750000 個已知濫發垃圾郵件者的網域。|
|**垃圾郵件管理**||
|設定連線篩選 IP 允許清單與 IP 封鎖清單的功能|在連線篩選中指定的 IP 位址會遵守單一 IP 位址及 CIDR IP 位址範圍。 服務也支援 IPv6 位址。 如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。|
|自訂每個使用者、群組或網域之內容篩選原則的功能|如需進行更為精細的篩選，您可以建立自訂內容篩選原則，並將它們套用至組織中的指定使用者、群組或網域。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。|
|設定要對經過內容篩選的郵件所採取的動作之功能|有多個可設定的動作。 例如，您可以刪除經過內容篩選的郵件，或將它們傳送到垃圾電子郵件資料夾或隔離。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。|
|設定進行嚴苛垃圾郵件篩選之進階選項的功能|如需詳細資訊，請參閱在 office [365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)（您可以在這裡設定）和[高級垃圾郵件篩選（ASF）365設定](advanced-spam-filtering-asf-options.md)（提供每個選項的特定詳細資料）。|
|國際垃圾郵件篩選|您可以將 EOP 設定為篩選以特定語言撰寫的郵件，或是從特定國家或地區傳送的電子郵件。 您可以設定高達 86 種不同語言和 250 個不同地區。 此服務會對高信賴度垃圾郵件套用設定的動作。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。|
|透過 Outlook 或 Outlook 網頁版 (先前為 Outlook Web 應用程式) 管理垃圾郵件|系統管理員和使用者可以建立安全的寄件者清單以及封鎖的寄件者清單。 如需詳細資訊: <br/>* **網頁上的 Outlook**：請參閱[封鎖或允許（垃圾郵件設定）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)。  <br/>* **Outlook**：查看[垃圾郵件篩選器的概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。 <br/><br/> 如果您正在使用 EOP 來協助保護內部部署信箱，請務必使用目錄同步作業協助確保這些設定會同步到服務。 若需設定目錄同步作業的詳細資訊，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md) 中的「使用目錄同步作業來管理郵件使用者」。|
|將誤報（良好的電子郵件標示為壞）和 false 負片（允許的電子郵件不正確）報告給 Microsoft。|如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。|
|使用者垃圾郵件隔離通知|如需詳細資訊，請參閱[Office 365 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)和[設定使用者垃圾郵件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。|
|透過網頁查看、尋找及管理隔離中的郵件|此功能適用於使用者及系統管理員。 如需詳細資訊，請參閱[在 Office 365 中管理被隔離的郵件和檔案為系統管理員](manage-quarantined-messages-and-files.md)，或[尋找並釋放被隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。|
|查看垃圾郵件隔離的郵件頭|在您查看隔離區中的郵件頭之後，您也可以將標頭文字複製並 pate 到[郵件頭分析器](https://mha.azurewebsites.net/)，以查看郵件發生問題的相關資訊。|
|**Anti-malware protection**||
|多重引擎反惡意程式碼保護|多重的反惡意程式碼引擎可協助隨時自動保護我們的客戶。|
|停用惡意程式碼篩選的選項|您無法停用惡意程式碼篩選，因為我們會對透過服務來路由傳送的所有電子郵件強制進行反惡意程式碼掃描。我們相信，所有客戶協助提供一致且嚴密的保護層級，是協助保護您電子郵件環境時所需的深度防禦策略中很重要的一部份。因此，系統會自動為所有客戶啟用惡意程式碼篩選。|
|郵件內文及附件的惡意程式碼檢查|此服務會檢查郵件本文和所有郵件附件中的使用中裝載是否有惡意程式碼。|
|預設或自訂惡意程式碼警示通知|您可以選擇在偵測到郵件有惡意程式碼而未傳遞時，將通知電子郵件傳送給寄件者或系統管理員。 刪除整封郵件時，只會發送這些通知。 如需詳細資訊，請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。|
|偵測到惡意程式碼時移除附件的選項|系統管理員可以選擇是否要刪除整個郵件或要移除附件，並將自訂的郵件傳送給收件者。 如需詳細資訊，請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。|
|反間諜軟體保護|反惡意程式碼保護內含防毒保護和反間諜軟體保護。|
|自訂每個使用者、群組或網域之惡意程式碼篩選原則的功能|如需進行更為精細的篩選，您可以建立自訂惡意程式碼篩選原則，並將它們套用至組織中的指定使用者、群組或網域。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。 如需詳細資訊，請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。|
|**郵件路由和連接器**||
|條件式郵件路由|如需詳細資訊，請參閱[案例：條件式郵件路由](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)。|
|隨機或強制 TLS|隨機或強制 TLS 可供連接器使用。 隨機 TLS 會嘗試 TLS 連線，但是如果 TLS 連線失敗時會使用 SMTP 連線。 強制 TLS 會強制使用 TLS 連線，這表示如果 TLS 連線失敗，就會拒絕郵件。 如需 TLS、安全性和連接器的詳細資訊，請參閱[Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。|
|地區路由 (流向特定地區的郵件流程限制)|如需詳細資訊，請參閱 [Exchange Online Protection 概觀](exchange-online-protection-overview.md) 中的「EOP 資料中心」一節。|
|SMTP 連線檢查程式工具|如需使用此工具測試郵件流程的詳細資訊，請參閱[test mail flow，方法是驗證您的 Microsoft 365 連接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。|
|符合子網域|如需關於啟用公認的網域之子網域的雙向郵件流程的詳細資訊，請參閱 [EOP 中的郵件流程](mail-flow-in-eop.md)。|
|**郵件流程規則**||
|原則式篩選和動作|自訂原則乃是根據 Exchange 郵件流程規則。 您可以透過網域、關鍵字、檔案名稱、檔案類型、主旨列、郵件內文、寄件者、收件者、標頭和 IP 位址進行篩選。 如需詳細資訊，請參閱 [Exchange Online Protection 中的郵件流程規則 (傳輸規則)](mail-flow-rules-transport-rules-0.md)。|
|依據文字模式篩選|郵件流程規則可以使用陣列或規則運算式來比對文字。 您也可以使用單一字串或字串陣列來比對許多郵件屬性，例如地址、主旨、內文或附件名稱。 如需詳細資訊，請參閱 [Exchange Online Protection 中的郵件流程規則 (傳輸規則)](mail-flow-rules-transport-rules-0.md)|
|自訂字典|郵件流程可以包含較長的文字和關鍵字清單，提供和自訂字典相同的功能。|
|以網域為基礎的原則規則|郵件流程規則的範圍可自訂以比對寄件者或收件者網域名稱、IP 位址範圍、地址關鍵字或模式、群組成員資格和其他條件。|
|掃描附件|您可以建立規則來掃描檔案名稱、副檔名以及附件的內容。|
|將原則規則通知傳送給寄件者|您可以透過「**拒絕此郵件並包含說明**」或「**拒絕其增強型狀態碼為此的郵件**」動作，來拒絕郵件並將未傳遞回報 (NDR) 傳送給寄件者。 如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|將郵件傳送至固定位址 (例如將郵件重新導向或複製到特定的位址)|郵件流程規則可以重新導向、新增副本或密件副本收件者、僅新增收件者，以及其他選項。 如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|輕易跨多個規則調整規則優先順序的功能|使用 Exchange 系統管理員中心來變更規則的處理順序。|
|篩選郵件然後變更郵件之路由或屬性的功能|您可以根據各種條件來篩選郵件，然後將一連串的動作套用至每封郵件。 如需詳細資訊，請參閱 [Exchange Online Protection 中的郵件流程規則 (傳輸規則)](mail-flow-rules-transport-rules-0.md)。|
|根據規則變更郵件的垃圾郵件信賴等級。|您可以檢查傳輸中的郵件，並根據您選擇的準則，將垃圾郵件信賴等級指派給它。 如需詳細資訊，請參閱[使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。|
|檢查郵件附件|您可以檢查附件的內容或附加檔案的特性，並定義根據檢查結果所要採取的動作。 如需詳細資訊，請參閱[使用郵件流程規則來檢查 Exchange Online 中的郵件附件](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。|
|**系統管理**||
|Web 式管理|EOP 系統管理員可以透過 Exchange 管理中心 (EAC) 介面 (支援 60 種語言) 來管理服務。 如需詳細資訊，請參閱 [Exchange Online Protection 中的 Exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。|
|目錄同步處理|目錄同步作業可透過 Azure Active Directory 同步處理工具 使用。如需詳細資訊，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md) 中的「使用目錄同步作業管理郵件使用者」一節。  |
|目錄架構邊緣封鎖 (DBEB)|DBEB 功能可讓您在服務網路的周邊處拒絕無效收件者的郵件。 DBEB 可讓系統管理員將擁有郵件功能的收件者新增至 Microsoft 365，並封鎖所有傳送至不存在於 Microsoft 365 的電子郵件地址的郵件。 如需設定 DBEB 的詳細資訊，請參閱 [使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。|
|遠端 Windows PowerShell 存取|透過遠端 Windows PowerShell 可使用完整的 EOP 功能。 如需詳細資訊，請參閱 [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)。|
|**回報和記錄**||
|郵件追蹤|郵件追蹤功能在電子郵件通過服務時，讓您以系統管理員的身分追蹤電子郵件。 它可以協助您判斷服務是否已接收、拒絕、延遲或傳遞目標電子郵件訊息。 此舉可讓您有效回答使用者的問題、疑難排解郵件流程問題、驗證原則變更，並減少連絡技術支援尋求協助的需求。 如需詳細資訊，請參閱[追蹤電子郵件](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)。|
|Web 式報告|Microsoft 365 系統管理中心裡的郵件保護報告會提供郵件資料。 例如，您可以監視偵測到多少垃圾郵件和惡意程式碼，或符合郵件流程規則的程度。 透過這些互動式報告，您可以快速取得摘要資料的視覺報告，並深入查看個別郵件的詳細資料，最多可回溯 90 天。 如需詳細資訊，請參閱[Use mail protection reports，以查看有關惡意程式碼、垃圾郵件和規則](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)偵測的資料。|
|稽核記錄|系統管理員角色群組報告和系統管理員稽核記錄可供 EOP 系統管理員使用。如需詳細資訊，請參閱 [EOP 中的稽核報告](auditing-reports-in-eop.md)。  |
|**服務等級協定 (SLA) 和支援**||
|垃圾郵件有效性 SLA|\> 99%|
|誤判率 SLA|\< 1:250,000|
|病毒偵測和封鎖 SLA|100% 已知病毒|
|每月執行時間 SLA|99.999%|
|電話和 web 技術支援，每天 24 小時，每週七天|如需 EOP 協助和支援選項的詳細資訊，請參閱 [EOP 的說明和支援](help-and-support-for-eop.md)。|
|**其他功能**||
|異地備援的伺服器全域網路|EOP 執行於資料中心的全球性網路，這些資料中心的設計目的是協助提供最佳的可用性。如需詳細資訊，請參閱 [Exchange Online Protection 概觀](exchange-online-protection-overview.md) 中的「EOP 資料中心」一節。  |
|內部部署伺服器無法接收郵件時，將郵件加入佇列|延期的郵件會在一天內保留在佇列中。 郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。 平均而言，郵件會每隔 5 分鐘重試一次。 如需詳細資訊，請參閱 [EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)。|
|Office 365 郵件加密可以作為附加元件服務使用|如需詳細資訊，請參閱 [Office 365 中的加密](../../compliance/encryption.md)。|
