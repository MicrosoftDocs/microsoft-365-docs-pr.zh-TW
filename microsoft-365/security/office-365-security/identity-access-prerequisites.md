---
title: 實施身分識別和裝置存取原則的必要條件工作-Microsoft 365 for enterprise |Microsoft 檔
description: 本文說明您在使用身分識別與裝置存取原則及設定時必須遵守的必要條件。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: df09f72e8bb5aee78ca4b45ce2804774ee16cbf2
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097113"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>實施身分識別與裝置存取原則的必要條件工作

本文說明系統管理員必須符合以使用建議的身分識別和裝置存取原則，以及使用條件式存取的必要條件。 此外，本文也會討論設定最佳單一登入 (SSO) 體驗的用戶端平臺的建議預設值。

## <a name="prerequisites"></a>必要條件

在使用建議的身分識別與裝置存取原則之前，您的組織必須符合必要條件。 針對所列的各種身分識別和驗證模型，需求各有不同：

- 僅雲端
- 混合使用密碼雜湊同步 (PHS) 驗證
- 使用傳遞驗證混合 (PTA) 
- 聯邦

下表詳細說明適用于所有身分識別模型的必要條件功能及其設定，除非另有說明。

|組態|例外狀況|
|---|:---:|
|[設定 PHS](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。  這必須啟用以偵測已洩漏的認證，並針對風險型條件式存取採取行動。 **附注：** 不論您的組織是否使用同盟驗證，都是必要的。|僅雲端|
|[啟用無縫單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) ，當使用者位於連接至組織網路的組織裝置時，自動簽署使用者。|僅限雲端和同盟|
|[設定具名網路](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection 會收集和分析可產生風險分數的所有可用工作階段資料。 建議您在 Azure AD 命名為 [網路設定] 中，為您的網路指定您組織的公用 IP 範圍。 來自這些範圍的流量會獲得較低的風險分數，而來自組織環境以外的流量會獲得較高的風險排名。||
|在[SSPR) 和多重要素驗證 (MFA) 時，註冊所有使用者的自助密碼重設 (](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。 我們建議您提前註冊 Azure AD Multi-Factor 驗證的使用者。 Azure AD 身分識別保護會利用 Azure AD Multi-Factor 驗證，以執行其他安全性驗證。 此外，為了獲得最佳登入經驗，我們建議使用者在其裝置上安裝 [Microsoft 驗證者應用程式](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 和 Microsoft 公司入口網站。 這些可從每個平臺的應用程式存放區安裝。||
|[啟用已加入網域之 Windows 電腦的自動裝置註冊](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 條件式存取會確定連接至應用程式的裝置已加入網域或相容性。 若要在 Windows 電腦上支援這個作業，則必須使用 Azure AD 註冊裝置。  本文討論如何設定自動裝置註冊。|僅雲端|
|**準備支援小組**. 已有針對無法完成 MFA 的使用者的計劃。 這可能會將其新增至原則排除群組，或為其註冊新的 MFA 資訊。 在進行其中一項安全性敏感性變更之前，您必須確定實際的使用者正在進行要求。 需要使用者的管理員協助進行核准是有效的步驟。||
|[將密碼回寫設定成內部部署 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 密碼回寫可讓 Azure AD 要求使用者在偵測到高風險帳戶時變更其內部部署密碼。 您可以使用下列兩種方式之一，使用 Azure AD Connect 來啟用此功能：在 Azure AD Connect 安裝精靈的 [選用功能] 畫面啟用 **密碼回寫** 功能，或透過 Windows PowerShell 加以啟用。|僅雲端|
|[設定 AZURE AD 密碼保護](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)。 Azure AD 密碼保護可偵測並封鎖已知的弱式密碼及其變體，也會封鎖貴組織特有的額外弱式詞彙。 預設全域禁用密碼清單會自動套用至 Azure AD 租用戶中的所有使用者。 您可以在自訂禁用密碼清單中定義其他條目。 使用者變更或重設密碼時，系統會檢查這些禁用密碼清單，以強制使用強式密碼。||
|[啟用 Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。 Azure AD 身分識別保護可讓您偵測影響組織之身分識別的潛在弱點，並設定自動修正原則為低、中、高的登入風險和使用者風險。||
|為 [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)和 [商務用 Skype Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)**啟用新式驗證**。 新式驗證是使用 MFA 的必要條件。 根據預設，Office 2016 和2019用戶端、SharePoint 和商務 OneDrive 都會啟用新式驗證。||
|

## <a name="recommended-client-configurations"></a>建議的用戶端設定

本節說明我們建議的預設平臺用戶端設定，以提供最佳的 SSO 體驗給您的使用者，以及條件式存取的技術必要條件。

### <a name="windows-devices"></a>Windows 裝置

建議您) Windows 10 (版本2004或更新版本，因為 Azure 是用來為內部部署和 Azure AD 提供盡可能最平滑的 SSO 體驗。 工作或學校發行的裝置應該設定成直接加入 Azure AD，或者如果組織使用內部部署 AD 網域加入，這些裝置應 [設定為自動和以無訊息方式註冊 AZURE ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

在 BYOD Windows 裝置中，使用者可以使用 [ **新增工作] 或 [學校帳戶**]。 請注意，Windows 10 裝置上的 Google Chrome 瀏覽器使用者需要 [安裝分機](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) ，以取得與 Microsoft Edge 使用者相同的平滑登入體驗。 此外，如果您的組織已加入網域的 Windows 8 或8.1 裝置，您可以為非 Windows 10 電腦安裝 Microsoft Workplace Join。 [下載套件以](https://www.microsoft.com/download/details.aspx?id=53554) 使用 Azure AD 註冊裝置。

### <a name="ios-devices"></a>iOS 裝置

建議您先在使用者裝置上安裝 [Microsoft 驗證應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) ，然後再部署條件式存取或 MFA 原則。 至少，當使用者要求使用者使用 Azure AD 登錄其裝置時，應安裝應用程式，方法是新增工作或學校帳戶，或安裝 Intune 公司入口網站應用程式，以將其裝置登記到管理中。 這取決於設定的條件式存取原則。

### <a name="android-devices"></a>Android 裝置

建議使用者安裝 [Intune 公司入口網站應用程式](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) 和 [Microsoft 驗證應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) ，然後再部署設定條件存取原則，或在特定驗證嘗試期間需要時要求。 安裝應用程式之後，可能會要求使用者向 Azure AD 註冊，或使用 Intune 註冊其裝置。 這取決於設定的條件式存取原則。

我們也建議在 Oem 和支援使用 Android 的 Samsung 或 Samsung Knox 的版本上標準化組織所擁有的裝置，以允許使用 Intune MDM 原則來管理及保護郵件帳戶。

### <a name="recommended-email-clients"></a>建議的電子郵件用戶端

下列電子郵件用戶端支援新式驗證和條件式存取。

|平台|用戶端|版本/附註|
|---|---|---|
|**Windows**|Outlook|2019、2016、2013 <p> [啟用新式驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [必要更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS 版 Outlook|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019和2016|
|**Linux**|不支援||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>保護文件時的建議用戶端平台

套用安全檔原則時，建議使用下列用戶端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 應用程式|SharePoint 應用程式|[OneDrive 同步處理用戶端](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|支援|支援|不適用|不適用|支援|
|Windows 10|支援|支援|不適用|不適用|支援|
|Android|支援|支援|支援|支援|N/A|
|iOS|支援|支援|支援|支援|N/A|
|macOS|支援|支援|不適用|不適用|不支援|
|Linux|不支援|不支援|不支援|不支援|不支援|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365 用戶端支援

如需 Microsoft 365 中用戶端支援的詳細資訊，請參閱下列文章：

- [Microsoft 365 用戶端應用程式支援-條件式存取](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 用戶端應用程式支援-多重要素驗證](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>保護系統管理員帳戶

針對 Microsoft 365 E3 或 E5，或搭配個別的 Azure AD Premium P1 或 P2 授權，您可以要求使用手動建立的條件式存取原則進行 MFA 的系統管理員帳戶。 請參閱 [條件式存取：對系統管理員要求 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) 以取得詳細資料。

在不支援條件式存取的 Microsoft 365 或 Office 365 版本中，您可以啟用 [安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) ，以要求對所有帳戶執行 MFA。

以下是一些額外的建議：

- 使用 [AZURE AD 特權身分識別管理](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) 來減少持久管理帳戶的數目。
- 使用「特殊許可權[存取管理](../../compliance/privileged-access-management-overview.md)」來保護您的組織不會因可能使用現有的許可權系統管理員帳戶存取機密資料或存取重要的設定設定而遭到破壞。
- 建立並使用個別帳戶，只指派給 [Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)*的管理*。 管理員應該擁有自己的使用者帳戶，以進行一般非系統管理，且只有在必要時才使用系統管理帳戶，才可完成與其角色或工作職能相關聯的工作。
- 遵循在 Azure AD 中保護特權帳戶的 [最佳作法](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) 。

## <a name="next-step"></a>下一步

[![步驟2：設定一般身分識別和存取條件式存取原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[設定一般身分識別和裝置存取原則](identity-access-policies.md)
