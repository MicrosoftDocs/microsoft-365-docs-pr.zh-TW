---
title: Microsoft 365 中的使用者垃圾郵件通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以在 Exchange Online Protection (EOP) 中瞭解隔離郵件的使用者垃圾郵件通知。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203708"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>使用使用者垃圾郵件通知來釋放及報告隔離的郵件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或垃圾郵件。 如需詳細資訊，請參閱 [EOP 中的隔離郵件](quarantine-email-messages.md)。

根據預設，會停用反垃圾郵件原則中的使用者垃圾郵件通知。 當系統管理員 [啟用使用者垃圾郵件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)時，收件者 (（包含啟用自動對應的共用信箱）) 會收到有關其郵件（已被隔離為垃圾郵件、大量電子郵件，或 (至 2020) 網路釣魚）的定期通知。

在共用信箱中，只有獲授與共享信箱 FullAccess 許可權的使用者才支援使用者垃圾郵件通知。 如需詳細資訊，請參閱 [Use THE EAC to edit shared 信箱委派](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。

群組不支援使用者垃圾郵件通知。

> [!NOTE]
> 以高可信度網路釣魚、惡意程式碼或郵件流程規則隔離的郵件 (也稱為傳輸規則) 僅供系統管理員使用。 如需詳細資訊，請參閱[在 EOP 中管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。

使用者垃圾郵件通知包含每個隔離郵件的下列資訊：

- **寄件者**：隔離郵件的傳送名稱和電子郵件地址。

- **Subject**：隔離郵件的主旨行文字。

- **日期**： UTC 中 (隔離郵件的日期和時間) 。

- **封鎖寄件者**：按一下此連結可將寄件者新增至您的封鎖寄件者清單。 如需詳細資訊，請參閱 [封鎖郵件寄件者](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **發行**：針對垃圾郵件 (不會) 郵件網路釣魚，您可以在這裡放開郵件，而不需要隔離安全性 & 規範中心。

- **檢查**：按一下此連結可移至 [安全性 & 規範中心] 中的 [隔離]，您 (可以根據郵件隔離的原因，按一下此連結) view、release、delete 或 report 您的隔離郵件。 如需詳細資訊，請參閱 [在 EOP 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。

![最終使用者垃圾郵件通知範例](../../media/end-user-spam-notification.png)

> [!NOTE]
> 封鎖的寄件者仍可傳送您的郵件。 此寄件者傳送給您信箱的任何郵件都會立即移至 [垃圾郵件] 資料夾。 來自此寄件者的未來郵件會移至您的 [垃圾郵件] 資料夾或使用者隔離區。 如果您想要在到達時刪除郵件，而不是隔離這些郵件，請使用 [郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也稱為 transport rules) 以在到達時刪除郵件。