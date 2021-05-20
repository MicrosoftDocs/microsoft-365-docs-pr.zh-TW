---
title: 調整防網路釣魚保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 系統管理員可以瞭解如何在 Microsoft 365 中找出網路釣魚郵件的原因，以及如何防止未來更多網路釣魚郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d8f3f93b3fe1643467a12f90123b839addad2ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537844"
---
# <a name="tune-anti-phishing-protection"></a>調整防網路釣魚保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

雖然 Microsoft 365 附帶的各種防網路釣魚功能預設為啟用，但是有些網路釣魚郵件仍可進入您的信箱。 本主題說明如何探索網路釣魚郵件的原因，以及您可以如何調整 Microsoft 365 組織中的反網路釣魚設定，_而不會不慎使事情更糟_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>第一件事是：處理任何已遭破壞的帳戶，並確定您封鎖其他網路釣魚郵件，讓

如果寄件者的帳戶因網路釣魚郵件而遭到損害，請依照[Microsoft 365 中回應受損電子郵件帳戶](responding-to-a-compromised-email-account.md)的步驟進行。

如果您的訂閱包含 Microsoft Defender for Office 365，您可以使用[Office 365 威脅情報](office-365-ti.md)來識別也收到網路釣魚郵件的其他使用者。 您可以使用其他選項封鎖網路釣魚郵件：

- [Microsoft Defender 中 Office 365 的安全連結](set-up-safe-links-policies.md)

- [Microsoft Defender 中 Office 365 的安全附件](set-up-safe-attachments-policies.md)

