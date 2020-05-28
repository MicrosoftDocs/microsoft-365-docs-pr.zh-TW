---
title: 啟用已加入網域的 Windows 10 裝置以供商務用 Microsoft 365 管理
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 瞭解如何啟用 Microsoft 365，以在幾個步驟中保護本機作用中已加入目錄的 Windows 10 裝置。
ms.openlocfilehash: e7f83e620fbb43a478dba98f78d5f471a541aea7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403051"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a>啟用已加入網域的 Windows 10 裝置以供商務用 Microsoft 365 管理

如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 for business 來保護您的 Windows 10 裝置，同時仍保持存取需要本機驗證的內部部署資源。
若要設定此保護，您可以執行**混合式 AZURE AD 聯結裝置**。 這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。

這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. 準備目錄同步處理 

在您從本機 Active Directory 網域同步處理使用者和電腦之前，請先複查[準備好目錄同步處理至 Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)。 具體說來：

   - 請確定目錄中的下列屬性沒有重複專案： **mail**、 **proxyAddresses**及**userPrincipalName**。 這些值必須是唯一的，而且必須移除任何重複專案。
   
   - 建議您為每個本機使用者帳戶設定**userPrincipalName** （UPN）屬性，使其符合與授權的 Microsoft 365 使用者相對應的主要電子郵件地址。 例如： *mary.shelley@contoso.com* ，而不是*mary@contoso。*
   
   - 如果 Active Directory 網域以非可路由的尾碼（如 .com*或* *lan*）結束，請不要依 internet 路由尾碼（如 *.com*或*org*）來調整本機使用者帳戶的 UPN 尾碼，如[準備目錄同步處理的非路由網域](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)中所述。 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. 安裝及設定 Azure AD Connect

若要將您的使用者、群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory，請安裝 Azure Active Directory Connect，並設定目錄同步作業。 請參閱[設定 Office 365 的目錄同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)處理以深入瞭解。

> [!NOTE]
> Microsoft 365 for business 的步驟完全相同。 

當您設定 Azure AD Connect 的選項時，建議您啟用 **[密碼同步**處理]、[**無縫單一 Sign-On**] 及 [**密碼寫回**功能]，這是 Microsoft 365 for business 中也支援的功能。

> [!NOTE]
> 在 Azure AD Connect 中，除了核取方塊之外，還有其他一些步驟可用於密碼回寫。 如需詳細資訊，請參閱 how [to：設定密碼回寫](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. 設定混合式 Azure AD 聯結

將 Windows 10 裝置加入混合式 Azure AD 之前，請確定您符合下列必要條件：

   - 您正在執行最新版本的 Azure AD Connect。

   - Azure AD connect 已同步處理要成為混合式 Azure AD 之裝置的所有電腦物件。 若電腦物件屬於特定的組織單位（OU），請確定這些 Ou 設定為同時在 Azure AD connect 中進行同步處理。

若要將現有的已加入網域的 Windows 10 裝置註冊成混合式 Azure AD 加入，請遵循教學課程中的步驟[：設定受管理網域的混合式 Azure Active Directory 加入](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)。 這種混合式-可讓您現有的內部部署 Active Directory 加入 Windows 10 電腦，並讓其成為雲端就緒。
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. 啟用自動註冊 Windows 10

 若要在 Intune 中自動註冊用於行動裝置管理的 Windows 10 裝置，請參閱[使用群組原則自動註冊 windows 10 裝置](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)。 您可以在本機電腦層級設定群組原則，也可以針對大量作業，使用群組原則管理主控台和 ADMX 範本，在您的網域控制站上建立此群組原則設定。

## <a name="5-configure-seamless-single-sign-on"></a>5. 設定無縫單一 Sign-On

  無縫 SSO 會在使用公司電腦時，自動將使用者登入其 Microsoft 365 雲端資源。 只需部署[Azure Active Directory 無縫單一 Sign-On](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)中所述的兩個群組原則選項之一：快速入門。 **群組原則**選項不允許使用者變更其設定，而**群組原則偏好**設定選項會設定值，但也會讓使用者可設定。

## <a name="6-set-up-windows-hello-for-business"></a>6. 設定 Windows Hello 企業版

 Windows Hello 企業版取代密碼，具有強雙因素驗證（2FA），用於簽署本機電腦。 其中一個因素是非對稱金鑰配對，另一個是 PIN 或其他本機手勢（如指紋或面部認可）（如果您的裝置支援它）。 建議您在可能的情況下，將密碼與2FA 和 Windows Hello 企業版取代。

若要設定混合式 Windows Hello 企業版，請複查[混合金鑰信任 Windows Hello 企業版必要條件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)。 然後依照[設定混合式 Windows Hello 企業版金鑰信任設定](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)中的指示進行。 
