---
title: 適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入。
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487597"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入

*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*

Azure AD 無縫單一 Sign-On (無縫 SSO) 會在使用者位於連接至其組織網路的電腦或裝置上時，自動登入使用者。Azure AD 無縫 SSO 可讓使用者輕鬆存取雲端架構應用程式，而不需要任何其他內部部署元件。

本文說明如何針對 Azure AD 無縫 SSO 設定 Microsoft 365 測試環境。

設定 Azure AD 無縫 SSO 包含兩個階段：
- [階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [階段 2：在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理

依照 [Microsoft 365 的密碼雜湊同步](password-hash-sync-m365-ent-test-environment.md)處理中的指示進行。 

您產生的設定如下所示：
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此組態包含：
  
- Microsoft 365 E5 試用版或付費訂閱。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。
- Azure AD Connect 會在 APP1 執行，定期將 AD DS) 網域 (的 TESTLAB Active Directory 網域服務同步處理至您 Microsoft 365 訂閱的 Azure AD 租使用者。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>階段 2：在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect

在此階段中，針對 Azure AD 無縫 SSO 的 APP1 設定 Azure AD Connect，然後驗證它是否運作正常。

### <a name="configure-azure-ad-connect-on-app1"></a>在 APP1 上設定 Azure AD Connect

1. 從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。

2. 從 APP1 桌面，執行 Azure AD Connect。

3. 在 [ **歡迎] 頁面**上，選取 [ **設定**]。

4. 在 [ **其他** 工作] 頁面上，選取 [ **變更使用者登入**]，然後選取 **[下一步]**。

5. 在 [連線 **到 AZURE AD]** 頁面上，輸入您的全域系統管理員帳號憑證，然後選取 **[下一步]**。

6. 在 [ **使用者登入** ] 頁面上，選取 [ **啟用單一登入**]，然後選取 **[下一步]**。

7. 在 [ **啟用單一登入** ] 頁面上，選取 [ **輸入認證**]。

8. 在 [ **Windows 安全性** ] 對話方塊中，輸入 **user1** 及 user1 帳戶的密碼，然後選取 **[確定]**，然後選取 **[下一步**]。

9. 在 [ **準備設定** ] 頁面上，選取 [ **設定**]。

10. 在 [設定完成] 頁面上 **，選取 [****結束**]。

11. 從 Azure 入口網站的左窗格中，選取 [ **azure Active Directory**  >  **Azure AD Connect**]。 確認 **無縫單一登入** 功能顯示為 [ **已啟用**]。

接下來，使用 user1@testlab 測試登入訂閱的功能 <strong>。</strong>\<*your public domain*> User1 帳戶的使用者名稱。

1. 從 Internet Explorer 的 APP1 上，選取 [設定] 圖示，然後選取 [ **網際網路選項**]。
 
2. 在 [ **網際網路選項**] 中，選取 [ **安全性** ] 索引標籤。

3. 選取 [ **本機內部**網路]，然後選取 [ **網站**]。

4. 在 [ **本機內部**網路] 中，選取 [ **高級**]。

5. 在 **[將此網站新增至] 區域**中，輸入**HTTPs：<span>//</span>autologon.microsoftazuread-sso.com**，然後選取 [**新增**  >  **關閉**  >  **]**[確定  >  **]**。

6. 登出然後再次登入，這次指定不同的帳戶。

7. 當系統提示您登入時，請指定 <strong>user1@testlab。</strong>\<*your public domain*> 名稱，然後選取 **[下一步]**。 您應該成功以 User1 登入，且系統不會提示您輸入密碼。 這可證明 Azure AD 無縫 SSO 正在執行。

請注意，User1 雖具有 TESTLAB AD DS 網域的網域管理員權限，但並不是 Azure AD 的全域管理員。 因此，您不會看到 [管理員]**** 圖示選項。

以下是您產生的組態：

![使用傳遞驗證測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

此組態包含：

- 使用 DNS 網域 testlab 的 Microsoft 365 E5 試用版或付費訂閱。\<*your domain name*> 註冊。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。
- Azure AD Connect 會在 APP1 上執行，以將來自 Microsoft 365 訂閱之 Azure AD 租用戶的帳戶和群組清單同步至 TESTLAB AD DS 網域。
- 啟用 Azure AD 無縫 SSO，使模擬內部網路上的電腦無需指定使用者帳戶密碼，即可登入 Microsoft 365 雲端資源。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[適用于企業的 Microsoft 365 檔](https://docs.microsoft.com/microsoft-365-enterprise/)
