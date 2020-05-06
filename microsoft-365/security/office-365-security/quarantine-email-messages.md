---
title: Office 365 中的隔離區
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 本文說明 Microsoft 365 中的隔離。 隔離會包含潛在危險或不需要的郵件。
ms.openlocfilehash: 396be17e07a347ab4d28a3e0b67dd137bda999db
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033863"
---
# <a name="quarantine-email-messages"></a>隔離電子郵件

如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection （EOP）客戶但沒有 Exchange Online 信箱的 Microsoft 365 客戶，則隔離可用於保留潛在危險或有害的郵件。

如果找到*任何*包含惡意程式碼的附件，反惡意程式碼原則就會自動隔離郵件。 如需詳細資訊，請參閱[Configure In Office 365 的反惡意程式碼原則](configure-anti-malware-policies.md)。

根據預設，反垃圾郵件原則會隔離網路釣魚郵件，並將垃圾郵件和大量電子郵件傳送至使用者的 [垃圾郵件] 資料夾。 不過，您也可以建立及自訂反垃圾郵件原則，以隔離垃圾郵件和大量電子郵件。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

使用者和系統管理員都可以處理隔離的郵件：

- 系統管理員可以使用所有類型的隔離郵件來處理所有使用者。 只有系統管理員可以處理被隔離為惡意程式碼、高可信度網路釣魚或郵件流程規則（也稱為傳輸規則）結果的郵件。 如需詳細資訊，請參閱[以 Office 365 系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。

- 如果郵件被隔離為垃圾郵件、大量電子郵件，或（從2020）網路釣魚，使用者可以使用隔離的郵件，而這些郵件是收件者。 如需詳細資訊，請參閱 [以 Office 365 使用者身分尋找並釋出被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。

  若要防止使用者管理其自己的隔離網路釣魚郵件，系統管理員可以針對反垃圾郵件原則中的**網路釣魚電子郵件**篩選判定，設定不同的動作。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

- 系統管理員和使用者可以向隔離中的 Microsoft 報告誤報。

如需有關隔離的詳細資訊，請參閱[隔離常見問題](quarantine-faq.md)。
