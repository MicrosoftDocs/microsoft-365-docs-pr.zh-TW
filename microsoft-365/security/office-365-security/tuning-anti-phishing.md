---
title: 調整 Office 365 中的反網路釣魚保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 系統管理員可以瞭解如何知道網路釣魚郵件的取得原因，以及如何防止未來的更多網路釣魚郵件。
ms.openlocfilehash: 93fdc17379627a2d595a3861ae3f8f1f9dcefeeb
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528986"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>調整 Office 365 中的反網路釣魚保護

雖然 Office 365 附帶的各種防網路釣魚功能預設為啟用，但是有些網路釣魚郵件仍可進入您的信箱。 本主題說明如何探索網路釣魚郵件的執行原因，以及您可以如何調整 Exchange Online 組織中的反網路釣魚設定，_而不會不慎使事情更糟_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>第一件事是：處理任何已遭破壞的帳戶，並確定您封鎖其他網路釣魚郵件，讓

如果寄件者的帳戶因網路釣魚郵件而遭到損害，請遵循在[Office 365 中回應受損電子郵件帳戶](responding-to-a-compromised-email-account.md)的步驟。

如果您的訂閱包含高級威脅防護（ATP），您可以使用[Office 365 威脅情報](office-365-ti.md)來識別也收到網路釣魚郵件的其他使用者。 您可以使用其他選項封鎖網路釣魚郵件：

- [ATP 安全連結](set-up-atp-safe-links-policies.md)

- [ATP 安全附件](set-up-atp-safe-attachments-policies.md)

- [Office 365 中的 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。 請注意，您可以暫時將原則中的**高級網路釣魚閥**值從**Standard**增加為**積極**、**更積極**或**最積極**的。

確認已開啟這些 ATP 功能。

## <a name="report-the-phishing-message-to-microsoft"></a>將網路釣魚郵件報告給 Microsoft

報告網路釣魚郵件有助於調整用來保護 Office 365 中所有客戶的篩選。 如需相關指示，請參閱[將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>檢查郵件頭

您可以檢查網路釣魚郵件的標頭，以查看是否有任何可以執行的動作，以防止更多網路釣魚郵件進入。 換句話說，檢查郵件頭可協助您識別組織中負責允許網路釣魚郵件的任何設定。

具體而言，您應該檢查郵件頭中的**X-Forefront-Antispam-Report**標頭欄位，以瞭解在垃圾郵件篩選判定（SFV）值中略過的垃圾郵件或網路釣魚篩選跡象。 略過篩選的郵件會有輸入`SCL:-1`，這表示您的其中一個設定是透過覆寫由服務所決定的垃圾郵件或網路釣魚 verdicts，允許這封郵件。 如需如何取得郵件頭及所有可用反垃圾郵件和反網路釣魚郵件標題之完整清單的詳細資訊，請參閱[Office 365 中的反垃圾郵件郵件頭](anti-spam-message-headers.md)。

## <a name="best-practices-to-stay-protected"></a>保持受保護狀態的最佳作法

- 請以每月的頻率執行[安全評分](../mtp/microsoft-secure-score.md)，以評估 Office 365 組織的安全性設定。

- 定期查看[哄騙情報報告](learn-about-spoof-intelligence.md)，並[設定假冒情報](set-up-anti-phishing-policies.md#spoof-settings)，以**隔離**可疑郵件，而不是傳遞給使用者的 [垃圾郵件] 資料夾。

- 定期查看「[威脅防護狀態」報告](view-reports-for-atp.md#threat-protection-status-report)。

- 有些客戶會將自己的網域放在反垃圾郵件原則中的允許寄件者或允許的網域清單中，以無意間允許網路釣魚郵件。 如果您選擇這麼做，您必須特別小心使用。 雖然這種設定可讓某些合法的郵件透過，但也會允許 Office 365 垃圾郵件和/或網路釣魚篩選器通常會封鎖的惡意郵件。

  若要處理受 Office 365 （誤報）封鎖的合法郵件（包括網域中的寄件者），最好在 DNS 中完整且完整地為您的 Office 365 中的_所有_電子郵件網域設定 SPF、DKIM 及 DMARC 記錄：

  - 確認您的 SPF 記錄識別出您網域中寄件者的_所有_電子郵件來源（請勿忘記協力廠商服務！）。

  - 使用 hard fail （\-）以確保已設定為執行此作業的電子郵件系統拒絕未授權的寄件者。 您可以使用[哄騙情報](learn-about-spoof-intelligence.md)來協助識別使用您網域的寄件者，這樣您就可以在 SPF 記錄中包含授權的協力廠商寄件者。

  如需設定指示，請參閱：
  
  - [在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)

  - [在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)

- 建議您盡可能將網域的電子郵件直接傳送到 Office 365。 換句話說，請將您的 Office 365 網域的 MX 記錄指向 Office 365。 Exchange Online Protection （EOP）可在您的使用者郵件直接傳遞至 Office 365 時，為您的雲端使用者提供最佳的保護。 如果您必須在 EOP 前使用協力廠商的電子郵件清潔系統，請使用增強型介面篩選功能。 如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- 多重要素驗證（MFA）是防範已遭破壞之帳戶的最佳方式。 您應強烈考慮為您的所有使用者啟用 MFA。 針對分段的方法，在您為所有人啟用 MFA 之前，先為您最機密的使用者（系統管理員、行政人員等等）啟用 MFA，以開始執行。 如需相關指示，請參閱[設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 將規則轉寄給外部收件者通常是被攻擊者用來提取資料。 使用[Microsoft Secure 得分](../mtp/microsoft-secure-score.md)中的 [**複查信箱轉寄規則**] 資訊，尋找甚至避免將轉寄規則轉接給外部收件者。 如需詳細資訊，請參閱[含有安全分數的用戶端外部轉寄降低風險規則](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/) (英文)。
