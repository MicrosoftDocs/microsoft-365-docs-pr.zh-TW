---
title: 為小組設定三層保護
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- M365solutions
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 在 Microsoft Teams 中保護檔案的設定建議。
ms.openlocfilehash: 643ca5d5c340dc72cb375c114c2c7edaecf3dd46
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702509"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>為小組設定三層保護

本系列文章會提供一些建議，讓您了解如何設定 Microsoft Teams 中的小組及其相關聯的 SharePoint 網站，以在兼顧安全性與共同作業順暢性的前提下保護檔案。

本文定義四種不同的設定，首先是公用小組與最開放的共用原則。 每項額外設定均代表有意識的保護升級，但對小組內儲存的檔案進行存取和共同作業的能力，則會減少為僅限相關小組成員。 

本文的設定符合 Microsoft 針對資料、身分識別和裝置的下列三層保護建議：

- 基準保護

- 敏感度保護

- 高敏感度保護

如需這些層級和每道層級的建議功能詳細資訊，請參閱下列資源。

- [Office 365 的身分識別與裝置保護](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [Office 365 的檔案保護方案](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="three-tiers-at-a-glance"></a>三層保護概覽

下表摘要列出每一層的設定。 您可以使用這些設定作為建議的起點，並依據組織需求調整設定。 您可能不需要有每一層。

||基準線 (公開)|基準線 (私人)|敏感性|高敏感度|
|:-----|:-----|:-----|:-----|:-----|
|私人或公用的小組|公開|Private|Private|Private|
|誰可以存取？|組織中所有人，包括 B2B 使用者。|僅限小組的成員。 其他人可以要求存取相關聯的網站。|僅限小組的成員。|僅限小組的成員。|
|私人頻道|擁有者和成員可以建立私人頻道|擁有者和成員可以建立私人頻道|只有擁有者可以建立私人頻道|只有擁有者可以建立私人頻道|
|網站層級的來賓存取|**新的及現有的來賓** (預設值)。|**新的及現有的來賓** (預設值)。|**新的及現有的來賓**或**只有貴組織中的人員** (視小組需求而定)。|**新的及現有的來賓**或**只有貴組織中的人員** (視小組需求而定)。|
|網站共用設定|**網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站**。|**網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站**。|**網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站**。|**只有網站擁有者可以共用檔案、資料夾和網站**。<br>存取要求**關閉**。|
|網站層級未受管理的裝置存取|**從傳統型應用程式、行動裝置應用程式與 Web 進行完整存取** (預設值)。|**從傳統型應用程式、行動裝置應用程式與 Web 進行完整存取** (預設值)。|**允許僅限 Web 的受限存取**。|**封鎖存取**。|
|預設的共用連結類型|**[只有貴組織中的人員]**|**[只有貴組織中的人員]**|**特定人員**|**具有現有存取的人員**|
|敏感度標籤|無|無|用來分類小組和控制來賓共用與未受管理裝置存取的敏感度標籤。|用來分類小組和控制來賓共用與未受管理裝置存取的敏感度標籤。 標籤也可以在檔案上用來加密檔案。|

高敏感度選項的變體[擁有安全性隔離的小組](secure-teams-security-isolation.md)會為一個小組使用唯一的敏感度標籤，以提供額外的安全性。 您可以使用此標籤來加密檔案，而且只有該小組的成員才能讀取這些檔案。

基準保護包含公用和私人小組。 公開小組可供組織中的任何人探索及存取。 私人小組則僅供小組成員探索及存取。 這兩種設定都會將相關聯 SharePoint 網站的共用功能限制為只有小組擁有者能使用，以協助權限的管理。

敏感度和高敏感度保護的小組則是私人小組，其共用和要求相關聯網站存取權的功能會受到限制，而且會使用敏感度標籤來設定關於來賓共用、裝置存取和內容加密的原則。

## <a name="sensitivity-labels"></a>敏感度標籤

敏感度和高敏感度層會使用敏感度標籤來協助保護小組及其檔案。 若要實作這些保護層，您必須啟用[敏感度標籤來保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

雖然基準層不需要敏感度標籤，但請考慮建立「一般」標籤，然後要求所有小組都要套用標籤。 這可協助確保使用者在建立小組時能注意到其選擇的敏感度。 如果您打算部署敏感度或高敏感度層，建議您建立「一般」標籤，以供用於基準小組和不敏感的檔案。

如果您不熟悉如何使用敏感度標籤，建議您閱讀[開始使用敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels)以便開始使用。 

如果您已在組織中部署敏感度標籤，請考慮敏感度和高敏感度層所用的標籤與您整體標籤策略的配適程度。 

## <a name="sharing-the-sharepoint-site"></a>共用 SharePoint 網站

每個小組都會有相關聯的 SharePoint 網站，並且會於其中儲存文件。 (這是小組頻道中的 [檔案]**** 索引標籤)。SharePoint 網站會保留自己的權限管理，但會連結至小組權限。 小組擁有者會作為網站擁有者而包含在內，小組成員則會作為相關聯網站的網站成員而包含在內。

所產生的權限允許：

- 小組擁有者可以管理網站並對網站內容擁有完全控制的權限。
- 小組成員可以建立和編輯網站上的檔案。 

根據預設，小組的擁有者和成員可以與非小組人員共用網站本身，而不需實際將這些人新增至小組。 建議您不要使用此方法，因為這會讓使用者管理變得複雜，並可能會導致非小組成員的人員能夠在小組擁有者不知情的情況下存取小組檔案。 為了避免發生這種情況，從基準保護層級起，建議您只允許擁有者能夠直接共用網站。

雖然小組沒有唯讀權限選項，但 SharePoint 網站有。 如果您有需要能夠檢視小組檔案但無法加以編輯的合作夥伴群組專案關係人，請考慮將這些人直接新增至具有讀取權限的 SharePoint 網站。

## <a name="sharing-files-and-folders"></a>共用檔案和資料夾

根據預設，小組的擁有者和成員都可以與非小組人員共用檔案和資料夾。 如果您允許了來賓共用功能，這些人可能包括組織外部的人員。 在這三層當中，我們都會更新預設的共用連結類型，以避免意外過度共用。 在高敏感度層中，我們將這類共用限制為只有小組擁有者能使用。

## <a name="guest-sharing"></a>來賓共用

如果您需要與組織外部人員共同作業，建議您設定 [SharePoint 和 OneDrive 與 Azure AD B2B 整合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)，以獲得最佳的共用和管理體驗。

小組來賓共用預設為關閉，不過 Office 365 群組 (小組成員資格儲存所在位置) 和 SharePoint 的共用則會開啟。 我們會在基準層開啟 Teams 共用，但如有需要，您可以使用敏感度標籤在敏感度和高敏感度層將其關閉。

敏感度標籤只會影響小組的來賓共用。 相關聯 SharePoint 網站的來賓共用設定是分開控制的，而且我們會讓您將敏感度和高敏感度層的設定保持一致。

在高敏感度層中，我們會設定敏感度標籤來加密套用此標籤的檔案。 如果您需要讓來賓能夠存取這些檔案，則必須在建立標籤時為來賓提供權限。

如果您需要與組織外部的人員共同作業，則強烈建議您讓基準層和敏感度或高敏感度層的來賓共用功能保持開啟。 比起在電子郵件訊息中以附件方式傳送檔案的體驗，Microsoft 365 中的來賓共用功能所提供的共用體驗更為安全且可受到控管。 其也降低了影子 IT 的風險，讓使用者無法使用未受到控管的消費性產品來與合法的外部共同作業者共用。

請參閱下列參考資料，為您的組織建立安全且有生產力的來賓共用環境：

- [與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)
- [在與組織外的人員共用檔案時，限制資訊意外暴露](share-limit-accidental-exposure.md)
- [建立安全的來賓共用環境](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>從未受管理的裝置存取

針對敏感度和高敏感度層，我們會針對有敏感度標籤的 SharePoint 內容限制存取權。 Azure AD 條件式存取提供了許多選項，可供您決定使用者存取 Microsoft 365 的方式，包括根據位置、風險、裝置合規性和其他因素的限制。 建議您閱讀[什麼是條件式存取？](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)，並考慮可能適合貴組織的其他原則。

## <a name="next-step"></a>後續步驟

首先要[設定基準層級的保護](configure-teams-baseline-protection.md)。 如有需要，您可以在基準之上再新增[敏感度保護](configure-teams-sensitive-protection.md)和[高敏感度保護](configure-teams-highly-sensitive-protection.md)。

## <a name="see-also"></a>另請參閱

[Microsoft Teams 中的安全性與合規性](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[安全性與合規性中心的警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)
