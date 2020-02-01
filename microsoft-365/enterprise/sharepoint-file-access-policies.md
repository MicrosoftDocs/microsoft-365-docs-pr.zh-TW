---
title: 建議的安全文件原則 - Microsoft 365 企業版 | Microsoft Docs
description: 描述如何保護 SharePoint 檔案存取之 Microsoft 建議的原則。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: f0cd296157e1d4856c27d1dc547de045510e788b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600760"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>保護 SharePoint 網站與檔案的原則建議

本文說明如何實作建議身分識別與裝置存取原則，以保護 SharePoint Online 和商務用 OneDrive。 本指南為基礎的[常見身分識別與裝置存取原則](identity-access-policies.md)。

這些建議根據三個不同的層級的安全性和保護 SharePoint 檔案可套用根據您所需要的精確度：**基礎**、**機密**和**高管制**。 您可以深入了解這些安全性層級和建議的用戶端作業系統，這些建議[概觀](microsoft-365-policies-configurations.md)中所參照。

除了實作此指導方針，請務必保護，包括設定機密和高管制內容的適當權限的資料量與設定 SharePoint 網站。 如需有關如何建立網站的基準，機密和高管制保護的詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>更新以包含 SharePoint 和商務用 OneDrive 的一般原則

下圖說明建議的原則，以保護檔案中 SharePoint Online 和 OneDrive for Business 的集合。 它會指出應該更新或新建立的新增保護 SharePoint Online 和商務用 OneDrive 的原則。

![SharePoint Online 和 OneDrive 的原則的摘要](../images/identity-access-ruleset-sharepoint.png)

如果您建立的一般原則時，您包含 SharePoint Online，您只需要建立新的原則。 當設定條件式存取規則，SharePoint Online 包含商務用 OneDrive。

新的原則來實作裝置保護機密和高管制內容套用至您指定的 SharePoint 網站的特定存取需求。

下表列出您可能需要檢閱並更新或建立新的 SharePoint Online 的原則。 一般原則連結至[常見的身分識別與裝置存取原則](identity-access-policies.md)> 一文中的關聯的設定指示。

|保護層級|原則|詳細資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[登入風險*中*] 或 [*高*時需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 SharePoint Online 中的雲端應用程式的工作分派|
|        |[封鎖不支援新式驗證的用戶端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|包含 SharePoint Online 中的雲端應用程式的工作分派|
|        |[定義應用程式保護原則](identity-access-policies.md#define-app-protection-policies)|請務必在應用程式清單中包含所有的建議應用程式。 請務必更新每個平台 (iOS、 Android、 Windows) 的原則|
|        |[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|包含 SharePoint Online 中的雲端應用程式清單|
|        |[使用 SharePoint Online 中的應用程式強制限制](#use-app-enforced-restrictions-in-sharepoint-online)|新增此新原則。 這會告知 Azure AD 以使用 SharePoint Online 中所指定的設定。 此規則會套用至所有使用者，但只會影響 SharePoint Online 存取原則中包含的網站的存取權|
|**敏感性**|[*低*、*中*或*高*登入風險時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在工作分派的雲端應用程式包含 SharePoint Online|
|         |[需要相容電腦*和*行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|包含 SharePoint Online 的雲端應用程式清單中|
||[SharePoint Online 的存取控制原則](#sharepoint-online-access-control-policies)： 允許從受管理的裝置瀏覽器唯讀存取特定的 SharePoint 網站|這可防止編輯] 和 [下載檔案。 使用 PowerShell 來指定網站|
|**高管制**|[*永遠*需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 SharePoint Online 中的雲端應用程式的工作分派|
||[SharePoint Online 的存取控制原則](#use-app-enforced-restrictions-in-sharepoint-online)： 從未受控裝置特定的 SharePoint 網站來封鎖存取|使用 PowerShell 來指定網站|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>使用 SharePoint Online 中的應用程式強制限制

如果您在 SharePoint Online 中實作存取控制，您必須告知以強制執行您在 SharePoint Online 中設定原則的 Azure AD 的 Azure AD 中建立此條件式存取原則。 此規則會套用至所有使用者，但只會影響您使用 PowerShell，當您在 SharePoint Online 中建立存取控制指定網站的存取權。

若要在本文中設定此原則，請參閱 「 封鎖] 或 [限制存取特定的 SharePoint 網站集合或 OneDrive 帳戶 」:[控制從未受管理裝置的存取](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。

## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online 的存取控制原則

Microsoft 建議您保護機密和高管制與裝置存取控制內容的 SharePoint 網站內容。 要這麼做，藉由建立指定的保護和套用以保護網站層級的原則。

- 機密網站： 允許瀏覽器唯讀存取。 這可防止使用者編輯及下載檔案。
- 高管制網站： 封鎖來自未受管理的裝置的存取。

請參閱本文中的 「 封鎖] 或 [限制存取特定的 SharePoint 網站集合或 OneDrive 帳戶 」:[控制從未受管理裝置的存取](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。

## <a name="how-these-policies-work-together"></a>這些原則如何共同運作

請務必了解 SharePoint 網站權限通常會根據網站的存取權的業務需求。 這些權限由網站擁有者，而且可以是高動態。 使用裝置存取原則可確保這些網站，不論是否使用者指派給 Azure AD 群組來保護 SharePoint 與比較基準，敏感性相關聯，或高管制保護。

下圖提供 SharePoint 裝置存取原則如何保護網站的存取權的範例。

![SharePoint 的裝置存取原則如何保護網站](../images/SharePoint-rules-scenario.png)

在此圖例中：

- James 指派給基準保護相關聯的條件式存取原則，但他可以能夠存取敏感或高管制保護相關聯的 SharePoint 網站。
- 如果 James 存取敏感或高管制的站台，他是使用其電腦的成員，其授與存取，只要是相容，他的電腦。
- 如果 James 存取機密的網站，他是屬於使用其未受管理的電話，這允許的比較基準使用者，他將會收到機密的站台，因為針對此網站的裝置存取原則的權限瀏覽器。
- 如果 James 存取高管制的網站，他是使用其未受管理的電話的成員，他將會封鎖由於針對此網站的存取原則。 他只可以存取此網站使用其 managed 和相容的電腦。

## <a name="next-steps"></a>後續步驟

[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
