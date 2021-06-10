---
title: 支援驗證 (DKIM) 簽署的郵件中識別的網域金鑰
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: 瞭解 Exchange Online Protection 和 Exchange Online 中 DKIM 已簽署郵件的驗證
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204628"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支援 DKIM 簽署郵件的驗證

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) 和 Exchange Online 都支援的功能變數名稱驗證識別郵件 ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件。

DKIM 可驗證電子郵件訊息未被其他人 *欺騙* ，而且已 *從該郵件* 所發來的網域傳送。 它會將電子郵件訊息與傳送電子郵件的組織緊密。 DKIM 驗證會自動用於所有使用 IPv6 所傳送的郵件。 當郵件透過 IPv4 傳送時，Microsoft 365 也會支援 DKIM。  (如需有關 IPv6 支援的詳細資訊，請參閱 [支援透過 IPv6 匿名輸入電子郵件訊息](support-for-anonymous-inbound-email-messages-over-ipv6.md)。 ) 

DKIM 會驗證郵件頭的 DKIM-Signature 標頭中顯示的數位簽署郵件。 DKIM-Signature 驗證的結果會加蓋 Authentication-Results 標頭。 顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> 如需 Authentication-Results 標頭的詳細資訊，請參閱 RFC 7001 ([Message Header 欄位，表示郵件驗證狀態](https://www.rfc-editor.org/rfc/rfc7001.txt)。 Microsoft 的 DKIM 實施會與此 RFC 相符。

系統管理員可以在 DKIM 驗證的結果上，建立 Exchange[郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也稱為 transport rules) 。 這些郵件流程規則可讓系統管理員視需要篩選或路由傳送郵件。