---
title: 非法回應郵件與 EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: 非法回應郵件所傳送的郵件伺服器，通常是因為傳入的垃圾郵件自動的退回的郵件。 非法回應 DNSBL 是一份傳送非法回應郵件的 IP 位址清單。 它不是濫發垃圾郵件者清單，我們不會嘗試從非法回應 DNSBL 移除我們的伺服器。
ms.openlocfilehash: e8a8f98045d111976078b09797a1078d0fbb6a6b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077274"
---
# <a name="backscatter-messages-and-eop"></a>非法回應郵件與 EOP

非法回應郵件所傳送的郵件伺服器，通常是因為傳入的垃圾郵件自動的退回的郵件。 因為 Exchange Online Protection (EOP) 是垃圾郵件篩選服務，我們的服務會拒絕傳送至不存在收件者及其他可疑目的地的電子郵件。 發生此情況時，EOP 產生未傳遞回報 (NDR) 郵件並傳回給「寄件者」。 因為濫發垃圾郵件者經常在郵件中利用偽造或無效的「寄件者」地址，NDR 所寄到的寄件者地址可能會導致非法回應郵件。 發生此情況時，與 EOP 網路相關聯的外寄伺服器可能會列在非法回應 DNS 封鎖清單 (DNSBL) 中。 非法回應 DNSBL 是一份傳送非法回應郵件的 IP 位址清單。 它不是濫發垃圾郵件者清單，我們不會嘗試從非法回應 DNSBL 移除我們的伺服器。 
  
> [!TIP]
> 根據 Backscatterer 網站的指示，該服務的設定或用法不建議對所有傳入的郵件使用拒絕模式。而是應該在安全模式中使用。如需實作正確非法回應設定的相關資訊，請造訪 [Backscatterer.org 網站](http://www.backscatterer.org/?target=usage)。 
  
## <a name="related-topics"></a>相關主題
  
[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)
  

