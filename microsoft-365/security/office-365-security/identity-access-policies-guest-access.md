---
title: 允許來賓和外部 B2B 存取的身分識別和裝置存取原則-Microsoft 365 for enterprise |Microsoft 檔
description: 描述建議的條件式存取和相關原則，以保護來賓和外部使用者的存取。
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
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
ms.openlocfilehash: 4a0eb530df2709294bf1c9aa0cf285e59c9fd1f8
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464201"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>允許來賓和外部 B2B 存取的原則

本文說明如何調整建議的常見身分識別和裝置存取原則，以允許來賓和具有 Azure Active Directory (Azure AD) 企業對企業 (B2B) 帳戶存取權的來賓和外部使用者存取。 本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。

這些建議適用于保護的 **基準** 層。 不過，您也可以依據 **敏感** 和 **高管制** 保護的需求細微性來調整建議。 

提供 B2B 帳戶的路徑，以與您的 Azure AD 租使用者進行驗證，不會讓這些帳戶存取您的整個環境。 B2B 使用者和其帳戶只能存取與其共用的資源 (例如，在條件式存取原則中授與服務內) 的檔案。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>更新共同原則以允許及保護來賓和外部存取 

為了使用 Azure AD B2B 帳戶來保護來賓和外部存取，下列圖表說明要從通用身分識別和裝置存取原則中新增或更新的原則。 

[![保護來賓存取的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[查看較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

下表列出您需要建立和更新的原則。 通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。

|保護層級|原則|其他相關資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[需要對來賓和外部使用者永遠進行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|建立這個新原則，並設定下列專案： <ul><li> 若為 **> 使用者和群組 > 包含的工作分派**，請選擇 [ **選取使用者和群組**]，然後選取 [ **所有來賓和外部使用者**]。 </li><li> **> 條件的工作分派 > 登入**，請將所有選項保留未勾選狀態，以永遠強制執行多重要素驗證 (MFA) 。</li>|
|        |[當登入風險為*中*或*高*時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|修改此原則，以排除來賓和外部使用者。|
|        |[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|修改此原則，以排除來賓和外部使用者。|

若要在條件式存取原則中包含或排除來賓和外部使用者，針對 **> 使用者和群組 > 包含** 或 **排除**的工作分派，請檢查 **所有來賓和外部使用者**。

![用於排除來賓和外部使用者之控制項的畫面捕獲](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>其他相關資訊

### <a name="guest-and-external-access-with-microsoft-teams"></a>Microsoft 小組的來賓和外部存取

Microsoft 小組定義下列專案：

- **來賓存取** 使用 Azure AD B2B 帳戶，可將其新增為小組成員，並擁有對該小組之通訊和資源的所有專屬許可權存取權。

- **外部存取** 適用于沒有 B2B 帳戶的外部使用者。 外部存取可以包含邀請，並參與通話、聊天和會議，但不包括小組成員資格和對小組資源的存取。

如需詳細資訊，請參閱「 [來賓」和「外部存取」小組之間的比較](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。

條件式存取原則只適用于小組中的來賓存取，因為有對應的 Azure AD B2B 帳戶。

請參閱 [保護小組聊天、群組和檔案的原則建議](teams-access-policies.md) ，以取得安全小組身分識別與裝置存取原則的詳細資訊。

### <a name="require-mfa-always-for-guest-and-external-users"></a>需要對來賓和外部使用者永遠進行 MFA
此原則會提示客人在您的租使用者中註冊 MFA，不論他們是否已在其主承租人中為 MFA 註冊。 當存取您租使用者中的資源時，來賓和外部使用者必須針對每個要求使用 MFA。 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>從風險型 MFA 排除來賓和外部使用者
雖然組織可以對使用 Azure AD 身分識別保護的 B2B 使用者強制執行風險原則原則，但由於其內部目錄中的現有身分識別，對資原始目錄中 B2B 共同作業使用者執行 Azure AD 身分識別保護有一些限制。 由於這些限制，Microsoft 建議您從以風險為基礎的 MFA 原則中排除來賓使用者，並要求這些使用者永遠使用 MFA。 

如需詳細資訊，請參閱 [B2B 協同作業使用者的身分識別保護限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。 

### <a name="excluding-guest-and-external-users-from-device-management"></a>從裝置管理排除來賓和外部使用者 
只有一個組織可以管理裝置。 如果您未從需要裝置規範的原則中排除來賓和外部使用者，這些原則將會封鎖這些使用者。 

## <a name="next-step"></a>下一步

![步驟4： Microsoft 365 雲端應用程式的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

為下列專案設定條件式存取原則：

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)

