---
title: 非法回應郵件與 EOP
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
description: 非法回應郵件都會自動的退回的郵件傳送至偽造的電子郵件地址。 非法回應 DNSBL 識別傳送非法回應郵件 （其中可能包含許多合法電子郵件來源） 的伺服器。 因為它不是濫發垃圾郵件者清單中，我們不會嘗試從非法回應 DNSBL 移除自誇。
ms.openlocfilehash: 3dc83c303e861c8762f2276de521e1b550ae2e59
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599730"
---
# <a name="backscatter-messages-and-eop"></a>非法回應郵件與 EOP

*非法回應郵件*是未傳遞回報 （也稱為 Ndr 或退回的郵件） 您會收到未傳送的郵件。 濫發垃圾郵件者冶 （詐騙） [從： 地址，他們的郵件，以及它們通常會使用實際電子郵件地址來強化可信度到他們的郵件。 因此，當他們無可不存在的收件者傳送郵件 （垃圾郵件是在大量作業），在目的地電子郵件伺服器可能盡責回應與 NDR，傳送給在 [從偽造寄件者： 地址。

Exchange Online Protection (EOP) 會盡一切努力來找出並以無訊息方式捨棄可疑的來源訊息而不會產生 NDR。 但是，根據流經服務真正的大量電子郵件，永遠 EOP 會不小心傳送非法回應郵件的可能性。

Backscatterer.org 維護已負責傳送非法回應郵件與 EOP 伺服器的伺服器可能會出現在此清單的電子郵件的封鎖清單 （也就是 DNS 封鎖清單或 DNSBL）。 但是，我們不會嘗試移除自誇從 Backscatterer.org 封鎖清單，因為它不是濫發垃圾郵件者 （依自己的許可） 的清單。

> [!TIP]
> 根據 Backscatter.or 網站 (`http://www.backscatterer.org/?target=usage`)，這些建議使用其服務來檢查在安全的模式，而不是拒絕模式中的內送電子郵件 （大型的電子郵件服務幾乎總是傳送某些非法回應郵件）。
