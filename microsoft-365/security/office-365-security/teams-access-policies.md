---
title: 建議的 Teams 原則-Microsoft 365 企業版 |Microsoft 檔
description: 說明有關如何保護 Teams 通訊和檔案存取之 Microsoft 建議的原則。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 52e6709d18bd5ecbc91755a6c0e7be336d346f0c
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599600"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>保護 Teams 聊天、群組和檔案的原則建議

本文說明如何執行建議的身分識別和裝置存取原則，以保護 Microsoft Teams 聊天、群組和內容（如檔案和行事曆）。 本指南以通用身分[識別和裝置存取原則](identity-access-policies.md)為基礎，具有 Teams 特有的額外資訊。 因為 Teams 會與我們的其他產品整合，另請參閱[原則建議，以保護 SharePoint 網站和](sharepoint-file-access-policies.md)檔案，以及[保護電子郵件的原則建議](secure-email-recommended-policies.md)。

這些建議是以三種不同的安全性和保護層級為基礎，可根據您的需求細微性來套用 Teams：基準、機密和高管制。 您可以在身分 [識別和裝置存取](microsoft-365-policies-configurations.md)設定中深入瞭解這些安全層及這些建議所參照的建議原則。

本文所包含的 Teams 部署的相關建議如下所述，以涵蓋特定驗證的情況，包括組織外部的使用者。 您必須遵循此指導方針，才可取得完整的安全性體驗。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>在其他相依服務開始之前的 Teams 快速入門

您不需要啟用相依服務即可開始使用 Microsoft Teams。 這些服務全部都是「運作」。 不過，您必須準備好管理下列服務相關元素：

- Microsoft 365 群組
- SharePoint 小組網站
- 商務用 OneDrive
- Exchange 信箱
- Stream 影片和 Planner 方案 (若啟用這些服務) 

## <a name="updating-common-policies-to-include-teams"></a>更新常見原則以包含 Teams

為了保護 Teams 中的聊天、群組和內容，下列圖表說明要從一般身分識別和裝置存取原則更新哪些原則。 針對每個要更新的原則，請確定 cloud app 的指派中包含 Teams 和相依的服務。

