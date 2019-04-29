---
title: 適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入。
ms.openlocfilehash: 210d59b0e578b807b9f9ee73e9bff11e7f2502a0
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400157"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入

Azure AD 無縫單一登入 (SSO) 會在使用者所在的個人電腦或裝置連線到公司網路時自動將他們登入。Azure AD 無縫 SSO 可讓使用者輕鬆存取雲端式應用程式，而不需要任何額外的內部部署元件。

本文說明如何設定您的 Microsoft 365 測試環境以進行 Azure AD 無縫 SSO。

此測試環境的設定分為兩個階段︰

1.  使用密碼雜湊同步處理建立 Microsoft 365 模擬企業測試環境。
2.  在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect。
    
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理

請遵循[適用於 Microsoft 365 的密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。
  
![使用密碼雜湊同步處理測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此組態包含： 
  
- Office 365 E5 和 EMS E5 試用版或付費訂閱。
- 簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成 
- Azure AD Connect 會在 APP1 上執行，以將 TESTLAB Active Directory Domain Services (AD DS) 網域定期同步至 Office 365 和 EMS E5 訂閱的 Azure AD 租用戶。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>階段 2：在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect

在這個階段中，您會在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect，然後驗證它是否運作正常。

### <a name="configure-azure-ad-connect-on-app1"></a>在 APP1 上設定 Azure AD Connect

1. 從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。

2. 從 APP1 的桌面執行 Azure AD Connect。

3. 在 [歡迎]**** 頁面上，按一下 [設定]****。

4. 在 [其他工作]**** 頁面上，按一下 [變更使用者登入]****，然後按一下 [下一步]****。

5. 在 [連線到 Azure AD]**** 頁面上，輸入您的全域管理員帳戶認證，然後按 [下一步]****。

6. 在 [使用者登入]**** 頁面上，選取 [啟用單登入]****，然後按 [下一步]****。

7. 在 [啟用單一登入]**** 頁面上，按一下 [輸入認證]****。

8. 在 [Windows 安全性]**** 對話方塊中，輸入 **user1** 和 user1 帳戶的密碼，然後按一下 [確定]****。按 [下一步]****。

9. 在 [準備設定]**** 頁面上，按一下 [設定]****。

10. 在 [組態完成]**** 頁面上，按一下 [結束]****。

11. 從 Azure 入口網站的左窗格，按一下 [Azure Active Directory > Azure AD Connect]****。確認 [無縫單一登入]**** 功能顯示為 [已啟用]****。

接下來，以 <strong>user1@testlab.</strong>\<您的公用網域> User1 帳戶的使用者名稱測試登入 Office 365 訂閱的能力。

1. 從 APP1 上的 Internet Explorer 中，按一下設定圖示，然後按一下 [網際網路選項]****。
 
2. 在 [網際網路選項]**** 中，按一下 [安全性]**** 索引標籤。

3. 按一下 [近端內部網路]****，然後按一下 [網站]****。

4. 在 [近端內部網路]**** 中，按一下[進階]****。

5. 在 [將這個網站新增到區域]**** 中，輸入 **https<span>://</span>autologon.microsoftazuread-sso.com**，然後按一下 [新增 > 關閉 > 確定 > 確定]****。

6. 登出 Office 365，然後再次登入，這次指定不同的帳戶。

7. 提示登入時，指定 <strong>user1@testlab.</strong>\<your public domain> name，然後按一下 [下一步]****。 您應該成功以 User1 登入，且系統不會提示您輸入密碼。 這可證明 Azure AD 無縫 SSO 正在執行。

請注意，User1 雖具有 TESTLAB AD DS 網域的網域管理員權限，但並不是 Azure AD 和 Office 365 的全域管理員。 因此，您不會看到 [管理員]**** 圖示選項。

以下是您產生的組態：

![使用傳遞驗證測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
此組態包含：

- 已註冊 DNS 網域 testlab.\<您的網域名稱> 的 Office 365 E5 和 EMS E5 試用版或付費訂閱。
- 簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成 
- Azure AD Connect 在 APP1 上執行，以將來自 Office 365 和 EMS E5 訂閱之 Azure AD 租用戶的帳戶和群組清單同步至 TESTLAB AD DS 網域。 
- 啟用 Azure AD 無縫 SSO，可讓模擬內部網路上的電腦登入 Microsoft 365 雲端，而無需指定使用者帳戶的密碼。

如需在生產中設定 Azure AD 無縫 SSO 的相關資訊和連結，請參閱身分識別階段中的[簡化使用者登入](identity-password-reset.md#identity-sso)步驟。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)


