---
title: 安全電子郵件建議原則原則 - Microsoft 365 企業版 | Microsoft Docs
description: 描述如何套用電子郵件原則和設定之 Microsoft 建議的原則。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 78defc7ad5da788ae49195f6c0027f3639d50f3e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291111"
---
# <a name="policy-recommendations-for-securing-email"></a>保護電子郵件的原則建議
本文說明如何實作建議身分識別與裝置存取原則，以保護組織的電子郵件和支援新式驗證和條件式存取的電子郵件用戶端。 這份指導的[常見身分識別與裝置存取原則](identity-access-policies.md)為基礎，同時還包括一些其他強化建議。


這些建議根據三個不同的層級的安全性和保護功能可以套用根據您所需要的精確度：**基礎**、**機密**和**高管制**。 您可以深入了解這些安全性層，以及[建議的安全性原則和設定簡介](microsoft-365-policies-configurations.md)中這些建議中所參考的建議用戶端作業系統。

這些建議需要讓使用者使用新式的電子郵件用戶端，包括 Outlook for iOS 和 Android 行動裝置上。 Outlook for iOS 和 Android 的 Office 365 的最佳功能提供支援。 這些行動的 Outlook 應用程式也會架構與安全性功能，可支援行動裝置使用和配合其他 Microsoft 雲端安全性功能。 如需詳細資訊，請參閱 < <b0>Outlook for iOS 和 Android 常見問題集</b0>。

## <a name="updating-common-policies-to-include-email"></a>更新加入電子郵件的一般原則
下圖說明常見的身分識別與裝置存取原則，並指出哪些原則需要進行更新，以保護電子郵件。 請注意額外的 Exchange Online，以封鎖 ActiveSync 用戶端的新規則。 這會強制使用 Outlook 行動裝置。

![保護電子郵件的原則更新的摘要](../images/identity-access-ruleset-mail.png)

如果您的原則範圍中包含 Exchange Online 和 Outlook，您設定它們，您只需要建立新的原則，以封鎖 ActiveSync 用戶端。 檢閱下列表格所列出的原則與下列一項將建議新增的項目，或確認這些已加入。 每個規則會連結至[常見的身分識別與裝置存取原則](identity-access-policies.md)> 一文中的關聯的設定指示。 

|保護層級|原則|詳細資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[登入風險*中*] 或 [*高*時需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 Exchange Online 中的雲端應用程式的工作分派|
|        |[封鎖用戶端不支援新式驗證](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|包含 Exchange Online 中的雲端應用程式的工作分派|
|        |[定義應用程式保護原則](identity-access-policies.md#high-risk-users-must-change-password)|請務必 Outlook 隨附的應用程式清單中。 請務必更新每個平台 (iOS、 Android、 Windows) 的原則|
|        |[需要核准的應用程式](identity-access-policies.md#require-approved-apps)|雲端應用程式的清單中包括 Exchange Online|
|        |[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|包含 Exchange Online 中的雲端應用程式清單|
|        |[封鎖 ActiveSync 用戶端](#block-activesync-clients)|新增這個新的原則| 
|**敏感性**|[*低*、*中*或*高*登入風險時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| 包含 Exchange Online 中的雲端應用程式的工作分派|
|         |[需要相容電腦*和*行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|雲端應用程式的清單中包括 Exchange Online|
|**高管制**|[*永遠*需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 Exchange Online 中的雲端應用程式的工作分派|

## <a name="block-activesync-clients"></a>封鎖 ActiveSync 用戶端
此原則可防止 ActiveSync 用戶端略過其他條件式存取規則。 規則設定僅適用於 ActiveSync 用戶端。 藉由選取**需要核准用戶端應用程式**，此原則會封鎖 ActiveSync 用戶端。 若要設定此原則：

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 您已成功登入之後，您會看到 Azure 儀表板。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

5. 輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。

6. 選擇 [雲端應用程式]。

7. 選擇 [**選取應用程式**中，選取 [ **Office 365 Exchange Online**。 選擇 [**選取**和**完成**]。

8. 選擇 [**條件**]，然後選擇 [**用戶端應用程式**。

9. 如**設定**中，選取 [**是**]。 檢查只有下列項目：**桌面用戶端和行動應用程式**和**Exchange ActiveSync 用戶端**。 選擇 [**完成**]。

10. 選擇 [存取控制] 區段中的 [授與]。

11. 選擇 [**授與存取權**，請選取 [**需要核准用戶端應用程式**。  對於多個控制項，請選取 [**需要選取的控制項**，然後選擇 [**選取**。 

12. 	選擇 **[建立]**。

## <a name="setup-office-365-message-encryption"></a>設定 Office 365 郵件加密
與新的 Office 365 郵件加密 (OME) 功能，利用 Azure 資訊保護中的保護功能，您的組織可以輕鬆地共用受保護的電子郵件與任何裝置上的任何人。 使用者可以傳送和接收受保護的郵件與其他 Office 365 組織，以及使用 Outlook.com、 Gmail，以及其他電子郵件服務的非 Office 365 客戶。

如需詳細資訊，請參閱 <<c0>設定新的 Office 365 郵件加密功能。 



## <a name="next-steps"></a>後續步驟

[了解保護 SharePoint 網站和檔案的原則建議](sharepoint-file-access-policies.md)
