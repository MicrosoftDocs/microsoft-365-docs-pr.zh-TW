---
title: Exchange Online 中的安全寄件者和封鎖寄件者清單
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: 如果您是 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員，您可以協助確保透過服務傳送的電子郵件訊息不會被標示為垃圾郵件。 若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598510"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online 中的安全寄件者和封鎖寄件者清單

如果您是 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員，您可以協助確保透過服務傳送的電子郵件訊息不會被標示為垃圾郵件。 若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。

*請參閱更新的版的秘訣和程序說明如何使用這些清單中的系統管理員*[如何防止良好的電子郵件被標示為在 Office 365 中的垃圾郵件](prevent-email-from-being-marked-as-spam.md)。

如果您不是系統管理員，而且您只想要管理自己在 Outlook 中的垃圾郵件所使用的安全寄件者清單，請參閱[垃圾郵件篩選器概觀](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)中的步驟。

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>什麼是安全及封鎖寄件者限制在 Exchange Online 嗎？

Exchange Online 中的安全及封鎖的寄件者限制跟在 Active Directory，以及 Outlook 限制。 其中包括：

- 安全寄件者限制： 1024

- 封鎖的寄件者限制： 500

注意：

您可能會遇到錯誤[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述。 若要解決此問題，請清除 「 信任來自我的連絡人的電子郵件 」] 核取方塊。 或者，降低量是預設連絡人] 資料夾中將它顯示在允許的最大限制遵守 1024年個在 Exchange Online 設定為 「 MaxSafeSenders 」 屬性的電子郵件地址。 如需此屬性與 Set-mailbox 指令程式的詳細資訊，請參閱 < 下列主題：

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>請參閱

[寄件者篩選在 Exchange 伺服器](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
