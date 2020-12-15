---
title: Microsoft 365 中優先順序帳戶的安全性建議
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何提升安全性設定，以及如何在 Microsoft 365 組織中提升優先順序帳戶的安全性設定，以及使用報表、警示和調查。
ms.openlocfilehash: aee238d2fb58d2772881d8d77f98959906943290
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668113"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365 中優先順序帳戶的安全性建議

如果您從組織中要求您執行某項緊急的電子郵件，您該怎麼辦？ 您會這麼做嗎？ 大多數人員會遵守要求。

針對攻擊者，強制轉換隨機網路以取得隨機或未知使用者之認證的一般網路釣魚攻擊是低效的。 另一方面， _spear 網路釣魚_ 或 _whaling_ 攻擊，其可讓使用者在電源或授權的位置受到攻擊，對攻擊者而言會有更大的回報。 如果這些優先順序帳戶遭到損害，攻擊者可能會利用組織內的系統管理員、財務、產品甚至實體存取能力，取得帳戶的存取權。

Microsoft 365 和 Microsoft Defender for Office 365 包含許多不同的功能，可協助您為優先順序帳戶提供額外的安全性層級。 本文將討論可用的功能及其用法。

## <a name="increase-sign-in-security-for-priority-accounts"></a>增加優先順序帳戶的登入安全性

優先順序帳戶需要增加的登入安全性。 您可以要求多重要素驗證 (MFA) 並停用舊版驗證通訊協定，以提升其登入安全性。

如需相關指示，請參閱 [步驟1。增加具有 MFA 的遠端工作者的登入安全性](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。 雖然本文是有關遠端工作者的資訊，但相同的概念也適用于優先順序使用者。

**附註**：

- 在 exchange Online 中，exchange Web 服務 (EWS) 、Exchange ActiveSync、POP3、IMAP4 和遠端 PowerShell 中已被取代的基本驗證。 如需詳細資訊，請參閱此 [博客文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。

- 您可以使用 Exchange Online 中的 [驗證原則](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 和 [用戶端存取規則](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) ，封鎖基本驗證和舊版驗證通訊協定，例如 POP3、IMAP4 和驗證的 SMTP。

- 您可以停用個別信箱上的 POP3 和 IMAP4 存取權。 您可以在組織層級停用已驗證的 SMTP，並在仍需要該 SMTP 的特定信箱上啟用該 SMTP。 如需相關指示，請參閱下列主題：
  - [啟用或停用使用者 POP3 或 IMAP4 存取權](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [啟用或停用已驗證的用戶端 SMTP 提交 (SMTP 驗證) ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>對優先順序帳戶使用嚴格的預先設定安全性原則

優先順序使用者需要更嚴格的動作，以用於 Exchange Online Protection (EOP) 和 Defender for Office 365 中提供的各種保護。

例如，若要將歸類為垃圾郵件的郵件傳送至 [垃圾郵件] 資料夾，您應該隔離這些相同的郵件（如果它們是用於優先順序帳戶）。

您可以使用預先設定的安全性原則中的 Strict 設定檔，為優先順序帳戶執行此嚴格的方法。

「預設」安全性原則是一個方便且集中的位置，可將建議的嚴格原則設定套用至 EOP 和 Defender for Office 365 中的所有保護。 如需詳細資訊，請參閱 [EOP 和 Microsoft Defender For Office 365 中的預先設定安全性原則](preset-security-policies.md)。

如需嚴格原則設定與預設和標準原則設定的區別之詳細資訊，請參閱 [EOP 和 Microsoft Defender For Office 365 security 的建議設定](recommended-settings-for-eop-and-office365-atp.md)。

## <a name="user-tags"></a>使用者標記

Microsoft Defender for Office 365 方案 2 (中的使用者標記是 Microsoft 365 E5 或附加元件訂閱) 中的一種方法，可快速識別及分類報告和事件調查中的特定使用者或使用者群組。

「**優先順序帳戶**」是一種內建的使用者標記， (稱為 _系統_ 標籤) ，可供您用來識別涉及優先順序帳戶的事件及警示。 如需 **優先順序帳戶** 的詳細資訊，請參閱 [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。

您也可以建立自訂標記，進一步識別和分類您的優先順序帳戶。 如需詳細資訊，請參閱 [User tags](user-tags.md)。 請注意，您可以在與自訂使用者標籤位於相同介面中 (系統標記) 管理 **優先順序帳戶** 。

## <a name="priority-accounts-in-reports-and-investigations-in-microsoft-365"></a>Microsoft 365 中報告和調查中的優先順序帳戶

****

|功能|描述|
|---|---|
|警示|受影響使用者的使用者標記是可見的，而且在安全性 & 合規性中心的 [ **View alerts** ] 頁面上以篩選器形式提供。 如需詳細資訊，請參閱 [查看提醒](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)。|
|威脅總管 <p> 即時偵測|在 [ **威脅瀏覽器** ] 中 (microsoft Defender for Office 365 plan 2) 或 **即時** 偵測 (Microsoft Defender for office 365 plan 1) ，使用者標記會顯示在 [電子郵件方格] 視圖和 [電子郵件詳細資料] 浮出視窗中。 使用者標記也可以做為可篩選的屬性。 如需詳細資訊，請參閱  [威脅資源管理器中的標記](threat-explorer.md#tags-in-threat-explorer)。|
|行銷活動檢視|使用者標記是 Microsoft Defender for Office 365 方案2中的眾多可篩選屬性之一。 如需詳細資訊，請參閱 [即時檢視](campaigns.md)。|
|威脅防護狀態報告|在實際 **威脅防護狀態報表** 中的所有 views 和詳細資料表格中，您可以依 **優先順序帳戶** 來篩選結果。 如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。|
|優先順序帳戶報告的電子郵件問題|Exchange 系統管理中心中「優先順序帳戶」報告的 **電子郵件問題** (EAC) 包含 **優先順序帳戶** 之未傳遞和延遲郵件的相關資訊。 如需詳細資訊，請參閱 [優先順序帳戶報告的電子郵件問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。|
|

## <a name="see-also"></a>也請參閱

[宣告 Office 365 的 Microsoft Defender 優先順序帳戶保護](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
