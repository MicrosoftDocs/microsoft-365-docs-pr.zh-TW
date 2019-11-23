---
title: 設定 EOP 的最佳作法
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 遵循下列 Exchange Online Protection (EOP) 最佳作法建議，以成功完成設定並避免發生常見組態錯誤。
ms.openlocfilehash: 95b415038fdddd1548b23edb89921084d70850c6
ms.sourcegitcommit: 2de2faea7da80712f448e35c2d6c425944013b7e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2019
ms.locfileid: "39204242"
---
# <a name="best-practices-for-configuring-eop"></a>設定 EOP 的最佳作法

遵循下列 Exchange Online Protection (EOP) 最佳作法建議，以成功完成設定並避免發生常見組態錯誤。建議您使用預設組態設定作為一般規則。本主題假設您已完成安裝程序。若您尚未完成 EOP 安裝，請參閱 [設定 EOP 服務](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用測試網域

建議您使用測試網域、子網域或低容量網域試用服務功能，然後才在較高容量的實際執行網域上進行實作。

## <a name="synchronize-recipients"></a>同步處理收件者

若您的組織在內部部署的 Active Directory 環境中已有使用者帳戶，則可將這些帳戶同步處理至雲端的 Azure Active Directory。建議使用目錄同步作業。若要深入了解使用目錄同步作業的好處及其設定步驟，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)。

## <a name="spf-record-customization-to-help-prevent-spoofing"></a>協助防止詐騙的 SPF 記錄自訂

當您設定好 EOP 時，您新增的寄件者原則架構 (SPF) 記錄 EOP 至您的 DNS 記錄。 SPF 記錄有助於抵禦詐騙行為。 如需有關如何 SPF 記錄可防止詐騙及如何將您的內部 IP 位址新增至 SPF 記錄的詳細資訊，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。

## <a name="set-anti-spam-options"></a>設定反垃圾郵件選項

管理您的連線篩選器設定來新增 IP 位址至 IP 允許和 IP 封鎖清單，並藉由選取 [**啟用安全清單**] 選項，其中應該減少誤判 （良好郵件被誤判為垃圾郵件） 的數目會收到。 深入瞭解[Configure the connection filter policy ](configure-the-connection-filter-policy.md)。 對於適用於整個組織的多個垃圾郵件設定]，看看[如何防止實際電子郵件被標示為在 Office 365 中的垃圾郵件](../../compliance/prevent-email-from-being-marked-as-spam.md)或[如何減少 Office 365 中的垃圾郵件](reduce-spam-email.md)）。 如果您有系統管理員層級的控制權，且您想要避免誤判或漏報，這些主題將有所幫助。

檢閱並選擇性地變更預設的設定來管理內容篩選器。 例如，您可以變更偵測到垃圾郵件的郵件會發生什麼情況的動作。 如果您想要追求積極的垃圾郵件篩選方法，您可以設定進階垃圾郵件篩選選項。 我們建議您測試這些選項，第一次之前實作它們在實際執行環境中 （藉由開啟它們）。 我們建議您組織網路釣魚有疑慮開啟**SPF 記錄： 完全未通過**選項。 瞭解更多[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)和[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)。

> [!IMPORTANT]
> 如果您使用預設的內容篩選動作，**移至垃圾郵件] 資料夾的郵件**，以確保巨集指令將搭配內部部署信箱，會需要來設定郵件流程規則 （也稱為傳輸規則），在內部部署 Exchange 組織，以偵測 EOP 所新增的垃圾郵件標頭。 如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

我們建議您檢閱[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)，包括的輸出郵寄最佳作法章節內容，以協助確保您的輸出郵件會傳遞。

您可以將誤判正常 (垃圾郵件) 和誤判 (非垃圾郵件) 提交至 Microsoft，以數種方式進行分析。 如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。

## <a name="set-anti-malware-options"></a>設定反惡意程式碼選項

檢閱並微調您的惡意程式碼篩選設定。 深入瞭解[設定反惡意程式碼原則](configure-anti-malware-policies.md)。 也建議您在我們的 [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md) 閱讀其他有關反惡意程式碼保護的常見問題及解答。

