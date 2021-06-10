---
title: 適用於 Office 365 測試環境的密碼雜湊同步處理
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 摘要：為您的 Office 365 測試環境設定及示範密碼雜湊同步處理並且登入。
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921501"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>適用於 Office 365 測試環境的密碼雜湊同步處理

*此測試實驗室指南可用於 enterprise 和 Office 365 企業版測試環境的 Microsoft 365。*

許多組織使用 Azure AD Connect 和密碼雜湊同步處理，將其內部部署 Active Directory Domain Services (AD DS) 樹系中的帳戶集同步處理至 Microsoft 365 訂閱的 Azure AD 租用戶帳戶集。 

本文說明如何在 Microsoft 365 測試環境中新增密碼雜湊同步處理，這會產生下列設定：
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
設定此測試環境包括三個階段：
- [階段 1：建立 Microsoft 365 模擬企業測試環境](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [階段 2：建立及註冊 testlab 網域](#phase-2-create-and-register-the-testlab-domain)
- [階段 3：在 APP1 上安裝 Azure AD Connect](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> 如需適用于企業測試實驗室指南堆疊的 Microsoft 365 中的所有文章的視覺對應，請移至[Microsoft 365 for enterprise test lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>階段 1：建立 Microsoft 365 模擬企業測試環境

依照[模擬企業基本設定的 Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md)中的指示進行。 您產生的設定如下所示：
  
![模擬企業基本設定](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
此組態包含：
  
- Microsoft 365 E5 試用版或付費訂閱。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路中的 DC1、APP1 和 CLIENT1 虛擬機器所組成。 DC1 是 testlab 的網域控制站。 <您的 *公用功能變數名稱*> AD DS 網域。

## <a name="phase-2-create-and-register-the-testlab-domain"></a>階段 2：建立及註冊 testlab 網域

在這個階段中，新增公用 DNS 網域，然後將其新增至您的訂閱。

首先，請與您的公用 DNS 註冊提供者合作，以根據您目前的功能變數名稱建立新的公用 DNS 功能變數名稱，然後將其新增至您的訂閱。 建議使用 name **testlab <*您的公用網域* >**。 例如，如果您的公用功能變數名稱是 **<span>contoso</span>.com**，請新增 public domain name： **<span>testlab</span>. contoso.com**。
  
接下來，透過網域註冊程式，將 **<testlab *您的公用網域* >** 網域新增至 Microsoft 365 試用或付費訂閱。 這包含在 testlab 中新增額外的 DNS 記錄 **。 <*您的公用網域* >** 網域。 如需詳細資訊，請參閱[Add a domain to Microsoft 365](../admin/setup/add-domain.md)。

您產生的設定如下所示：
  
![testlab 網域名稱註冊](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
此組態包含：

- 使用 DNS 網域 testlab Microsoft 365 E5 試用版或付費訂閱。 <*您的公用功能變數名稱*> 已註冊。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。

請注意，testlab <*您的公用功能變數名稱*> 現在如下：

- 由公用 DNS 記錄支援。
- 已在您的 Microsoft 365 訂閱中註冊。
- 模擬內部網路上的 AD DS 網域。
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>階段 3：在 APP1 上安裝 Azure AD Connect

在這個階段中，請在 APP1 上安裝及設定 Azure AD 連線工具，然後驗證它是否運作正常。
  
首先，在 APP1 上安裝及設定 Azure AD 連線。

1. 從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\\User1 帳戶連線到 APP1。
    
2. 從 APP1 的桌面，開啟系統管理員層級 Windows PowerShell 命令提示字元，然後執行下列命令以停用 Internet Explorer 增強的安全性：
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. 從工作列中，選取 [ **Internet Explorer** ]，然後移至 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 。
    
4. 在 [Microsoft Azure Active Directory 連線] 頁面上，選取 [**下載**]，然後選取 [**執行**]。
    
5. 在 [**歡迎使用 Azure AD 連線**] 頁面上，選取 [**我同意**]，然後選取 [**繼續**]。
    
6. 在 [ **Express 設定**] 頁面上，選取 [**使用快速設定**]。
    
7. 在 [**連線至 Azure AD** ] 頁面上，在 [使用者名稱] 中輸入全域管理員帳戶名稱 **，** 在 [**密碼**] 中輸入其密碼，然後選取 **[下一步]**。
    
8. 在 [**連線到 AD DS** ] 頁面上，輸入 [ **TESTLAB \\ User1** in **Username]，** 在 [**密碼**] 中輸入密碼，然後選取 **[下一步]**。
    
9. 在 [ **準備設定** ] 頁面上，選取 [ **安裝**]。
    
10. 在 [設定完成] 頁面上 **，選取 [****結束**]。
    
11. 在 Internet Explorer 中，移至 Microsoft 365 系統管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))。
    
12. 在左功能窗格中，選取 [ **使用者] >**[作用中的使用者]。
    
    請注意名為 **User1** 的帳戶。 此帳戶是來自 TESTLAB AD DS 網域，且經過證明目錄同步作業可以運作。
    
13. 選取 **User1** 帳戶，然後選取 [ **授權和應用程式**]。
    
14. 在 [**產品授權**] 中，選取您的位置 (必要時) 、停用 **Office 365 E5** 授權，然後啟用 **Microsoft 365 E5** 授權。 

15. 選取頁面底部的 [ **儲存** ]，然後選取 [ **關閉**]。
    
接下來，使用 user1@testlab 測試登入訂閱的功能 **。 <*您的網功能變數名稱稱* >** 使用者名稱使用者名稱：

1. 從 APP1 登出，然後再次登入，這次指定不同的帳戶。

2. 當系統提示您輸入使用者名稱和密碼時，請指定 **user1@testlab。 <*您的功能變數名稱* >** 和 user1 密碼。 您應該可以用 User1 的身分成功登入。
 
請注意，User1 雖具有 TESTLAB AD DS 網域的網域管理員權限，但並不是全域管理員。 因此，您不會看到 [管理員] 圖示選項。 

您產生的設定如下所示：

![使用密碼雜湊同步處理測試環境的模擬企業](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

此組態包含： 
  
- 使用 DNS 網域 TESTLAB Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱。 <*您的功能變數名稱*> 已註冊。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。 Azure ad 連線會在 APP1 上執行，定期將 TESTLAB AD DS 網域同步處理至 Microsoft 365 訂閱的 Azure AD 租使用者。
- TESTLAB AD DS 網域中的 User1 帳戶已經與 Azure AD 租用戶同步處理。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)