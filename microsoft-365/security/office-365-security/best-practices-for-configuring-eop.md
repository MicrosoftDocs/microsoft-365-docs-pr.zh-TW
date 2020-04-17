---
title: 設定 EOP 和 Office 365 ATP 的最佳作法
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 遵循下列 Exchange Online Protection (EOP) 最佳作法建議，以成功完成設定並避免發生常見組態錯誤。
ms.openlocfilehash: 9bddb736d41b4fd56790b8bbe9dbb00d07e75553
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528614"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>設定 EOP 和 Office 365 ATP 的最佳作法

遵循下列 Exchange Online Protection (EOP) 最佳作法建議，以成功完成設定並避免發生常見組態錯誤。 本主題假設您已完成安裝程序。 若您尚未完成 EOP 安裝，請參閱 [設定 EOP 服務](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用測試網域

建議您使用測試網域、子網域或低容量網域試用服務功能，然後才在較高容量的實際執行網域上進行實作。

## <a name="synchronize-recipients"></a>同步處理收件者

如果您的組織在內部部署 Active Directory 環境中有現有的使用者帳戶，您可以將這些帳戶同步處理至雲端中的 Azure Active Directory。 建議使用目錄同步作業。 若要深入了解使用目錄同步作業的好處及其設定步驟，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)。

## <a name="recommended-settings"></a>建議的設定

我們可讓安全性管理員自訂其安全性設定，以滿足組織的需求。 雖然一般來說，在 EOP 和 Office 365 ATP 中也有兩個安全性層級，我們建議： Standard 和 Strict。 這些設定會列在[EOP 和 Office 365 ATP 安全性的建議設定](recommended-settings-for-eop-and-office365-atp.md)中。

### <a name="miscellaneousnon-policy-settings"></a>雜項/非原則設定

這些設定涵蓋安全性原則以外的功能範圍。

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|[在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)|是|是||
|[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)|是|是|使用 action = Standard 的隔離，對 Strict 採取動作 = 拒絕。|
|部署報告訊息附加元件，以改善使用者對可疑電子郵件的報告|是|是||
|排程惡意程式碼和垃圾郵件報告|是|是||
|應禁止或監視自動轉送至外部網域|是|是||
|應啟用整合審計|是|是||
|[IMAP 與信箱的連線能力](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|停用|停用||
|[POP 與信箱的連線能力](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|停用|停用||
|將 SMTP 驗證提交至信箱|停用|停用||
|EWS 至信箱的連接|停用|停用||
|[PowerShell 連線能力](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|停用|停用|可用於信箱使用者或郵件使用者（ [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user) Cmdlet 所傳回的使用者物件）。|
|盡可能使用[哄騙智慧](learn-about-spoof-intelligence.md)白名單寄件者|是|是||
|以目錄為基礎的邊緣封鎖（DBEB）|已啟用|已啟用|網欄位型別 = 權威性|
|[設定所有系統管理員帳戶的多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|已啟用|已啟用||

## <a name="troubleshooting"></a>疑難排解

使用系統管理中心的報告疑難排解一般問題和趨勢。 使用訊息追蹤工具，尋找關於訊息的單點特定資料。 請參閱[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)，以深入了解報告功能。 若要深入瞭解郵件追蹤工具，請參閱[安全性 & 合規性中心的郵件追蹤](message-trace-scc.md)。

## <a name="report-false-positive-and-false-negatives-to-microsoft"></a>向 Microsoft 報告誤報和漏報

若要協助改善服務中每個人的垃圾郵件篩選，您應該將誤報（良好的電子郵件標記為壞）和漏報（不允許使用的電子郵件），以進行分析。 如需詳細資訊，請參閱[將郵件和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="create-mail-flow-rules"></a>建立郵件流程規則

建立郵件流程規則或自訂篩選，以符合您的業務需求。

在實際執行環境中部署新規則時，請先選取其中一個測試模式，以查看規則的效果。 當您認為規則是以預期的方式運作後，請將規則模式變更為 [**強制執行**]。

當您部署新規則時，請考慮新增其他 [**產生**附隨報告] 動作，以監視規則採取的動作。

在您的組織同時包含內部部署 Exchange 和 Office 365 的混合式環境中，請考慮您在郵件流程規則中使用的條件。 如果您想要將規則套用至整個組織，請務必使用內部部署 Exchange 和 Office 365 中提供的條件。 在這兩種環境中，大部分的條件都是可用的，只在一個環境或另一個環境中提供。 若要深入瞭解，請參閱[Exchange Online 中的郵件流程規則（傳輸規則）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
