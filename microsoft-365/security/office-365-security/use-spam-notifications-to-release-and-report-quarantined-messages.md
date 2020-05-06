---
title: Microsoft 365 中的使用者垃圾郵件通知
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
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解隔離郵件的使用者垃圾郵件通知。
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034995"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>使用使用者垃圾郵件通知來釋放及報告隔離的郵件

在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或不想要的郵件。 如需詳細資訊，請參閱 [Office 365 中的隔離區](quarantine-email-messages.md)。

根據預設，會停用反垃圾郵件原則中的使用者垃圾郵件通知。 當系統管理員[啟用使用者垃圾郵件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)時，收件者會收到有關其郵件（已被隔離為垃圾郵件、大量電子郵件，或（截止到四月，2020）網路釣魚的定期通知。

> [!NOTE]
> 以高可信度網路釣魚、惡意程式碼或郵件流程規則（也稱為傳輸規則）隔離的郵件只適用于系統管理員。 如需詳細資訊，請參閱[以 Office 365 系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。

使用者垃圾郵件通知包含每個隔離郵件的下列資訊：

- **寄件者**：隔離郵件的傳送名稱和電子郵件地址。

- **Subject**：隔離郵件的主旨行文字。

- **日期**：郵件被隔離的日期和時間（UTC）。

- **封鎖寄件者**：按一下此連結可將寄件者新增至您的封鎖寄件者清單。 如需詳細資訊，請參閱[在 Outlook 中封鎖郵件寄件者](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **發行**：針對垃圾郵件（沒有網路釣魚）郵件，您可以在這裡放開郵件，而不需要隔離安全性 & 規範中心。

- **檢查**：按一下此連結，以移至 [安全性 & 規範中心] 中的 [隔離]，您可以在此發行、刪除或報告您的隔離郵件。 如需詳細資訊，請參閱 [以 Office 365 使用者身分尋找並釋出被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。

![最終使用者垃圾郵件通知範例](../../media/end-user-spam-notification.png)
