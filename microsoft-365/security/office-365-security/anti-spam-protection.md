---
title: 反垃圾郵件保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解反垃圾郵件設定和篩選器，協助避免 Exchange Online Protection (EOP) 中的垃圾郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 52e891a86e75309dadd445736738a3f25584823e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624858"
---
# <a name="anti-spam-protection-in-eop"></a>EOP 中的反垃圾郵件保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> 本主題適用于系統管理員。 如需使用者的主題，請參閱 [垃圾郵件篩選程式的 [概述](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) ]，並 [瞭解垃圾郵件和網路釣魚](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)。

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，電子郵件會自動抵禦垃圾郵件 (垃圾郵件) 的 EOP。

Microsoft 的電子郵件安全藍圖包含一種無與倫比的跨產品方式。 EOP 反垃圾郵件和反網路釣魚技術是透過電子郵件平臺進行套用，以在整個網路中為使用者提供最新的反垃圾郵件和反網路釣魚工具和革新功能。 EOP 的目標是提供綜合且可用的電子郵件服務，以協助偵測和保護使用者免受垃圾郵件、欺詐電子郵件威脅 (網路釣魚) 和惡意程式碼。

隨著電子郵件使用方式成長，電子郵件濫用。 未受監控的垃圾郵件可能會堵塞收件匣和網路、影響使用者滿意度，並影響合法電子郵件通訊的效能。 這就是 Microsoft 繼續投資反垃圾郵件技術的原因。 簡而言之，它會以包含並篩選垃圾郵件的方式開始。

> [!TIP]
> 當您想要根據郵件信封 (（例如，寄件者的網域或) 郵件的來源 IP 位址）來允許或封鎖郵件時，下列反垃圾郵件技術很有用。 若要根據負載允許或封鎖郵件 (例如，在郵件中 URLs 或附加的檔) 中，您應該使用 [承租人允許/封鎖清單入口網站](tenant-allow-block-list.md)。

## <a name="anti-spam-technologies-in-eop"></a>EOP 中的反垃圾郵件技術

為了協助減少垃圾郵件，EOP 包含垃圾郵件保護，使用專有的垃圾郵件篩選技術來識別和分隔垃圾郵件與合法的電子郵件。 EOP 垃圾郵件篩選從我們的消費者平臺（Outlook .com）獲知已知垃圾郵件和網路釣魚威脅和使用者意見反應。 來自垃圾郵件分類計畫中 EOP 使用者的持續反應，可協助確保 EOP 技術不斷訓練有素並改進。

EOP 中的反垃圾郵件設定是由下列技術所組成：

- 連線 **篩選**：透過 Ip 允許清單、Ip 封鎖清單和 *安全清單*，在輸入電子郵件連線中及早識別好和不良的電子郵件來源伺服器， (由 Microsoft) 所維護的受信任寄件者的動態但不可編輯清單。 您可以在連線篩選原則中設定這些設定。 若要深入瞭解，請參閱 [Configure connection 篩選](configure-the-connection-filter-policy.md)。

