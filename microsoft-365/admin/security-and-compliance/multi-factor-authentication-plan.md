---
title: 規劃 Microsoft 365 部署的多重要素驗證
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Microsoft 365 中的多重要素驗證，以及設定它時所需遵循的步驟。
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665665"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>規劃 Microsoft 365 部署的多重要素驗證

多重要素驗證 (MFA) 是一種需要使用多種驗證方法並為使用者登入和交易額外添加一層安全性的驗證方法。 其運作方式是要求包含使用者帳戶密碼以外資訊的附加驗證步驟，例如：
  
- 傳送至您 smart phone 的隨機產生的驗證碼
    
- 電話
    
- 智慧卡 (虛擬或實體) 
    
- 生物特徵辨識裝置 
    
## <a name="mfa-in-microsoft-365"></a>Microsoft 365 中的 MFA

Microsoft 365 使用 MFA 協助提供額外的安全性，並從 Microsoft 365 系統管理中心加以管理。 Microsoft 365 提供下列[Azure Multi-Factor 驗證](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)功能的子集做為訂閱的一部分： 
  
- 為使用者啟用及強制執行 MFA 的能力
    
- 使用行動裝置 App (線上和單次密碼 [OTP]) 做為次要驗證因素
    
- 使用電話做為次要驗證因素
    
- 使用短訊息服務（SMS）短消息作為第二個驗證因素
    
- 非瀏覽器用戶端的應用程式密碼（例如，Microsoft Lync 2013 通訊軟體）
    
- 驗證電話期間的預設 Microsoft 問候語
    
