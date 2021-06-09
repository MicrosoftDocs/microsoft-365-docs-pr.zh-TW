---
title: Advanced eDiscovery 中的電子郵件執行緒
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 進行 Advanced eDiscovery 分析時，電子郵件執行緒會分析電子郵件交談，並將每封郵件分隔成不同的類別。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285559"
---
# <a name="email-threading-in-advanced-ediscovery"></a>Advanced eDiscovery 中的電子郵件執行緒

請考慮已有一段時間的電子郵件交談。 在大多數情況下，線索上的最後一封電子郵件會包含上述所有電子郵件的內容;檢查最後一個電子郵件將會提供執行緒中發生之談話的完整內容。 電子郵件執行緒識別這類電子郵件，讓檢閱者可以在不遺失任何內容的情況下，審閱收集的檔數。

## <a name="what-does-email-threading-do"></a>電子郵件執行緒的功能為何？

電子郵件串接會分析每封電子郵件，並將它 deconstructs 至個別郵件;每封電子郵件都是個別郵件的鏈。 然後，它會分析審閱集中的所有電子郵件，以判斷電子郵件是否有獨特的內容，或此鏈是否完全包含在不同的電子郵件中。 在結束電子郵件中分為四個類別：

- **包含項**：此電子郵件中的最後一則訊息具有唯一的內容，且此電子郵件有其他電子郵件 (這些電子郵件的內容完全包含在此電子郵件中) 所含的所有附件。

- **已移除附件的包含項**：此電子郵件中的最後一則訊息具有唯一的內容，但此電子郵件未包含其他電子郵件 (這些電子郵件的內容完全包含在此電子郵件中) 所含的某些附件。

- **包含項複本**：包含項/已移除附件的包含項電子郵件的完全相同複本

- **無**：此電子郵件的內容完全包含在至少一封標示為包含項/已移除附件的包含項的電子郵件中。

## <a name="how-is-it-different-from-conversations-in-outlook"></a>它與 Outlook 中的交談有何不同？

這聽起來像是 Outlook 中的交談群組。 不過，有一些重要的區別。 請考慮可分為兩個交談的電子郵件交談;例如，某人回應的電子郵件並不是最新的交談，所以交談中的最後兩封電子郵件都有唯一的內容。

Outlook 仍會將電子郵件組合成單一交談;只閱讀最後一個電子郵件會丟失第二對最後一個電子郵件的內容，也就是包含唯一的內容。 因為電子郵件執行緒會將每封電子郵件剖析為個別元件，並加以比較，所以電子郵件執行緒會將最後兩封電子郵件都標示為包含在內，以確保您閱讀所有標記為包含的電子郵件時，不會漏掉任何內容。
