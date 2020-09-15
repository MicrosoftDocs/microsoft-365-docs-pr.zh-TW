---
title: 建議的團隊原則-Microsoft 365 for enterprise |Microsoft 檔
description: 說明有關如何保護小組通訊和檔案存取之 Microsoft 建議的原則。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/12/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: fc2b83fc167a9385383d7085ed6d1e8db15abd42
ms.sourcegitcommit: a13f43a3e981c90f1e0b9805c9c16a56f67fc650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651129"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>保護小組聊天、群組和檔案的原則建議

本文說明如何執行建議的身分識別和裝置存取原則，以保護 Microsoft 團隊聊天、群組和內容（如檔案和行事曆）。 本指南以通用身分 [識別和裝置存取原則](identity-access-policies.md)為基礎，具有特定小組特有的額外資訊。 因為小組與我們的其他產品整合，另請參閱 [原則建議，以保護 SharePoint 網站和](sharepoint-file-access-policies.md) 檔案，以及 [保護電子郵件的原則建議](secure-email-recommended-policies.md)。

這些建議是以三種不同的安全性和保護層級為基礎，可根據您的需求細微性來套用這些小組：基準、機密和高管制。 您可以在身分 [識別和裝置存取](microsoft-365-policies-configurations.md)設定中深入瞭解這些安全層及這些建議所參照的建議原則。

本文中包含其他小組部署的相關建議，以涵蓋特定驗證的情況，包括組織外部的使用者。 您必須遵循此指導方針，才可取得完整的安全性體驗。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>在其他相依服務之前快速開始使用團隊

您不需要啟用相依服務即可開始使用 Microsoft 團隊。 這些都是「直接運作」。 不過，您必須準備好管理下列專案：

- Microsoft 365 群組
- SharePoint 小組網站
- 商務用 OneDrive
- Exchange 信箱
- Stream 影片和 Planner 方案 (若啟用這些服務) 

## <a name="updating-common-policies-to-include-teams"></a>將常見原則更新為包含小組

為了保護「聊天」、群組及小組內容，下列圖表說明要從通用身分識別和裝置存取原則更新哪些原則。 針對每個要更新的原則，請確定 cloud app 的指派中包含小組和相依的服務。

