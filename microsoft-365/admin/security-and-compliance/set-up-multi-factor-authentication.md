---
title: 為使用者設定多重要素驗證
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 瞭解如何為您的組織設定多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: b0fd16fc74319c88a6f91bf56ac96346915c35ac
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049757"
---
# <a name="set-up-multi-factor-authentication"></a>設定多重要素驗證
  
根據您對[Microsoft 365 中的多重要素驗證（MFA）和支援](multi-factor-authentication-microsoft-365.md)的瞭解，您可以將它設定好，並將其部署至您的組織。

開始之前，請先確定這些特殊條件是否適用于您並採取適當的動作：

- 如果您有 Windows 裝置上的 Office 2013 用戶端，請[啟用新式驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。

- 如果您有使用 Active Directory Federation Services （AD FS）的協力廠商目錄服務，請設定 Azure MFA 伺服器。 如需詳細資訊，請參閱[使用 Azure Multi-Factor 驗證和協力廠商 VPN 解決方案的高級案例](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。

將會在需要時向所有其他使用者要求執行其他驗證。 如需詳細資訊，請造訪[兩要素驗證方法和設定](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)。

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>步驟1：決定要求使用者使用 MFA 的方法

> [!NOTE]
> 您必須是全域系統管理員，才能設定或修改 MFA。 有三種方式可要求使用者使用 MFA 進行登入。如需詳細資訊，請參閱[Microsoft 365 中的 MFA 支援](multi-factor-authentication-microsoft-365.md)。

- 安全性預設值（適用于小型企業的建議）

  如果您在2019年10月21日之後購買訂閱或試用版，且意外提示您進行 MFA，[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)會自動為您的訂閱啟用。
  
  每個新的 Microsoft 365 訂閱都會自動開啟安全性預設值。 這表示每位使用者都必須在其行動裝置上設定 MFA，並安裝 Microsoft 驗證應用程式。

  所有使用者都必須使用 Microsoft 驗證應用程式作為其他驗證方法，而且會封鎖舊版驗證。 

- 條件式存取原則（建議企業使用）

  使用者在 MFA 登記期間選擇其他驗證方法。

- 每個使用者帳戶（不建議）

  使用者在 MFA 登記期間選擇其他驗證方法。

## <a name="step-2-test-mfa-on-your-pilot-users"></a>步驟 2： 在試驗使用者上測試 MFA

如果您使用的是條件式存取原則或個別使用者 MFA （不建議使用），請在您的公司或組織中選取試驗使用者，以測試 MFA 註冊和登入。例如：

- 針對條件式存取原則，建立試驗使用者群組和需要 MFA 做為群組成員及所有應用程式的原則。 然後，將試驗使用者的帳戶新增至群組。

- 針對每一使用者 MFA，一次可對您的試驗使用者的使用者帳戶啟用 MFA。

請與您的試驗使用者合作，以解決問題，以準備您的組織的順利推出。

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>步驟 3： 通知組織即將推出 MFA

使用電子郵件通知、hallway 海報、小組會議或正式訓練，以確保您的員工瞭解：

- 為何登入需要 MFA
- [如何註冊以進行其他驗證方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [註冊後如何登入](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [如何變更其其他驗證方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [如何處理類似于新智慧型電話的情況](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

最重要的是，請確定您***的員工瞭解何時要強制執行 MFA 需求***，使其不會令人感到驚訝。

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>步驟 4： 向您的組織或使用者推出 MFA 需求

根據您所選擇的 MFA 需求方法，將 MFA 驗證向外推行您的試驗測試人員之外的員工。

### <a name="security-defaults"></a>安全性預設

您可以在 Azure 入口網站中，從 Azure Active Directory （Azure AD）的**屬性**窗格中啟用或停用安全性預設值。

1.  使用全域系統管理員認證登入[Microsoft 365 admin center](https://admin.microsoft.com) 。
2.  移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
3.  在頁面底部，選擇 [管理安全性預設]****。
4.  選擇 **[是]** 啟用安全性預設值，並選擇 [**否**] 以停用安全性預設值，然後選擇 [**儲存**]。

如果您已使用[基準條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，以下是您移至使用安全性預設值的方式。

1.  移至 [[條件式存取原則] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。
2.  選擇 [**開啟**的每一個基準原則]，並將 [**啟用原則**] 設定為 [**關閉**]。
2.  移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4.  在頁面底部，選擇 [管理安全性預設]****。
5.  選擇 **[是]** 啟用安全性預設值，並選擇 [**否**] 以停用安全性預設值，然後選擇 [**儲存**]。

### <a name="conditional-access-policies"></a>條件式存取原則

建立、設定及啟用適當的原則，其中包括需要 MFA 進行 MFA 的使用者群組。

### <a name="per-user-mfa-not-recommended"></a>每一使用者 MFA （不建議）

針對與您的部署對應的 MFA 啟用使用者帳戶。

### <a name="supporting-your-employees"></a>支援您的員工

當您的員工註冊並開始以 MFA 登入時，請確定您的 IT 專家、IT 部門或服務台可以快速解答問題並解決問題。

如需[疑難排解 MFA 登入的相關資訊](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)，請參閱本文。 