- [Microsoft Defender 中 Office 365 的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。 請注意，您可以暫時將原則中的 **高級網路釣魚閥** 值從 **Standard** 增加為 **積極**、 **更積極** 或 **最積極** 的。

確認已開啟這些 Office 365 功能的 Defender。

## <a name="report-the-phishing-message-to-microsoft"></a>將網路釣魚郵件報告給 Microsoft

報告網路釣魚郵件有助於調整用於保護 Microsoft 365 中所有客戶的篩選器。 如需相關指示，請參閱 [將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>檢查郵件頭

您可以檢查網路釣魚郵件的標頭，以查看是否有任何可以執行的動作，以防止更多網路釣魚郵件進入。 換句話說，檢查郵件頭可協助您識別組織中負責允許網路釣魚郵件的任何設定。

具體說來，您應該檢查郵件頭中的 **X-Forefront-Antispam-Report** 標頭欄位，以瞭解是否已略過篩選垃圾郵件篩選判定中的垃圾郵件或網路釣魚 (SFV) 值。 略過篩選的郵件會有輸入 `SCL:-1` ，這表示您的其中一個設定是透過覆寫由服務所決定的垃圾郵件或網路釣魚 verdicts，允許這封郵件。 如需如何取得郵件頭及所有可用反垃圾郵件和反網路釣魚郵件頭之完整清單的詳細資訊，請參閱[Microsoft 365 中的反垃圾郵件郵件頭](anti-spam-message-headers.md)。

## <a name="best-practices-to-stay-protected"></a>保持受保護狀態的最佳作法

- 請以每月的頻率執行 [安全分數](../defender/microsoft-secure-score.md) ，以評估組織的安全性設定。

- 針對因錯誤而導致隔離的郵件，或透過所允許的郵件，我們建議您在 [威脅瀏覽器和即時](threat-explorer.md)偵測中搜尋這些郵件。 您可以依寄件者、收件者或郵件識別碼進行搜尋。 找到訊息之後，按一下主旨以移至 [詳細資料]。 針對隔離的郵件，請查看「偵測技術」為何，這樣您就可以使用適當的方法來覆寫。 若為允許的郵件，請查看允許郵件使用的原則。

- 來自欺騙寄件者的電子郵件 (郵件的 [寄件者] 位址不符合郵件的來源，) 會歸為 Office 365 的 Defender 中的網路釣魚。 有時哄騙是良性的，有時候使用者不想要隔離特定欺騙寄件者的郵件。 若要將影響降至最低，請定期查看 [哄騙情報洞察力](learn-about-spoof-intelligence.md)、[承租人允許/封鎖清單](tenant-allow-block-list.md)中的 [**偽造**] 索引標籤，以及 [欺騙偵測報告](view-email-security-reports.md#spoof-detections-report)。 當您已複習允許和封鎖的欺騙性寄件者，並做任何必要的覆寫後，您就可以自信地 [設定反網路釣魚原則中的欺騙情報](set-up-anti-phishing-policies.md#spoof-settings) ，以 **隔離** 可疑郵件，而不是將可疑郵件傳遞至使用者的 [垃圾郵件] 資料夾。

- 您可以在 Microsoft Defender for Office 365 中，為模擬 (網域或使用者) ，重複上述步驟。 模仿報告位於 **威脅管理** \> **儀表板** \> **Insights** 底下。

- 定期查看「 [威脅防護狀態」報告](view-reports-for-mdo.md#threat-protection-status-report)。

- 有些客戶會將自己的網域放入反垃圾郵件原則中的允許寄件者或允許網域清單中，以無意間允許網路釣魚郵件。 雖然這種設定可讓某些合法的郵件透過，但也會允許垃圾郵件和/或網路釣魚篩選器通常會封鎖惡意郵件。 除了允許網域之外，您還應該修正基礎問題。

  若要處理)  (Microsoft 365 封鎖的合法郵件，最好的方法是針對您網域中的寄件者，針對 _所有_ 的電子郵件網域，完整且完整地設定 DNS 中的 SPF、DKIM 及 DMARC 記錄：

  - 確認您的 SPF 記錄識別出您網域中寄件者的 _所有_ 電子郵件來源 (請勿忘記協力廠商服務！ ) 。

  - 使用硬性失敗 (\- 所有) ，以確保已設定為執行此作業的電子郵件系統拒絕未授權的寄件者。 您可以使用「 [欺騙性智慧真知灼見](learn-about-spoof-intelligence.md) 」來識別使用您網域的寄件者，這樣您就可以在 SPF 記錄中包含授權的協力廠商寄件者。

  如需設定指示，請參閱：

  - [設定 SPF 以協助防止詐騙 ](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 驗證從您自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)

  - [使用 DMARC 驗證電子郵件](use-dmarc-to-validate-email.md)

- 建議您盡可能將網域的電子郵件直接傳遞至 Microsoft 365。 換句話說，請將 Microsoft 365 網域的 MX 記錄指向 Microsoft 365。 Exchange Online Protection (EOP) 能夠在將其郵件直接傳遞至 Microsoft 365 時，為您的雲端使用者提供最佳的保護。 如果您必須在 EOP 前使用協力廠商的電子郵件清潔系統，請使用增強型介面篩選功能。 如需相關指示，請參閱[強化篩選的 Exchange Online 中的連接器](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- 使用者應使用 [報告訊息增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md) ，向 Microsoft 報告訊息，以進行系統訓練。 系統管理員也應利用 [管理員提交](admin-submission.md) 功能。

- 多重因素驗證 (MFA) 是防範已遭破壞之帳戶的最佳方式。 您應強烈考慮為您的所有使用者啟用 MFA。 針對分段的方法，在您為每個人啟用 MFA 之前，先為最機密的使用者啟用 MFA (系統管理員、行政人員等等 ) 。 如需相關指示，請參閱 [設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 將規則轉寄給外部收件者通常是被攻擊者用來提取資料。 使用 [Microsoft Secure 得分](../defender/microsoft-secure-score.md)中的 [**複查信箱轉寄規則**] 資訊，尋找甚至避免將轉寄規則轉接給外部收件者。 如需詳細資訊，請參閱[含有安全分數的用戶端外部轉寄降低風險規則](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) (英文)。
