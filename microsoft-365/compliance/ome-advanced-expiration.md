---
title: 為由 Office 365 進階郵件加密所加密的電子郵件設定到期日
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
description: 與 Office 365 進階郵件加密功能掌握 Office 365 郵件加密 (OME)，您可以擴充您的電子郵件安全性設定的自訂品牌範本透過電子郵件到期日。
ms.openlocfilehash: 6790cc7103ad098419bde96b93738424626cd0cc
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38685467"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>為由 Office 365 進階郵件加密所加密的電子郵件設定到期日

Office 365 進階郵件加密隨附於[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 E5、 Microsoft 365 E5 （非營利組織版人員價格），Office 365 企業版 E5 （非營利組織版人員價格） 和 Office 365 教育版 A5。 如果貴組織擁有不包含 Office 365 進階郵件加密的訂閱，您可以購買它與 Microsoft 365 E5 規範 SKU 附加元件的 Microsoft 365 E3，Microsoft 365 E3 （非營利組織版人員價格），或 Office 365 進階為 Microsoft 365 E3，Microsoft 365 E3 的合規性 SKU 附加元件 （非營利組織版人員價格），或 Office 365 Sku。

您可以使用郵件到期上您的使用者傳送給外部收件者使用 OME 入口網站來存取加密的電子郵件的電子郵件。 您強制使用 OME 入口網站，以檢視和回覆加密所使用 Windows Powershell 中指定到期日的自訂品牌的範本貴組織所傳送的電子郵件的收件者。

以 O365 全域系統管理員身分，當您套用公司品牌自訂外觀的 Office 365 組織的電子郵件，您也可以指定這些電子郵件訊息的到期日。 使用 Office 365 進階郵件加密，您可以建立多個範本發出的加密電子郵件從您的組織。 使用範本，您可以控制多久收件者可以存取您的使用者所傳送的郵件。

當使用者收到郵件已設定到期日時，使用者會看到的包裝函式電子郵件的到期日期。 如果使用者嘗試開啟過期的郵件，則會在 OME 入口網站中出現的錯誤。

您只能設定到期日的電子郵件給外部收件者。

使用 Office 365 進階郵件加密，只要您將自訂品牌套 Office 365 適用於包裝函式電子郵件符合您要套用該範本的郵件流程規則。 此外，您只可以使用到期，如果您使用自訂品牌。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>建立自訂品牌範本，以藉由使用 PowerShell 來強制郵件到期

1. 搭配 Office 365 組織中具有全域系統管理員權限的帳戶，[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

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

- [郵件原則及符合性服務說明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