- **垃圾郵件篩選 (內容篩選)**： EOP 使用垃圾郵件篩選 verdicts **垃圾** 郵件、 **高可信度垃圾郵件**、 **大量電子郵件**、 **網路釣魚電子** 郵件和 **高可信度網路釣魚電子** 郵件來分類郵件。 您可以根據這些 verdicts 設定要採取的動作，而且可以針對隔離而非傳遞的郵件，設定使用者通知選項。 如需詳細資訊，請參閱[設定 Microsoft 365 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。

  > [!NOTE]
  > 根據預設，垃圾郵件篩選會設定為將標記為垃圾郵件的郵件傳送至收件者的 [垃圾郵件] 資料夾。 不過，在 EOP 保護內部部署 Exchange 信箱的混合式環境中，您必須設定兩個郵件流程規則 (也稱為「內部部署 Exchange 組織中的傳輸規則) ，以辨識新增至郵件的 EOP 垃圾郵件頭。 如需詳細資訊，請參閱[設定 EOP 以將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。

- **輸出垃圾郵件篩選**： EOP 也會檢查，確定您的使用者不會在輸出郵件內容中或超過輸出郵件限制傳送垃圾郵件。 如需詳細資訊，請參閱[設定 Microsoft 365 中的外寄垃圾郵件篩選](configure-the-outbound-spam-policy.md)。

- **哄騙情報**：如需詳細資訊，請參閱 [EOP 中的反欺詐防護](anti-spoofing-protection.md)。

## <a name="manage-errors-in-spam-filtering"></a>在垃圾郵件篩選中管理錯誤

良好的郵件可能會辨識為垃圾郵件 (也稱為誤報) ，也就是可將垃圾郵件傳遞至收件匣。 您可以使用下列各節中的建議來找出發生的狀況，並協助避免未來發生。

以下是適用于任一案例的一些最佳作法：

- 永遠將 misclassified 郵件提交給 Microsoft。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

- **檢查反垃圾郵件訊息標頭**：這些值會告訴您郵件為何被標示為垃圾郵件，或為何略過垃圾郵件篩選。 如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。

- 將 **您的 MX 記錄指向 Microsoft 365**：為了讓 EOP 能夠提供最佳保護，我們一定會建議您先將電子郵件傳遞至 Microsoft 365。 如需相關指示，請參閱[在任何 dns 主機服務提供者處建立 dns 記錄以進行 Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。

  如果 MX 記錄指向其他位置 (例如，協力廠商的反垃圾郵件解決方案或裝置) ，EOP 可提供準確的垃圾郵件篩選功能是很困難的。 在此案例中，您必須設定連接器的增強篩選 (也稱為 _略過清單_) 。 如需相關指示，請參閱[強化篩選的 Exchange Online 中的連接器](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- **使用電子郵件驗證**：如果您擁有電子郵件網域，您可以使用 DNS 來協助確保來自該網域中寄件者的郵件合法。 若要協助防止垃圾郵件和 EOP 中有害的欺騙性，請使用下列所有電子郵件驗證方法：

  - **SPF**：寄件者原則框架會驗證郵件的來源 IP 位址是否與傳送網域的擁有者相對應。 若要快速瞭解 SPF，並快速設定它，請參閱 [設定 spf 以協助防止欺詐](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如需更深入了解 Microsoft 365 如何使用 SPF 或是進行疑難排解或非標準的部署 (例如混合式部署)，請先參閱 [ 365 如何使用寄件者原則架構 (SPF) 防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

  - **DKIM**： DomainKeys 已識別的郵件會將數位簽章新增至您的網域所傳送之郵件的郵件頭。 如需詳細資訊，請參閱[使用 DKIM 驗證在 Microsoft 365 中從您的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。

  - **DMARC**：以網域為基礎的郵件驗證、報告及符合性，可協助目的地電子郵件系統判斷如何處理因 SPF 或 DKIM 檢查失敗的郵件，並為您的電子郵件合作夥伴提供另一個信任層級。 如需詳細資訊，請參閱[USE DMARC validate email in Microsoft 365](use-dmarc-to-validate-email.md)。

- **請確認您的大量電子郵件設定**：您在反垃圾郵件原則中設定的大量投訴層級 (BCL) 閾值，會決定大量電子郵件 (也稱為 _灰色郵件_) 標示為垃圾郵件。 預設的 PowerShell 設定 _MarkAsSpamBulkMail_ 也會對結果產生貢獻。 如需詳細資訊，請參閱[設定 Microsoft 365 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>避免將垃圾郵件傳遞至收件匣

- **驗證您的組織設定**：留意允許郵件略過垃圾郵件篩選的設定 (例如，如果您將自己的網域新增至反垃圾郵件原則) 中的允許網域清單。 如需建議的設定，請參閱[EOP 和 Microsoft Defender for Office 365 security 的建議設定](recommended-settings-for-eop-and-office365.md)，並[建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。

- **確認使用者信箱中已啟用垃圾郵件規則**：此規則預設為啟用，但如果停用，則標記為垃圾郵件的郵件就無法移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱在[Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

- **使用可用的封鎖寄件者清單**：如需詳細資訊，請參閱 [建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。

- **從大量電子郵件取消訂閱** 如果郵件是使用者為 (電子報、產品 ) 宣告等所註冊的專案，且包含知名來源的取消訂閱連結，請考慮要求他們只是取消訂閱。

- **獨立 EOP：在內部部署 Exchange 中建立郵件流程規則，以進行 EOP 垃圾郵件篩選 verdicts**：在 EOP 保護內部部署 Exchange 信箱的 EOP 環境中，您必須設定郵件流程規則， (也稱為 Exchange 內部部署中) 的傳輸規則。若要轉譯 EOP 垃圾郵件篩選判定專案，垃圾郵件規則可以將郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[設定 EOP 以將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。

### <a name="prevent-good-email-from-being-identified-as-spam"></a>防止令人滿意的電子郵件被識別為垃圾郵件

以下是您可以採取以協助避免誤報的一些步驟：

- **確認使用者 Outlook 的垃圾郵件篩選設定**：

  - **確認已停用 Outlook 垃圾郵件篩選器**：當 Outlook 垃圾郵件篩選器設定為預設值 **無自動篩選** 時，Outlook 不會嘗試將 massages 分類為垃圾郵件。  當其設為 [**低**] 或 [**高**] 時，Outlook 垃圾郵件篩選程式會使用自己的 SmartScreen 篩選技術來識別及移動垃圾郵件至 [垃圾郵件] 資料夾，這樣您就可以取得誤報。 請注意，Microsoft 已停止針對 Exchange 和 Outlook 在2016年11月的 SmartScreen 篩選器產生垃圾郵件定義更新。 現有的 SmartScreen 垃圾郵件定義會保留，但其效果可能會隨著時間降低。

  - **確認已停用 Outlook 的 [僅限安全清單] 設定**：啟用此設定時，只會將來自使用者安全寄件者清單或安全收件者清單中寄件者的郵件傳遞至收件匣;來自其他人的電子郵件會自動移至 [垃圾郵件] 資料夾。

  如需這些設定的詳細資訊，請參閱在[Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

- **使用可用的安全寄件者清單**：如需詳細資訊，請參閱 [建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。

- **驗證使用者在傳送和接收限制內**，如 Exchange Online 服務描述中的 [接收及傳送限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)所述。

- **獨立 EOP：使用目錄同步** 處理：如果您使用獨立 EOP 來協助保護內部部署 Exchange 組織，您應該使用目錄同步處理，將使用者設定與服務同步。 這樣做可確保 EOP 信任您使用者的 [安全寄件者] 清單。 如需詳細資訊，請參閱[使用目錄同步處理來管理郵件使用者](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)。

## <a name="anti-spam-legislation"></a>反垃圾郵件法律

在 Microsoft，我們相信新技術和自我規章的開發必須支援有效的政府原則和法律架構。 全球的垃圾郵件劇增已 spurred 眾多的法律團體，以控制商業電子郵件。 許多國家/地區現在有適當的垃圾郵件法。 美國雙方都有規定垃圾郵件的聯邦和州法律，此互補的方法是協助 curtail 垃圾郵件，同時啟用合法電子商務以 prosper。 「CAN-垃圾郵件」法案會展開可用來 curbing 欺詐電子郵件和欺騙性電子郵件的工具。