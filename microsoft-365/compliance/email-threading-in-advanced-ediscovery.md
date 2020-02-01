---
title: 電子郵件執行緒
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
ms.assetid: ''
description: ''
ms.openlocfilehash: dd155668c8ed91bced7fc7d84764f08ef9799002
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595088"
---
# <a name="email-threading"></a>電子郵件執行緒

請考慮有一段時間移電子郵件交談。 在大多數情況下，在執行緒上的最後一個電子郵件會包含所有上述的電子郵件; 的內容檢閱最後一個電子郵件將會提供執行緒上發生的交談的完整內容。 電子郵件執行緒識別這類電子郵件，以便檢閱者可以檢閱收集文件的分數，而不會遺失任何內容。

## <a name="what-does-email-threading-do"></a>電子郵件執行緒做什麼？

每個電子郵件和 desconstructs 電子郵件執行緒會剖析至個別郵件;每個電子郵件是個別郵件的鏈結之一。 然後，它會分析檢閱設定來決定一封電子郵件是否有獨特的內容，或如果鏈結完全包含在不同的電子郵件中的所有電子郵件。 在結尾的電子郵件會分成四種類別：

- **Inclusive**： 最後一封電子郵件中的具有唯一的內容，且電子郵件的所有其他的內容完全包含此電子郵件中的電子郵件中所含的附件。


- **減 Inclusive**： 最後一封電子郵件中的具有唯一的內容，但電子郵件並不包含一些其他的內容完全包含此電子郵件中的電子郵件中所含的附件。

- **內含的複本**： 完全相同的 [內含/內含減電子郵件複本

- **None**： 這封電子郵件的內容完全包含至少一個電子郵件標示為 [內含/內含減號。

## <a name="how-is-it-different-from-conversations-in-outlook"></a>如何是否不同於 Outlook 中的交談？
一眼這聲音非常類似於 Outlook 中的交談群組。 不過，有一些重要的差別。 請考慮到兩個交談; got 分叉電子郵件交談比方說，有人回應電子郵件不是最新的交談中讓交談中的最後兩個電子郵件兩者都有唯一的內容。

Outlook 會仍組成群組加入單一對話; 電子郵件閱讀的最後一個電子郵件會表示缺少倒數第二個電子郵件，也包含唯一內容的內容。 因為電子郵件執行緒剖析出每封電子郵件到個別元件，並比較它們，電子郵件執行緒會將標記這兩個最後兩個電子郵件為 inclusives，確保，您就不會遺漏任何內容，只要讀取所有的電子郵件標示為 （含）。