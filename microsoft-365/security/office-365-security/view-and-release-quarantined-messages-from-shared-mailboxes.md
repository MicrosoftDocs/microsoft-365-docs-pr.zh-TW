---
title: 從共用信箱中查看和釋出隔離的郵件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 使用者可以瞭解如何查看並處理已送往他們有權共用信箱的隔離郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3efccca375745b0850c91039165b72a7d6f0bcb3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931443"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>從共用信箱中查看和釋出隔離的郵件

> [!NOTE]
> 本文所述的功能目前為預覽版，並不提供所有人使用，且可能會有所變更。

使用者可以管理隔離的郵件，其中它們是其中一個收件者，如 [EOP](find-and-release-quarantined-messages-as-a-user.md)中的使用者一樣尋找和釋出隔離的郵件。 但是，如果使用者擁有信箱的完全存取和傳送為或代理傳送者許可權，那麼共用信箱呢？這如 [Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)中的共用信箱所述？

之前，若要讓使用者管理送往共用信箱的隔離郵件，系統管理員必須讓共用信箱的自動對數保持啟用 (當系統管理員將另一個信箱的存取權授予使用者時，系統預設會啟用此) 。 不過，根據使用者能夠存取的信箱大小和數量，Outlook 嘗試開啟使用者具有存取權的所有信箱時，可能會影響效果。  因此，許多系統管理員選擇移除共用信箱 [的自動對數](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。

現在，使用者不再需要自動對數來管理已送往共用信箱的隔離郵件。 這樣才有效。 有兩種不同的方法可以存取已送往共用信箱的隔離郵件：

- 如果系統管理員已啟用反[](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies)垃圾郵件策略中的使用者垃圾郵件通知，任何能夠存取共用信箱中使用者垃圾郵件通知的使用者，都可以按一下通知中的 [檢閱> 按鈕，在安全性&合規性中心隔離。 請注意，這個方法只能讓使用者管理已隔離並寄到共用信箱的郵件。 使用者在此情境中無法管理自己的隔離郵件。

- 使用者可以前往 [安全性與合規性中心的隔離&隔離](find-and-release-quarantined-messages-as-a-user.md)。 根據預設，只會顯示已給使用者的郵件。 不過，使用者可以變更 [郵件識別碼 (預設為) 收件者電子郵件地址、輸入共用信箱電子郵件地址，然後按一下 [重新整理， 查看已隔離的郵件已送到共用信箱中。

  ![按照收件者電子郵件地址排序隔離的郵件。](../../media/quarantine-sort-results-by-recipient-email-address.png)

不論使用哪種方法，使用者都可以在隔離郵件中包含收件者 **欄以避免混淆** 。 要顯示的欄數上限為 7，因此使用者必須按一下 [修改欄、移除現有的欄 (例如，[政策類型) ;選取收件者，然後按一下 [儲存或儲存為預設值。  

  ![移除政策類型欄，並新增要隔離的收件者欄。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>必須記住的事項

- 第一個針對隔離郵件採取行動的使用者，會決定該郵件的接收物件是使用共用信箱的每個人。 例如，如果有 10 個使用者存取共用信箱，而使用者決定刪除隔離郵件，這 10 個使用者將會刪除該郵件。 同樣地，如果使用者決定釋出郵件，該郵件會釋出至共用信箱，且共用信箱的其他使用者都可以進行共用。

- 目前 **，針對已** 送往共用信箱的隔離郵件，在詳細資料飛出區中無法使用封鎖寄件者按鈕。

- 若要在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中管理共用信箱的隔離郵件，使用者需要以共用信箱電子郵件地址使用 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) Cmdlet 做為 _RecipientAddress_ 參數的值來識別郵件。 例如：

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  然後，使用者可以從清單中選取隔離郵件來查看或採取動作。

  此範例顯示所有已送往共用信箱的隔離郵件，然後從隔離中釋出列表中的第一封郵件 (清單中的第一封郵件是 0，第二封郵件是 1，以) 此類比。

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  如需詳細的語法及參數資訊，請參閱下列主題：

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
