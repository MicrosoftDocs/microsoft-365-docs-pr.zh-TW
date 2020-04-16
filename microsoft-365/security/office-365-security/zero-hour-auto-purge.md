---
title: 零小時自動清除（ZAP）-retroactive 防護垃圾郵件、惡意程式碼和網路釣魚。
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: 零小時自動清除（ZAP）是 Office 365 中的電子郵件保護功能，可偵測已傳遞至 Exchange Online 的垃圾郵件、惡意程式碼或網路釣魚郵件。 ZAP 執行此作業的方式取決於偵測到的惡意內容類型。
ms.openlocfilehash: 44bdab5d37863bc543d953a89ac3129b3530437d
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516770"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-office-365"></a>零小時自動清除（ZAP）-防護 Office 365 中的垃圾郵件和惡意程式碼

## <a name="overview"></a>概觀

零小時自動清除（ZAP）是 Office 365 中的電子郵件保護功能，retroactively 偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意網路釣魚、垃圾郵件或惡意程式碼郵件。

您可以使用包含 Exchange Online 信箱之任何 Office 365 訂閱隨附的預設 Exchange Online Protection （EOP）的 ZAP。 在會保護內部部署 Exchange 信箱的獨立 EOP 環境中，ZAP 無法運作。

## <a name="how-zap-works"></a>ZAP 的運作方式

Office 365 每天都會即時更新垃圾郵件和惡意程式碼簽名。 不過，使用者仍然可以接收惡意郵件，但有各種原因，包括在傳遞給使用者後 weaponized 內容。 在不斷監控 Office 365 垃圾郵件和惡意程式碼簽名的更新時，ZAP 會解決此問題。 ZAP 可以尋找及移除已在使用者信箱中的郵件。

對使用者而言，ZAP 動作是無縫的;如果偵測到郵件並加以移動，不會通知他們。

[安全寄件者清單](create-safe-sender-lists-in-office-365.md)、郵件流程規則（也稱為傳輸規則）、收件匣規則或其他篩選器優先于 ZAP。

### <a name="malware-zap"></a>惡意程式碼 ZAP

若為傳遞之後發現包含惡意程式碼的**讀取或未讀取郵件**，ZAP 會隔離包含惡意程式碼附件的郵件。 只有系統管理員可以從隔離區中查看和管理惡意程式碼郵件。

在反惡意程式碼原則中，預設會啟用惡意程式碼 ZAP。 如需詳細資訊，請參閱[Configure In Office 365 的反惡意程式碼原則](configure-anti-malware-policies.md)。

### <a name="phish-zap"></a>網路釣魚 ZAP

針對傳送後識別為網路釣魚的**讀取或未讀取郵件**，ZAP 結果取決於針對網路釣魚電子郵件原則中設定的**網路釣魚電子**郵件篩選的動作。 下列清單說明網路釣魚和其可能的 ZAP 結果的可用篩選判定動作：

- **新增 X-Header**，**並將主旨行前置文字**： ZAP 不會對郵件採取任何動作。

- **將郵件移至垃圾郵件**：只要信箱上啟用垃圾郵件規則（預設為啟用），ZAP 就會將郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[在 Office 365中設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

- **將郵件重新導向至電子郵件地址**、**刪除郵件**、**隔離訊息**： ZAP 會隔離郵件。 只有系統管理員可以查看和管理網路釣魚隔離的郵件。

根據預設，反垃圾郵件原則中已啟用網路釣魚 ZAP，**網路釣魚電子郵件**篩選決定的預設動作為**隔離訊息**，這表示網路釣魚網站預設會隔離郵件。

如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

### <a name="spam-zap"></a>垃圾郵件 ZAP

針對傳送後被識別為垃圾郵件的**未讀取郵件**，ZAP 結果取決於針對**垃圾**郵件篩選決定在適用的反垃圾郵件原則中所設定的動作。 下列清單說明了垃圾郵件及其可能的 ZAP 結果的可用篩選：

- **新增 X-Header**，**並將主旨行前置文字**： ZAP 不會對郵件採取任何動作。

- **將郵件移至垃圾郵件**：只要信箱上啟用垃圾郵件規則（預設為啟用），ZAP 就會將郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[在 Office 365中設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

- **將郵件重新導向至電子郵件地址**、**刪除郵件**、**隔離訊息**： ZAP 會隔離郵件。 使用者可以查看和管理自己的垃圾郵件隔離郵件。

根據預設，反垃圾郵件原則中已啟用垃圾郵件 ZAP，**垃圾**郵件篩選判定的預設動作是**將郵件移至垃圾郵件資料夾**，這表示垃圾郵件 ZAP 預設會將**未讀取**的郵件移至 [垃圾郵件] 資料夾。

如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a>Office 365 高級威脅防護（ATP）的 ZAP 考慮

在[動態傳遞](dynamic-delivery-and-previewing.md)掃描的處理常式中，或惡意程式碼篩選已使用**惡意程式碼警示文字 .txt**檔取代附件的情況下，ZAP 將不會隔離任何郵件。 如果針對這些類型的郵件接收網路釣魚或垃圾郵件信號，而且反垃圾郵件原則中的篩選判定會設定為對郵件採取某些動作（移至 [垃圾郵件]、[重新導向]、[刪除] 隔離），則 ZAP 會預設為「移至垃圾郵件」動作。

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否已移動您的郵件

若要判斷 ZAP 是否已移動您的郵件，您可以使用[威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)或[威脅總管 (及即時偵測)](threat-explorer.md)。 請注意，在系統動作中，不會在 Exchange 信箱審計記錄檔中記錄 ZAP。

## <a name="zap-faq"></a>ZAP FAQ

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>問：如果合法的郵件移至 [垃圾郵件] 資料夾，會發生什麼情況？

A：您應該遵循正常的報告過程[誤報](report-junk-email-messages-to-microsoft.md)。 郵件會從 [收件匣] 移至 [垃圾郵件] 資料夾，其唯一原因是服務已判斷郵件是垃圾郵件或惡意的。

### <a name="q-what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>問：我使用 Office 365 隔離而非 [垃圾郵件] 資料夾的情況為何？

A：根據本主題稍早所述的設定反垃圾郵件原則，ZAP 會對郵件採取動作。

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a>問：如果我使用郵件流程規則或允許/封鎖的寄件者清單，該怎麼辦？

A：郵件流程規則或封鎖及允許組織設定優先。 這些郵件會從 ZAP 中排除。

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>問：郵件會移至另一個資料夾（例如 [收件匣規則]）？

當郵件尚未刪除，或是只要相同或更強的動作尚未套用，則該郵件仍可運作。 例如，如果網路釣魚原則設定為 [隔離]，而且使用者或系統管理員已經 junked 電子郵件，則隔離會採取動作隔離檔案。

### <a name="q-does-zap-change-the-message-header"></a>問： ZAP 是否會變更郵件頭？

A： ZAP 動作不會對郵件頭進行任何變更。

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a>問： ZAP 如何影響信箱的保留狀態？

A： ZAP 不會隔離保留信箱中的郵件。 根據為反垃圾郵件原則中的垃圾郵件或網路釣魚所設定的動作，ZAP 可以將郵件移至 [垃圾郵件] 資料夾。

如需 Exchange Online 中的保留的詳細資訊，請參閱[Exchange online 中的 In-Place 保留和訴訟暫](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)止。
