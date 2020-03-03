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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: '了解如何在 Microsoft 365 系統管理中心設定組織的密碼到期原則。 '
ms.openlocfilehash: 88953317bea2b96c04c291dd028a4e9131b9a83e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361658"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>設定組織的密碼到期原則

本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。  

如果您是使用者，則無權將密碼設為永不到期。 請要求貴公司或學校的技術支援人員，為您執行本文所述的步驟。

身為系統管理員，您可以將使用者密碼設為在指定天數後過期，或將密碼設為永不過期。 

> [!Tip]
> 根據預設，密碼會設定為在 90 天內過期。 最新研究強烈指出強制密碼變更的弊大於利。 它們會讓使用者選擇較弱的密碼、重複使用密碼或以容易被駭客猜測到的方式更新舊密碼。 如果將密碼設定為永不到期，建議您啟用[多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)。

如果您要將使用者密碼設定在指定的時間量後到期，請遵循下列步驟進行。
> [!IMPORTANT]
> 只有 [Office 365 全域系統管理員](../add-users/about-admin-roles.md)才能執行這些步驟。
  
1. 在系統管理中心中，移至 [設定]**** \> [設定]****。

2. 移至<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全性與隱私權</a>頁面。
 如果您不是 Office 365 全域系統管理員，就看不到 [安全性和隱私權] 選項。
  
3. 選取 [密碼到期原則]****。
  
4. 如果您不希望使用者必須變更密碼，請選取 [將使用者密碼設定為在幾天後到期]**** 核取方塊。
  
5. 輸入密碼應到期的頻率。 選擇介於 14 到 730 之間的天數。
  
6. 在第二個方塊中，輸入使用者何時應收到其密碼到期的通知，然後選取 [儲存]****。 Choose a number of days from 1 to 30.
    
7. 使用者的密碼過期時，會收到通知 (顯示在其螢幕的右下角)。
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>關於密碼到期功能，您應知道的重要事項

有關這項功能截至 2018 年 1 月的運作情形，這裡是您需要了解的一些事項：
  
- 在快取中的密碼過期之前，不會強制要求只使用 Outlook App 的使用者重設其 Office 365 密碼。這可能會在實際到期日之後的數天發生。針對此問題，目前沒有系統管理員層級的因應措施。
    
- 使用者不會收到其密碼即將在 X 天後過期的電子郵件通知。您想要這項功能嗎？ **[在這裡投票！](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**
    
## <a name="prevent-last-password-from-being-used-again"></a>避免再次使用上次的密碼

如果要避免使用者回收舊密碼，您可以在 Azure AD 中執行此動作。 請參閱[設定組織的密碼到期原則](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide)。

此外，如果某位員工使用行動裝置來存取 Office 365，您可以將它清除，以確保不會從該位置儲存並回收密碼。 若要進一步了解，請參閱[抹除及封鎖離職員工的行動裝置](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device)。


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-office-365"></a>將內部部署 Active Directory 的使用者密碼雜湊同步處理到 Azure AD (Office 365)

本文用於為僅限雲端使用者 (Azure AD) 設定到期原則。 不適用於使用密碼雜湊同步處理、傳遞驗證或內部部署同盟 (例如 ADFS) 的混合式身分識別使用者。
  
若要了解如何將使用者密碼雜湊從內部部署 AD 同步處理到 Azure AD，請參閱[使用 Azure AD Connect 同步處理實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。