[![保護對小組及其相依服務之存取的原則更新摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[查看較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

以下是要納入小組的雲端應用程式指派中的相依服務：

- Microsoft Teams
- SharePoint 和商務用 OneDrive
- Exchange Online
- 商務用 Skype Online
- Microsoft Stream (會議錄製) 
- Microsoft Planner (Planner 工作和規劃資料) 

此表格列出必須針對 [一般身分識別和裝置存取原則](identity-access-policies.md)中的每個原則所進行的原則，以及所有 Office 應用程式的更大原則設定的連結。

|保護層級|原則|小組實施的進一步資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[當登入風險為*中*或*高*時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|請確定小組和相依服務均包含在應用程式清單中。 小組也會考慮訪客存取和外部存取規則，您將在本文稍後深入瞭解這些規則。|
|        |[封鎖不支援新式驗證的用戶端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在雲應用程式的指派中包含小組和相依服務。|
|        |[高風險使用者必須變更密碼](identity-access-policies.md#high-risk-users-must-change-password)|強制小組使用者在登入時，在其帳戶中偵測到高風險活動時變更其密碼。 請確定小組和相依服務均包含在應用程式清單中。|
|        |[套用應用程式資料保護原則](identity-access-policies.md#apply-app-data-protection-policies)|請確定小組和相依服務均包含在應用程式清單中。 更新每個平臺 (iOS、Android、Windows) 的原則。|
|        |[需要核准的應用程式和應用程式保護](identity-access-policies.md#require-approved-apps-and-app-protection)|在此原則中包括小組和相依服務。|
|        |[定義裝置合規性原則](identity-access-policies.md#define-device-compliance-policies)|在此原則中包括小組和相依服務。|
|        |[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在此原則中包括小組和相依服務。|
|**敏感度**|[當登入風險為*低*、*中*或*高*時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|小組也會考慮訪客存取和外部存取規則，您將在本文稍後深入瞭解這些規則。 在此原則中包括小組和相依服務。|
|         |[需要相容 *的電腦和* 行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在此原則中包括小組和相依服務。|
|**高管制**|[*永遠* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|不論使用者身分識別，您的組織都會使用 MFA。 在此原則中包括小組和相依服務。
| | |

## <a name="teams-dependent-services-architecture"></a>小組相依服務架構

為了供參考，下圖說明服務小組所依賴的服務。 如需詳細資訊及其他圖解，請參閱 microsoft [團隊和 microsoft 的相關生產力服務，請參閱 microsoft 365 FOR IT 架構設計](../solutions/productivity-illustrations.md)人員。

![圖表顯示團隊對 SharePoint、商務 OneDrive 和 Exchange 的相依性依賴性](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>為小組啟用來賓和外部存取

在 Azure AD 中，來賓和外部使用者皆相同。 這兩種皆為來賓的使用者類型。 來賓使用者 B2B 使用者。 Microsoft 小組區分來賓使用者和應用程式中的外部使用者。 雖然瞭解各小組的各項處理方式很重要，但這兩種類型的使用者都是 Azure AD 中 B2B 使用者，而 B2B 使用者同時套用的建議原則，也是建議的原則。 如需允許來賓存取的建議原則，請參閱 [允許來賓和外部 B2B 存取的原則](identity-access-policies-guest-access.md)。

### <a name="guest-access-in-teams"></a>Teams 中的來賓存取

除了您公司或組織內部的使用者原則之外，管理員還可以讓來賓存取允許以使用者為基礎的使用者，在您的公司或組織外部的人員存取小組資源，並與內部人員（例如群組交談、聊天和會議）進行互動。 您可以在下列連結中深入瞭解來賓存取： [小組訪客存取權](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>小組中的外部存取

外部存取有時候會與來賓存取混淆，所以請務必明確這兩個非內部存取機制的實際差別很大。 「來賓存取」是以每位使用者為基礎進行， (您一次新增一個使用者) ，當系統管理員啟用外部存取時，可讓您同時將外部網域的所有使用者新增至小組。 不過，這些外部使用者的存取權和功能，不如透過來賓存取新增的人員。 外部存取使用者可以透過小組與您的內部使用者交談。

如需有關外部存取的詳細資訊，以及如何在需要時加以實施，請參閱 [管理 Microsoft 團隊中的外部存取](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>小組原則

在上述一般原則之外，有一些小組特有的原則可和應設定，以管理各種小組功能。

### <a name="teams-and-channels-policies"></a>小組和管道原則

小組和頻道是 Microsoft 小組中的兩個常用元素，也有一些原則可供您用來控制使用者使用團隊和管道時可以執行和不能執行的動作。 雖然您可以建立全域小組，但如果您的組織有5000位使用者或更少的使用者，您很可能會發現，使用小型小組和管道來滿足您的組織需求，以滿足特定目的。

建議您變更預設原則或建立自訂原則，您也可以深入瞭解如何管理您在此連結上的原則： [管理 Microsoft 小組中的團隊原則](https://docs.microsoft.com/microsoftteams/teams-policies)。

### <a name="messaging-policies"></a>郵件原則

您也可以透過預設全域原則或透過自訂原則來管理訊息或聊天，這可協助您的使用者以適合組織的方式與彼此進行通訊。 您可以在 [管理小組的郵件原則](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)時查看這項資訊。

### <a name="meeting-policies"></a>會議原則

不需要在小組會議中規劃及實施原則，即可完成小組討論。 會議是小組的基本元件，可讓使用者正式開會及呈現給許多使用者，以及共用與會議相關的內容。 在會議上為組織設定正確的原則是必要的。

如需詳細資訊，請參閱 [管理小組中的會議原則](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) 。

### <a name="app-permission-policies"></a>應用程式許可權原則

小組也可讓您在不同的地方使用應用程式，例如通道或個人聊天。 針對可以新增及使用哪些應用程式，以及在維護內容豐富的環境（也是安全）上都有哪些原則。

如需應用程式許可權原則的相關資訊，請參閱 [管理 Microsoft 小組中的應用程式許可權原則](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。

## <a name="next-steps"></a>後續步驟

![步驟4： Microsoft 365 雲端應用程式的原則](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

為下列專案設定條件式存取原則：

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

