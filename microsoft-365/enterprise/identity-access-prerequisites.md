---
title: 必要條件工時實作身分識別與裝置存取原則-Microsoft 365 企業版 |Microsoft Docs
description: 描述如何套用身分識別和裝置存取原則和設定之 Microsoft 建議的原則。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 2bb13d2af70b90f8c98a4bb902156f840e7f57f1
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289004"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>實作身分識別與裝置存取原則的必要工作

本文說明必須才能部署建議身分識別與裝置存取原則實作的必要條件。 本文也討論了建議為您的使用者，以及條件式存取的技術必要條件提供最佳 SSO 體驗的預設平台用戶端設定。


## <a name="prerequisites"></a>必要條件

實作建議身分識別與裝置存取原則前, 幾個必要條件必須符合您的組織。 下表詳述適用您環境的必要條件。 


| 組態 | 僅限雲端 | Active Directory 與密碼雜湊同步處理 |  傳遞驗證 |  使用 AD FS 的同盟 |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [設定密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。這必須啟用來偵測遺漏的認證，並對它們的風險型條件式存取。 **附註：** 不論您的組織是否使用受管理的驗證，例如通過驗證 (PTA) 或同盟的驗證需要這樣做。 |    | 是 | 是 | 是 |
| [啟用無縫單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)即可自動登入是在連線至公司網路其公司規範的裝置上的使用者。 |  | 是 | 是 |  |
| [設定具名網路](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection 會收集和分析可產生風險分數的所有可用工作階段資料。 我們建議您在名為網路設定 Azure AD 中指定為您的網路貴組織的公用 IP 範圍。 來自這些範圍流量降低的風險分數，並從公司環境外部的流量所指定的較高風險分數。 | 是  | 是 | 是 | 是 |
|[登錄所有使用者的自助密碼重設 (SSPR) 與多重要素驗證 (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。 我們建議您註冊 Azure MFA 使用者事先。 Azure AD Identity Protection 利用 Azure MFA 來執行額外的安全性驗證。 此外，為了最佳登入體驗，請建議使用者安裝[Microsoft Authenticator app](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)和其裝置上的 Microsoft 公司入口網站應用程式。 這些可以從每個平台的應用程式存放區安裝。 | 是 | 是 | 是 | 是 |
| [啟用自動裝置註冊加入網域的 Windows 電腦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 條件式存取會確定裝置連線至應用程式已加入網域或相容。 若要在 Windows 電腦上支援這個作業，則必須使用 Azure AD 註冊裝置。  本文討論如何設定自動裝置註冊。 |   | 是 |  是 |  是 |
| **準備支援小組**. 已有針對無法完成 MFA 的使用者的計劃。 這可能是將它們新增至原則排除項目] 群組中，或註冊為他們的新 MFA 資訊。 之前進行任一這些敏感的安全性變更，您必須確保實際使用者提出要求。 需要使用者的管理員協助進行核准是有效的步驟。 | 是 | 是 | 是 | 是 |  
| [將密碼回寫設定成內部部署 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 密碼回寫可讓 Azure AD 以要求使用者在偵測到高風險帳戶遭到入侵時，會變更其內部部署密碼。 您可以啟用下列兩種方式之一使用 Azure AD Connect 這項功能： 在 [Azure AD Connect 設定精靈] 的 [選擇性功能] 畫面中啟用**密碼回寫**] 或 [啟用透過 Windows PowerShell。 |   | 是 | 是 | 是 |
| [啟用 Azure Active Directory Identity Protection](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)。 Azure AD Identity Protection 可讓您偵測會影響組織身分識別的潛在弱點，並設定自動的修復原則對低、 中、、 高程度的登入風險與使用者風險。  | 是 | 是 | 是 | 是 |
| **啟用新式驗證** [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)和[商務用 Skype](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 新式驗證是使用多重要素驗證 (MFA) 的必要條件。 預設會啟用新式驗證的 Office 2016 用戶端、 SharePoint Online 和商務用 OneDrive。 | 是 | 是 | 是 | 是 |
||||||



## <a name="recommended-client-configurations"></a>建議的用戶端設定
本章節說明我們建議您的使用者，以及條件式存取的技術必要條件提供最佳 SSO 體驗的預設平台用戶端設定。

### <a name="windows-devices"></a>Windows 裝置
建議使用 Windows 10 (1703 版或更新版本)，因為 Azure 設計成可提供內部部署和 Azure AD 的最流暢 SSO 體驗。 工作或學校發出裝置應設定為直接加入 Azure AD，或如果組織使用內部部署 AD 網域加入，那些裝置應該[會自動設定為，並以無訊息方式登錄與 Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

針對 BYOD Windows 裝置，使用者可以使用**新增的工作或學校帳戶**。 請注意，在 Windows 10 上的 Chrome 瀏覽器使用者需要[安裝的分機號碼](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)若要取得的相同順利登入經驗為 Edge/IE 中的使用者。 此外，如果您的組織具有已加入網域的 Windows 7 裝置，您可以安裝 Microsoft 工作場所加入的[下載套件來註冊](https://www.microsoft.com/download/details.aspx?id=53554)的非 Windows 10 電腦裝置與 Azure AD。

### <a name="ios-devices"></a>iOS 裝置
建議先在使用者裝置上安裝 [Microsoft Authenticator 應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)，再部署條件式存取或 MFA 原則。 在最低限度下，當使用者上當系統要與 Azure AD 註冊他們的裝置，藉由新增公司或學校帳戶，或其安裝 Intune 公司入口網站應用程式註冊其裝置管理到應安裝應用程式。 這取決於設定的條件式存取原則。

### <a name="android-devices"></a>Android 裝置
部署條件式存取原則之前，或在特定驗證嘗試期間需要時，建議使用者先安裝 [Intune 公司入口網站應用程式](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)和 [Microsoft Authenticator 應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 安裝應用程式之後，可能會要求使用者向 Azure AD 註冊，或使用 Intune 註冊其裝置。 這取決於設定的條件式存取原則。

我們也建議公司擁有裝置 (COD) 標準化上 Oem 和支援的工作或適用 Samsung Knox 允許郵件帳戶、 管理和由 Intune MDM 原則保護 Android 的版本。


### <a name="recommended-email-clients"></a>建議的電子郵件用戶端
下列的電子郵件用戶端支援新式驗證和條件式存取。 

|平台|用戶端|版本/附註|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016、 2013年[啟用新式驗證](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)、[必要更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS 版 Outlook|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|不支援||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>保護文件時的建議用戶端平台
已套用的安全文件原則時，建議使用下列用戶端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 應用程式|SharePoint 應用程式|OneDrive 同步處理用戶端|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|支援|支援|不適用|不適用|預覽<sup>*</sup>|
|Windows 8.1|支援|支援|不適用|不適用|預覽<sup>*</sup>|
|Windows 10|支援|支援|不適用|不適用|預覽<sup>*</sup>|
|Windows Phone 10|不支援|未支援|不支援|不支援|不支援|
|Android|支援|支援|支援|支援|不適用|
|iOS|支援|支援|支援|支援|不適用|
|macOS|公開預覽|公開預覽|不適用|不適用|不支援|
|Linux|不支援|未支援|未支援|未支援|未支援|

<sup>*</sup>深入了解使用條件式存取的[OneDrive 同步處理用戶端](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)。

### <a name="office-365-client-support"></a>Office 365 用戶端支援
如需有關 Office 365 用戶端支援的詳細資訊，請參閱下列文章：
- [Office 365 用戶端應用程式支援人員-條件式存取](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 用戶端應用程式支援行動應用程式管理](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 用戶端應用程式支援新式驗證](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>保護系統管理員帳戶
Azure AD 提供簡單的方法，供您開始保護與預先設定的條件式存取原則的系統管理員存取權。 在 Azure AD，前往 [**條件式存取**，並尋找此原則 —**基準線原則： 系統管理員需要 MFA**。 選取此原則，然後選取 [**立即使用原則**。 

此原則需要 MFA 的下列角色：
- 全域系統管理員
- SharePoint 系統管理員
- Exchange 系統管理員
- 條件式存取系統管理員
- 安全性系統管理員

如需詳細資訊，請參閱[Azure AD 系統管理員帳戶的比較基準安全性原則](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)。

其他建議如下：
- 使用 Azure AD Privileged Identity Management 減少持續性系統管理帳戶數目。 請參閱 <<c0>開始使用 PIM。 
- 若要防止外洩可能會使用現有的組織[使用 Office 365 中的特殊權限的存取管理](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview)特殊權限與常設存取權的敏感資料或存取重要的組態設定的系統管理員帳戶。 
- 使用系統管理員帳戶僅適用於管理。 系統管理員應該有個別的使用者帳戶的一般非系統管理員使用與僅使用其管理的帳戶時所需完成其工作職責相關聯的工作。 [Office 365 系統管理員](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)角色的權限更多比 Office 365 服務。
- 遵循在 Azure AD 中保護特殊權限的帳戶，本[文章](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)所述的最佳作法。

## <a name="next-steps"></a>後續步驟

[設定一般身分識別與裝置存取原則](identity-access-policies.md)

