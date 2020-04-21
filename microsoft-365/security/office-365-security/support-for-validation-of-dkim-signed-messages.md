---
title: 支援 DKIM 簽署郵件的驗證
f1.keywords:
- NOCSH
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
description: 深入瞭解 Exchange Online Protection 和 Exchange Online 中的 DKIM 已簽署郵件的驗證
ms.openlocfilehash: 1abe517ed7922b60abb3a78436ed61b4d0b3ed55
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631202"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支援 DKIM 簽署郵件的驗證

Exchange Online Protection （EOP）和 Exchange Online 支援網域機碼的輸入驗證，識別出郵件（[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)）郵件。 DKIM 是一種方法，用來驗證郵件是由其來源的網域所傳送，且沒有其他人冒充。 它會將電子郵件訊息與負責傳送電子郵件的組織緊密聯繫。 DKIM 驗證會自動用於透過 IPv6 通訊傳送的所有郵件。 在 IPv4 傳送郵件時，Microsoft 365 現在也會支援 DKIM。 （如需 IPv6 支援的詳細資訊，請參閱[在 IPv6 中支援匿名輸入電子郵件訊息](support-for-anonymous-inbound-email-messages-over-ipv6.md)。）

DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

系統管理員可以在 DKIM 驗證的結果上建立 Exchange[郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)（也稱為傳輸規則），以視需要篩選或路由傳送郵件。
