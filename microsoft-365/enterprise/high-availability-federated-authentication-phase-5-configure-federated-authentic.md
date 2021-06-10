---
title: 高可用性同盟驗證階段5設定 Microsoft 365 的同盟驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 摘要：針對 Microsoft Azure 中 Microsoft 365 的高可用性同盟驗證設定 Azure AD 連線。
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929405"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a>高可用性同盟驗證階段5：設定 Microsoft 365 的同盟驗證

在此最後一個部署 Azure 基礎結構服務中 Microsoft 365 的高可用性同盟驗證的最後階段，您可以取得及安裝公用憑證授權單位單位所發出的憑證、驗證您的設定，然後在目錄同步處理伺服器上安裝並執行 Azure AD 連線。 Azure AD 連線針對同盟驗證，設定 Microsoft 365 訂閱和 Active Directory Federation Services (AD FS) 和 web 應用程式 proxy 伺服器。
  
如需所有階段，請參閱[在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)。
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a>取得公用憑證並將其複製到目錄同步處理伺服器

從具有下列屬性的公用憑證授權單位單位取得數位憑證：
  
- 適用于建立 SSL 連線的 x.509 憑證。
    
- 主體替代名稱 (SAN) 擴充屬性設定為您的同盟服務 FQDN (範例： fs.contoso.com) 。
    
- 憑證必須有私密金鑰，而且可以儲存為 PFX 格式。
    
此外，您的組織電腦和裝置必須信任發行數位憑證的公用憑證授權單位單位。 這項信任是透過從您的電腦和裝置上的「受信任的根憑證授權單位」存放區中安裝的公用憑證授權單位單位來建立。 執行 Microsoft Windows 的電腦一般會從一般使用的憑證授權單位單位安裝一組這類憑證。 若尚未安裝您的公用憑證授權單位單位的根憑證，則必須將其部署至您組織的電腦和裝置。
  
如需有關同盟驗證之憑證需求的詳細資訊，請參閱 [同盟安裝和設定的必要條件](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)。
  
當您收到憑證時，請將它複製到目錄同步處理伺服器 C：磁片磁碟機上的資料夾。 例如，將檔案命名為 SSL，並將其儲存在目錄同步處理伺服器上的 [C： \\ 證書] 資料夾中。
  
## <a name="verify-your-configuration"></a>驗證您的設定

您現在應該可以為 Microsoft 365 設定 Azure AD 連線和同盟驗證。 若要確定您是，以下是檢查清單：
  
- 您組織的公用網域會新增至您的 Microsoft 365 訂閱。
    
- 組織的 Microsoft 365 使用者帳戶會設定為您組織的公用功能變數名稱，而且可成功登入。
    
- 您已根據您的公用功能變數名稱判斷同盟服務 FQDN。
    
- 您的同盟服務 FQDN 的公用 DNS A 記錄指向 web 應用程式 proxy 伺服器的網際網路對向 Azure 負載平衡器的公用 IP 位址。
    
- 您的同盟服務 FQDN 的私人 DNS A 記錄會指向 AD FS 伺服器內部 Azure 負載平衡器的私人 IP 位址。
    
- 適用于將 SAN 設定為您的同盟服務 FQDN 之 SSL 連線的公用憑證授權單位單位-isssued 數位憑證是儲存在目錄同步處理伺服器上的 PFX 檔案。
    
- 公用憑證授權單位單位的根憑證會安裝在電腦和裝置上的「受信任的憑證授權單位單位」存放區中。
    
以下是 Contoso 組織的範例：
  
**Azure 中高可用性同盟驗證基礎結構的範例設定**

