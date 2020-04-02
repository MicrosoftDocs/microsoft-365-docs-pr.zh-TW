---
title: Office 365 進階郵件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 中的高級郵件加密可讓系統管理員更進一步使用受保護的郵件，以協助組織滿足其合規性義務。
ms.openlocfilehash: 3b7f4d595b8c3592530b107dd7f71aeb8d0dc57e
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106171"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 進階郵件加密

Office 365 Advanced Message Encryption 包含在[Microsoft 365 企業版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 （非盈利性人員定價）、Office 365 企業版 E5 （非盈利性員工定價）和 Office 365 教育版 A5 中。 如果您的組織中有未包含 Office 365 Advanced Message Encryption 的訂閱，您可以使用 microsoft 365 E5 相容性 SKU 附加元件（適用于 Microsoft 365 E3）進行購買。 microsoft 365 E3 （非盈利性員工定價）或 Office 365 Advanced 合規性 SKU 附加元件（適用于 Microsoft 365 E3）、Microsoft 365 E3 （非盈利性員工定價）、Office 365 SKUs，或 microsoft 365 E5/A5 資訊保護和控管 SKU 附加元件（適用于 Microsoft 365 A3/E3）。

Office 365 中的高級郵件加密可協助客戶滿足法規遵從性義務，需要更多彈性控制外部收件者，以及他們存取加密的電子郵件。 使用 Office 365 中的高級郵件加密，您可以控制在組織外與自動原則共用的敏感電子郵件。 您可以設定這些原則來識別敏感資訊類型，例如 PII、財務或健康情況 IDs，也可以使用關鍵字來增強保護。 設定原則之後，您可以使用自訂的署名電子郵件範本對原則進行配對，然後新增到期日，以對符合原則的電子郵件進行特殊的控制。 此外，系統管理員可以隨時撤銷郵件存取權，透過安全的網頁入口網站進一步控制從外部存取的加密電子郵件。

您只能撤銷及設定傳送給外部收件者之電子郵件的到期日。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>開始使用 Office 365 Advanced Message Encryption

下列文章說明如何設定及使用高級郵件加密。

您的組織必須具有包含 Office 365 Advanced Message Encryption 的訂閱。 如需支援之訂閱的詳細資訊，請參閱[郵件原則及符合性服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

若尚未設定 Office 365 郵件加密，請參閱[設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。

使用高級郵件加密時，您不只限於單一署名範本。 相反地，您可以建立及使用多個商標範本。 如需詳細資訊，請參閱[將貴組織的品牌新增至加密郵件](add-your-organization-brand-to-encrypted-messages.md)。

[設定 Office 365 高級郵件加密所加密之電子郵件的到期日](ome-advanced-expiration.md)。 控制在組織外共用的敏感電子郵件使用自動原則，透過將安全的 web 入口網站的存取權終止至加密的電子郵件，增強保護。

[撤銷 Office 365 高級郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md)。 控制組織外共用的敏感電子郵件，並透過安全的 web 入口網站撤銷加密的電子郵件，增強保護。  

使用 Office 365 Advanced Message Encryption 時，無論您何時套用自訂商標範本，Office 365 都會對符合您套用範本之郵件流程規則的電子郵件套用包裝。 您只能撤銷郵件，並將到期日期套用至使用者透過入口網站取得的郵件。 換句話說，已套用自訂商標範本的電子郵件。 如需詳細資訊和範例，請參閱[確保所有外部收件者都使用 OME 入口網站來讀取加密郵件](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)的指導方針。
