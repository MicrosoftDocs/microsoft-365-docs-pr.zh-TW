---
title: 實作身分識別與裝置的必要工作存取原則-Microsoft 365 企業版 |Microsoft 文件
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
ms.openlocfilehash: ee517e774e0606c62efdc67d869ad0aca5a41640
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866774"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>實作身分識別與裝置存取原則的必要工作

本文說明必須要實作的建議的身分識別和裝置存取原則可以部署之前的必要條件。本文也會討論我們建議您的使用者，以及設定格式化的條件存取的技術必要條件提供最佳的 SSO 體驗預設平台的用戶端設定。


## <a name="prerequisites"></a>必要條件

實作建議的身分識別和裝置存取原則之前，有數個您的組織必須符合的必要條件。下表詳細說明適用您環境的必要條件。 


| 組態 | 僅限雲端 | 使用密碼雜湊同步處理的 active Directory |  傳遞驗證 |  使用 AD FS 同盟 |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [設定密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。這必須啟用偵測遺漏的認證和風險型條件式存取的處理它們。**附註：** 這是必要的無論您的組織是否使用受管理的驗證、 like 通過驗證 (PTA) 或同盟的驗證。 |    | 是 | 是 | 是 |
| [啟用一致的單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)以自動登入中它們位於其公司裝置連線至公司網路上的時的使用者。 |  | 是 | 是 |  |
| [設定名為網路](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。Azure AD 身分識別保護收集並進行分析來產生風險分數的所有可用的工作階段資料。我們建議您指定貴組織的公用 IP 範圍為您的網路中名為 [網路設定 Azure AD。來自這些範圍的流量會降低的風險分數，並從外部公司環境的流量會授與的較高風險分數。 | 是  | 是 | 是 | 是 |
|[註冊的自助式密碼重設 (SSPR) 及多重要素驗證 (MFA) 的所有使用者](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。我們建議您註冊 Azure MFA 使用者隨時。Azure AD 身分識別保護進行的 Azure MFA 用來執行其他安全性驗證。此外，獲得最佳的登入體驗，我們建議使用者安裝[Microsoft 驗證器應用程式](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)和裝置上的 Microsoft 公司入口網站應用程式。這些可安裝的應用程式儲存區的每個平台。 | 是 | 是 | 是 | 是 |
| [啟用自動裝置註冊的已加入網域的 Windows 電腦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。設定格式化的條件存取會確認裝置連線到應用程式已加入網域或相容。若要支援此 Windows 的電腦上，裝置必須註冊使用 Azure AD。 本文將告訴您如何設定自動裝置註冊。 |   | 是 |  是 |  是 |
| **準備支援小組**。備妥無法完成 MFA 使用者有的計劃。這無法將它們新增至原則排除] 群組中或登錄為他們的新 MFA 資訊。之前任一這些安全性機密變更，您需要確定要求進行真正的使用者。需要以協助進行核准的使用者的經理是有效的步驟。 | 是 | 是 | 是 | 是 |  
| [若要設定密碼回寫內部部署 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。密碼回寫允許要求在使用者變更其內部密碼，高風險帳戶遭到入侵偵測到時的 Azure AD。您可以啟用此功能使用 Azure AD 連接兩種方式之一： Azure AD 連線安裝精靈] 中的選用功能畫面中啟用**密碼回寫**] 或 [啟用透過 Windows PowerShell。 |   | 是 | 是 | 是 |
| [啟用 Azure Active Directory 識別保護](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)。Azure AD 身分識別保護可讓您偵測潛在弱點會影響您組織的身分識別和設定自動的修復原則以低、 中型或高登入的風險與使用者風險。  | 是 | 是 | 是 | 是 |
| **啟用經過驗證**的[Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)和[Skype 的商務 Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。現代驗證是使用多重要素驗證 (MFA) 的必要條件。預設會啟用經過驗證的 Office 2016 用戶端、 SharePoint Online 和 OneDrive for Business。 | 是 | 是 | 是 | 是 |
||||||



## <a name="recommended-client-configurations"></a>建議的用戶端設定
本章節說明我們建議您的使用者，以及設定格式化的條件存取的技術必要條件提供最佳的 SSO 體驗預設平台的用戶端設定。

### <a name="windows-devices"></a>Windows 裝置
我們建議 Windows 10 （版本 1703年或更新版本）、 Azure 的設計用來提供最平滑 SSO 體驗可能的內部部署和 Azure AD。工作或學校發出裝置應該設定為直接加入 Azure AD 或如果組織使用內部部署 AD 網域加入，這些裝置應該[設定成自動和以無訊息方式登錄與 Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

BYOD Windows 裝置的使用者可以使用**新增工作或學校帳戶**。請注意上 Windows 10 的 Chrome 瀏覽器使用者需要安裝[延伸](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)以取得相同順利登入經驗 Edge/IE 使用者一樣。此外，如果您的組織有已加入網域的 Windows 7 裝置，您可以安裝 Microsoft 工作場所加入[下載套件註冊](https://www.microsoft.com/download/details.aspx?id=53554)的非 Windows 10 電腦裝置與 Azure AD。

### <a name="ios-devices"></a>iOS 裝置
建議您部署設定格式化的條件存取或 MFA 原則之前先安裝使用者裝置上的[Microsoft 驗證器應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。在最低限度下，當使用者要求要新增工作中註冊 Azure AD 使用者的裝置或學校帳戶，或安裝 Intune 的公司入口網站應用程式以註冊使用者的裝置將管理應該安裝應用程式。已設定的設定格式化的條件存取原則而定。

### <a name="android-devices"></a>Android 裝置
部署條件式存取原則之前，或在特定驗證嘗試期間需要時，建議使用者先安裝 [Intune 公司入口網站應用程式](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)和 [Microsoft Authenticator 應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 安裝應用程式之後，可能會要求使用者向 Azure AD 註冊，或使用 Intune 註冊其裝置。 這取決於設定的條件式存取原則。

也建議公司擁有裝置 (COD) 標準化 Oem 及支援 Android 工時或 Samsung Knox 允許郵件帳號、 管理及受到 Intune MDM 原則的版本。


### <a name="recommended-email-clients"></a>建議的電子郵件用戶端
下列的電子郵件用戶端支援摩登的驗證和設定格式化的條件的存取。 

|平台|用戶端|版本/附註|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016、 2013年[啟用現代驗證](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)、[必要的更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS 版 Outlook|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|不支援||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>保護文件時的建議用戶端平台
當已套用安全文件原則建議使用下列用戶端。

|平台|Word/Excel PowerPoint|OneNote|OneDrive 應用程式|SharePoint 應用程式|OneDrive 同步處理用戶端|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|支援|支援|N/A|N/A|預覽<sup>*</sup>|
|Windows 8.1|支援|支援|N/A|N/A|預覽<sup>*</sup>|
|Windows 10|支援|支援|N/A|N/A|預覽<sup>*</sup>|
|Windows Phone 10|不支援|不支援|不支援|不支援|不支援|
|Android|支援|支援|支援|支援|N/A|
|iOS|支援|支援|支援|支援|N/A|
|macOS|公開預覽|公開預覽|N/A|N/A|不支援|
|Linux|不支援|不支援|不支援|不支援|不支援|

<sup>*</sup>深入了解使用設定格式化的條件存取[OneDrive 同步處理用戶端](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)。

### <a name="office-365-client-support"></a>Office 365 用戶端支援
如需 Office 365 用戶端支援的詳細資訊，請參閱下列文章：
- [Office 365 用戶端應用程式支援設定格式化的條件的存取](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 用戶端應用程式支援行動裝置應用程式管理](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 用戶端應用程式支援摩登的驗證](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>保護系統管理員帳戶
Azure AD 提供簡單方法，讓您開始保護使用預先設定的設定格式化的條件存取原則的系統管理員存取權。在 Azure AD 移至 [**設定格式化的條件的存取**並尋找此原則 —**基準原則： 的系統管理員需要 MFA**。選取此原則，然後選取 [**立即使用原則**。 

此原則會需要 MFA 的下列角色：
- 全域管理員
- SharePoint 管理員
- Exchange 系統管理員
- 設定格式化的條件存取系統管理員
- 安全性管理員

如需詳細資訊，請參閱[Azure AD 管理員帳戶的標準安全性原則](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)。

其他建議如下：
- 使用 Azure AD 權限的身分識別管理降低持續性的系統管理帳戶的數目。請參閱[開始使用 PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started)。 
- [使用 Office 365 中的存取權限的管理](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview)來保護您的組織中可以使用現有的缺口的權限管理員帳戶具有出位置的存取權機密資料或重要的組態設定的存取權。 
- 使用 Office 365 系統管理員帳戶僅適用於管理的。系統管理員應該會有個別的使用者帳戶的一般非系統管理使用與只能使用其管理的帳戶時所需完成其工作職責相關聯的工作。[Office 365 系統管理員](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)角色具有比 Office 365 服務的更多權限。
- 遵循保護在 Azure AD 的權限的帳戶 ＞[文章](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)中所述的最佳作法。

## <a name="next-steps"></a>後續步驟

[設定一般的身分識別與裝置存取原則](identity-access-policies.md)

