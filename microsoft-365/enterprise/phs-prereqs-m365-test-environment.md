---
title: 身分識別與裝置存取 - 您的 Microsoft 365 測試環境中密碼雜湊同步處理的先決條件
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境，以使用密碼雜湊同步處理驗證的先決條件測試身分識別與裝置存取。
ms.openlocfilehash: 274f73b1cd6a925b972ab14417c9d854c48c2f00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074153"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>身分識別與裝置存取 - 您的 Microsoft 365 測試環境中密碼雜湊同步處理的先決條件

[身分識別與裝置存取組態](microsoft-365-policies-configurations.md)是一組組態和條件式存取原則，用來保護對與 Azure Active Directory (Azure AD) 整合之所有服務的存取，包括 Microsoft 365 企業版中的 Office 365 和 Enterprise Mobility + Security (EMS)。

本文說明如何設定符合[具有密碼雜湊同步處理的 Active Directory 先決條件組態](identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的 Microsoft 365 測試環境。

設定此測試環境有八個階段：

1.  使用密碼雜湊同步處理測試環境建立模擬企業
2.  設定 Azure AD 無縫單一登入
3.  設定具名位置
4.  設定密碼回寫
5.  為所有使用者帳戶設定自助式密碼重設
6.  為所有使用者帳戶設定多重要素驗證
7.  啟用 Azure AD Identity Protection
8.  為 Exchange Online 和商務用 Skype Online 啟用新式驗證

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>階段 1：使用密碼雜湊同步處理 Microsoft 365 測試環境建立模擬企業

遵循[密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。
以下是所產生的組態。

![使用密碼雜湊同步處理測試環境的模擬企業](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>階段 2：設定 Azure AD 無縫單一登入

遵循[測試實驗室指南 Azure AD 無縫單一登入階段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的指示。

## <a name="phase-3-configure-named-locations"></a>階段 3：設定具名位置

首先，判斷組織使用的公用 IP 位址或位址範圍。

接下來，遵循[在 Azure Active Directory 中設定具名位置](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的指示，新增位址或位址範圍做為具名位置。 

## <a name="phase-4-configure-password-writeback"></a>階段 4：設定密碼回寫

遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。

## <a name="phase-5-configure-self-service-password-reset"></a>階段 5：啟用自助式密碼重設

遵循[測試實驗室指南密碼重設階段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的指示。 

為特定 Azure AD 群組中的帳戶啟用重設密碼時，請將下列帳戶新增至**重設密碼**群組：

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

## <a name="phase-7-enable-azure-ad-identity-protection"></a>階段 7：啟用 Azure AD Identity Protection

遵循[測試實驗室指南 Azure AD Identity Protection 階段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection) 中的指示。 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>階段 8：為 Exchange Online 和商務用 Skype Online 啟用新式驗證

若為 Exchange Online，請遵循[這些指示](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)。 

若為商務用 Skype Online：

1. 連線到[商務用 Skype Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

2. 執行此命令。

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. 使用此命令以確認變更是否成功。

  ```
  Get-CsOAuthConfiguration
  ```

結果會是符合[具有密碼雜湊同步處理的 Active Directory 先決條件組態](identity-access-prerequisites.md#prerequisites)需求、用於身分識別與裝置存取的測試環境。 

## <a name="next-step"></a>下一步

使用[一般身分識別與裝置存取原則](identity-access-policies.md)來設定根據先決條件建置的原則，並保護身分識別與裝置。

## <a name="see-also"></a>請參閱

[其他身分識別測試實驗室指南](m365-enterprise-test-lab-guides.md#identity)

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
