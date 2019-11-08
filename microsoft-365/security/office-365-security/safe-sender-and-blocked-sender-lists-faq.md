---
title: Exchange Online 中的安全寄件者和封鎖寄件者清單
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
description: 以 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分，您可以協助確保服務透過電子郵件訊息不會標示為垃圾郵件。 若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。
ms.openlocfilehash: 03d0bb35f174b1dcc76fa93f5a5411e8a437ea25
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031778"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online 中的安全寄件者和封鎖寄件者清單

以 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分，您可以協助確保服務透過電子郵件訊息不會標示為垃圾郵件。 若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。 
  
 *請參閱更新的版的秘訣和程序說明如何使用身為系統管理員在這些清單*[防止誤判電子郵件標示為垃圾郵件安全清單或其他技術](https://go.microsoft.com/fwlink/p/?LinkID=534224)。 
  
如果您不是系統管理員，而且您只想要管理自己在 Outlook 中的垃圾郵件所使用的安全寄件者清單，請參閱本概觀[垃圾郵件篩選器](https://go.microsoft.com/fwlink/?LinkId=817222)中的步驟。 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>什麼是安全及封鎖寄件者限制在 Exchange Online 嗎？

Exchange Online 中的安全及封鎖的寄件者限制跟在 Active Directory，以及 Outlook 限制。 其中包括：
  
- 安全寄件者限制： 1024
    
- 封鎖的寄件者限制： 500
    
注意：
  
您可能會遇到錯誤[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述。 若要解決此問題，請清除 「 信任來自我的連絡人的電子郵件 」] 核取方塊。 或者，降低量是預設連絡人] 資料夾中將它顯示在允許的最大限制遵守 1024年個在 Exchange Online 設定為 「 MaxSafeSenders 」 屬性的電子郵件地址。 如需此屬性與 Set-mailbox 指令程式的詳細資訊，請參閱 < 下列主題：
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a>另請參閱

[寄件者篩選在 Exchange 2016](https://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

