---
title: Office 365 部署多重要素驗證方案
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
description: 深入瞭解 Office 365 中的多重要素驗證，以及設定所需遵循的步驟。
ms.openlocfilehash: be3b355f4487e2df5c2e20c9911c3bb421d5f7e1
ms.sourcegitcommit: 00ce4626e1be182c5a91210a23662c9704384efa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170937"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Office 365 部署多重要素驗證方案

多重要素驗證 (MFA) 是一種需要使用多種驗證方法並為使用者登入和交易額外添加一層安全性的驗證方法。它的運作方式是要求使用下列兩種或更多的驗證方法：
  
- 隨機產生的密碼
    
- 電話
    
- 智慧卡 (虛擬或實體) 
    
- 生物特徵辨識裝置 
    
## <a name="multi-factor-authentication-in-office-365"></a>Office 365中的多重要素驗證

Office 365 使用多重要素驗證，協助提供額外的安全性，並從 Microsoft 365 系統管理中心加以管理。 Office 365 提供下列 Azure Multi-Factor 驗證功能的子集做為訂閱的一部分： 
  
- 能夠啟用並強制執行使用者的多重要素驗證
    
- 使用行動裝置 App (線上和單次密碼 [OTP]) 做為次要驗證因素
    
- 使用電話做為次要驗證因素
    
- 使用簡訊服務 (SMS) 訊息做為次要驗證因素
    
- 非瀏覽器用戶端的應用程式密碼 (例如，Microsoft Lync 2013 通訊軟體)
    
- 驗證電話期間的預設 Microsoft 問候語
    
如需新增功能的完整清單，請參閱 [Azure 多重要素驗證版本比較](https://go.microsoft.com/fwlink/?LinkId=506927)。您可以購買 Azure 多重要素驗證服務，隨時獲得完整功能。 
  
視您擁有的是 Office 365 之僅限雲端部署或使用單一登入和 Active Directory 同盟服務 (AD FS) 的混合設定而定，您會獲得不同的功能子集。 
  
|**您在何處管理 Office 365 租用戶？**|**MFA 次要因素選項**|
|:-----|:-----|
|僅限雲端  <br/> |Azure Multi-Factor 驗證（文字或電話）  <br/> |
|混合設定、受管理的內部部署  <br/> | 如果您透過內部部署管理使用者身分識別，您有下列選擇：  <br/>  實體或虛擬智慧卡（使用 AD FS 時）  <br/> [Azure Multi-Factor 驗證](https://go.microsoft.com/fwlink/p/?LinkId=526677)（AD FS 的模組）  <br/>  Azure Active Directory （Azure AD） Multi-Factor 驗證  <br/> |
   
  
下圖顯示更新的 Office 2013 裝置 App (Windows 版) 如何讓使用者能夠使用 MFA 登入。 Office 2013 裝置應用程式透過使用[Active Directory 驗證程式庫（ADAL）](https://go.microsoft.com/fwlink/p/?LinkId=526684)來支援多重要素驗證。 Azure AD 託管使用者可以登入的網頁。 身分識別提供者可以是 Azure AD 或 AD FS 等同盟身分識別提供者。 同盟使用者的驗證按下列步驟進行：
  
1. Azure AD 將使用者重新導向到由 Office 365 租用戶的記錄之身分識別提供者託管的登入網頁。身分識別提供者取決於使用者登入名稱中指定的網域。
    
2. 使用者在他的裝置的登入網頁上登入。 
    
3. 使用者成功登入後，身分識別提供者會傳回權杖給 Azure AD。
    
4. Azure AD 會傳回 JSON Web 權杖 (JWT) 給 Office 裝置 App，而裝置 App 會搭配 Office 365 使用 JWT 獲得授權。 
    
請見下圖的詳細說明：
  
![Office 2013 裝置應用程式的現代化驗證。](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a>軟體需求

若要啟用適用於 Office 2013 用戶端應用程式的 MFA，您必須安裝下列軟體 (以下所列的版本或更新版本)，根據您擁有的是[隨選即用型安裝](#click-to-run-based-installations)或 [MSI 型安裝](#msi-based-installations)而定。
  
若要判斷您的 Office 安裝是否為隨選即用或 MSI 型：
  
1. 啟動 Outlook 2013。
    
2. **在 [檔案] 功能表上**，選擇 [ **Office 帳戶**]。
    
3. For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed. 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a>隨選即用型安裝

若是隨選即用型安裝，您必須安裝下列軟體 (以下所列的檔案版本或更新的檔案版本)。如果您的檔案版本並非大於或等於列出的檔案版本，請使用下列步驟進行更新。
  
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

若要啟用 MFA，您必須完成下列事項：
  
1. 啟用新式驗證的用戶端：
    
  - [在 Windows 裝置上啟用 Office 2013 的新式驗證](enable-modern-authentication.md) 。 
    
  - 使用協力廠商目錄服務設定 Azure Multi-Factor 驗證。
    
    請參閱[Azure Multi-Factor 驗證和協力廠商 VPN 解決方案的高級案例](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)，以取得此程式接受之特定身分識別提供者的資訊。 
    
2. [設定 Office 365 的多重要素驗證](set-up-multi-factor-authentication.md)
    
3. 告知個別使用者如何使用 MFA 登入：[使用雙步驟驗證登入 Office 365](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)。
    
> [!IMPORTANT]
> 如果您已對使用者啟用 Azure Multi-Factor 驗證，而且他們的任何執行 Office 2013 的裝置都未啟用新式驗證，則需要在這些裝置上使用 AppPasswords。 如需更多有關 AppPasswords 以及應使用它們的時機/位置/方式，請參閱：[Azure 多重要素驗證的應用程式密碼](https://go.microsoft.com/fwlink/p/?LinkId=528178)。 
  
## <a name="faq"></a>常見問題集

[新式驗證 Wiki 文章的相關常見問題集](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 **已知問題：**
  
[Office 2013 和 Office 365 專業增強版新式驗證：上線前的相關須知](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Azure 多重要素驗證疑難排解：**
  
請參閱[Azure Multi-Factor 驗證疑難排解](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。
  
[如何針對使用 AD FS 時的 Office 2013 新式驗證之登入問題進行疑難排解](https://support.microsoft.com/kb/3052203/)
  
 **當無法使用替代識別碼時：**
  
[如何使用 PowerShell 修正 UPN 重複的問題](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[用來修正使用者主體名稱重複問題的指令碼](https://go.microsoft.com/fwlink/p/?LinkId=396725) (英文)
  
 **用戶端存取篩選：**
  
[Office 2013 和 Office 365 專業增強版新式驗證和用戶端存取篩選原則：上線前的相關須知](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **哪些應用程式支援 MFA？**
  
|**Windows**|**Mac**|**iOS**|**Android 手機**|**Android 平板電腦**|
|:-----|:-----|:-----|:-----|:-----|
|此版本支援 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 及商務用 Skype 的新式驗證。  <br/> |此版本支援 Mac 版 Word 2016、Mac 版 Excel 2016 及 Mac 版 PowerPoint 2016 的新式驗證。  <br/> |此版本支援 iPad 版 Word、iPad 版 Excel 及 iPad 版 PowerPoint 的新式驗證。  <br/> |此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。  <br/> |此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。  <br/> |
|此版本支援 Outlook 2013 和 Outlook 2016 的新式驗證。  <br/> |此版本支援 Mac 版 Outlook 2016 的新式驗證。  <br/> |此版本支援 iPad 版 Outlook 的新式驗證。  <br/> |||
   

