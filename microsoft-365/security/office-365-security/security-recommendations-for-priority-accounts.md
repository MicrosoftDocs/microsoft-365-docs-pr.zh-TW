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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: 系統管理員可以瞭解如何提升安全性設定，以及如何針對其 Microsoft 365 組織中優先順序帳戶使用報告、警示與調查。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 10890a5fe797439de0bfc28bf28a216318016908
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929303"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365 中優先順序帳戶的安全性建議

並非所有使用者帳戶都有相同公司資訊的存取權。 有些帳戶可以存取敏感性資訊，例如財務資料、產品開發資訊、合作夥伴存取重要建系統等。 如果帳戶遭到入侵，可存取高度機密資訊的帳戶會造成嚴重的威脅。 我們將這些類型的帳戶稱為 _優先順序帳戶_。 優先順序帳戶 (但不限於其他) CEOS、COS、CFOS、基礎結構系統管理員帳戶、建建系統帳戶等。

針對駭客，針對一般或不明使用者而投射隨機網的普通網路釣魚攻擊沒有效率。 另一方面，_以_ 優先順序帳戶為目標的網路釣魚或網路釣魚攻擊，對攻擊者來說十分值得。 因此，優先順序帳戶比一般保護更需要強大，以防止帳戶被入侵。

Microsoft 365 和 Office 365 的 Microsoft Defender 包含數種主要功能，可針對您的優先順序帳戶提供額外一層安全性。 本文說明這些功能及使用方法。

![圖示表單中的安全性建議摘要](../../media/security-recommendations-for-priority-users.png)

****

|工作|所有 Office 365 企業版方案|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[提高優先順序帳戶的登錄安全性](#increase-sign-in-security-for-priority-accounts)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[針對優先順序帳戶使用嚴格預先設定安全性原則](#use-strict-preset-security-policies-for-priority-accounts)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[將使用者標記應用程式至優先順序帳戶](#apply-user-tags-to-priority-accounts)|||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[監控警示、報告和偵測中優先順序的帳戶](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[訓練使用者](#train-users)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>提高優先順序帳戶的登錄安全性

優先順序帳戶需要提高的簽到安全性。 您可以要求 MFA 的多重要素驗證功能來 (，) 停用舊版驗證通訊協定，提高他們的) 安全性。

