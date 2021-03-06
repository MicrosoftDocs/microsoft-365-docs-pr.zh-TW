---
title: 為使用者設定多重要素驗證
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何為您的組織設定多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: 7ee6f3a7fc01fa998e3b984683ddad1402fe5587
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393616"
---
# <a name="set-up-multifactor-authentication"></a>設定多重要素驗證

根據您對[多重因素驗證 (MFA) 及其在 Microsoft 365 中支援](multi-factor-authentication-microsoft-365.md)的了解，是時候進行設定並將其階段性推出至您的組織了。

> [!IMPORTANT]
> 如果您在 2019 年10 月 21 日之後購買訂閱或試用版，且在您登入時，提示您進行 MFA，則將自動為您的訂閱啟用[安全性預設值](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

## <a name="before-you-begin"></a>開始之前

- 您必須是全域系統管理員才能管理 MFA。 如需詳細資訊，請參閱[系統管理員角色](../add-users/about-admin-roles.md)。
- 如果您已開啟舊版每一使用者 MFA，請 [關閉舊版每一使用者 MFA](#turn-off-legacy-per-user-mfa)。
- 如果您在 Windows 裝置上安裝有 Office 2013 用戶端，請[開啟 Office 2013 用戶端新式驗證](./enable-modern-authentication.md)。
- 進階：如果您使用 Active Directory 同盟服務 (AD FS) 搭配協力廠商目錄服務，請設定 Azure MFA Server。 如需詳細資訊，請參閱[使用 Azure AD Multifactor Authentication 和協力廠商 VPN 解決方案的進階案例](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) (部分機器翻譯)。

## <a name="turn-security-defaults-on-or-off"></a>開啟或關閉安全性預設值

大部分的組織，安全性預設值皆提供有良好的額外登入安全性。 如需詳細資訊，請參閱[什麼是安全性預設？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果您新訂閱，則系統可能會自動為您開啟安全性預設值。

您可以在 Azure 入口網站中的 Azure Active Directory (Azure AD) **屬性** 窗格中，啟用或停用安全性預設值。

1. 使用全域系統管理員憑證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
2. 在左側導覽中，請選擇 **[顯示所有]**，然後在 **[系統管理中心]** 底下，選擇 **[Azure Active Directory]**。
3. 在 **[Azure Active Directory 系統管理中心]** 選擇 **[Azure Active Directory**\>**屬性**]。
4. 在頁面底部，選取 **[管理安全性預設]**。
5. 選擇 **[是]** 以啟用安全性預設，或 **[否]** 以停用安全性預設，然後選擇 **[儲存]**。

如果您使用的是[基準條件式存取原則](/azure/active-directory/conditional-access/concept-baseline-protection)，則會在您移往使用安全性預設之前，提示您將之關閉。

1. 移至 [[條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 頁面。
2. 選擇每個 **開啟** 的基準原則，並將 **啟用原則** 設定為 **關閉**。
3. 移至 [Azure Active Directory - [屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4. 在頁面底部，選取 **[管理安全性預設]**。
5. 選擇 **[是]** 可啟用安全性預設，以及 **[否]** 可停用安全性預設，然後選擇 **[儲存]**。

## <a name="use-conditional-access-policies"></a>使用 [條件式存取] 原則

如果貴組織有更仔細的登入安全需求，[條件式存取] 原則可讓您有更多控制權。 [條件式存取] 允許您建立並定義原則条件，在使用人被授權對應用程式或服務的存取之前反應登入事件和請求附加操作。

> [!IMPORTANT]
> 在啟用條件式存取原則之前，請關閉 [每一使用者 MFA] 和 [安全性預設]。

購買 Azure AD Premium P1 的客戶或含此授權的授權（例如 Microsoft 365 商務版 Premium）和 Microsoft 365 E3 皆可使用條件式存取。 如需詳細資訊，請參閱[建立 [條件式存取] 原則](/azure/active-directory/authentication/tutorial-enable-azure-mfa)。

透過 Azure AD Premium P2 授權或含此授權的授權 (例如 Microsoft 365 E5) 可使用風險型條件式存取。 如需詳細資訊，請參閱 [風險型 [條件式存取]](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)。

如需有關 Azure AD P1 和 P2 的詳細資訊，請參閱 [Azure Active Directory 定價](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="turn-on-modern-authentication-for-your-organization"></a>為您的組織開啟 [新式] 驗證。

對於多數訂閱，新式驗證會自動開啟，但如果您在 2017 年 8 月之前購買訂閱，可能需要開啟新式驗證，才能讓多重要素驗證之類的功能在 Windows 用戶端 (例如 Outlook) 中運作。


1. 在 Microsoft 365 系統管理中心，於左側導覽中選擇 **[設定]** \> **[組織設定]**。
2. 在 **[服務]** 索引標籤底下，選擇 **[新式驗證]**，然後在 **[新式驗證]** 窗格中，確保 **[啟用新式驗證]** 已選取。 選取 **[儲存變更]**。

### <a name="turn-off-legacy-per-user-mfa"></a>關閉舊版的每一使用者 MFA

如果您先前已開啟每一使用者 MFA，您必須先將它關閉才能啟用安全性預設。

1. 在 Microsoft 365 系統管理中心，在左側導覽中選擇 **[使用者]**\> **[使用中的使用者]**。
1. 在 **[使用中的使用者]** 頁面中，選擇 **[多重要素驗證]**。
1. 在多重要素驗證頁面上，選取每個使用者並將其 [多重要素驗證] 狀態設為 **停用**。

## <a name="next-steps"></a>後續步驟

- [如何註冊以取得其他驗證方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [什麼是多重要素驗證](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [註冊之後如何登入](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [如何變更其他驗證方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a>相關內容

[開啟多重要素驗證](../../business-video/turn-on-mfa.md) (影片)\
[為您的手機開啟多重要素驗證](../../business-video/set-up-mfa.md) (影片)