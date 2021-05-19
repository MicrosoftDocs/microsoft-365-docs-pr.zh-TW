---
title: 在 Microsoft 365 群組、Teams 及 SharePoint 中管理存取權
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 瞭解如何在 Microsoft 365 群組、Teams 及 SharePoint 中管理存取。
ms.openlocfilehash: 3e0485813a264fe9042e0de9596ba07e50ef72a3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538144"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>在 Microsoft 365 群組、Teams 及 SharePoint 中管理存取權

有許多控制項可讓您控制人員在群組、小組和 SharePoint 中存取資源的方式。 請查看這些選項，並考慮其如何對應至您的業務需求、資料敏感度，以及您的使用者需要共同作業的人員範圍。

下表提供 Microsoft 365 中可用之存取控制的快速參考。 以下各節提供進一步的資訊。

|類別|描述|參考|
|:-------|:----------|:--------|
|[成員資格]|||
||個人小組探索|[管理 Microsoft Teams 中的私營小組探索](/microsoftteams/manage-discovery-of-private-teams)|
||根據規則的動態群組成員資格|[在 Azure Active Directory 中建立或更新動態群組](/azure/active-directory/users-groups-roles/groups-create-rule)|
||控制誰可以共用檔案、資料夾及網站。|[設定及管理存取要求](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|條件式存取|||
||多重要素驗證|[Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)|
||根據群組、小組或網站敏感度來控制裝置存取。|[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)|
||限制未受管理裝置的網站存取。|[控制從非管理裝置 SharePoint 存取](/sharepoint/control-access-from-unmanaged-devices)|
||根據位置控制網站存取|[根據網路位置控制對 SharePoint 和 OneDrive 資料的存取](/sharepoint/control-access-based-on-network-location)|
|來賓存取|||
||允許或封鎖 SharePoint 從指定的網域共用。|[依網域限制 SharePoint 和 OneDrive 內容的共用](/sharepoint/restricted-domains-sharing)|
||允許或封鎖來自指定網域的小組或群組成員資格。|[允許或封鎖邀請來自特定組織的 B2B 使用者](/azure/active-directory/b2b/allow-deny-list)|
||阻止匿名共用。|[關閉 [任何人] 連結](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||控制匿名存取連結的許可權。|[設定任何人的連結許可權連結](./best-practices-anonymous-sharing.md#set-link-permissions)|
||控制匿名共用連結的到期。|[設定任何人連結的到期日](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||根據預設，控制使用者顯示的共用連結類型。|[變更網站的預設連結類型](/sharepoint/change-default-sharing-link)|
||限制對特定人員的外部共用。|[限制對指定安全性群組的外部共用](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||根據資訊敏感度，控制對群組、小組或網站的來賓存取。|[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)|
||關閉 [共用選項]。|[在 Microsoft 365 中限制共用](./microsoft-365-limit-sharing.md)|
|使用者管理|||
||定期查看小組和群組成員資格。|[何謂 Azure AD access 評論？](/azure/active-directory/governance/access-reviews-overview)|
||將存取管理自動化至群組和團隊。|[何謂 Azure AD 的權利管理？](/azure/active-directory/governance/entitlement-management-overview)|
||允許或封鎖人員在 Teams 中建立專用通道。|[在 Microsoft Teams 中管理專用通道的生命週期](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>[成員資格]

小組和群組的成員資格是由擁有者所控制。 成員可以邀請其他人，但邀請會傳送給擁有者以供核准。 雖然組織中的任何人都會發現公用團隊和群組，但您可以控制是否可探索私人團隊和群組：

- [管理 Microsoft Teams 中的私營小組探索](/microsoftteams/manage-discovery-of-private-teams)

您可以根據某些準則（例如部門），以動態方式管理群組或小組的成員資格。 在此情況下，成員和擁有者無法邀請人員加入小組。 動態群組會使用您在 Azure Active Directory 中定義的中繼資料，以控制群組的成員。 請確定您使用的中繼資料是完整的，且最新的是不正確的中繼資料，可能會導致使用者無法使用群組或加入不正確的使用者。

- [在 Azure Active Directory 中建立或更新動態群組](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint 網站可讓您加入群組或小組成員資格以外的人員、成員及訪客之外的功能。 視您的需求而定，您可能會想要限制誰可以邀請人員加入網站。 此外，根據特定網站中資訊的靈敏度，您可能想要限制誰可以共用檔案和資料夾。 這些限制是由小組、群組或網站擁有者所設定：

- [設定及管理存取要求](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>條件式存取

透過 Microsoft 365，您可以對組織內部和外部的人員要求多重要素驗證。 有許多選項會提示使用者輸入第二個驗證因素的情況。 強烈建議您為組織部署多重要素驗證：

- [Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)

如果您的某些群組和小組有機密資訊，您可以根據群組或小組的靈敏度標籤強制執行裝置管理原則。 您可以完全封鎖非受管理裝置的存取，或僅允許有限的 web 存取：

- [使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)

在 SharePoint 中，您可以限制特定網路位置的網站存取權。

- [根據網路位置控制對 SharePoint 和 OneDrive 資料的存取](/sharepoint/control-access-based-on-network-location)


其他資源：

- [規劃條件式存取部署](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune 概述](/mem/intune/fundamentals/what-is-intune)

- [控制從非管理裝置 SharePoint 存取](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>來賓存取

您可以根據電子郵件地址的網域來限制來賓。 SharePoint 提供整個組織和網站特有的網域限制設定。 群組和 Teams 使用 Azure AD 中的網域允許和拒絕清單。 請務必設定這兩項設定，以避免不必要的共用，並確保一致的使用者體驗：

- [依網域限制 SharePoint 和 OneDrive 內容的共用](/sharepoint/restricted-domains-sharing)

- [允許或封鎖邀請來自特定組織的 B2B 使用者](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 允許使用共用連結的 *任何人* 匿名共用檔案和資料夾。 可以轉寄 *任何人* 的連結，且具有連結的任何人都可以存取共用專案。 視您的資料敏感度而定，請考慮如何使用 *任何使用任何* 連結的連結-包括完全關閉，將連結許可權限制為唯讀，或為其設定到期時間：

- [關閉 [任何人] 連結](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [設定任何人的連結許可權連結](./best-practices-anonymous-sharing.md#set-link-permissions)

- [設定任何人連結的到期日](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

共用檔案或資料夾時，使用者可以選擇數種連結類型。 若要降低意外共用不當的風險，您可以變更使用者共用時呈現給使用者的預設連結類型。 例如，從 [ *任何人* ] 連結（可讓 *您的組織連結中* 的「匿名存取人員」）變更預設值，可降低敏感資訊不需要的外部共用共用風險。

- [變更網站的預設連結類型](/sharepoint/change-default-sharing-link)

如果您的組織有需要與來賓共用的機密資料，但您卻擔心不適當的共用，您可以將檔案和資料夾的外部共用限制于指定之安全性群組的成員。 如此一來，您就可以限制外部與特定人員群組共用，或要求您的使用者在將其新增至安全性群組之前，先進行適當的外部共用訓練：

- [限制對指定安全性群組的外部共用](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

群組和 Teams 具有允許或拒絕來賓存取的組織層級設定。 雖然您可以 [使用 Microsoft PowerShell 限制對特定小組或群組的 guest 存取](per-group-guest-access.md)，但我們建議您透過敏感度標籤來執行此動作。 使用靈敏度標籤，您可以根據所套用的標籤自動允許或拒絕來賓存取：

- [使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)

在您經常邀請客人加入群組和小組的環境中，請考慮設定定期進行的「來賓存取」複查。 系統會提示擁有者查看群組和小組中的客人，以及核准或拒絕存取權。

- [設定來賓存取權檢閱](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 提供許多不同的共用資訊方法。 如果您有機密資訊，而且想要限制共用的方式，請參閱限制共用的選項：

- [在 Microsoft 365 中限制共用](./microsoft-365-limit-sharing.md)

其他資源：

- [使用 Microsoft 365 設定安全的共同作業](./setup-secure-collaboration-with-teams.md)

- [與未驗證使用者共用檔案和資料夾的最佳做法](./best-practices-anonymous-sharing.md)

- [在與組織外的人員共用檔案時，限制資訊意外暴露](./share-limit-accidental-exposure.md)

- [建立安全的來賓共用環境](./create-secure-guest-sharing-environment.md)

- [啟用 B2B 外部共同作業，並管理誰可以邀請來賓](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>使用者管理

當組織中的群組和團隊演變時，很好的作法是定期查看小組和群組成員資格。 對於具有變更成員資格的小組和群組、包含機密資訊的小組和群組，或包含來賓的小組和群組，這可能特別有用。 請考慮為這些小組和群組設定存取權檢查：

- [何謂 Azure AD access 評論？](/azure/active-directory/governance/access-reviews-overview)

許多組織都與其他組織或主要廠商合作，其深度共同合作。 在這些案例中管理使用者管理和存取資源的難度很困難。 請考慮自動化部分使用者管理工作，甚至將部分轉移至夥伴組織：

- [何謂 Azure AD 的權利管理？](/azure/active-directory/governance/entitlement-management-overview)

Teams 中的私人通道允許範圍內的交談和小組成員的子集間的檔案共用。 視您的特定業務需求而定，您可能會想要允許或封鎖此功能。

- [Microsoft Teams 中的專用通道](/MicrosoftTeams/private-channels)

- [在 Microsoft Teams 中管理專用通道的生命週期](/MicrosoftTeams/private-channels-life-cycle-management)

其他資源：

- [Azure Active Directory身分識別管理](/azure/active-directory/governance)

## <a name="related-topics"></a>相關主題

[共同作業管理規劃逐步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[建立共同作業管理計畫](collaboration-governance-first.md)

[Microsoft Teams 中的安全性與合規性](/microsoftteams/security-compliance-overview)

[在 SharePoint 中管理共用設定](/sharepoint/turn-external-sharing-on-or-off)

[在 Yammer 中建立及管理外部網路](/yammer/work-with-external-users/create-and-manage-an-external-network)

[為 Teams 設定三層保護](./configure-teams-three-tiers-protection.md)