![Azure 中設定高可用性 Microsoft 365 同盟驗證基礎結構的範例](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a>執行 Azure AD 連線以設定同盟驗證

Azure AD 連線工具使用下列步驟來設定 AD FS 伺服器、web 應用程式 proxy 伺服器及 Microsoft 365 以進行同盟驗證：
  
1. 使用具有本機系統管理員許可權的網域帳戶，建立目錄同步處理伺服器的遠端桌面連線。
    
2. 從目錄同步處理伺服器的桌面，開啟 Internet Explorer，然後移至 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 。
    
3. 在 [ **Microsoft Azure Active Directory 連線**] 頁面上，按一下 [**下載**]，然後按一下 [**執行**]。
    
4. 在 [**歡迎使用 Azure AD 連線**] 頁面上，按一下 [**我同意**]，然後按一下 [**繼續]。**
    
5. 在 [ **Express 設定**] 頁面上，按一下 [**自訂**]。
    
6. 在 [ **安裝必要元件** ] 頁面上，按一下 [ **安裝**]。
    
7. 在 [使用者登入] 頁面上，按一下 [和 AD FS 的同盟]，然後按 [下一步]。
    
8. 在 [**連線至 Azure AD** ] 頁面上，輸入 Microsoft 365 訂閱的全域系統管理員帳戶名稱和密碼，然後按 **[下一步]**。
    
9. 在 [**連線您的目錄**] 頁面上，確定已選取 **樹** 系中的內部部署 Active Directory 網域服務 (AD DS) 樹系，輸入網域管理員帳戶的名稱和密碼，然後按一下 [**新增目錄**]，再按 **[下一步]**。
    
10. 在 [ **AZURE AD 登錄** 設定] 頁面上，按 **[下一步]**。
    
11. 在 [ **網域與 OU 篩選** ] 頁面上，按 **[下一步]**。
    
12. 在 [ **唯一識別您的使用者** ] 頁面上，按 **[下一步]**。
    
13. 在 [ **篩選使用者和裝置** ] 頁面上，按 **[下一步]**。
    
14. 在 [ **選用功能** ] 頁面上，按 **[下一步]**。
    
15. 在 [ **AD fs 伺服器** 陣列] 頁面上，按一下 [ **設定新的 AD fs 伺服器** 陣列]。
    
16. 按一下 **[流覽]** ，並指定公用憑證授權單位單位之 SSL 憑證的位置和名稱。
    
17. 出現提示時，請輸入憑證密碼，然後按一下 **[確定]**。
    
18. 確認 **主體名稱** 及 **同盟服務名稱** 已設定為您的同盟服務 FQDN，然後按 **[下一步]**。
    
19. 在 [ **AD fs 伺服器** ] 頁面上，輸入您第一個 AD fs 伺服器的名稱 (Table M-專案 4-虛擬機器名稱] 欄) ，然後按一下 [ **新增**]。
    
20. 輸入您第二個 AD FS 伺服器的名稱 (Table M-專案 5-虛擬機器名稱] 欄) ，按一下 [ **新增**]，然後按 **[下一步]**。
    
21. 在 [ **Web 應用程式 proxy 伺服器** ] 頁面上，輸入您第一個 Web 應用程式 proxy 伺服器的名稱 (Table M-專案 6-虛擬機器名稱] 欄) ，然後按一下 [ **新增**]。
    
22. 輸入第二個 web 應用程式 proxy 伺服器的名稱 (Table M-專案 7-虛擬機器名稱] 欄) ，按一下 [ **新增**]，然後按 **[下一步]**。
    
23. 在 [ **網域管理員認證** ] 頁面上，輸入網域管理員帳戶的使用者名稱和密碼，然後按 **[下一步]**。
    
24. 在 [ **AD FS 服務帳戶** ] 頁面上，輸入企業系統管理員帳戶的使用者名稱和密碼，然後按 **[下一步]**。
    
25. 在 [ **AZURE AD 網域** ] 頁面的 [ **網域**] 中，選取您組織的 DNS 功能變數名稱，然後按 **[下一步]**。
    
26. 在 [準備設定] 頁面上，按一下 [安裝]。
    
27. 在 [安裝完成] 頁面上，按一下 [驗證]。 您應該會看到兩封訊息，指出內部網路和網際網路設定均已成功驗證。
    
  - 內部網路郵件應該會列出您的 AD FS 伺服器之 Azure 內部負載平衡器的私人 IP 位址。
    
  - 網際網路訊息應該會列出您的 web 應用程式 proxy 伺服器之 Azure 網際網路對向負載平衡器的公用 IP 位址。
    
28. 在 [安裝完成] 頁面上，按一下 [結束]。
    
以下是伺服器的最後設定，具有預留位置名稱。
  
**第5階段： Azure 中高可用性同盟驗證基礎結構的最終設定**

![Azure 中高可用性 Microsoft 365 同盟驗證基礎結構的最終設定](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Azure 中 Microsoft 365 的高可用性同盟驗證基礎結構已完成。
  
## <a name="see-also"></a>另請參閱

[Azure 中的 Microsoft 365 高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Microsoft 365 開發/測試環境的同盟身分識別](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 解決方案與架構中心](../solutions/index.yml)

[Microsoft 365 的同盟身分識別](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)