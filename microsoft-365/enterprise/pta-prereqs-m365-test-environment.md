---
title: 身分識別與裝置存取 - 您的 Microsoft 365 測試環境中傳遞驗證的先決條件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境，以使用傳遞驗證的先決條件測試身分識別與裝置存取。
ms.openlocfilehash: f257b85672a1a1b27f600d145b1f9f3296b21980
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199846"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a>身分識別與裝置存取 - 您的 Microsoft 365 測試環境中傳遞驗證的先決條件

*此測試實驗室指南僅可用於企業測試環境的 Microsoft 365。*

身分[識別與裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)設定是一組設定和條件式存取原則，可保護對與 Azure Active Directory (Azure AD) 相關的 enterprise Microsoft 365 中所有服務的存取。

本文說明如何設定符合[傳遞驗證先決條件組態](../security/office-365-security/identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的 Microsoft 365 測試環境。

設定此測試環境有10個階段：

1. 使用傳遞驗證 Microsoft 365 測試環境建立模擬企業
2. 設定 Azure AD 無縫單一登入
3. 設定具名位置
4. 設定密碼回寫
5. 設定自助式密碼重設
6. 設定多重要素驗證
7. 啟用加入網域的 Windows 電腦的自動裝置註冊
8. 設定 Azure AD 密碼保護 
9. 啟用 Azure AD Identity Protection
10. 為 Exchange Online 和商務用 Skype Online 啟用新式驗證

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a>階段 1：使用傳遞驗證 Microsoft 365 測試環境建立模擬企業

遵循[傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。

以下是所產生的組態。

![使用傳遞驗證測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>階段 2：設定 Azure AD 無縫單一登入

遵循[測試實驗室指南 Azure AD 無縫單一登入階段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的指示。

## <a name="phase-3-configure-named-locations"></a>階段 3：設定具名位置

首先，判斷組織使用的公用 IP 位址或位址範圍。

接下來，遵循[在 Azure Active Directory 中設定具名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的指示，新增位址或位址範圍做為具名位置。 

## <a name="phase-4-configure-password-writeback"></a>階段 4：設定密碼回寫

遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。

## <a name="phase-5-configure-self-service-password-reset"></a>階段 5：啟用自助式密碼重設

遵循[測試實驗室指南密碼重設階段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的指示。 

為特定 Azure AD 群組中的帳戶啟用重設密碼時，請將下列帳戶新增至 **重設密碼** 群組：

- 使用者 2
- 使用者 3
- 使用者 4
- 使用者 5

僅對使用者 2 帳戶測試密碼重設。

## <a name="phase-6-configure-multi-factor-authentication"></a>階段 6：設定多重要素驗證

針對下列使用者帳戶，遵循[測試實驗室指南多重要素驗證階段 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 中的指示：

- 使用者 2
- 使用者 3
- 使用者 4
- 使用者 5

僅針對使用者 2 帳戶測試多重要素驗證。

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>階段7：啟用加入網域的 Windows 電腦的自動裝置註冊 

遵循[下列指示](/azure/active-directory/devices/hybrid-azuread-join-plan)，啟用已加入網域之 Windows 電腦的自動裝置註冊。

## <a name="phase-8-configure-azure-ad-password-protection"></a>階段8：設定 Azure AD 密碼保護 

請遵循 [這些指示](/azure/active-directory/authentication/concept-password-ban-bad) 來封鎖已知的弱密碼及其變種。

## <a name="phase-9-enable-azure-ad-identity-protection"></a>階段9：啟用 Azure AD 身分識別保護

遵循[測試實驗室指南 Azure AD Identity Protection 階段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的指示。 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>階段10：為 Exchange Online 和商務用 Skype 線上啟用新式驗證

若為 Exchange Online，請遵循[這些指示](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)。 

若為商務用 Skype Online：

1. 連線到[商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

2. 執行此命令。

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. 使用此命令以確認變更是否成功。

  ```powershell
  Get-CsOAuthConfiguration
  ```

結果會是符合[傳遞驗證先決條件組態](../security/office-365-security/identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的測試環境。 

## <a name="next-step"></a>下一步

使用[一般身分識別與裝置存取原則](../security/office-365-security/identity-access-policies.md)來設定根據先決條件建置的原則，並保護身分識別與裝置。

## <a name="see-also"></a>請參閱

[其他身分識別測試實驗室指南](m365-enterprise-test-lab-guides.md#identity)

[身分識別藍圖](identity-roadmap-microsoft-365.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)
