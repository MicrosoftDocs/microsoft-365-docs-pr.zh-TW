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
localization_priority: Priority
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
description: 了解如何為您的組織設定多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083535"
---
# <a name="set-up-multi-factor-authentication"></a>設定多重要素驗證
  
根據您對[多重因素驗證 (MFA) 及其在 Microsoft 365 中支援](multi-factor-authentication-microsoft-365.md)的了解，是時候進行設定並將其階段推出至您的組織了。

開始之前，請先判斷這些特殊條件是否適用於您，並採取適當的動作：

- 如果您在 Windows 裝置上安裝有 Office 2013 用戶端，請[啟用新式驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。

- 如果您使用 Active Directory 同盟服務 (AD FS) 搭配協力廠商目錄服務，請設定 Azure MFA 伺服器。 如需詳細資訊，請參閱 [Azure 多重因素驗證和協力廠商 VPN 解決方案搭配的進階腳本](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。

將會在需要時向所有其他使用者要求執行其他驗證。 如需詳細資料，請造訪[雙因素驗證方法和設定](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)。

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>步驟 1 ：決定要求您使用者使用 MFA 的方法

> [!NOTE]
> 您必須是全域系統管理員才能設定或修改 MFA。 有三種方法可以要求您的使用者使用 MFA 登入。如需詳細資料，請參閱 [Microsoft 365 中的 MFA 支援](multi-factor-authentication-microsoft-365.md)。

- 安全性預設值 (建議給小型企業使用)

  如果您在 2019 年10 月 21 日之後購買訂閱或試用版，且未預期情況下提示您進行 MFA，則將自動為您的訂閱啟用[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。
  
  每一個新 Microsoft 365 訂閱都會自動開啟安全性預設值。 這表示每位使用者都必須設定 MFA，並在其行動裝置上安裝 Microsoft Authenticator 應用程式。

  所有使用者都必須使用 Microsoft Authenticator 應用程式做為其額外驗證方法，且舊版驗證會被封鎖。 

- 條件式存取原則 (建議用於企業) 

  使用者要在 MFA 註冊過程中選擇其他驗證方法。

- 依每一使用者帳戶 (不建議使用) 

  使用者要在 MFA 註冊過程中選擇其他驗證方法。

## <a name="step-2-test-mfa-on-your-pilot-users"></a>步驟 2： 對您的試驗使用者測試 MFA

如果您使用的是條件式存取原則或依每位使用者 MFA (不建議使用)，請選取您企業或組織中的試驗使用者來測試 MFA 註冊和登入。例如：

- 若要設定條件式存取原則，請建立試驗使用者群組，以及要求將 MFA 用於群組成員和所有應用程式的原則。 然後，將您的試驗使用者帳戶新增至群組中。

- 針對依每一名使用者 MFA，請一次為一名試驗使用者的使用者帳戶啟用 MFA。

與您的試驗使用者共同解決問題，以準備好順暢階段推出給對組織。

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>步驟 3： 通知組織 MFA 即將來臨

您可以使用電子郵件通知、走道海報、小組會議或正式訓練，以確保員工了解：

- 為什麼需要 MFA 才能登入
- [如何註冊以取得其他驗證方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [註冊之後如何登入](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [如何變更其他驗證方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [如何處理新智慧型手機等狀況](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

最重要的是，請確認您的員工了解***何時將要實施 MFA 需求***，以免使其措手不及。

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>步驟 4： 向貴組織或使用者階段推出 MFA 需求

根據您所選擇的 MFA 需求方法，將 MFA 驗證階段推出至試驗測試人員以外的員工。

### <a name="security-defaults"></a>安全性預設

您可以在 Azure 入口網站中的 Azure Active Directory (Azure AD) **屬性**窗格中，啟用或停用安全性預設值。

1.  使用全域系統管理員憑證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
2.  移至 [Azure Active Directory - [屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
3.  在頁面底部，選取 [管理安全性預設]****。
4.  選擇 [是]**** 可啟用安全性預設，以及 [否]**** 可停用安全性預設，然後選擇 [儲存]****。

如果您一直是使用[基準條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，以下是移轉為使用安全性預設值的方法。

1.  移至 [條件式存取原則][](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 頁面。
2.  選擇每個**開啟**的基準原則，並將**啟用原則**設定為**關閉**。
2.  移至 [Azure Active Directory - [屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4.  在頁面底部，選取 [管理安全性預設]****。
5.  選擇 [是]**** 可啟用安全性預設，以及 [否]**** 可停用安全性預設，然後選擇 [儲存]****。

### <a name="conditional-access-policies"></a>條件式存取原則

建立、設定及啟用適當的原則，以納入需要進行 MFA 登入的使用者群組。

### <a name="per-user-mfa-not-recommended"></a>依每一使用者 MFA (不建議使用) 

針對您的階段推出，為使用者帳戶啟用 MFA 功能。

### <a name="supporting-your-employees"></a>支援您的員工

當員工註冊並開始使用 MFA 登入時，請確認您的 IT 專家、IT 部門或服務支援人員能迅速回答問題並解決問題。

請參閱這篇文章，以取得有關[如何疑難排解 MFA 登入的資訊](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)。 


