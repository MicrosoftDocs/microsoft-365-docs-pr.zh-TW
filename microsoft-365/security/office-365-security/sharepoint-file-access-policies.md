---
title: 建議的安全檔原則-Microsoft 365 for enterprise |Microsoft 檔
description: 描述如何保護 SharePoint 檔案存取之 Microsoft 建議的原則。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203423"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>保護 SharePoint 網站和檔案的原則建議

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- SharePoint Online 


本文說明如何執行建議的身分識別和裝置存取原則，以保護 SharePoint 和 OneDrive 商務。 本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。

這些建議是根據您的需求細微性，以三種不同的安全性和保護層級來保護 SharePoint 檔案： **基準**、 **機密** 和 **高管制**。 您可以在 [ [概述](microsoft-365-policies-configurations.md)] 中深入瞭解這些安全性層，以及建議的用戶端作業系統。

除了執行這項指導之外，請務必設定具有適當保護的 SharePoint 網站，包括為敏感和高管制內容設定適當的許可權。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>更新常見原則，以納入 SharePoint 和 OneDrive 商務

為了保護 SharePoint 和 OneDrive 中的檔案，下圖說明要從一般身分識別和裝置存取原則更新哪些原則。

[![保護對小組及其相依服務之存取的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

如果您在建立通用原則時包含 SharePoint，您只需要建立新的原則。 針對條件式存取原則，SharePoint 包含 OneDrive。

新的原則會將特定存取需求套用至指定的 SharePoint 網站，以實現敏感和高管制內容的裝置保護。

下表列出您需要複查和更新或為 SharePoint 建立新的原則。 通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。

|保護層級|原則|詳細資訊|
|---|---|---|
|**Baseline**|[當登入風險為 *中* 或 *高* 時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在雲端應用程式的指派中包含 SharePoint。|
||[封鎖不支援新式驗證的用戶端](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|在雲端應用程式的指派中包含 SharePoint。|
||[套用應用程式資料保護原則](identity-access-policies.md#apply-app-data-protection-policies)|請確定所有建議的應用程式都包含在應用程式清單中。 請務必更新每個平臺 (iOS、Android、Windows) 的原則。|
||[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在雲端應用程式的清單中包含 SharePoint。|
||[在 SharePoint 中使用應用程式強制限制](#use-app-enforced-restrictions-in-sharepoint)|新增此新原則。 這會告訴 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的設定。 這個原則會套用至所有使用者，但是只會影響 SharePoint 存取原則中所包含之網站的存取權。|
|**敏感度**|[當登入風險為 *低*、*中* 或 *高* 時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在雲端應用程式的指派中包含 SharePoint。|
||[需要相容 *的電腦和* 行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在雲端 app 清單中包含 SharePoint。|
||[SharePoint 存取控制原則](#sharepoint-access-control-policies)：允許來自未受管理裝置之特定 SharePoint 網站的瀏覽器存取權。|這可避免檔案的編輯和下載。 使用 PowerShell 來指定網站。|
|**高管制**|[*永遠* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在雲端應用程式的指派中包含 SharePoint。|
||[SharePoint 存取控制原則](#use-app-enforced-restrictions-in-sharepoint)：封鎖非管理裝置對特定 SharePoint 網站的存取權。|使用 PowerShell 來指定網站。|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>在 SharePoint 中使用應用程式強制限制

如果您在 SharePoint 中執行存取控制，您必須在 Azure AD 中建立此條件式存取原則，以通知 Azure AD 強制執行您在 SharePoint 中設定的原則。 這個原則會套用至所有使用者，但是只會影響您在 SharePoint 中建立存取控制時使用 PowerShell 所指定之網站的存取權。

若要設定此原則，請參閱 [控制存取非管理裝置](/sharepoint/control-access-from-unmanaged-devices)中的「封鎖或限制存取特定 SharePoint 網站集合或 OneDrive 帳戶」。

## <a name="sharepoint-access-control-policies"></a>SharePoint 的存取控制原則

Microsoft 建議您使用裝置存取控制，以機密和高管制內容來保護 SharePoint 網站中的內容。 您可以建立原則，以指定保護的層級，以及要套用保護的網站。

- 機密網站：允許僅供瀏覽器存取。 這會防止使用者編輯及下載檔案。
- 高度管制網站：封鎖非管理裝置的存取。

請參閱「阻止或限制存取特定 SharePoint 網站集合或 OneDrive 帳戶」，以 [控制來自非管理裝置的存取](/sharepoint/control-access-from-unmanaged-devices)。

## <a name="how-these-policies-work-together"></a>這些原則共同運作的方式

請務必瞭解，SharePoint 網站許可權通常是以網站存取權的業務需求為基礎。 這些許可權是由網站擁有者管理，而且可以是高動態的。 使用 SharePoint 裝置存取原則可確保對這些網站的保護，不論是否將使用者指派至與基線、敏感或高度管制保護相關聯的 Azure AD 群組。

下圖提供 SharePoint 裝置存取原則如何保護使用者對網站存取的範例。

[![SharePoint 裝置存取原則如何保護網站的範例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[查看較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James 具有指派的基準條件式存取原則，但可獲得對具有敏感或高管制保護之 SharePoint 網站的存取權。

- 如果 James 存取敏感或高管制的網站，他是使用自己電腦的成員，只要其電腦符合規範，就會授與其存取權。
- 如果 James 存取機密的網站，他是使用未受管理的電話的成員（允許基準使用者使用），他只會收到對機密網站的瀏覽器存取權（由於為此網站設定的裝置存取原則）。
- 如果 James 存取高管制網站，他是使用非管理電話的成員，則會因此網站設定的存取原則而封鎖。 他只能使用受管理和相容的電腦來存取此網站。

## <a name="next-step"></a>下一步

![步驟4： Microsoft 365 雲端應用程式的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

為下列專案設定條件式存取原則：

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)