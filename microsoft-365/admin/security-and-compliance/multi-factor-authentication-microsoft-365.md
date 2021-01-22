---
title: Microsoft 365 的多重要素驗證
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解 Microsoft 365 中的多重要素驗證。
ms.openlocfilehash: 7d62d88acb5137bd0674de7a42b44103bc9fc5f0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926543"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Microsoft 365 的多重要素驗證

密碼是驗證電腦或線上服務之登錄的最常見方法，但也容易受到任何影響。 使用者可以選擇簡易密碼，並針對不同電腦和服務的多個登錄使用相同的密碼。

若要為 Sign-in 提供額外的安全性層級，您必須使用多重要素驗證 (MFA) ，它同時使用一個密碼 ，這個密碼應該很強，並且根據：

- 您擁有無法輕易複製的手機，例如智慧型手機。
- 您獨有的專案，例如指紋、臉部或其他指紋屬性。

驗證使用者密碼之後，才能使用額外的驗證方法。 使用 MFA 時，即使強使用者密碼遭到入侵，攻擊者並沒有您的智慧型手機或指紋才能完成該登錄。

## <a name="mfa-support-in-microsoft-365"></a>Microsoft 365 中的 MFA 支援

根據預設，Microsoft 365 和 Office 365 都支援使用：

- 一則文字訊息，會送到需要使用者輸入驗證碼的電話。
- 通話。
- Microsoft Authenticator 智慧型手機應用程式。

在這兩種情況下，MFA 的登錄都是使用「您擁有、不容易複製」的方法進行額外驗證。 啟用 Microsoft 365 和 Office 365 的 MFA 有多種方式：

- 使用安全性預設值
- 使用條件式存取策略
- 針對每個個別使用者帳戶 (不建議) 

這些方法是以您的 Microsoft 365 方案為基礎。

|方案|建議|客戶類型|
|---|---|---|
|所有 Microsoft 365 方案|使用安全性預設值，要求所有使用者帳戶使用 MFA。 <p> 您也可以針對個別使用者帳戶設定每個使用者 MFA，但不建議您這樣做。|小型企業|
|Microsoft 365 商務進階版 <p> Microsoft 365 E3 <p> Azure Active Directory (Azure AD) 進版 P1 授權|使用條件式存取策略，以根據群組成員資格、應用程式或其他準則要求使用者帳戶使用 MFA。|小型企業對企業|
|Microsoft 365 E5 <p> Azure AD Premium P2 授權|使用 Azure AD 身分識別保護來根據登錄風險準則要求 MFA。|企業|
||||

### <a name="security-defaults"></a>安全性預設

安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。 這些訂閱會開啟安全性預設值，其中：

- 需要所有使用者將 MFA 與 Microsoft Authenticator App 一同使用。
- 區塊舊版驗證。

使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。 14 天過後，使用者就無法登入，除非其完成 MFA 註冊。

安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。 您可以使用條件式存取策略來停用安全性預設值，以 MFA 為根據。

從 Azure 入口網站中 Azure  AD 的屬性窗格啟用或停用安全性預設值。

![目錄屬性頁面的圖片。](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

您可以在任何 Microsoft 365 方案使用安全性預設值。

如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

### <a name="conditional-access-policies"></a>條件式存取原則

條件式存取原則是一組規則，可指定要在什麼條件下評估和允許登入。 例如，您可以建立敘述如下的條件式存取原則：

- 如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。

此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。

您也可以使用條件式存取策略來使用進一步功能，例如要求特定 App 使用 MFA，或是在符合規範的裝置上完成該登錄，例如執行 Windows 10 的膝上型電腦。

您從 Azure 入口網站中的 Azure AD 安全性窗格設定條件式存取策略。

![條件式存取功能表選項的圖片](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

您可以將條件式存取策略用於：

- Microsoft 365 商務進階版
- Microsoft 365 E3 和 E5
- Azure AD Premium P1 和 Azure AD Premium P2 授權

對於使用 Microsoft 365 商務進版小型企業，您可以利用下列步驟輕鬆使用條件式存取政策：

1. 建立群組以包含需要 MFA 的使用者帳戶。
2. 啟用 **全域系統管理員的需要 MFA** 政策。
3. 使用這些設定建立以群組為基礎的條件式存取政策：
    - 指派>使用者和群組：上述步驟 1 的組名。
    - 指派>雲端 App 或動作：所有雲端 App。
    - 存取控制專案>授予>存取>需要多重要素驗證。
4. 啟用該政策。
5. 將使用者帳戶新增到上述步驟 1 中建立並測試的群組。
6. 若要要求其他使用者帳戶使用 MFA，請將其新增到步驟 1 中建立群組。

此條件式存取政策可讓您以自己的步調將 MFA 需求推出給使用者。

企業應該使用 [一般條件式存取策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) 來設定下列策略：

- [要求系統管理員使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [要求所有使用者使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

使用 Azure AD 身分識別保護，您可以建立額外的條件式存取策略，在有中或高之登錄風險時要求[MFA。](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)

您可以使用 Azure AD 身分識別保護與以風險為基礎的條件式存取策略，以執行：

- Microsoft 365 E5
- Azure AD Premium P2 授權

如需詳細資訊，請參閱這個 [Azure AD Identity Protection 概觀](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

### <a name="legacy-per-user-mfa-not-recommended"></a>不建議使用舊版每個使用者 MFA (MFA) 

您應該使用安全性預設值或條件式存取策略，要求使用者帳戶的登錄使用 MFA。不過，如果無法使用上述任一項，Microsoft 強烈建議擁有系統管理員角色的使用者帳戶使用 MFA，尤其是任何大小訂閱的全域系統管理員角色。

您從 Microsoft 365系統管理中心的使用中使用者窗格啟用個別使用者帳戶的 MFA。

![作用中使用者頁面上多重要素驗證選項的圖片](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

啟用後，下次使用者進行登錄時，系統會提示他們註冊 MFA，以及選擇並測試其他驗證方法。

### <a name="using-these-methods-together"></a>共同使用這些方法

下表顯示啟用 MFA 與安全性預設、條件式存取原則和每一使用者帳戶設定的結果。

||Enabled|停用|次要驗證方法|
|---|---|---|---|
|**安全性預設**|無法使用條件式存取策略|可以使用條件式存取原則|Microsoft Authenticator 應用程式|
|**條件式存取原則**|如果有任何啟用，您則無法啟用安全性預設值|如果已停用所有原則，則可啟用安全性預設|在註冊 MFA 期間由使用者指定|
|**不建議使用舊版每個使用者 MFA (MFA)**|會優先于安全性預設值和條件式存取策略，要求每一個登錄都使用 MFA|安全性預設值和條件式存取政策所覆蓋|在註冊 MFA 期間由使用者指定|
||||

如果已啟用安全性預設值，系統會提示所有新使用者進行 MFA 註冊，以及下一次使用 Microsoft Authenticator App。

## <a name="ways-to-manage-mfa-settings"></a>管理 MFA 設定的方法

管理 MFA 設定的方法有兩種。

在 Azure 入口網站中，您可以：

- 啟用和停用安全性預設值
- 設定條件式存取策略

在 Microsoft 365 系統管理中心，您可以設定每個使用者和服務 MFA 設定。

## <a name="your-next-step"></a>您的下一個步驟

[設定 Microsoft 365 的 MFA](set-up-multi-factor-authentication.md)
