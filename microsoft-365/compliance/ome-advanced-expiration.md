---
title: 為由 Office 365 進階郵件加密所加密的電子郵件設定到期日
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 使用 office 365 的高級郵件加密功能在 Office 365 郵件加密（OME）的上方，您可以透過自訂的署名範本來設定電子郵件的到期日，以擴充電子郵件的安全性。
ms.openlocfilehash: c9b639c016e86c3883191b04d4c7480625745e91
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626901"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>為由 Office 365 進階郵件加密所加密的電子郵件設定到期日

Office 365 Advanced Message Encryption 包含在[Microsoft 365 企業版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 （非盈利性人員定價）、Office 365 企業版 E5 （非盈利性員工定價）和 Office 365 教育版 A5 中。 如果您的組織中有未包含 Office 365 Advanced Message Encryption 的訂閱，您可以使用 microsoft 365 E5 相容性 SKU 附加元件（適用于 microsoft 365 E3）購買它、Microsoft 365 E3 （非盈利性員工定價），或 Microsoft 365 E3、Microsoft 365 E3 （非盈利性員工定價）或 Office SKUs 的 Office 365 高級規範 SKU 附加元件。

您可以使用郵件到期的電子郵件，讓使用者傳送給使用 OME 入口網站來存取加密電子郵件的外部收件者。 您可以使用 OME 入口網站，透過在 Windows Powershell 中指定到期日的自訂署名範本，以查看及回復組織所傳送的加密電子郵件。

作為 O365 全域管理員，當您套用公司品牌以自訂群組織的電子郵件訊息的外觀時，您也可以指定這些電子郵件的到期日期。 使用 Office 365 Advanced Message Encryption，您可以建立多個範本，以用於來自組織的加密電子郵件。 使用範本，您可以控制收件者存取使用者所傳送之郵件的時間長短。

當使用者收到具有到期日設定的郵件時，使用者會看到包裝電子郵件中的到期日。 如果使用者嘗試開啟到期的郵件，則會在 OME 入口網站中顯示錯誤。

您只能將電子郵件的到期日期設定為外部收件者。

使用 Office 365 Advanced Message Encryption 時，無論您何時套用自訂品牌，Office 365 都會對符合郵件流程規則的電子郵件套用您要套用範本的包裝。 此外，如果您使用自訂署名，您只可以使用到期。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>使用 PowerShell 建立自訂品牌範本以強制郵件到期

1. 使用具備組織中全域系統管理員許可權的帳戶，連線[至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 執行 Set-omeconfiguration Cmdlet。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

其中：

- `Identity`是自訂範本的名稱。

- `ExternalMailExpiryInDays`識別收件者可以在郵件到期之前保留郵件的天數。 您可以使用1到730天之間的任何值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有關 Office 365 Advanced Message Encryption 的詳細資訊

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [撤銷由 Office 365 進階郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md)

- [郵件原則及合規性服務說明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
