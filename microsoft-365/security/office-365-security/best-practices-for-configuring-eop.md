---
title: 設定 EOP 的最佳作法
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 請遵循下列針對獨立 Exchange Online Protection (EOP) 的最佳作法建議，以便自行設定以取得成功，並避免常見的設定錯誤。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfd0b7290bdcded887ef6b81d5b0d4acbdd6cddb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203446"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>設定獨立 EOP 的最佳作法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
-  [Exchange Online Protection 獨立](exchange-online-protection-overview.md)

請遵循下列針對獨立 Exchange Online Protection (EOP) 的最佳作法建議，以便自行設定以取得成功，並避免常見的設定錯誤。 本主題假設您已完成安裝程序。 若您尚未完成 EOP 安裝，請參閱 [設定 EOP 服務](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用測試網域

建議您使用測試網域、子網域或低容量網域試用服務功能，然後才在較高容量的實際執行網域上進行實作。

## <a name="synchronize-recipients"></a>同步處理收件者

如果您的組織在內部部署 Active Directory 環境中有現有的使用者帳戶，您可以將這些帳戶同步處理至雲端中的 Azure Active Directory。 建議使用目錄同步作業。 若要深入了解使用目錄同步作業的好處及其設定步驟，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)。

## <a name="recommended-settings"></a>建議的設定

我們可讓安全性管理員自訂其安全性設定，以滿足組織的需求。 雖然一般規則，EOP 和 Microsoft Defender for Office 365 有兩個安全性層級，我們建議： Standard 和 Strict。 這些設定會列在 [EOP 和 Microsoft Defender For Office 365 安全性的建議設定](recommended-settings-for-eop-and-office365.md)中。

### <a name="miscellaneousnon-policy-settings"></a>雜項/非原則設定

這些設定涵蓋安全性原則以外的功能範圍。

<br>

****

|安全性功能名稱|標準版|嚴格|留言|
|---|---|---|---|
|[設定 SPF 以協助防止詐騙 ](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)|是|是||
|[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)|是|是|使用 `action=quarantine` Standard 和 `action=reject` Strict。|
|部署 [報告訊息載入](enable-the-report-message-add-in.md) 宏或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md) ，以改進使用者對可疑電子郵件的報告|是|是||
|排程惡意程式碼和垃圾郵件報告|是|是||
|應禁止或監視自動轉送至外部網域|是|是||
|應啟用整合審計|是|是||
|[IMAP 與信箱的連線能力](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|停用|停用||
|[POP 與信箱的連線能力](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|停用|停用||
|已驗證的 SMTP 提交|停用|停用|已驗證的用戶端 SMTP 提交 (也稱為「用戶端 SMTP 提交」或「SMTP 驗證」) ，POP3 及 IMAP4 的用戶端和應用程式以及產生及傳送電子郵件的裝置也是必要的。 <p> 如需全域或選擇性地啟用和停用 SMTP 驗證的指示，請參閱 [在 Exchange Online 中啟用或停用已驗證用戶端 smtp 提交](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)。|
|EWS 至信箱的連接|停用|停用|Outlook 會針對空閒/忙碌、外出時設定和行事曆共用使用 Exchange Web 服務。 如果您不能全域停用 EWS，您可以使用下列選項： <ul><li>若您的用戶端支援新式驗證 (新式 auth) ，請使用 [驗證原則](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) ，以防止 EWS 使用基本驗證。</li><li>使用 [用戶端存取規則](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) ，將 EWS 限制在特定使用者或來源 IP 位址。</li><li>控制全域或每位使用者對特定應用程式的 EWS 存取。 如需相關指示，請參閱 [Control access TO EWS In Exchange](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)。</li></ul> <p> [報告訊息增益集](enable-the-report-message-add-in.md)和[報告網路釣魚增益集](enable-the-report-phish-add-in.md)預設會在支援的環境中使用 REST，但是如果無法使用，則會回到 EWS。 使用 REST 的支援環境如下：<ul><li>Exchange Online</li><li>Exchange 2019 或 Exchange 2016</li><li>Microsoft 365 訂閱或單一時間購買 Outlook 2019 的目前 Windows Outlook for Windows。</li><li>Microsoft 365 訂閱的目前 Outlook for Mac，或單一時間購買 Outlook for Mac 2016 或更新版本。</li><li>iOS 和 Android 版 Outlook</li><li>Outlook 網頁版</li></ul>|
|[PowerShell 連線能力](/powershell/exchange/disable-access-to-exchange-online-powershell)|停用|停用|可供信箱使用者或郵件使用者 ([Get-User](/powershell/module/exchange/get-user) Cmdlet) 所傳回的使用者物件。|
|使用 [哄騙情報](learn-about-spoof-intelligence.md) 將寄件者新增至您的允許清單|是|是||
|[以目錄為基礎的 Edge 封鎖 (DBEB) ](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|已啟用|已啟用|網欄位型別 = 權威性|
|[設定所有系統管理員帳戶的多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|已啟用|已啟用||
|

## <a name="troubleshooting"></a>疑難排解

使用系統管理中心的報告疑難排解一般問題和趨勢。 使用訊息追蹤工具，尋找關於訊息的單點特定資料。 請參閱[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)，以深入了解報告功能。 若要深入瞭解郵件追蹤工具，請參閱 [安全性 & 合規性中心的郵件追蹤](message-trace-scc.md)。

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>報告對 Microsoft 的誤報和漏報

若要協助改善服務中每個人的垃圾郵件篩選，您應報告誤報 (已標示為錯誤) 和 false 不利的電子郵件， (有錯誤的電子郵件) Microsoft 進行分析。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="create-mail-flow-rules"></a>建立郵件流程規則

建立郵件流程規則 (也稱為傳輸規則) 或自訂篩選以滿足您的業務需求。

在實際執行環境中部署新規則時，請先選取其中一個測試模式，以查看規則的效果。 當您認為規則是以預期的方式運作後，請將規則模式變更為 [ **強制執行**]。

當您部署新規則時，請考慮新增其他 [ **產生** 附隨報告] 動作，以監視規則採取的動作。

在您的組織同時包含內部部署 Exchange 和 Exchange Online 的混合式環境中，請考慮您在郵件流程規則中使用的條件。 如果您想要將規則套用至整個組織，請務必使用內部部署 Exchange 和 Exchange Online 中提供的條件。 在這兩種環境中，大部分的條件都是可用的，只在一個環境或另一個環境中提供。 若要深入瞭解，請參閱 [郵件流程規則 (傳輸規則) 在 Exchange Online 中](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。