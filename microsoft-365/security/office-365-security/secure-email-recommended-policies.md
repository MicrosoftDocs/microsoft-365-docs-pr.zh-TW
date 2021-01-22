---
title: 安全的電子郵件建議政策 - 適用于企業的 Microsoft 365 |Microsoft Docs
description: 描述如何套用電子郵件原則和設定之 Microsoft 建議的原則。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: f3654762bf4d4c28a82b1e93829094b9e0386a60
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926519"
---
# <a name="policy-recommendations-for-securing-email"></a>保護電子郵件的原則建議

本文說明如何執行建議的身分識別與裝置存取策略，以保護支援新式驗證與條件式存取的組織電子郵件和電子郵件客戶客戶。 此指引以一 [般身分識別與裝置存取策略為](identity-access-policies.md) 根據，並包含一些額外的建議。

這些建議是以三種不同的安全性和保護層級為基礎，可以根據您的需求細微度來加以運用：比較基準、機密以及 **高度規範**。   您可以深入了解這些安全性層，以及[建議的安全性原則和設定簡介](microsoft-365-policies-configurations.md)中這些建議中所參考的建議用戶端作業系統。

這些建議會要求您的使用者使用新式電子郵件用戶端，包括行動裝置上的 iOS 版 Outlook 和 Android 版 Outlook。 iOS 和 Android 版 Outlook 支援 Office 365 的最佳功能。 這些行動版 Outlook App 也採用安全性功能進行架構，可支援行動用途並與其他 Microsoft 雲端安全性功能共同作業。 詳細資訊請參閱 iOS 版 Outlook 和 [Android 版 Outlook 的常見問題](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。

## <a name="update-common-policies-to-include-email"></a>更新一般策略以包含電子郵件

若要保護電子郵件，下圖說明要從一般身分識別與裝置存取策略更新哪些策略。

[![用於保護 Teams 存取權及其從屬服務之策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[查看此影像的較大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

請注意，Exchange Online 新增了封鎖 ActiveSync 用戶端的新策略。 這會強制使用 Outlook Mobile。

如果您在設定 Exchange Online 和 Outlook 時將 Exchange Online 和 Outlook 納入其中，您只需要建立新策略來封鎖 ActiveSync 用戶端。 請審查下表中列出的政策，並新增建議專案，或確認其中已包含這些。 每個策略會連結至一般身分識別與 [裝置存取策略中關聯的組組指示](identity-access-policies.md)。

|保護層級|原則|其他相關資訊|
|---|---|---|
|**Baseline**|[當登錄風險中或高 *時需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在指派雲端 App 中納入 Exchange Online|
||[封鎖不支援新式驗證的用戶端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在指派雲端 App 中納入 Exchange Online|
||[Apply APP 資料保護原則](identity-access-policies.md#apply-app-data-protection-policies)|請確定 Outlook 已包含在應用程式清單中。 請務必針對 iOS、Android、Windows (每個平臺更新) |
||[需要核准的應用程式和 APP 保護](identity-access-policies.md#require-approved-apps-and-app-protection)|將 Exchange Online 納入雲端應用程式清單|
||[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|將 Exchange Online 納入雲端應用程式清單|
||[封鎖 ActiveSync 用戶端](#block-activesync-clients)|新增此新政策|
|**敏感度**|[在低、中或高登錄風險時需要MFA ](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在指派雲端 App 中納入 Exchange Online|
||[需要符合規範的 PC *及* 行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|將 Exchange Online 納入雲端應用程式清單|
|**高管制**|[*一* 直需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在指派雲端 App 中納入 Exchange Online|
|

## <a name="block-activesync-clients"></a>封鎖 ActiveSync 用戶端

此策略可防止 ActiveSync 用戶端忽略其他條件式存取策略。 原則群組原則只會適用于 ActiveSync 用戶端。 選取需要 **[App 保護原則，](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** 此策略會區塊 ActiveSync 用戶端。 您可以在使用條件式存取進行雲端 App 存取的需要 App 保護原則中，找到建立 [此策略的詳細資訊](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。

- 請遵循「步驟 2：使用 ActiveSync (EAS) 設定 Exchange Online 的 Azure AD 條件式存取策略」：Office [365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)App 需要具有 App 保護原則核准的 App，以避免使用基本驗證的 Exchange ActiveSync 用戶端無法連線至 Exchange Online。

您也可以使用驗證策略來停用基本 [驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)，強制所有用戶端存取要求使用新式驗證。

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>限制從 Outlook 網頁版存取 Exchange Online

您可以限制使用者在裝置上從 Outlook 網頁版本下載附件的能力。 這些裝置上的使用者可以使用 Office Online 來查看和編輯這些檔案，而不必將檔案洩漏到裝置上並儲存。 您也可以封鎖使用者在未受到管理裝置上看到附件。

步驟如下：

1. [連線到 Exchange Online 遠端 PowerShell 會話](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。
2. 如果您還沒有 OWA 信箱策略，請用 [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) Cmdlet 建立一個。
3. 如果您想要允許檢視附件但不允許下載，請使用此命令：

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. 如果您想要封鎖附件，請使用此命令：

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. 在 Azure 入口網站中，使用這些設定來建立一個新的條件式存取政策：

   **作業** \>**使用者和群組**：選取要包含和排除的適當使用者和群組。

   **作業** \>**雲端 App 或動作** \>**雲端應用程式** \>**包含** \>**選取應用程式**：選取 **Office 365 Exchange Online**

   **存取控制** \>**會話**：選取 **使用應用程式強制限制**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>要求 iOS 和 Android 裝置必須使用 Outlook

若要確保 iOS 和 Android 裝置的使用者只能使用 iOS 和 Android 版 Outlook 存取公司或學校內容，您需要一個會檢查這些潛在使用者的條件式存取政策。

請參閱使用 iOS 和 Android 版 Outlook 在管理郵件共同處理存取中設定 [此策略的步驟]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。

## <a name="set-up-message-encryption"></a>設定郵件加密

有了新的 Office 365 郵件加密 (OME) 功能，利用 Azure 資訊保護中的保護功能，貴組織就可以輕鬆地與任何裝置上的任何人共用受保護的電子郵件。 使用者可以與其他 Microsoft 365 組織以及使用 Outlook.com、Gmail 和其他電子郵件服務的非客戶一起傳送及接收受保護的郵件。

詳細資訊請參閱設定新的 [Office 365 郵件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。

## <a name="next-steps"></a>後續步驟

![步驟 4：Microsoft 365 雲端應用程式政策](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

設定條件式存取策略：

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
