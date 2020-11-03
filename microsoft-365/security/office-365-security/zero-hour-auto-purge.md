---
title: '零小時自動清除 (ZAP) '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解零小時自動清除 (ZAP) 是否可以 retroactively 將 Exchange Online 信箱中已傳遞的郵件移至 [垃圾郵件] 資料夾，或 retroactively 發現為垃圾郵件或網路釣魚的隔離區。
ms.openlocfilehash: e59d93285dd75a749739b8247c156c19533ce2b1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845441"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>在 Exchange Online 中，以零小時自動清除 (ZAP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>ZAP 的基本功能

在 Exchange Online 中有信箱的 Microsoft 365 組織中，零小時自動清除 (ZAP) 是一種電子郵件保護功能，retroactively 偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意網路釣魚、垃圾郵件或惡意程式碼郵件。

ZAP 無法在獨立 Exchange Online Protection (EOP 中運作) 保護內部部署 Exchange 信箱的環境。

## <a name="how-zap-works"></a>ZAP 的運作方式

垃圾郵件和惡意程式碼會在服務中即時更新。 不過，使用者仍然可以接收惡意郵件，但有各種原因，包括在傳遞給使用者後 weaponized 內容。 ZAP 會持續監控服務中垃圾郵件和惡意程式碼簽名的更新，以解決此問題。 ZAP 可以尋找及移除已在使用者信箱中的郵件。

對使用者而言，ZAP 動作是無縫的;如果偵測到郵件並加以移動，不會通知他們。

[安全寄件者清單](create-safe-sender-lists-in-office-365.md)、郵件流程規則 (也稱為傳輸規則) 、收件匣規則或其他篩選，其優先順序會高於 ZAP。 類似于郵件流程中所發生的情況，這表示即使服務決定所傳送的郵件需求 ZAP，但由於安全寄件者設定的原因，郵件並未採取動作。 這是將郵件設定為略過篩選所需注意的另一個原因。

### <a name="malware-zap"></a>惡意程式碼 ZAP

若為傳遞之後發現包含惡意程式碼的 **讀取或未讀取郵件** ，ZAP 會隔離包含惡意程式碼附件的郵件。 只有系統管理員可以從隔離區中查看和管理惡意程式碼郵件。

在反惡意程式碼原則中，預設會啟用惡意程式碼 ZAP。 如需詳細資訊，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

### <a name="phish-zap"></a>網路釣魚 ZAP

針對傳送後識別為網路釣魚的 **讀取或未讀取郵件** ，ZAP 結果取決於針對網路釣魚電子郵件原則中設定的 **網路釣魚電子** 郵件篩選的動作。 下列清單說明網路釣魚和其可能的 ZAP 結果的可用篩選判定動作：

- **新增 X-Header** ， **並將主旨行前置文字** ： ZAP 不會對郵件採取任何動作。

- **將郵件移至垃圾郵件** ：將郵件移至 [垃圾郵件] 資料夾，只要信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。 如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

- **將郵件重新導向至電子郵件地址** 、 **刪除郵件** 、 **隔離訊息** ： ZAP 會隔離郵件。

根據預設，反垃圾郵件原則中已啟用網路釣魚 ZAP， **網路釣魚電子郵件** 篩選決定的預設動作為 **隔離訊息** ，這表示網路釣魚網站預設會隔離郵件。

如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱 [在 Microsoft 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

### <a name="spam-zap"></a>垃圾郵件 ZAP

針對傳送後被識別為垃圾郵件的 **未讀取郵件** ，ZAP 結果取決於針對 **垃圾** 郵件篩選決定在適用的反垃圾郵件原則中所設定的動作。 下列清單說明了垃圾郵件及其可能的 ZAP 結果的可用篩選：

- **新增 X-Header** ， **並將主旨行前置文字** ： ZAP 不會對郵件採取任何動作。

- **將郵件移至垃圾郵件** ：將郵件移至 [垃圾郵件] 資料夾，只要信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。 如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

- **將郵件重新導向至電子郵件地址** 、 **刪除郵件** 、 **隔離訊息** ： ZAP 會隔離郵件。 使用者可以查看和管理自己的垃圾郵件隔離郵件。

根據預設，反垃圾郵件原則中已啟用垃圾郵件 ZAP， **垃圾** 郵件篩選判定的預設動作是 **將郵件移至垃圾郵件資料夾** ，這表示垃圾郵件 ZAP 預設會將 **未讀取** 的郵件移至 [垃圾郵件] 資料夾。

如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱 [在 Microsoft 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 的 ZAP 考慮

在安全附件掃描中，ZAP 不會隔離 [動態傳遞](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) 的處理常式中的任何郵件，或者 EOP 惡意程式碼篩選已以 **惡意程式碼 Text.txt警示** 取代附件的郵件。 如果針對這些類型的郵件接收網路釣魚或垃圾郵件信號，而且反垃圾郵件原則中的篩選判定會設定為對郵件採取某些動作 (移至 [垃圾郵件]、[重新導向]、[刪除] 或 [隔離]) 然後，ZAP 會預設為「移至垃圾郵件」動作。

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否已移動您的郵件

若要判斷 ZAP 是否已移動您的郵件，您可以使用[威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)或[威脅總管 (及即時偵測)](threat-explorer.md)。 請注意，在系統動作中，不會在 Exchange 信箱審計記錄檔中記錄 ZAP。

## <a name="zap-faq"></a>ZAP FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>將合法郵件移至 [垃圾郵件] 資料夾時會發生什麼情況？

您應遵循正常的報告處理常式來 [誤報](report-junk-email-messages-to-microsoft.md)。 郵件會從 [收件匣] 移至 [垃圾郵件] 資料夾，其唯一原因是服務已判斷郵件是垃圾郵件或惡意的。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>使用隔離資料夾而非 [垃圾郵件] 資料夾時該怎麼辦？

根據本主題稍早所述的設定反垃圾郵件原則，ZAP 會對郵件採取動作。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>如果我使用安全寄件者、郵件流程規則或允許/封鎖的寄件者清單，該怎麼辦？

安全寄件者、郵件流程規則或封鎖及允許組織設定會優先。 因為服務正在執行您設定的工作，所以這些郵件會從 ZAP 中排除。 這是將郵件設定為略過篩選所需注意的另一個原因。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>當郵件移至另一個資料夾 (例如收件匣規則) 時，該怎麼辦？

只要郵件尚未刪除，或是尚未套用相同或更強的動作，ZAP 仍可運作。 例如，如果網路釣魚原則設定為 [隔離]，而且使用者或系統管理員已經 junked 電子郵件，則隔離會採取動作隔離檔案。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP 如何影響信箱的保留狀態？

ZAP 不會隔離保留信箱中的郵件。 根據為反垃圾郵件原則中的垃圾郵件或網路釣魚所設定的動作，ZAP 可以將郵件移至 [垃圾郵件] 資料夾。

如需 Exchange Online 中的保留的詳細資訊，請參閱 [Exchange online 中的 In-Place 保留和訴訟暫](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)止。
