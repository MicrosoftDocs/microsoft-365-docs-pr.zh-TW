---
title: 零時差自動清除 - 防範垃圾郵件和惡意程式碼
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
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
description: 零時差自動清除 (ZAP) 是一種電子郵件防護功能，可偵測含垃圾郵件或惡意程式碼且已傳遞到使用者收件匣的郵件，然後將惡意內容呈現為無害。 ZAP 執行此作業的方式取決於偵測到的惡意內容類型。
ms.openlocfilehash: 9ffe169baaa522ca86f712bc0fde41d4985092cd
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111897"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零時差自動清除 - 防範垃圾郵件和惡意程式碼

## <a name="overview"></a>概觀

零時差自動清除 (ZAP) 是一種電子郵件防護功能，可偵測含網路釣魚、垃圾郵件或惡意程式碼且已傳遞到使用者收件匣的郵件，然後將惡意內容呈現為無害。 ZAP 執行此作業的方式取決於偵測到的惡意內容類型。 郵件可能會因為郵件內容、URL 或附件而遭到 ZAP 處理。

任何包含 Exchange Online 信箱的 Office 365 訂用帳戶都會隨附預設 Exchange Online Protection，在其中即可取得 ZAP。

## <a name="how-zap-works"></a>ZAP 的運作方式

Office 365 每天都會即時更新反垃圾郵件引擎和惡意程式碼簽章。 不過，使用者仍可能因為各種原因而收到傳遞至其收件匣的惡意郵件，原因包括內容是否在傳遞給使用者後具攻擊性。 ZAP 可透過持續監視 Office 365 垃圾郵件和惡意程式碼簽章的更新，解決這種情況。 ZAP 可以尋找及移除已在使用者收件匣中的先前傳遞郵件。

ZAP 動作對信箱使用者而言很順暢；但如果電子郵件遭到移動，使用者就不會收到通知。 郵件不能保留超過 2 天。

允許清單、[郵件流程規則](use-transport-rules-to-configure-bulk-email-filtering.md) (也稱為傳輸規則)，以及使用者規則或其他優先於 ZAP 的篩選條件。

### <a name="malware-zap"></a>惡意程式碼 ZAP

對於新偵測的惡意程式碼，ZAP 會將整個郵件 (包括其附件) 移至惡意程式碼隔離區。 無論郵件的讀取狀態為何，都會移動郵件。 如果我們在動態傳遞掃描的過程中收到郵件的惡意程式碼訊號，ZAP 就會對郵件採取 [移至垃圾郵件] 動作。 然後允許動態傳遞完成傳遞掃描時間，並採取適當的動作。

在惡意程式碼原則中，預設會啟用惡意程式碼 ZAP。 您可以在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的 [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) Cmdlet 上，使用 *ZapEnabled* 參數來停用惡意程式碼 ZAP。 在安全性與合規性中心編輯惡意程式碼原則，也可以啟用或停用惡意程式碼 ZAP。

### <a name="phish-zap"></a>網路釣魚 ZAP

對於在傳遞後被識別為網路釣魚的郵件，ZAP 會根據涵蓋特定使用者的垃圾郵件原則採取行動，而不管郵件的讀取狀態為何。 如果網路釣魚動作原則設定為「不要」** 採取任何動作 (新增 X-header、修改主旨、不執行任何動作)，則 ZAP 將不會對郵件採取任何動作。 如果網路釣魚活動設定為 [移至垃圾郵件]，則 ZAP 會將郵件移到使用者收件匣的 [垃圾郵件] 資料夾。 **對於任何其他網路釣魚動作 (重新導向、刪除、隔離)，ZAP 會將郵件移到網路釣魚隔離區**。 請參閱下面的設定需求與排除項目。 深入了解如何[設定您的垃圾郵件篩選原則](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)。

在垃圾郵件原則中，預設會啟用網路釣魚 ZAP。 使用 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) (一個 EOP Cmdlet) 的 PhishZapEnabled** 參數可以停用網路釣魚 ZAP。

### <a name="spam-zap"></a>垃圾郵件 ZAP

對於在傳遞後被識別為垃圾郵件的郵件，ZAP 會根據涵蓋特定使用者的垃圾郵件原則採取行動 (但僅限於未讀取郵件時)。  如果原則垃圾郵件動作設定為「不要」採取任何動作 (新增 X-header、修改主旨、不執行任何動作)，則 ZAP 將不會對郵件採取任何動作。 如果垃圾郵件活動設定為 [移至垃圾郵件]，則 ZAP 會將郵件移到使用者收件匣的 [垃圾郵件] 資料夾。 **對於任何其他垃圾郵件動作 (重新導向、刪除、隔離)，ZAP 會將郵件移垃圾郵件隔離區**。 請參閱下面的設定需求與排除項目。 深入了解如何[設定您的垃圾郵件篩選原則](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)。

