---
title: 退信攻擊與 EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解退信攻擊和 Microsoft Exchange Online Protection （EOP）
ms.openlocfilehash: 14460b75920b053461722b5a129d785fb6952a5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035589"
---
# <a name="backscatter-and-eop"></a>退信攻擊與 EOP

*退信攻擊*是您接收到未傳送之郵件的未傳遞回報（也稱為 NDRs 或退回的郵件）。 垃圾郵件傳送者（哄騙）其郵件的寄件者位址，通常會使用實際的電子郵件地址，使其郵件成為信譽。 因此，垃圾郵件製造者不可避免傳送郵件給不存在的收件者（垃圾郵件是高容量作業）時，目的地電子郵件伺服器實質上會欺騙您將 NDR 中無法傳遞的郵件傳回寄件者： address 中的偽造寄件者。

Exchange Online Protection （EOP）會盡一切努力識別 dubious 來源中的郵件，並以無訊息方式丟棄郵件，而不會產生 NDR。 不過，根據整個服務流動大量電子郵件的情況，EOP 會無意間傳送退信攻擊的可能性。

Backscatterer.org 維護負責傳送退信攻擊之電子郵件伺服器的封鎖清單（也稱為 DNS 封鎖清單或 DNSBL），而 EOP 伺服器可能會出現在此清單中。 不過，我們不會嘗試從 Backscatterer.org 封鎖清單中移除自己，因為它不是垃圾郵件傳送者的清單（由其自有的許可）。

> [!TIP]
> Backscatter.org 網站（<http://www.backscatterer.org/?target=usage>）建議使用其服務，以在安全模式中檢查內送電子郵件，而不是拒絕模式（大型電子郵件服務幾乎永遠會傳送某些退信攻擊）。
