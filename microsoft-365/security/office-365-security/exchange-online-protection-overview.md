---
title: Exchange Online Protection (EOP) 一覽表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Exchange Online Protection (EOP) 可協助保護您的內部部署電子郵件組織，以進行獨立和混合式環境。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a925b251ff79aec5acaa0b2c1da2aee3f5a6d70d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930160"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概觀

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) 是雲端架構篩選服務，可保護您的組織，避免垃圾郵件、惡意程式碼和其他電子郵件威脅。 EOP 包含 Exchange Online 信箱的所有 Microsoft 365 組織。

> [!NOTE]
> 您也可以自行提供 EOP，以保護內部部署信箱和混合式環境，以保護內部部署 Exchange 信箱。 如需詳細資訊，請參閱[獨立 Exchange Online Protection](/exchange/standalone-eop/standalone-eop)。

設定 EOP 安全性功能的步驟，以及與您在 Microsoft Defender Office 365 中所做的新增安全性比較，請參閱[防範威脅](protect-against-threats.md)。 建議的 EOP 功能設定可用於[EOP 和 Microsoft Defender Office 365 security 的建議設定](recommended-settings-for-eop-and-office365.md)。

本文的其餘部分將說明 EOP 的運作方式，以及 EOP 中提供的功能。

## <a name="how-eop-works"></a>EOP 的運作方式

若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="來自網際網路的電子郵件的圖形，或從客戶對 EOP 及透過連線、反惡意程式碼、郵件流程規則---原則篩選和內容篩選的電子郵件，在垃圾郵件或隔離或使用者郵件傳遞的最後一開始之前。":::

1. 當傳入郵件進入 EOP 時，它最初會透過連線篩選來檢查寄件者的信譽。 大部分的垃圾郵件會在此點停止，並由 EOP 拒絕。 如需詳細資訊，請參閱[設定連線篩選](configure-the-connection-filter-policy.md)。

2. 然後檢查郵件是否有惡意程式碼。 如果在郵件中找到惡意程式碼或附件 (s) 郵件會路由傳送至僅限系統管理員的隔離存放區。 若要深入瞭解惡意程式碼保護，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。

3. 郵件會繼續進行原則篩選，它會根據任何郵件流程 (規則（也稱為傳輸規則，也就是您已建立的傳輸規則) ）進行評估。 例如，當郵件到達特定寄件者時，規則可以傳送通知給管理員。

   在內部部署組織中，使用 Exchange Enterprise CAL 與服務授權，[資料遺失防護功能 (DLP) ](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)檢查也會在 EOP。

