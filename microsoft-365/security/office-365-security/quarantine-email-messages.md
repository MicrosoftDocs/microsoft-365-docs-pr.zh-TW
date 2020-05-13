---
title: 隔離的電子郵件
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
description: 系統管理員可以深入瞭解 Exchange Online Protection （EOP）中存放潛在危險或有害郵件的隔離。
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208279"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP 中隔離的電子郵件

在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，隔離可用於保留潛在危險或不需要的郵件。

如果找到*任何*包含惡意程式碼的附件，反惡意程式碼原則就會自動隔離郵件。 如需詳細資訊，請參閱[在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

根據預設，反垃圾郵件原則會隔離網路釣魚郵件，並將垃圾郵件和大量電子郵件傳送至使用者的 [垃圾郵件] 資料夾。 不過，您也可以建立及自訂反垃圾郵件原則，以隔離垃圾郵件和大量電子郵件。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

使用者和系統管理員都可以處理隔離的郵件：

- 系統管理員可以使用所有類型的隔離郵件來處理所有使用者。 只有系統管理員可以處理被隔離為惡意程式碼、高可信度網路釣魚或郵件流程規則（也稱為傳輸規則）結果的郵件。 如需詳細資訊，請參閱[在 EOP 中以系統管理員身分管理隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。

- 當郵件被隔離為垃圾郵件、大量電子郵件，或（從2020年4月）網路釣魚時，使用者就可以像是收件者的收件者那樣使用隔離的郵件。 如需詳細資訊，請參閱[在 EOP 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。

  若要防止使用者管理其自己的隔離網路釣魚郵件，系統管理員可以針對反垃圾郵件原則中的**網路釣魚電子郵件**篩選判定，設定不同的動作。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

- 系統管理員和使用者可以向隔離中的 Microsoft 報告誤報。

如需有關隔離的詳細資訊，請參閱[隔離常見問題](quarantine-faq.md)。