有關指示，請參閱 [步驟 1。使用 MFA 提高遠端工作者的登錄安全性](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。 雖然本文主要說明遠端工作者，但優先順序使用者也是同樣的概念。

**注意**：我們強烈建議您全域停用所有優先順序使用者的舊版驗證通訊協定，如前一篇文章所述。 如果您的商務需求防止您這麼做，Exchange Online 提供下列控制項來協助限制舊版驗證通訊協定的範圍：

- 您可以使用 Exchange [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) Online 中的驗證原則及用戶端存取[規則](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)來封鎖或允許特定使用者的基本驗證和舊版驗證通訊協定，例如 POP3、IMAP4 和已驗證的 SMTP。

- 您可以在個別信箱上停用 POP3 和 IMAP4 存取。 您可以在組織層級停用已驗證的 SMTP，並針對仍然需要驗證的特定信箱啟用它。 相關指示請參閱下列主題：
  - [為使用者啟用或停用 POP3 或 IMAP4 存取](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [啟用或停用已驗證的用戶端 SMTP 提交 (SMTP AUTH) ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

此外，也值得一提，Exchange Online for Exchange Web Services (EWS) 、Exchange ActiveSync、POP3、IMAP4 和遠端 PowerShell 中，基本驗證正被系統取消。 詳情請參閱此 [部落格文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>針對優先順序帳戶使用嚴格預先設定安全性原則

優先順序使用者針對 Exchange Online Protection 和 EOP (以及 Office 365 的 Defender 提供的各種保護，需要更) 的動作。

例如，如果郵件是供優先順序帳戶使用，您應該隔離那些被歸類為垃圾郵件的郵件，而不是將郵件傳送至垃圾郵件資料夾。

您可以在預先設定的安全性原則中，使用 Strict 設定檔，針對優先順序帳戶採用這種嚴格方法。

預先設定的安全性原則是方便且集中的位置，可針對 EOP 和 Office 365 的所有保護，使用建議的嚴格原則設定。 詳細資訊請參閱 EOP 中預先設定的安全性原則，以及[適用于 Office 365 的 Microsoft Defender。](preset-security-policies.md)

有關嚴格規定設定與預設和標準策略設定之間如何差異的詳細資訊，請參閱 EOP 和 [Office 365](recommended-settings-for-eop-and-office365-atp.md)安全性的 Microsoft Defender 建議設定。

## <a name="apply-user-tags-to-priority-accounts"></a>將使用者標記應用程式至優先順序帳戶

Microsoft Defender for Office 365 方案 2 (作為 Microsoft 365 E5 或附加元件訂閱) 中的使用者標記，是一種在報告和事件調查中快速識別及分類特定使用者或使用者群組的方法。

**優先順序帳戶** 是一種內建的使用者 (，稱為系統標記 _) ，_ 可用於識別涉及優先順序帳戶的事件和警示。 有關優先順序帳戶詳細資訊 **，請參閱** 管理及 [監控優先順序帳戶](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。

您也可以建立自訂標記，進一步識別並分類優先順序帳戶。 詳細資訊請參閱使用者 [標記](user-tags.md)。 請注意，您可以在與自訂使用者標記 **(** 介面) 管理優先順序帳戶及系統標記。

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>監控警示、報告和偵測中優先順序的帳戶

在保護並標記優先順序使用者之後，您可以使用 EOP 和 Office 365 的 Defender 中可用的報告、警示與調查，快速找出涉及優先順序帳戶的事件或偵測。 下表說明支援使用者標記的功能。

<br>

****

|功能|描述|
|---|---|
|警示|在安全性與合規性中心的View 通知頁面上，受影響的使用者使用者標記會以篩選器&使用。  詳細資訊請參閱檢視 [警示](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)。|
|威脅總管 <p> 即時偵測|在 **威脅** 總管 (Microsoft Defender for Office 365 方案 2 **)** 或即時偵測 (Microsoft Defender for Office 365 方案 1) 中，使用者標記會顯示在電子郵件格線視圖和電子郵件詳細資料飛出區中。 使用者標記也可做為可篩選的屬性。 詳細資訊請參閱威脅管  [中的標記](threat-explorer.md#tags-in-threat-explorer)。|
|行銷活動檢視|使用者標記是 Microsoft Defender for Office 365 方案 2 中許多可篩選的屬性之一。 詳細資訊請參閱行銷活動 [視圖](campaigns.md)。|
|威脅防護狀態報告|在威脅防護狀態報表中，幾乎所有視圖和詳細資料表都可以按優先順序帳戶 **篩選結果**。 詳細資訊請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。|
|優先順序帳戶的電子郵件問題報告|Exchange **admin center** (EAC) 優先順序帳戶的電子郵件問題報告包含優先順序帳戶未傳遞和延遲 **訊息的資訊**。 詳細資訊請參閱優先順序 [帳戶的電子郵件問題報告](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。|
|

## <a name="train-users"></a>訓練使用者

具有優先順序帳戶的訓練使用者，可以協助節省這些使用者和安全性作業小組許多時間與挫折感。 聰明的使用者較不會開啟可疑電子郵件訊息中的附件或按一下連結，而且較有可能避免可疑的網站。

教育人員學校 [網路安全性活動](https://www.belfercenter.org/CyberPlaybook) 手冊為在貴組織中建立強大的安全性認知文化提供了絕佳指南，包括訓練使用者識別網路釣魚攻擊。

Microsoft 365 提供下列資源，協助告知貴組織的使用者：

<br>

****

|概念|資源|說明|
|---|---|---|
|Microsoft 365|[可自訂的學習路徑](https://docs.microsoft.com/office365/customlearning/)|這些資源可以協助您將訓練組織的使用者整合在一起。|
|Microsoft 365 安全性|[學習模組：使用 Microsoft 365 的內建智慧型安全性保護貴組織](https://docs.microsoft.com/learn/modules/security-with-microsoft-365)|本單元可讓您說明 Microsoft 365 安全性功能如何共同作業，並說明這些安全性功能的好處。|
|多重要素驗證|[雙步驟驗證：額外的驗證頁面是什麼？](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|本文可協助使用者瞭解什麼是多重要素驗證，以及為何在貴組織中使用多重要素驗證。|
|攻擊攻擊訓練|[開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)|Microsoft Defender for Office 365 方案 2 中的模擬攻擊訓練可讓系統管理員設定、啟動和追蹤特定使用者群組的模擬網路釣魚攻擊。|

此外，Microsoft 建議使用者採取本文所述的動作：保護您的帳戶和裝置，防範 [駭客和惡意程式碼](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)。 這些動作包括：

- 使用強式密碼
- 保護裝置
- 啟用 Windows 10 和 Mac PC 上的安全性功能 (未管理裝置) 

## <a name="see-also"></a>另請參閱

[在 Microsoft Defender 中宣佈 Office 365 的優先順序帳戶保護](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
