---
title: 為由 Office 365 進階郵件加密所加密的電子郵件設定到期日
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 與 Office 365 進階郵件加密功能掌握 Office 365 郵件加密 (OME)，您可以擴充您的電子郵件安全性設定的自訂品牌範本透過電子郵件到期日。
ms.openlocfilehash: 7c4ad1fb4a91bd62569edc5db9042dfbd2dbd9fe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077847"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>為由 Office 365 進階郵件加密所加密的電子郵件設定到期日

掌握 Office 365 郵件加密在特定的訂閱中使用 office 365 進階郵件加密。 進階的郵件加密包含在[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 企業版 E5 和 Office 365 教育版 A5 中。 如果貴組織擁有不包含 Office 365 進階郵件加密的 Office 365 訂閱，您可以以 E5 合規性的進階合規性 SKU 與附加元件形式購買進階郵件加密。

您可以使用郵件到期上您的使用者傳送給外部收件者使用 OME 入口網站來存取加密的電子郵件的電子郵件。 您強制使用 OME 入口網站，以檢視和回覆加密所使用 Windows Powershell 中指定到期日的自訂品牌的範本貴組織所傳送的電子郵件的收件者。

以 O365 全域系統管理員身分，當您套用公司品牌自訂外觀的 Office 365 組織的電子郵件，您也可以指定這些電子郵件訊息的到期日。 使用 Office 365 進階郵件加密，您可以建立多個範本發出的加密電子郵件從您的組織。 使用範本，您可以控制多久收件者可以存取您的使用者所傳送的郵件。

當使用者收到郵件已設定到期日時，使用者會看到的包裝函式電子郵件的到期日期。 如果使用者嘗試開啟過期的郵件，則會在 OME 入口網站中出現的錯誤。

您只能設定到期日的電子郵件給外部收件者。

使用 Office 365 進階郵件加密，只要您將自訂品牌套 Office 365 適用於包裝函式電子郵件符合您要套用該範本的郵件流程規則。 此外，您只可以使用到期，如果您使用自訂品牌。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>建立自訂品牌範本，以藉由使用 PowerShell 來強制郵件到期

1. 搭配 Office 365 組織中具有全域系統管理員權限的帳戶，[連線到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 執行新增 Set-omeconfiguration 指令程式。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

其中：

- `Identity`是自訂樣板的名稱。

- `ExternalMailExpiryInDays`識別收件者可以保留郵件過期前的天數。 您可以使用 1 – 730 天之間的任何值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 進階郵件加密的詳細資訊

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [撤銷由 Office 365 進階郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md)

- [郵件原則及符合性服務說明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
