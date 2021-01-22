---
title: 允許來賓和外部使用者 B2B 存取的身分識別與裝置存取政策 - 適用于企業使用者的 Microsoft 365 |Microsoft Docs
description: 說明建議的條件式存取和相關策略，以保護來賓和外部使用者的存取。
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932607"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>允許來賓存取和 B2B 外部使用者存取的策略

本文將討論調整建議的裝置和身分識別存取策略，以允許擁有 Azure Active Directory (Azure AD) 企業對企業 (B2B) 帳戶的來賓和外部使用者存取。 本指引以一 [般身分識別與裝置存取策略為根據](identity-access-policies.md)。

這些建議是設計成 **適用于基礎保護** 層級。 但您也可以根據您的特定需求調整對敏感和高度受規範 **之保護的建議**。 

提供 B2B 帳戶與 Azure AD 租使用者進行驗證的路徑，不會讓這些帳戶存取整個環境。 B2B 使用者及其帳戶可以存取服務和資源，例如檔案，可條件式存取策略與使用者共用。

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>更新共同策略以允許及保護來賓與外部使用者存取

此圖表顯示針對 B2B 來賓和外部使用者存取，在一般身分識別與裝置存取策略之間新增或更新哪些策略。

[![保護來賓存取之策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[查看此影像的較大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

下表列出您需要建立及更新的策略。 共同策略會連結至共同身分識別與裝置存取策略文章中的相關 [組組](identity-access-policies.md) 指示。

|保護層級|原則|其他相關資訊|
|---|---|---|
|**Baseline**|[一向要求來賓和外部使用者使用 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|建立此新策略，並設定： <ul><li>針對 **指派>** 包括使用者>群組，選擇選取使用者和群組，然後選取所有 **來賓和外部使用者**。</li><li>針對 **>與**>，請取消核>所有選項，以在 MFA 中一 (多重要素驗證) 。</li></ul>|
||[當登錄風險中或高 *時需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|修改此策略以排除來賓和外部使用者。|
||[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|修改此策略以排除來賓和外部使用者。|

若要在條件式存取策略中納入或排除來賓和外部使用者，請針對工作分派>使用者和群組>**包括** 或排除，請勾選所有 **來賓和外部使用者**。

![排除來賓和外部使用者之控制項的螢幕畫面](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>其他相關資訊

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>使用 Microsoft Teams 的來賓和外部使用者存取權

Microsoft Teams 定義下列使用者：

- **來賓存取** 會使用 Azure AD B2B 帳戶，可新增為團隊的成員，並存取團隊的通訊和資源。

- **外部存取** 適用于沒有 B2B 帳戶的外部使用者。 外部使用者存取包含邀請、通話、聊天和會議，但不包括團隊成員資格和團隊資源的存取權。

有關詳細資訊，請參閱團隊 [的來賓與外部使用者存取權之間的比較](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。

有關保護 Teams 的身分識別與裝置存取策略，請參閱保護 Teams 聊天、群組和檔案安全之政策 [建議](teams-access-policies.md)。

### <a name="require-mfa-always-for-guest-and-external-users"></a>一向要求來賓和外部使用者使用 MFA

此政策會提示來賓在租使用者中註冊 MFA，不論他們是否已在家庭租使用者中註冊 MFA。 存取您租使用者中的資源時，來賓和外部使用者必須針對每個要求使用 MFA。

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>將來賓和外部使用者排除在風險型 MFA 之外

雖然組織可以針對使用 Azure AD 身分識別保護的 B2B 使用者強制執行以風險為基礎的策略，但是針對 B2B 共同合作使用者在資原始目錄中的身分識別，而其 Azure AD 身分識別保護的執行有一些限制。 由於這些限制，Microsoft 建議您將來賓排除在以風險為基礎的 MFA 政策外，並要求這些使用者永遠使用 MFA。

詳細資訊請參閱 [B2B 共同合作使用者身分識別保護的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。

### <a name="excluding-guests-and-external-users-from-device-management"></a>從裝置管理中排除來賓和外部使用者

只有一個組織可以管理裝置。 如果您不將來賓和外部使用者排除在需要裝置合規性的政策外，則那些政策會封鎖這些使用者。

## <a name="next-step"></a>下一步

![步驟 4：Microsoft 365 雲端應用程式政策](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

設定條件式存取策略：

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