在垃圾郵件原則中，預設會啟用垃圾郵件 ZAP。 您可以在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)Cmdlet 的 SpamZapEnabled** 參數來停用垃圾郵件 ZAP。

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>網路釣魚和垃圾郵件 ZAP 需求、排除項目和通知

> [!IMPORTANT]
> 先前用於控制網路釣魚和垃圾郵件 ZAP 的 ZapEnabled** Cmdlet 參數，將於 **2020 年 2 月 1 日淘汰**。 如果您已撰寫使用 ZapEnabled 參數的任何指令碼，我們建議將其更新為使用 SpamZapEnabled 和 PhishZapEnabled。 在過渡時期，將透過 Cmdlet 提供 3 個參數 (ZapEnabled、PhishZapEnabled 和 SpamZapEnabled)。 直到透過 UI 或 PowerShell 明確設定後，PhishZapEnabled 和 SpamZapEnabled 才會顯示來自 ZapEnabled 參數的繼承值。 一旦設定新參數，就不會再從 ZapEnabled 參數繼承。 在其被取代之後，設定 ZapEnabled 不會對 PhishZapEnabled 或 SpamZapEnabled 屬性造成任何影響，ZapEnabled 將會從 Cmdlet 的參數清單中移除。

ZAP 不會將任何郵件移到正在進行動態傳遞掃描或已經有惡意程式碼裁決 (含已取代的附件) 的隔離區。 如果收到這些郵件類型的網路釣魚或垃圾郵件訊號，且垃圾郵件原則/網路釣魚動作已設定為採取某種動作 (移至垃圾郵件、重新導向、刪除、隔離)，則 ZAP 會預設為「移至垃圾郵件」動作。 若要讓 ZAP 對郵件採取「移至垃圾郵件」動作，使用者必須啟用其垃圾郵件防護，並使用預設垃圾郵件設定。 (如需 Outlook 使用者選項的詳細資料，請參閱[變更垃圾郵件篩選工具中的防護層級](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。)

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否已移動您的郵件

若要判斷 ZAP 是否已移動您的郵件，您可以使用[威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)或[威脅總管 (及即時偵測)](threat-explorer.md)。

## <a name="disable-zap"></a>停用 ZAP

若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

### <a name="disable-malware-zap"></a>停用惡意程式碼 ZAP**

您可以在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的 [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) Cmdlet 上，透過 *ZapEnabled* 參數停用惡意程式碼 ZAP。 在安全性與合規性中心編輯惡意程式碼原則，也可以啟用或停用惡意程式碼 ZAP。

此範例會在名為「Test」的惡意程式碼篩選原則中停用 ZAP。

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

如需詳細的語法及參數資訊，請參閱 [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)。

### <a name="disable-phish-zap-and-spam-zap"></a>停用網路釣魚 ZAP 和垃圾郵件 ZAP

若要停用 O365 租用戶或一組使用者的網路釣魚和垃圾資料 ZAP，請使用 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) (一個 EOP Cmdlet) 的 PhishZapEnabled** 和 SpamZapEnabled** 參數。

在下列範例中，已針對名為「Test」的內容篩選原則停用網路釣魚和垃圾郵件 ZAP。

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)。

## <a name="faq"></a>常見問題集

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>如果合法郵件移至垃圾郵件資料夾，則會發生什麼情況？

您應依照[誤報](../../compliance/prevent-email-from-being-marked-as-spam.md)的正常報告程序進行。 郵件會從 [收件匣] 移至 [垃圾郵件] 資料夾的唯一原因，是因為服務已判定郵件是垃圾郵件或惡意郵件。

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>如果我使用 Office 365 隔離區，而不是垃圾郵件資料夾，該怎麼辦？

ZAP 會根據反垃圾郵件原則中的網路釣魚和垃圾郵件動作設定採取動作。 如需有關惡意程式碼、網路釣魚和垃圾郵件 ZAP 的詳細資訊，請參閱上面內容。

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>如果我有自訂郵件流程規則 (封鎖/允許規則)，該怎麼辦？

由系統管理員 (郵件流程規則) 或封鎖和允許規則建立的規則優先。 這類郵件會從特徵準則中排除，所以郵件流程會遵循規則動作 (封鎖/允許規則)。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>如果郵件移到另一個資料夾 (例如收件匣規則)，該怎麼辦？

除非郵件已遭刪除或位於垃圾郵件中，否則在此情況下，ZAP 仍可運作。

## <a name="related-topics"></a>相關主題

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)

[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件，以避免誤判問題](reduce-spam-email.md)
