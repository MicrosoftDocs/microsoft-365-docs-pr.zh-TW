---
title: 步驟 6：設定電子郵件加密
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解及設定 Office 365 的特殊權限存取管理。
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067176"
---
# <a name="step-6-configure-email-encryption"></a>步驟 6：設定電子郵件加密

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

有三種類型的 Microsoft 365 中的電子郵件加密。

|||
|:-------|:-----|
| Office 郵件加密 (OME) | Exchange Online 傳送組織外部的電子郵件加密。 |
| 資訊版權管理 (IRM) | 加密和權限會對電子郵件。 |
| Secure/Multipurpose Internet Mail Extensions (S/MIME) | 加密及數位簽章的電子郵件保護。 |
|||

## <a name="office-365-message-encryption"></a>Office 365 郵件加密

OME，與您的組織可以傳送和接收您組織內部和外部的人員之間的加密的電子郵件訊息。 OME 適用於 Outlook.com、 yahoo ！、 Gmail，以及其他電子郵件服務。 電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件。

![OME 加密的電子郵件](../media/infoprotect-email-encryption/ome-encryption.png)

您設定定義加密條件的傳輸規則。 當使用者傳送的郵件符合某規則時，會自動套用加密。

若要檢視加密的郵件，收件者可以取得一次性密碼，登入 Microsoft 帳戶或登入公司或學校帳戶與 Microsoft 365 相關聯。 收件者也可以傳送加密的回覆。 則不需要自己 Microsoft 365 訂用帳戶檢視加密的郵件，或傳送加密的回覆。

如需詳細資訊，請參閱〈[Office 365 郵件加密](https://docs.microsoft.com/Office365/SecurityCompliance/ome)〉。

## <a name="irm"></a>IRM

Microsoft 365 中的 IRM 可協助您保護您的資訊與其他加密，並藉由套用智慧型原則，指定誰具有存取他們可以執行的動作。 電子郵件訊息，您可以使用 IRM 進行加密，並將流量限制套用。 例如，您可以指定某些收件者有管理電子郵件的所有功能，而且某些不都具有列印或轉寄電子郵件的能力。 

IRM 原則設定 Microsoft 365 內，且可以套用至文件中的 SharePoint Online 和電子郵件訊息。 受 IRM 保護的電子郵件包含套用的原則設定套用和跟隨它。 

![IRM 保護的電子郵件](../media/infoprotect-email-encryption/irm-protection.png)

當收件者開啟電子郵件與包含的原則時，可用來將郵件解密，並判斷收件者可以如何使用它的原則設定。 

如需詳細資訊，請參閱〈[Exchange Online 中的資訊版權管理]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online)〉。

## <a name="smime"></a>S/MIME

S/MIME 是一種數位憑證型電子郵件型保護解決方案，可讓您同時加密，並以數位方式簽署郵件時。 郵件加密有助於確保只有預定的收件者可以開啟並閱讀郵件。 數位簽章可協助收件者驗證寄件者的身分識別，並判斷該寄件者無法傳送它。

![S/MIME 的電子郵件保護](../media/infoprotect-email-encryption/smime-protection.png)

S/MIME 可用於電子郵件至您的 Microsoft 365 訂閱中的其他信箱或外部的使用者。
郵件加密及數位簽章之所以可行，透過包含公用和私人索引鍵加密或解密訊息，以及建立和驗證數位簽章的數位憑證。
若要使用 S/MIME，您必須擁有公開金鑰每個收件者。 收件者維護自己私用的機碼，必須保持安全。 如果危害您的私密金鑰，您需要取得新的數位憑證，並重新分散到所有可能的寄件者的公開金鑰。

如需詳細資訊，請參閱[為郵件簽章和加密的 S/MIME](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)。


作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step6)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 7](../media/stepnumbers/Step7.png)|[設定 Office 365 的特殊權限存取管理](infoprotect-configure-privileged-access-management.md)|
