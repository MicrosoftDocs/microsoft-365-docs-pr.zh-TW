---
title: 支援透過 IPv6 的匿名輸入電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: 了解如何設定 Exchange Online Protection 和 Exchange Online 來源 IPv6 的匿名郵件的支援。
ms.openlocfilehash: c29c1fa450ca2a2e213930c4f4a394aaf462e31d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031988"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>支援透過 IPv6 的匿名輸入電子郵件

Exchange Online Protection (EOP) 和 Exchange Online 均可支援透過 IPv6 通訊接收來自未透過傳輸層安全性 (TLS) 傳送郵件之寄件者的匿名輸入電子郵件。 您可以選擇集來向 Microsoft 支援服務要求這項功能，藉由開啟 Microsoft 365 系統管理中心，透過 IPv6 接收訊息[https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)、 [**支援**，，然後按一下 [**新增服務要求**)。 如果您未選擇加入 IPv6，則會繼續透過 IPv4 接收郵件。
  
透過 IPv6 將郵件傳輸至服務的寄件者必須符合下列兩項需求：
  
1. 傳送 IPv6 地址必須具備有效的 PTR 記錄 (傳送 IPv6 地址的 [反向 DNS 記錄](https://en.wikipedia.org/wiki/Reverse_DNS_lookup))。 
    
2. 寄件者必須通過 SPF 驗證 (定義於 [RFC 7208](https://tools.ietf.org/html/rfc7208)) 或 [DKIM 驗證](https://dkim.org/) (定義於 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt))。
    
選擇加入 IPv6 之前，不論您的組態為何，符合這些需求都是必要的。 若已符合這兩項需求，郵件就會通過經歷此服務所提供的正常電子郵件篩選。 如果一或其他不符合，郵件會遭到拒絕以其中一個下列 450 回應：
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
如果您未選擇透過 IPv6 接收郵件，而寄件者藉由手動連線到郵件伺服器以試圖強制透過 IPv6 傳送郵件，則此郵件會遭到拒絕並出現類似下面的 550 回應：
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>相關資訊

[支援 DKIM 簽署郵件的驗證](support-for-validation-of-dkim-signed-messages.md)
  