[![保護 Teams 及其相依服務存取權的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

這些服務是在 Teams 的雲端應用程式指派中包含的相依服務：

- Microsoft Teams
- SharePoint 和商務用 OneDrive
- Exchange Online
- 商務用 Skype Online
- Microsoft Stream (會議錄製) 
- Microsoft Planner (Planner 工作和規劃資料) 

下表列出在[一般身分識別和裝置存取原則](identity-access-policies.md)中，每個原則所需的訪問原則，以及每個原則的連結，這些原則都有設定所有 Office 應用程式的更大原則。

|保護層級|原則|Teams 執行的進一步資訊|
|---|---|---|
|**Baseline**|[當登入風險為 *中* 或 *高* 時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|請確定應用程式清單中包含 Teams 和相依的服務。 Teams 還有其他來賓存取規則和外部存取規則，您也可以在本文稍後深入瞭解這些規則。|
||[封鎖不支援新式驗證的用戶端](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|在雲應用程式的指派中包含 Teams 和相依的服務。|
||[高風險使用者必須變更密碼](identity-access-policies.md#high-risk-users-must-change-password)|強制 Teams 使用者在登入時若偵測到其帳戶的高風險活動，請變更其密碼。 請確定應用程式清單中包含 Teams 和相依的服務。|
||[套用應用程式資料保護原則](identity-access-policies.md#apply-app-data-protection-policies)|請確定應用程式清單中包含 Teams 和相依的服務。 更新每個平臺 (iOS、Android Windows) 的原則。|
||[定義裝置合規性原則](identity-access-policies.md#define-device-compliance-policies)|在此原則中加入 Teams 和相依的服務。|
||[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在此原則中加入 Teams 和相依的服務。|
|**敏感度**|[當登入風險為 *低*、*中* 或 *高* 時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams 還有其他來賓存取規則和外部存取規則，您也可以在本文稍後深入瞭解這些規則。 在此原則中加入 Teams 和相依的服務。|
||[需要相容 *的電腦和* 行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在此原則中加入 Teams 和相依的服務。|
|**高管制**|[*永遠* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|不論使用者身分識別，您的組織都會使用 MFA。 在此原則中加入 Teams 和相依的服務。 |
|

## <a name="teams-dependent-services-architecture"></a>Teams 相依的服務架構

為了供參考，下圖說明 Teams 所依賴的服務。 如需詳細資訊和圖例，請參閱[IT 架構師 Microsoft 365 中的 Microsoft Teams 和相關的生產力服務](../../solutions/productivity-illustrations.md)。

[![圖表顯示 SharePoint、商務用 OneDrive 及 Exchange 的 Teams 相依性](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[查看較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>來賓和 Teams 的外部存取

Microsoft Teams 定義下列訪問類型：

- **來賓存取** 針對來賓或外部使用者使用 Azure AD B2B 帳戶，可將其新增為小組成員，並擁有對該小組之通訊和資源的所有專屬許可權存取權。

- **外部存取** 適用于沒有 Azure AD B2B 帳戶的外部使用者。 外部存取可以包含邀請，並參與通話、聊天和會議，但不包括小組成員資格和對小組資源的存取。

條件式存取原則只適用于 Teams 中的來賓存取，因為存在對應的 Azure AD B2B 帳戶。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

如需允許使用 Azure AD B2B 帳戶存取來賓和外部使用者的建議原則，請參閱 [允許來賓和外部 B2B 帳戶存取的原則](identity-access-policies-guest-access.md)。

### <a name="guest-access-in-teams"></a>Teams 中的來賓存取

除了您公司或組織內部的使用者原則之外，管理員還可以讓來賓存取允許以使用者為基礎的使用者，在您的公司或組織外部的人員存取 Teams 資源，並與內部人員（例如群組交談、聊天和會議）進行互動。

如需來賓存取及其實施方式的詳細資訊，請參閱[Teams 來賓存取](/microsoftteams/guest-access)。

### <a name="external-access-in-teams"></a>Teams 中的外部存取

外部存取有時候會與來賓存取混淆，所以請務必明確這兩種非內部存取機制是不同的存取類型。

「外部存取」是一種從整個外部網域 Teams 使用者，以便在 Teams 中尋找、通話、聊天及設定使用者的會議。 Teams 管理員設定組織層級的外部存取。 如需詳細資訊，請參閱[Manage external access in Microsoft Teams](/microsoftteams/manage-external-access)。

外部存取使用者與透過來賓存取新增的人員相比，具有較少的存取權和功能。 例如，外部存取使用者可以與您的內部使用者互動 Teams，但無法存取小組通道、檔案或其他資源。

外部存取不使用 Azure AD B2B 使用者帳戶，因此不會使用條件式存取原則。

## <a name="teams-policies"></a>Teams 原則

在上面所列的一般原則之外，有 Teams 特定原則，可且應設定，以管理各種 Teams 功能。

### <a name="teams-and-channels-policies"></a>Teams 及通道原則

Teams 及通道是 Microsoft Teams 中的兩個常用元素，而且有一些原則可供您用來控制使用者使用團隊和管道時可以執行和不能執行的動作。 雖然您可以建立全域小組，但如果您的組織有5000位使用者或更少的使用者，您很可能會發現，使用小型小組和管道來滿足您的組織需求，以滿足特定目的。

建議您變更預設原則或建立自訂原則，您可以深入瞭解如何在此連結中管理原則：[管理 Microsoft Teams 中的小組原則](/microsoftteams/teams-policies)。

### <a name="messaging-policies"></a>訊息原則

您也可以透過預設全域原則或透過自訂原則來管理訊息或聊天，這可協助您的使用者以適合組織的方式與彼此進行通訊。 在[Teams 中管理郵件原則](/microsoftteams/messaging-policies-in-teams)時，可以查看這項資訊。

### <a name="meeting-policies"></a>會議原則

不需要規劃及實施 Teams 會議的原則，即可完成 Teams 討論。 會議是 Teams 的基本元件，可讓使用者正式開會及呈現給許多使用者，以及共用會議相關的內容。 在會議上為組織設定正確的原則是必要的。

如需詳細資訊，請參閱[Teams 中的管理會議原則](/microsoftteams/meeting-policies-in-teams)。

### <a name="app-permission-policies"></a>應用程式權限原則

Teams 也可讓您在不同的地方使用應用程式，例如通道或個人聊天。 針對可以新增及使用哪些應用程式，以及在維護內容豐富的環境（也是安全）上都有哪些原則。

如需應用程式許可權原則的相關資訊，請參閱[Microsoft Teams 中的管理應用程式許可權原則](/microsoftteams/teams-app-permission-policies)。

## <a name="next-steps"></a>後續步驟

![步驟4： Microsoft 365 cloud app 的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

為下列專案設定條件式存取原則：

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)