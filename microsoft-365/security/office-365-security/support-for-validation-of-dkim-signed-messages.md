---
title: 支援 DKIM 簽署郵件的驗證
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: 了解的驗證的 DKIM 簽署郵件在 Exchange Online Protection 和 Exchange Online
ms.openlocfilehash: bb02e558c7aaf07a7b13ec0bdb237a9ab84220f4
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871229"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支援 DKIM 簽署郵件的驗證

Exchange Online Protection (EOP) 和 Exchange Online 支援輸入的驗證的網域金鑰 Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件。 DKIM 會驗證郵件已傳送從它說來自網域並不詐騙由其他人的方法。 它會繫結負責將它傳送的組織將電子郵件訊息。 透過 IPv6 通訊傳送的所有郵件，會自動使用 DKIM 驗證。 Office 365 現在還可以支援 DKIM，透過 IPv4 傳送郵件時。 （如需 IPv6 支援的詳細資訊，請參閱[支援透過 IPv6 的匿名輸入的電子郵件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。）

DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

系統管理員可以建立 Exchange[郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)（也稱為傳輸規則） 來篩選在 DKIM 驗證結果上，或將郵件路由傳送做為所需。