4. 郵件會透過內容篩選 (反垃圾郵件和反欺騙) ，惡意郵件會被識別為垃圾郵件、高可信度垃圾郵件、網路釣魚、高可信度網路釣魚或大量 (反垃圾郵件原則) 或欺詐 (反網路釣魚原則中的欺騙性原則) 。 您可以根據篩選判定 (隔離、移至 [垃圾郵件] 資料夾等 ) ，設定要對郵件採取的動作。 如需詳細資訊，請參閱 [configure 反垃圾郵件原則](configure-your-spam-filter-policies.md) 及 [設定 EOP 中的反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

成功傳送這些保護層的郵件會傳送給收件者。

如需詳細資訊，請參閱 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

### <a name="eop-datacenters"></a>EOP 資料中心

EOP 會在用於提供最佳可用性的全球資料中心網路上執行。 例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。 每個資料中心的伺服器都會以您的名義接收郵件，提供組織和網際網路之間的分隔區，從而減少伺服器的負載。 透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。

EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：

- 在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。
- 在亞太地區 (APAC)，所有 Exchange Online 信箱都位於 APAC 資料中心，且郵件目前透過 APAC 資料中心傳送供 EOP 篩選。
- 在美洲，服務會發佈于下列位置：
  - 南美洲： Exchange Online 信箱位於巴西和智利的資料中心內。 所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。 隔離的郵件會儲存在租使用者所在的資料中心。
  - 加拿大： Exchange Online 信箱位於加拿大的資料中心內。 所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。 隔離的郵件會儲存在租使用者所在的資料中心。
  - 美國： Exchange Online 信箱位於美國資料中心。 所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。 隔離的郵件會儲存在租使用者所在的資料中心。
- 至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。

### <a name="eop-features"></a>EOP 功能

本節提供 EOP 中可用之主要功能的高層級概述。

如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

**附註**：

- EOP 使用數個幫助偵測郵件中已知惡意連結的 URL 封鎖清單。
- EOP 使用知名的網域清單來傳送垃圾郵件。
- EOP 使用多個反惡意程式碼引擎，可協助隨時自動保護我們的客戶。
- EOP 檢查郵件內文中的有效負載和所有郵件附件中是否有惡意程式碼。
- 如需保護原則的建議值，請參閱[EOP 和 Microsoft Defender for Office 365 security 的建議設定](recommended-settings-for-eop-and-office365.md)。
- 如需設定保護原則的快速指示，請參閱 [防禦威脅](protect-against-threats.md)。

<br>

****
|功能|註解|
|---|---|
|**Protection**||
|反惡意程式碼|[EOP 中的反惡意程式碼保護](anti-malware-protection.md) <p> [反惡意程式碼保護常見問題集](anti-malware-protection-faq-eop.yml) <p> [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)|
|輸入反垃圾郵件|[EOP 中的反垃圾郵件保護](anti-spam-protection.md) <p> [反垃圾郵件保護常見問題集](anti-spam-protection-faq.yml) <p> [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)|
|輸出反垃圾郵件|[EOP 中的外寄垃圾郵件保護](outbound-spam-controls.md) <p> [在 EOP 中設定輸出垃圾郵件篩選](configure-the-outbound-spam-policy.md) <p> [在 Microsoft 365 中控制自動外部電子郵件轉接](external-email-forwarding.md)|
|連線篩選|[設定連線篩選](configure-the-connection-filter-policy.md)|
|反網路釣魚|[Microsoft 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md) <p> [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)|
|反詐騙保護|[EOP 中的欺騙智慧洞察力](learn-about-spoof-intelligence.md) <p> [管理租用戶允許/封鎖清單中](tenant-allow-block-list.md)|
|以零小時為序的自動清除 (用於傳遞惡意程式碼、垃圾郵件和網路釣魚郵件的 ZAP) |[Exchange Online 中的 ZAP](zero-hour-auto-purge.md)|
|預設安全性原則|[EOP 和 Microsoft Defender for Office 365 中的預設安全性原則](preset-security-policies.md) <p> [EOP 和 Microsoft Defender for Office 365 中的保護原則設定分析器](configuration-analyzer-for-security-policies.md)|
|承租人允許/封鎖清單|[管理租用戶允許/封鎖清單中](tenant-allow-block-list.md)|
|郵件寄件者的封鎖清單|[在 EOP 中建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)|
|允許郵件寄件者的清單|[在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)|
|目錄架構邊緣封鎖 (DBEB)|[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**隔離和提交**||
|系統管理員提交|[使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)|
|使用者提交 (自訂信箱) |[使用者提交原則](user-submission.md)|
|隔離-系統管理員|[在 EOP 中管理隔離的郵件與檔案](manage-quarantined-messages-and-files.md) <p> [隔離的郵件常見問題](quarantine-faq.yml) <p> [回報訊息和檔案至 Microsoft。](report-junk-email-messages-to-microsoft.md) <p> [Microsoft 365 的反垃圾郵件標頭](anti-spam-message-headers.md) <p> 您可以使用「 [郵件頭分析器](https://mha.azurewebsites.net/)」來分析隔離郵件的郵件頭。|
|隔離-使用者|[在 EOP 中尋找及釋出隔離的郵件](find-and-release-quarantined-messages-as-a-user.md) <p> [使用使用者垃圾郵件通知來釋放及報告隔離的郵件](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**郵件流程**||
|郵件流程規則|[Exchange Online 中的郵件流程規則 (傳輸規則)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Exchange Online 中的郵件流程規則動作](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [管理 Exchange Online 中的郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [郵件流程規則程序在 Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|公認的網域|[管理 Exchange Online 中公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|連接器|[使用 Exchange Online 中的連接器設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|增強的連接器篩選|[Exchange Online 中連接器的增強篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**監視**||
|郵件追蹤|[郵件追蹤](message-trace-scc.md) <p> [Exchange 系統管理中心的郵件追蹤](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|電子郵件 & 協同報告|[檢視電子郵件安全性報告](view-email-security-reports.md)|
|郵件流程報告|[檢視郵件流程報告](view-mail-flow-reports.md) <p> [Exchange 系統管理中心的郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|郵件流程 insights|[郵件流程 insights](mail-flow-insights-v2.md) <p> [Exchange 系統管理中心的郵件流程洞察力](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|稽核報告|[Exchange 系統管理中心的審計報告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|警示原則|[警示原則](../../compliance/alert-policies.md)|
|**服務等級協定 (SLA) 和支援**||
|垃圾郵件有效性 SLA|\> 99%|
|誤判率 SLA|\< 1:250,000|
|病毒偵測和封鎖 SLA|100% 已知病毒|
|每月執行時間 SLA|99.999%|
|電話和 web 技術支援，每天 24 小時，每週七天|[EOP 的說明和支援](help-and-support-for-eop.md)。|
|**其他功能**||
|異地備援的伺服器全域網路|EOP 執行於資料中心的全球性網路，這些資料中心的設計目的是協助提供最佳的可用性。 如需詳細資訊，請參閱本文前面的 [EOP 資料中心](#eop-datacenters) ] 區段。|
|內部部署伺服器無法接收郵件時，將郵件加入佇列|延期的郵件會在一天內保留在佇列中。 郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。 平均而言，郵件會每隔 5 分鐘重試一次。 如需詳細資訊，請參閱 [EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.yml)。|
|Office 365 郵件加密可做為附加元件|如需詳細資訊，請參閱 [Office 365 中的加密](../../compliance/encryption.md)。|
|||
