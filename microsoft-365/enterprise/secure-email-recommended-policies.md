---
title: 安全電子郵件建議原則原則 - Microsoft 365 企業版 | Microsoft Docs
description: 描述如何套用電子郵件原則和設定之 Microsoft 建議的原則。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: dd35bf0d7439a19d7b1562e7a0d0681679b34c36
ms.sourcegitcommit: c079cc893cd1bd5d894b13814063a2f42238806e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43035108"
---
# <a name="policy-recommendations-for-securing-email"></a>保護電子郵件的原則建議

本文說明如何執行建議的身分識別和裝置存取原則，以保護支援新式驗證和條件式存取的組織電子郵件和電子郵件客戶程式。 本指南是以[通用身分識別和裝置存取原則](identity-access-policies.md)為基礎，也包含一些額外的建議。

這些建議是以三種不同的安全性和保護層級為基礎，可以根據您的需求細微性來套用：**基準**、**機密**和**高管制**。 您可以深入了解這些安全性層，以及[建議的安全性原則和設定簡介](microsoft-365-policies-configurations.md)中這些建議中所參考的建議用戶端作業系統。

這些建議要求您的使用者使用現代電子郵件客戶程式，包括行動裝置上的 Outlook iOS 和 Android。 適用于 iOS 和 Android 的 Outlook 提供 Office 365 的最佳功能支援。 這些行動性 Outlook 應用程式也會使用支援行動使用的安全性功能，以及與其他 Microsoft cloud 安全性功能共同運作。 如需詳細資訊，請參閱[Outlook for iOS 和 ANDROID 常見問題](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。

## <a name="updating-common-policies-to-include-email"></a>更新常見原則以包含電子郵件

下圖說明一般身分識別和裝置存取原則，並指出需要更新哪些原則以保護電子郵件。 請注意，新增 Exchange Online 的新規則，以封鎖 ActiveSync 用戶端。 這會強制使用 Outlook mobile。

![保護電子郵件的原則更新摘要](../media/identity-access-ruleset-mail.png)

當您設定 Exchange Online 和 Outlook 時，如果您已在設定原則的範圍內包含 Exchange Online 和 Outlook，您只需要建立新原則來封鎖 ActiveSync 用戶端。 請查看下表所列的原則，並進行建議的新增，或確認是否已包含這些原則。 每個規則都連結到[通用身分識別和裝置存取原則](identity-access-policies.md)文章中相關的設定指示。

|保護層級|原則|詳細資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[當登入風險為*中*或*高*時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在雲應用程式的指派中包含 Exchange Online|
|        |[封鎖不支援新式驗證的用戶端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在雲應用程式的指派中包含 Exchange Online|
|        |[套用應用程式資料保護原則](identity-access-policies.md#apply-app-data-protection-policies)|請確定 Outlook 已包含在應用程式清單中。 請務必更新每個平臺的原則（iOS、Android、Windows）|
|        |[需要核准的應用程式和應用程式保護](identity-access-policies.md#require-approved-apps-and-app-protection)|在雲端應用程式清單中包含 Exchange Online|
|        |[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在雲端 app 清單中包含 Exchange Online|
|        |[封鎖 ActiveSync 用戶端](#block-activesync-clients)|新增此新原則| 
|**敏感性**|[當登入風險為*低*、*中*或*高*時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| 在雲應用程式的指派中包含 Exchange Online|
|         |[需要相容*的電腦和*行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在雲端應用程式清單中包含 Exchange Online|
|**高管制**|[*永遠*需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在雲應用程式的指派中包含 Exchange Online|

## <a name="block-activesync-clients"></a>封鎖 ActiveSync 用戶端

這個原則可防止 ActiveSync 用戶端略過其他條件式存取規則。 規則設定只適用于 ActiveSync 用戶端。 選取 [**[要求應用程式保護原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**]，此原則會封鎖 ActiveSync 用戶端。 若要瞭解如何建立此原則的詳細資料，請參閱[使用條件式存取之 cloud app access 的應用程式保護原則](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。

1. 在第1種情形中，請遵循「步驟2：設定 Exchange ActiveSync Online 的 Azure AD 條件式存取原則」（EAS）」，其[案例1： Office 365 應用程式需要核准的應用程式與應用程式保護原則](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)，可防止 Exchange ActiveSync 用戶端利用基本驗證連線至 Exchange Online。

## <a name="setup-office-365-message-encryption"></a>設定 Office 365 郵件加密

透過新的 Office 365 郵件加密（OME）功能（可利用 Azure 資訊保護中的保護功能），您的組織可以輕鬆地與任何設備上的任何人共用受保護的電子郵件。 使用者可以使用 Outlook.com、Gmail 及其他電子郵件服務，與其他 Office 365 組織及非 Office 365 客戶一起傳送及接收受保護的郵件。

如需詳細資訊，請參閱[設定新的 Office 365 郵件加密功能](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)。

## <a name="next-steps"></a>後續步驟

[了解保護 SharePoint 網站和檔案的原則建議](sharepoint-file-access-policies.md)
