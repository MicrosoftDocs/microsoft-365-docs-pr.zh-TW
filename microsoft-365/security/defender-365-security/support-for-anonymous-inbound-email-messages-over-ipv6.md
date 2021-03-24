---
title: 新增透過 IPv6 支援匿名輸入電子郵件
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在 Exchange Online 和 Exchange Online Protection 的 IPv6 來源中設定匿名輸入電子郵件的支援。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df06891401802d212cbfdb55085662901f5546e9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057216"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>在 Microsoft 365 中新增對 IPv6 匿名輸入電子郵件的支援

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 組織使用 Exchange Online 信箱和獨立 Exchange Online Protection (EOP) 沒有 Exchange Online 信箱的組織都支援透過 IPv6 的匿名輸入電子郵件。 來源 IPv6 電子郵件伺服器必須符合下列兩項需求：

- 來源 IPv6 位址必須具有有效的反向 DNS 查閱 (PTR) 記錄，允許目的地從 IPv6 位址尋找功能變數名稱。

- 寄件者必須通過 SPF 驗證 (定義於 [RFC 7208](https://tools.ietf.org/html/rfc7208)) 或 [DKIM 驗證](http://dkim.org/) (定義於 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt))。

在您的組織可以透過 IPv6 接收匿名的輸入電子郵件之前，系統管理員必須先聯繫 Microsoft 支援人員，並要求。 如需如何開啟支援要求的指示，請參閱 [聯繫支援人員以取得商務產品-系統管理](../../admin/contact-support-for-business-products.md)說明。

在您的組織中啟用匿名輸入 IPv6 郵件支援之後，郵件會透過服務提供的一般郵件篩選功能。

## <a name="troubleshooting"></a>疑難排解

- 如果來源電子郵件伺服器沒有 IPv6 反向 DNS 查閱記錄，郵件將會因下列錯誤而拒絕：

  > 450 4.7.25 服務無法使用，傳送 IPv6 位址 [2a01：111： f200：2004：： 240] 必須具有反向 DNS 記錄。

- 如果寄件者未通過 SPF 或 DKIM 驗證，郵件將會因下列錯誤而拒絕：

  > 450 4.7.26 服務無法使用。傳送的郵件 IPv6 [2a01：111： f200：2004：： 240] 必須通過 SPF 或 DKIM 驗證。

- 如果您在加入宣告之前嘗試接收匿名 IPv6 郵件，郵件將會因下列錯誤而拒絕：

  > 550 5.2.1 服務無法使用，[contoso.com] 不接受透過 IPv6 的電子郵件。

## <a name="related-topics"></a>相關主題

[支援 DKIM 簽署郵件的驗證](support-for-validation-of-dkim-signed-messages.md)