如需新增功能的完整清單，請參閱[Azure Multi-Factor 驗證](https://go.microsoft.com/fwlink/?LinkId=506927)。 您可以透過購買[Azure Multi-Factor 驗證授權](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)，永遠取得完整功能。 
  
您會收到不同的功能子集，具體取決於您使用的是僅限雲端的身分識別，其中的使用者帳戶已存在於 Microsoft 365，或是使用單一登入和 Active Directory Federation Services （AD FS）的混合式設定。 
  
|**您在何處管理 Microsoft 365？**|**MFA 次要因素選項**|
|:-----|:-----|
|僅限雲端  <br/> | Azure Multi-Factor 驗證（文字或電話）  <br/> |
|混合設定、受管理的內部部署  <br/> | 如果您透過內部部署管理使用者身分識別，您有下列選擇：  <br/> -實體或虛擬智慧卡（AD FS）  <br/> -Azure Multi-Factor 驗證（AD FS 的模組）  <br/>  -Azure Multi-Factor 驗證  <br/> |
   
Office 2013 裝置應用程式透過使用[Active Directory 驗證程式庫（ADAL）](https://go.microsoft.com/fwlink/p/?LinkId=526684)來支援 MFA。 Azure Active Directory （Azure AD）主控使用者可以登入的網頁。 身分識別提供者可以是 Azure AD 或 AD FS 等同盟身分識別提供者。 同盟使用者的驗證按下列步驟進行：
  
1. Azure AD 會將使用者重新導向至由組織之身分識別提供者所主控的登入網頁。 身分識別提供者取決於使用者登入名稱中指定的網域。
    
2. 使用者在他的裝置的登入網頁上登入。 
    
3. 使用者成功登入後，身分識別提供者會傳回權杖給 Azure AD。
    
4. Azure AD 會將 JSON Web Token （JWT）傳回給 Office 裝置應用程式，而且裝置應用程式會透過使用與 Microsoft 365 的 JWT 驗證。 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Office 2013 用戶端應用程式的需求

若要啟用適用於 Office 2013 用戶端應用程式的 MFA，您必須安裝下列軟體 (以下所列的版本或更新版本)，根據您擁有的是[隨選即用型安裝](#click-to-run-based-installations)或 [MSI 型安裝](#msi-based-installations)而定。
  
若要判斷您的 Office 安裝是否為隨選即用或 MSI 型：
  
1. 啟動 Outlook 2013。
    
2. **在 [檔案] 功能表上**，選擇 [ **Office 帳戶**]。
    
3. For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed. 
    
    ![如何判斷您的 Office 2013 安裝是隨選即用或以 MSI 為基礎的](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

Sor 詳細資訊，請參閱[關於新式驗證 wiki 文章的常見問題](https://go.microsoft.com/fwlink/p/?LinkId=530064)。
  
### <a name="click-to-run-based-installations"></a>隨選即用型安裝

若為隨選即用安裝，您必須安裝下列軟體，並列出下列檔案版本或更新的檔案版本。 如果您的檔案版本並非大於或等於列出的檔案版本，請使用下列步驟進行更新。
  
|**檔案名稱**|**電腦上的安裝路徑**|**檔案版本**|
|:-----|:-----|:-----|
|MSO.Dll  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|Csi。Dll  <br/> |CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook .exe  <br/> |C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|ADAL.Dll  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |不盡相同  <br/> |
   
### <a name="msi-based-installations"></a>MSI 型安裝

若是 MSI 型安裝，您必須安裝下列軟體 (以下所列的檔案版本或更新的檔案版本)。如果您的檔案版本並非大於或等於列出的檔案版本，請使用「更新知識庫文章」一欄中的連結進行更新。
  
|**檔案名稱**|**電腦上的安裝路徑**|**可於何處取得更新**|**版本**|
|:-----|:-----|:-----|:-----|
|MSO.Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|Csi。Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook .exe  <br/> |C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|ADAL.Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |不適用  <br/> |
   
## <a name="enable-mfa"></a>啟用 MFA

若要為您的訂閱啟用 MFA，請遵循下列步驟：
  
1. 視需要： 

  - [在 Windows 裝置上啟用 Office 2013 的新式驗證](enable-modern-authentication.md)。
    
  - 使用協力廠商目錄服務設定 Azure Multi-Factor 驗證。
    
    請參閱[使用 Azure Multi-Factor 驗證和協力廠商 VPN 解決方案的高級案例](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)，以取得此程式接受之特定身分識別提供者的資訊。 
    
2. [設定 Microsoft 365 的 MFA](set-up-multi-factor-authentication.md)。
    
3. 告訴個別使用者如何以 MFA 登入。 請參閱[使用 MFA 登入 Microsoft 365](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb)。

> [!IMPORTANT]
> 如果您已對使用者啟用 Azure Multi-Factor 驗證，而且他們的任何執行 Office 2013 的裝置都未啟用新式驗證，則需要在這些裝置上使用 AppPasswords。 如需 AppPasswords 及應使用方式的詳細資訊，請參閱下列網址： [Azure Multi-Factor 驗證的應用程式密碼](https://go.microsoft.com/fwlink/p/?LinkId=528178)。
  
## <a name="faq"></a>常見問題集

[新式驗證 Wiki 文章的相關常見問題集](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a>已知問題

[Office 2013 和 Microsoft 365 Apps for enterprise 新式驗證：上架之前所需注意的事項](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Azure 多重要素驗證疑難排解：**
  
請參閱[Azure Multi-Factor 驗證疑難排解](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。
  
[如何針對使用 AD FS 時的 Office 2013 新式驗證之登入問題進行疑難排解](https://support.microsoft.com/kb/3052203/)
  
 **當無法使用替代識別碼時：**
  
[如何使用 PowerShell 修正 UPN 重複的問題](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[用來修正使用者主體名稱重複問題的指令碼](https://go.microsoft.com/fwlink/p/?LinkId=396725) (英文)
  
 **用戶端存取篩選：**
  
[適用于企業新式驗證及用戶端存取篩選原則的 Office 2013 和 Microsoft 365 應用程式：上架須知](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **哪些應用程式支援 MFA？**
  
|**Windows**|**Mac**|**iOS**|**Android 手機**|**Android 平板電腦**|
|:-----|:-----|:-----|:-----|:-----|
|此版本支援 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 及商務用 Skype 的新式驗證。  <br/> |此版本支援 Mac 版 Word 2016、Mac 版 Excel 2016 及 Mac 版 PowerPoint 2016 的新式驗證。  <br/> |此版本支援 iPad 版 Word、iPad 版 Excel 及 iPad 版 PowerPoint 的新式驗證。  <br/> |此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。  <br/> |此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。  <br/> |
|此版本支援 Outlook 2013 和 Outlook 2016 的新式驗證。  <br/> |此版本支援 Mac 版 Outlook 2016 的新式驗證。  <br/> |此版本支援 iPad 版 Outlook 的新式驗證。  <br/> |||
   

