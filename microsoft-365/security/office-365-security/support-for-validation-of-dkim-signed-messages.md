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
description: 深入瞭解 Exchange Online Protection 和 Exchange Online 中的 DKIM 已簽署郵件的驗證
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 111bf169d60e386dc48ef086bbe631b8760201a6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916523"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支援 DKIM 簽署郵件的驗證

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) 和 Exchange Online 都支援功能變數名稱驗證，識別出郵件 ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件。

DKIM 可驗證電子郵件訊息未被其他人 *欺騙* ，而且已 *從該郵件* 所發來的網域傳送。 它會將電子郵件訊息與傳送電子郵件的組織緊密。 DKIM 驗證會自動用於所有使用 IPv6 所傳送的郵件。 當郵件透過 IPv4 傳送時，Microsoft 365 也會支援 DKIM。  (如需有關 IPv6 支援的詳細資訊，請參閱 [支援透過 IPv6 匿名輸入電子郵件訊息](support-for-anonymous-inbound-email-messages-over-ipv6.md)。 ) 

DKIM 會驗證郵件頭的 DKIM-Signature 標頭中顯示的數位簽署郵件。 DKIM-Signature 驗證的結果會加蓋 Authentication-Results 標頭。 顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> 如需 Authentication-Results 標頭的詳細資訊，請參閱 RFC 7001 ([Message Header 欄位，表示郵件驗證狀態](https://www.rfc-editor.org/rfc/rfc7001.txt)。 Microsoft 的 DKIM 實施會與此 RFC 相符。

系統管理員可以在 DKIM 驗證的結果上，建立 Exchange [郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也稱為傳輸規則) 。 這些郵件流程規則可讓系統管理員視需要篩選或路由傳送郵件。