---
title: 設定組織的密碼到期原則
f1.keywords:
- CSH
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 了解系統管理員如何在 Microsoft 365 系統管理中心設定為學校 公司或非利益組織設定密碼到期原則。
ms.openlocfilehash: 7f12918211718b91313c0c89b11eaeb0a8cc3181
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635819"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>設定貴組織的密碼到期原則

## <a name="before-you-begin"></a>在您開始之前

本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。 若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。 [何謂系統管理員帳戶?](../../business-video/admin-center-overview.md)

身為系統管理員，您可以將使用者密碼設為在指定天數後過期，或將密碼設為永不過期。根據預設，貴組織的密碼會設為永不過期。

最新研究強烈指出強制密碼變更的弊大於利。 它們會讓使用者選擇較弱的密碼、重複使用密碼或以容易被駭客猜測到的方式更新舊密碼。 建議您啟用[多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)。 若要深入了解密碼原則，請查看[密碼原則建議](../misc/password-policy-recommendations.md)。

您必須是[全域系統管理員](../add-users/about-admin-roles.md)才能執行這些步驟。

如果您是使用者，則無權將密碼設為永不過期。請要求貴公司或學校的技術支援人員，為您執行本文所述的步驟。

## <a name="set-password-expiration-policy"></a>設定密碼到期原則

如果您要將使用者密碼設定在指定的時間量後到期，請遵循下列步驟進行。

1. 在系統管理中心中，移至 **[設定]** \> **[組織設定]**。

2. 移至<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全性與隱私權</a>頁面。
 如果您不是全域系統管理員，就看不到 [安全性和隱私權] 選項。
  
3. 選取 **[密碼到期原則]**。
  
4. 如果您不希望使用者必須變更密碼，請取消選取 **[將使用者密碼設定為在幾天後到期]** 旁的核取方塊。
  
5. 輸入密碼到期的頻率。選擇 14 到 730 之間的天數。
  
6. 在第二個方塊中，輸入使用者何時應收到其密碼到期的通知，然後選取 **[儲存]**。 選擇介於 10 到 30 之間的天數。
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>關於密碼到期功能，您應知道的重要事項
  
在快取中的密碼過期之前，不會強制要求只使用 Outlook App 的使用者重設其 Microsoft 365 密碼。這可能會在實際到期日之後的數天發生。針對此問題，目前沒有系統管理員層級的因應措施。

## <a name="prevent-last-password-from-being-used-again"></a>避免再次使用上次的密碼

如果想要避免您的使用者回收舊密碼，您可以在內部部署 Active Directory (AD) 中強制使用密碼記錄來執行此動作。 請參閱 [建立自訂密碼原則](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)。

在 Azure AD 中，當使用者變更密碼時，不能再次使用最後一個密碼。 密碼原則會套用至在 Azure AD 中建立並直接管理的所有使用者帳戶。 不能修改此密碼原則。 請參閱 [Azure AD 密碼原則](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)。

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>將內部部署 Active Directory 的使用者密碼雜湊同步處理到 Azure AD (Microsoft 365)

本文用於為僅限雲端使用者 (Azure AD) 設定到期原則。 不適用於使用密碼雜湊同步處理、傳遞驗證或內部部署同盟 (例如 ADFS) 的混合式身分識別使用者。
  
若要了解如何將使用者密碼雜湊從內部部署 AD 同步處理到 Azure AD，請參閱[使用 Azure AD Connect 同步處理實作密碼雜湊同步處理](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>密碼原則和 Azure Active Directory 中的帳戶限制

您可以設定更多密碼原則和 Azure Active Directory 中的限制。 如需詳細資訊，請參閱 [密碼原則和 Azure Active Directory 中的帳戶限制](/azure/active-directory/authentication/concept-sspr-policy)。

## <a name="update-password-policy"></a>已更新密碼原則

Set-MsolPasswordPolicy 指令會更新指定網域或租用戶的密碼原則。需要進行兩個設；一是在必須變更之前，指出密碼保持有效的時間長度，而二是指出在使用者收到密碼即將到期的第一次通知時所觸發的密碼到期日前的天數。

若要瞭解如何更新特定網域或租使用者的密碼原則，請參閱 [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0)。

## <a name="related-content"></a>相關內容

[讓使用者重設自己的密碼](../add-users/let-users-reset-passwords.md) (文章)
[重設密碼](../add-users/reset-passwords.md) (文章)