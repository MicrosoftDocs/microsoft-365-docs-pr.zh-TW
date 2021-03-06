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
description: 透過自訂的署名範本，使用 Office 365 進階郵件加密來設定電子郵件的到期日，以擴充電子郵件的安全性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927783"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>為由 Office 365 進階郵件加密所加密的電子郵件設定到期日

Office 365 進階郵件加密包含[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非盈利性員工定價) 、Office 365 企業版 E5 (非盈利性員工定價) 和 Office 365 教育版 A5。 如果您的組織中有未包括 Office 365 進階郵件加密的訂閱，您可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合規性 SKU 附加元件購買它，Microsoft 365 E3 (非盈利性員工定價) 或 Office 365 進階合規性的 SKU 附加元件，Microsoft 365 E3 Microsoft 365 E3 非盈利性員工定價 (，或) Office 365。

您可以使用郵件到期的電子郵件，讓使用者傳送給使用 OME 入口網站來存取加密電子郵件的外部收件者。 您可以使用 OME 入口網站，透過在 Windows PowerShell 中指定到期日的自訂署名範本，以查看及回復組織所傳送的加密電子郵件。

Office 365 全域系統管理員，當您套用公司品牌以自訂群組織的電子郵件訊息的外觀時，您也可以指定這些電子郵件的到期日期。 透過 Office 365 進階郵件加密，您可以建立多個範本，以用於來自組織的加密電子郵件。 使用範本，您可以控制收件者存取使用者所傳送之郵件的時間長短。

當使用者收到具有到期日設定的郵件時，使用者會看到包裝電子郵件中的到期日。 如果使用者嘗試開啟到期的郵件，則會在 OME 入口網站中顯示錯誤。

您只能將電子郵件的到期日期設定為外部收件者。

使用 Office 365 進階郵件加密時，每當您套用自訂品牌時，Office 365 都會對符合您套用範本之郵件流程規則的電子郵件套用包裝。 此外，如果您使用自訂署名，您只可以使用到期。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>使用 PowerShell 建立自訂品牌範本以強制郵件到期

1. [連線，以](/powershell/exchange/connect-to-exchange-online-powershell)具備組織中全域系統管理員許可權的帳戶來 Exchange Online PowerShell。

2. 執行 New-OMEConfiguration Cmdlet。

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

其中：

- `Identity` 是自訂範本的名稱。

- `ExternalMailExpiryInDays` 識別收件者可以在郵件到期之前保留郵件的天數。 您可以使用1到730天之間的任何值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 進階郵件加密的詳細資訊

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [撤銷由 Office 365 進階郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md)

- [郵件原則及合規性服務說明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)