---
title: 實施身分識別和裝置存取原則的必要條件工作-Microsoft 365 企業版 |Microsoft 檔
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
ms.openlocfilehash: 8ac644ccd7772d8e4c53395c8a42ff6ddbd683a6
ms.sourcegitcommit: a6878de8ab977b675a45fc847ff46a9c0365dc56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2019
ms.locfileid: "35231856"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>實施身分識別和裝置存取原則的必要條件工作

本文說明在您部署建議的身分識別和裝置存取原則之前, 必須先執行的必要條件。 本文也討論我們建議的預設平臺用戶端設定, 以提供最佳的 SSO 體驗給您的使用者, 以及條件式存取的技術必要條件。


## <a name="prerequisites"></a>必要條件

在實施建議的身分識別和裝置存取原則之前, 您的組織必須符合數個必要條件。 下表詳細說明適用于您環境的必要條件。 


| 組態 | 僅限雲端 | 具有密碼雜湊同步處理的 Active Directory |  傳遞驗證 |  與 AD FS 的同盟 |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [設定密碼雜湊同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)處理。必須啟用這一功能, 才能偵測出已洩漏的認證, 並對其進行風險型條件式存取。 **附注:** 不論您的組織是否使用受管理的驗證 (例如傳遞驗證 (PTA) 或同盟驗證), 都是必要的。 |    | 是 | 是 | 是 |
| 在連線至公司網路的公司裝置上,[啟用無縫單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)以自動簽署使用者。 |  | 是 | 是 |  |
| [設定具名網路](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection 會收集和分析可產生風險分數的所有可用工作階段資料。 我們建議您在 Azure AD (名為 network configuration) 中指定貴組織的公用 IP 範圍。 來自這些範圍的流量會獲得降低的風險分數, 而來自公司環境以外的流量則會獲得較高的風險分數。 | 是  | 是 | 是 | 是 |
|[註冊所有使用者的自助密碼重設 (SSPR) 和多重要素驗證 (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。 我們建議您提前為 Azure MFA 註冊使用者。 Azure AD Identity Protection 利用 Azure MFA 來執行額外的安全性驗證。 此外, 針對最佳登入經驗, 我們建議使用者在其裝置上安裝[Microsoft 驗證應用程式](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)和 Microsoft 公司入口網站應用程式。 這些可從每個平臺的應用程式存放區中安裝。 | 是 | 是 | 是 | 是 |
| [啟用已加入網域的 Windows 電腦的自動裝置註冊](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 條件式存取會確定連接到應用程式的裝置已加入網域或合規性。 若要在 Windows 電腦上支援這個作業，則必須使用 Azure AD 註冊裝置。  本文討論如何設定自動裝置註冊。 |   | 是 |  是 |  是 |
| **準備支援小組**. 已有針對無法完成 MFA 的使用者的計劃。 這可以是將它們新增至原則排除群組, 或為它們註冊新的 MFA 資訊。 在進行其中一種安全性敏感變更之前, 您必須確定實際的使用者提出要求。 需要使用者的管理員協助進行核准是有效的步驟。 | 是 | 是 | 是 | 是 |  
| [將密碼回寫設定成內部部署 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 密碼回寫可讓 Azure AD 在偵測到高風險帳戶洩漏時, 要求使用者變更其內部部署密碼。 您可以使用下列兩種方式之一來啟用此功能: 在 Azure AD Connect 安裝精靈的 [選用功能] 畫面中啟用**密碼回寫**, 或透過 Windows PowerShell 加以啟用。 |   | 是 | 是 | 是 |
| [啟用 Azure Active Directory 身分識別保護](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)。 Azure AD Identity Protection 可讓您偵測影響組織身分識別的潛在弱點, 並將自動補救原則設定為低、中、高的登入風險和使用者風險。  | 是 | 是 | 是 | 是 |
| 啟用[Exchange online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)和[商務用 Skype online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)的**新式驗證**。 新式驗證是使用多重要素驗證 (MFA) 的必要條件。 Office 2016 用戶端、SharePoint Online 和商務用 OneDrive 預設會啟用新式驗證。 | 是 | 是 | 是 | 是 |
||||||



## <a name="recommended-client-configurations"></a>建議的用戶端設定
本節說明我們建議的預設平臺用戶端設定, 以提供最佳的 SSO 體驗給您的使用者, 以及條件式存取的技術必要條件。

### <a name="windows-devices"></a>Windows 裝置
建議使用 Windows 10 (1703 版或更新版本)，因為 Azure 設計成可提供內部部署和 Azure AD 的最流暢 SSO 體驗。 工作或學校發行的裝置應該設定為直接加入 Azure AD, 或如果組織使用內部部署 AD 網域加入, 這些裝置應[設定為自動和以無訊息方式註冊 AZURE AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

若為 BYOD Windows 裝置, 使用者可以使用 [**新增工作] 或 [學校帳戶**]。 請注意, Windows 10 上的 Chrome 瀏覽器使用者必須[安裝分機](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog), 以取得與 EDGE/IE 使用者相同的平滑登入體驗。 此外, 如果您的組織已加入網域的 Windows 7 裝置, 您可以為非 Windows 10 電腦安裝 Microsoft Workplace Join。[下載套件以](https://www.microsoft.com/download/details.aspx?id=53554)向 Azure AD 註冊裝置。

### <a name="ios-devices"></a>iOS 裝置
建議先在使用者裝置上安裝 [Microsoft Authenticator 應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)，再部署條件式存取或 MFA 原則。 在要求使用者使用 Azure AD 註冊裝置時, 應至少安裝應用程式, 方法是新增工作或學校帳戶, 或安裝 Intune 公司入口網站, 以將其裝置註冊至管理。 這取決於設定的條件式存取原則。

### <a name="android-devices"></a>Android 裝置
部署條件式存取原則之前，或在特定驗證嘗試期間需要時，建議使用者先安裝 [Intune 公司入口網站應用程式](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)和 [Microsoft Authenticator 應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 安裝應用程式之後，可能會要求使用者向 Azure AD 註冊，或使用 Intune 註冊其裝置。 這取決於設定的條件式存取原則。

此外, 我們也建議公司所擁有的裝置 (貨到) 在 Oem 和支援使用 Android 的 Android Knox 的版本, 以允許由 Intune MDM 原則管理及保護的版本上進行標準化。


### <a name="recommended-email-clients"></a>建議的電子郵件用戶端
下列電子郵件客戶程式支援新式驗證和條件式存取。 

|平台|用戶端|版本/附註|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013[啟用新式驗證](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910),[必要更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**適用**|iOS 版 Outlook|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|不支援||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>保護文件時的建議用戶端平台
套用安全檔原則時, 建議使用下列用戶端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 應用程式|SharePoint 應用程式|OneDrive 同步處理用戶端|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|支援|支援|不適用|不適用|預覽<sup>*</sup>|
|Windows 8.1|支援|支援|不適用|不適用|預覽<sup>*</sup>|
|Windows 10|支援|支援|不適用|不適用|預覽<sup>*</sup>|
|Windows Phone 10|不支援|未支援|不支援|不支援|不支援|
|Android|支援|支援|支援|支援|不適用|
|適用|支援|支援|支援|支援|不適用|
|macOS|公開預覽|公開預覽|不適用|不適用|不支援|
|Linux|不支援|未支援|未支援|未支援|未支援|

<sup>*</sup>深入瞭解使用[OneDrive 同步處理用戶端](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)的條件式存取。

### <a name="office-365-client-support"></a>Office 365 用戶端支援
如需 Office 365 用戶端支援的詳細資訊, 請參閱下列文章:
- [Office 365 用戶端應用程式支援-條件式存取](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 用戶端應用程式支援-行動裝置應用程式管理](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 用戶端應用程式支援-新式驗證](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>保護系統管理員帳戶
Azure AD 提供簡單的方法, 讓您開始使用預先設定的條件式存取原則來保護系統管理員存取。 在 Azure AD 中, 移至 [**條件存取**], 並尋找此原則-**基準原則: 需要使用 MFA 進行系統管理員 (預覽)**。 選取 [這個原則], 然後選取 [**立即使用原則**]。 

此原則需要對下列角色進行 MFA:
- 全域系統管理員
- SharePoint 管理員
- Exchange 系統管理員
- 條件式存取管理員
- 安全性管理員

如需詳細資訊, 請參閱[AZURE AD 系統管理員帳戶的基準安全性原則](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)。

其他建議包括:
- 使用 Azure AD Privileged Identity Management 減少持續性系統管理帳戶數目。 請參閱[Start USING PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started)。 
- [使用 Office 365 中的 [特殊許可權存取管理](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview)], 保護您的組織不會因使用現有的特權系統管理員帳戶存取敏感性資料或存取重要的設定設定而遭到破壞。 
- 僅使用系統管理員帳戶進行管理。 系統管理員應該要有個別的使用者帳戶, 以進行一般非系統管理使用, 並在必要時使用其管理帳戶, 以完成與工作功能相關聯的工作。 [Office 365 系統管理員](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)角色的許可權明顯高於 Office 365 服務。
- 遵循[本文](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)所述, 遵循 Azure AD 中的特權帳戶的最佳作法。

## <a name="next-steps"></a>後續步驟

[設定一般身分識別和裝置存取原則](identity-access-policies.md)

