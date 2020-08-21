---
title: EOP 中的退信攻擊
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: '在本文中，您將瞭解退信攻擊和 Microsoft Exchange Online Protection (EOP) '
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827782"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信攻擊

*退信攻擊* 是未傳遞回報 (也稱為 NDRs 或退回郵件，) 您收到您未傳送的郵件。 垃圾郵件竊取 () 其郵件的寄件者位址，而且經常會使用實際的電子郵件地址來為其郵件的信譽。 因此，垃圾郵件製造者不可避免傳送郵件給非現有的收件者 (垃圾郵件是高容量作業) 時，目的地電子郵件伺服器實質上會欺騙您將 NDR 中無法傳遞的郵件，傳回寄件者： address 中的偽造寄件者。

在使用 Exchange Online 中的信箱或獨立 Exchange Online (Protection 中的 Microsoft 365 組織中，EOP) 不含 Exchange Online 信箱的組織，EOP 會盡一切努力識別 dubious 來源中的郵件，並無任何產生 NDR。 不過，根據整個服務流動大量電子郵件的情況，EOP 會無意間傳送退信攻擊的可能性。

Backscatterer.org 會維護封鎖清單 (也稱為 DNS 封鎖清單或 DNSBL) 的電子郵件伺服器負責傳送退信攻擊，而 EOP 伺服器可能會出現在此清單中。 不過，我們不會嘗試從 Backscatterer.org 封鎖清單中移除自己，因為它不是自己的許可) 所 (的垃圾郵件者清單。

> [!TIP]
> Backscatter.org 網站 (<http://www.backscatterer.org/?target=usage>) 建議使用其服務，以在安全模式中檢查內送電子郵件，而不是以「拒絕」模式， (較大型的電子郵件服務幾乎總會傳送部分退信攻擊) 。
