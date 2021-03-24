---
title: 隔離的電子郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 中包含可能危險或有害郵件的隔離。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060063"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP 中隔離的電子郵件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，隔離可用於存放可能危險或不需要的郵件。

如果找到 *任何* 包含惡意程式碼的附件，反惡意程式碼原則就會自動隔離郵件。 如需詳細資訊，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

根據預設，反垃圾郵件原則會隔離網路釣魚郵件，並將垃圾郵件和大量電子郵件傳送至使用者的 [垃圾郵件] 資料夾。 不過，您也可以建立及自訂反垃圾郵件原則，以隔離垃圾郵件和大量電子郵件。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

使用者和系統管理員都可以處理隔離的郵件：

- 系統管理員可以使用所有類型的隔離郵件來處理所有使用者。 只有系統管理員可以處理被隔離為惡意程式碼、高可信度網路釣魚的郵件，或郵件流程規則的結果 (也稱為傳輸規則) 。 如需詳細資訊，請參閱[在 EOP 中管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。

- 如果郵件被隔離為垃圾郵件、大量電子郵件， (或在 2020) 網路釣魚時，使用者可以使用被隔離的郵件，而這些郵件是收件者。 如需詳細資訊，請參閱 [在 EOP 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。

  若要防止使用者管理其自己的隔離網路釣魚郵件，系統管理員可以針對反垃圾郵件原則中的 **網路釣魚電子郵件** 篩選判定，設定不同的動作。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

- 系統管理員和使用者可以向隔離中的 Microsoft 報告誤報。

如需有關隔離的詳細資訊，請參閱 [隔離常見問題](quarantine-faq.md)。