如果您擔心包含惡意程式碼的可執行檔，您可以建立郵件流程規則會封鎖任何具有可執行內容的電子郵件附件。 若要封鎖[使用郵件流程規則檢查郵件附件中 Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)中所列的檔案類型，請遵循[如何減少惡意程式碼威脅透過檔案附件封鎖在 Exchange Online Protection](https://support.microsoft.com/kb/2959596)中的步驟。

您可以使用[常見的附件類型篩選器](protect-against-threats.md#part-1---anti-malware-protection)的反惡意程式碼原則。

為了增加防護，建議使用郵件流程規則封鎖下列部分或所有副檔名：ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh。 您可以使用**任何附件副檔名包括這些字詞**條件來執行這項操作。

系統管理員和使用者可以提交惡意程式碼，使其通過篩選器，或送出您認為檔案被誤判為惡意程式碼，藉由將它傳送給 Microsoft 進行分析。 如需詳細資訊，請參閱[Submitting malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)。

## <a name="create-mail-flow-rules"></a>建立郵件流程規則

建立郵件流程規則或自訂篩選，以符合您的業務需求。

在實際執行環境中部署新規則時，請先選取其中一個測試模式，以查看規則的效果。 一旦您滿意，規則的運作情況符合預期，將規則模式變更為 [**強制**。

當您部署新規則時，請考慮新增額外的**產生附隨報告**來監視巨集指令中的規則動作。

這兩個內部部署 Exchange 混合式環境，包含組織中和 Office 365，請考慮您用於郵件流程規則的條件。 如果您想要套用至整個組織的規則，請務必使用可用的兩個內部部署 Exchange 和 Office 365 中的條件。 雖然大部分的條件會提供兩個環境中，有一些，才會提供一個環境或其他。 了解請參閱[郵件流程規則 （傳輸規則） 在 [Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。

您可以使用郵件流程規則檢查郵件附件的郵件傳輸中組織內。 設定規則條件，以尋找附件，並在偵測到的附件採取動作。 深入瞭解如何[使用郵件流程規則檢查郵件附件中 Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。

### <a name="phishing-and-spoofing-prevention"></a>預防網路釣魚和詐騙

您可以藉由偵測個人資訊是在何時以電子郵件離開組織，以改善防網路釣魚保護。例如，您可以在郵件流程規則中使用下列規則運算式，以偵測可能危害隱私的個人財務資料或資訊傳輸。

- `\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d`（MasterCard 或 Visa）

- `\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d`(American Express)

- `\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d`（任何 16 位數的數字）

- `\d\d\d\-\d\d\-\d\d\d\d`（社會安全編號）

封鎖似乎是從自己網域所傳送的內送惡意電子郵件，也可以減少成功的垃圾郵件和網路釣魚活動。例如，您可以建立郵件流程規則，拒絕郵件由貴公司網域傳送到相同的公司網域，以封鎖這種類型的寄件者偽造。

> [!CAUTION]
> 我們建議只有在您確定您網域中的合法電子郵件不是從網際網路傳送至您的郵件伺服器時，才建立此拒絕規則。當郵件從貴組織中的使用者傳送給外部收件者，隨後又轉寄給貴組織中的其他收件者時，可能會發生這種情形。

## <a name="reporting-and-troubleshooting"></a>報告和疑難排解

在系統管理中心使用報告來疑難排解一般問題和趨勢。 使用訊息追蹤工具，尋找關於訊息的單點特定資料。 請參閱[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)，以深入了解報告功能。 請參閱[Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)，以深入了解郵件追蹤工具。

## <a name="for-more-information"></a>相關資訊

[EOP 一般常見問題集](eop-general-faq.md)

[EOP 的說明和支援](help-and-support-for-eop.md)

[如何在 Office 365 中防止實際電子郵件被標示為垃圾郵件](../../compliance/prevent-email-from-being-marked-as-spam.md)

[如何減少 Office 365 中的垃圾郵件](reduce-spam-email.md)
