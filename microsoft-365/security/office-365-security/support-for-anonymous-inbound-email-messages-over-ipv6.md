---
title: 新增對 IPv6 匿名輸入電子郵件的支援
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Exchange Online 和 Exchange Online Protection 的 IPv6 來源中設定匿名輸入電子郵件的支援。
ms.openlocfilehash: 414c10f3387138ed7e62f2de4e8549e45d128d2e
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131516"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>在 Office 365 中新增對 IPv6 匿名輸入電子郵件的支援

Office 365 組織若有 Exchange Online 信箱和獨立 Exchange Online Protection （EOP）組織，但沒有 Exchange Online 信箱的電子郵件支援透過 IPv6 的匿名輸入電子郵件。 來源 IPv6 電子郵件伺服器必須符合下列兩項需求：

- 來源 IPv6 位址必須具有有效的反向 DNS 查詢（PTR）記錄，允許目的地從 IPv6 位址中尋找功能變數名稱。

- 寄件者必須通過 SPF 驗證 (定義於 [RFC 7208](https://tools.ietf.org/html/rfc7208)) 或 [DKIM 驗證](https://dkim.org/) (定義於 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt))。

在您的組織可以透過 IPv6 接收匿名的輸入電子郵件之前，系統管理員必須先聯繫 Microsoft 支援人員，並要求。 如需如何開啟支援要求的指示，請參閱[聯繫支援人員以取得商務產品-系統管理](../../admin/contact-support-for-business-products.md)說明。

在您的組織中啟用匿名輸入 IPv6 郵件支援之後，郵件會透過服務提供的一般郵件篩選功能。

## <a name="troubleshooting"></a>疑難排解

- 如果來源電子郵件伺服器沒有 IPv6 反向 DNS 查閱記錄，郵件將會因下列錯誤而拒絕：

  > 450 4.7.25 服務無法使用，傳送 IPv6 位址 [2a01：111： f200：2004：： 240] 必須具有反向 DNS 記錄。

- 如果寄件者未通過 SPF 或 DKIM 驗證，郵件將會因下列錯誤而拒絕：

  > 450 4.7.26 服務無法使用。傳送的郵件 IPv6 [2a01：111： f200：2004：： 240] 必須通過 SPF 或 DKIM 驗證。

- 如果您在加入宣告之前嘗試接收匿名 IPv6 郵件，郵件將會因下列錯誤而拒絕：

  > 550 5.2.1 服務無法使用，[contoso.com] 不接受透過 IPv6 的電子郵件。

## <a name="for-more-information"></a>如需詳細資訊

[支援 DKIM 簽署郵件的驗證](support-for-validation-of-dkim-signed-messages.md)
