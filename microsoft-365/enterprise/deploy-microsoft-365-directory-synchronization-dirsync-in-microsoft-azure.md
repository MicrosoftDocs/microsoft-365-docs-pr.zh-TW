---
title: 在 Microsoft Azure 中部署 Microsoft 365 目錄同步處理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: 瞭解如何在 Azure 中的虛擬機器上部署 Azure AD 連線，以同步處理內部部署目錄與 Azure AD 租使用者之間的帳戶。
ms.openlocfilehash: 52c1bb2eb53cc4e6753d528e0d82822b2a0eebc5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919083"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>在 Microsoft Azure 中部署 Microsoft 365 目錄同步處理

Azure Active Directory (Azure AD) 連線 (（以前稱為目錄同步處理工具、目錄同步處理工具或 DirSync.exe 工具) ）是您在加入網域的伺服器上安裝，以同步處理內部部署 Active Directory 網域服務 (AD DS) 使用者到 Microsoft 365 訂閱的 Azure AD 租使用者。 Microsoft 365 會使用 Azure AD 作為其目錄服務。 您的 Microsoft 365 訂閱包含 Azure AD 租使用者。 此租使用者也可以用來管理組織的身分識別與其他雲端工作負載，包括其他的 SaaS 應用程式和 Azure 中的應用程式。

您可以在內部部署伺服器上安裝Azure AD Connect，您也可以因為以下原因將其安裝在 Azure 中的虛擬機器上：
  
- 您可以更快速地佈建和設定雲端架構伺服器，以讓您的使用者可以更早使用服務。
- Azure 以更輕鬆的方式提供更佳的網站可用性。
- 您可以減少組織中的內部部署伺服器數目。

本解決方案需要內部部署網路與 Azure 虛擬網路之間的連線。如需詳細資訊，請參閱[使內部部署網路與 Microsoft Azure 虛擬網路連線](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)。 
  
> [!NOTE]
> 本文說明單一樹系中單一網域的同步處理。 Azure AD 連線會同步處理 Active Directory 樹系中的所有 AD DS 網域與 Microsoft 365。 如果您有多個 Active Directory 樹系與 Microsoft 365 同步，請參閱[多樹系目錄同步處理單一 Sign-On 案例](/azure/active-directory/hybrid/whatis-hybrid-identity)。 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>在 Azure 中部署 Microsoft 365 目錄同步處理的概述

下列圖表顯示 azure AD 連線于 azure 中的虛擬機器上執行 (會將內部部署 AD DS 樹系同步處理至 Microsoft 365 訂閱的目錄同步伺服器) 。
  
![azure 中虛擬機器上的 azure ad 連線工具會將內部部署帳戶同步處理至具有流量流量之 Microsoft 365 訂閱的 azure ad 租使用者。](../media/CP-DirSyncOverview.png)
  
在此圖表中，有兩個使用站對站 VPN 或 ExpressRoute 連線連接的網路。有一個其中存在 AD DS 網域控制器的內部部署網路，和一個 Azure 虛擬網路，其中包含目錄同步處理伺服器 (執行 [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) 的虛擬機器)。從目錄同步處理伺服器會產生二個主要流量：
  
-  Azure AD Connect 將內部部署網路上的網域控制器排入佇列，來處理帳戶和密碼的變更。
-  azure ad 連線會將帳戶和密碼的變更傳送至您 Microsoft 365 訂閱的 Azure AD 實例。 因為目錄同步處理伺服器位於內部部署網路的擴充部分，所以這些變更會透過內部部署網路的 proxy 伺服器來傳送。
    
> [!NOTE]
> 此解決方案說明單一 active Directory 網域在單一 Active Directory 樹系中的同步處理。 Azure AD 連線同步處理 Active Directory 樹系中的所有 Active Directory 網域與 Microsoft 365。 如果您有多個 Active Directory 樹系與 Microsoft 365 同步，請參閱[多樹系目錄同步處理單一 Sign-On 案例](/azure/active-directory/hybrid/whatis-hybrid-identity)。 
  
部署此解決方案有兩個主要步驟：
  
1. 建立 Azure 虛擬網路，以及建立您的內部部署網路的站對站 VPN 連線。如需詳細資訊，請參閱＜[使內部部署網路與 Microsoft Azure 虛擬網路連線](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)＞。
    
2. 在 azure 中已加入網域的虛擬機器上安裝[Azure AD 連線](https://www.microsoft.com/download/details.aspx?id=47594)，然後將內部部署 AD DS 同步處理至 Microsoft 365。 這涉及以下步驟：
    
    建立 Azure 虛擬機器以執行 Azure AD Connect。
    
    安裝及設定 [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)。
    
    若要設定 Azure AD 連線，必須 (Azure AD 系統管理員帳戶和 AD DS 企業系統管理員帳戶的使用者名稱和密碼) 的認證。 Azure AD 連線會立即執行，並將內部部署 AD DS 樹系同步處理成 Microsoft 365。
    
在生產環境中部署此方案之前，您可以使用 [模擬的企業基本](simulated-ent-base-configuration-microsoft-365-enterprise.md) 設定中的指示，將此設定設為概念證明、示範或實驗。
  
> [!IMPORTANT]
> 當 Azure AD Connect 組態完成時，它不會儲存 AD DS 企業系統管理員帳戶認證。 
  
> [!NOTE]
> 此解決方案會說明如何同步處理單一 AD DS 樹系至 Microsoft 365。 本文中所討論的拓撲只是實施此方案的一種方法。 組織的拓撲可能會因您的獨特網路需求和安全性考慮而有所不同。 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>針對 Azure 中的 Microsoft 365 主機主控目錄同步處理伺服器的計畫
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>必要條件

開始之前，請先檢閱本解決方案的下列必要條件：
  
- 檢閱＜[規劃您的 Azure 虛擬網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)＞中的相關規劃內容。
    
- 確保您符合設定 Azure 虛擬網路的所有[必要條件](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites)。
    
- 擁有包含 Active Directory 整合功能的 Microsoft 365 訂閱。 如需 Microsoft 365 訂閱的相關資訊，請前往[Microsoft 365 訂閱頁面](https://products.office.com/compare-all-microsoft-office-products?tab=2)。
    
- 布建一個執行 Azure AD 連線的 Azure 虛擬機器，以同步處理內部部署 AD DS 樹系與 Microsoft 365。
    
    您必須具有 AD DS 企業系統管理員帳戶和 Azure AD 系統管理員帳戶的認證 (名稱和密碼)。
    
### <a name="solution-architecture-design-assumptions"></a>解決方案架構設計假設

下列清單描述此解決方案所採用的設計選擇。
  
- 這個解決方案使用具備站對站 VPN 連線的單一 Azure 虛擬網路。Azure 虛擬網路會裝載單一子網路，其具有一部執行 Azure AD Connect 的目錄同步處理伺服器。 
    
- 在內部部署網路上會有網域控制站和 DNS 伺服器。
    
- Azure AD Connect 會執行密碼雜湊同步處理，而非單一登入。您不需要部署 Active Directory 同盟服務 (AD FS) 基礎結構。若要深入了解密碼雜湊同步處理與單一登入選項，請參閱＜[為您的 Azure Active Directory 混合式識別解決方案選擇正確的驗證方法](/azure/active-directory/hybrid/choose-ad-authn)＞。
    
在您的環境中部署此解決方案時，您可能會考慮的其他設計選擇。其中包含下列各項：
  
- 如果現有的 Azure 虛擬網路中有現有的 DNS 伺服器，請判斷您的目錄同步處理伺服器是否要使用它們 (而非使用內部部署網路的 DNS 伺服器) 來進行名稱解析。
    
- 如果現有的 Azure 虛擬網路中有網域控制站，請判斷設定 Active Directory 網站及服務是否是較好的選擇。目錄同步處理伺服器可以將 Azure 虛擬網路的網域控制器排入佇列，來處理帳戶和密碼的變更，而非內部部署網路上的網域控制器。
    
## <a name="deployment-roadmap"></a>部署藍圖

在 Azure 中的虛擬機器上部署 Azure AD Connect 由三個階段所組成：
  
- 階段 1：建立及設定 Azure 虛擬網路
    
- 階段 2：建立及設定 Azure 虛擬機器
    
- 階段 3：安裝及設定 Azure AD Connect
    
部署之後，您還必須在 Microsoft 365 中為新使用者帳戶指派位置和授權。


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>階段 1：建立及設定 Azure 虛擬網路

若要建立及設定 Azure 虛擬網路，請完成＜[使內部部署網路與 Microsoft Azure 虛擬網路連線](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)＞中的＜[階段 1：準備內部部署網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network)＞和＜[階段 2：在 Azure 中建立跨單位的虛擬網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure)＞。
  
這是您產生的組態。
  
![Azure 所主控 Microsoft 365 之目錄同步處理伺服器的階段1](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
本圖顯示使用站對站 VPN 或 ExpressRoute 連線方式，連線到 Azure 虛擬網路的內部部署網路。
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a>階段 2：建立及設定 Azure 虛擬機器

使用＜[在 Azure 入口網站中建立第一個 Windows 虛擬機器](https://go.microsoft.com/fwlink/p/?LinkId=393098)＞中的指示，在 Azure 中建立虛擬機器。使用下列設定：
  
- 在 [基本概念] 窗格中，選取相同的訂閱、位置及資源群組做為您的虛擬網路，並在安全位置記錄使用者名稱和密碼。您稍後連線到虛擬機器時會需要這些資訊。
    
- 在 [選擇大小] 窗格中，選擇 [A2 標準] 大小。
    
- 在 [設定] 窗格中，請在 [儲存體] 區段中，選取 [標準] 儲存體類型。在 [網路] 區段中，選取您裝載目錄同步處理伺服器 (不是閘道子網路) 的虛擬網路和子網路名稱。其他所有設定都保留預設值。
    
驗證目錄同步處理伺服器正確使用 DNS，檢查內部 DNS 以確定已使用其 IP 位址，新增虛擬機器的位址 (A) 記錄。 
  
使用[連線到虛擬機器並且登入](/azure/virtual-machines/windows/connect-logon)中的指示，使用遠端桌面連線以連線到目錄同步處理伺服器。登入之後，將虛擬機器加入到內部部署 AD DS 網域。
  
若要讓 Azure AD Connect 取得存取網際網路資源的權限，您必須設定目錄同步處理伺服器來使用內部部署網路的 Proxy 伺服器。您應該連絡您的網路系統管理員，以取得需要執行的其他設定步驟。
  
這是您產生的組態。
  
![Azure 所主控 Microsoft 365 之目錄同步處理伺服器的階段2](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
本圖顯示在跨部署 Azure 虛擬網路中的目錄同步處理伺服器虛擬機器。
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>階段 3：安裝及設定 Azure AD Connect

完成下列程序：
  
1. 透過具有本機系統管理員權限的 AD DS 網域帳戶使用遠端桌面連線，連線到目錄同步處理伺服器。請參閱[連線到虛擬機器並且登入](/azure/virtual-machines/windows/connect-logon)。
    
2. 在目錄同步處理伺服器中，開啟[為 Microsoft 365 文章設定目錄同步](set-up-directory-synchronization.md)處理，並遵循密碼雜湊同步處理的目錄同步處理指示。
    
> [!CAUTION]
> 安裝程式會在本機使用者組織單位 (OU) 中建立 **AAD_xxxxxxxxxxxx** 帳戶。請勿移動或移除此帳戶，否則同步處理將會失敗。
  
這是您產生的組態。
  
![Azure 所主控 Microsoft 365 之目錄同步處理伺服器的階段3](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
本圖顯示在跨部署 Azure 虛擬網路中的 Azure AD Connect 目錄同步處理伺服器。
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>將位置和授權指派給 Microsoft 365 中的使用者

Azure AD 連線會從內部部署 AD DS 將帳戶新增至您的 Microsoft 365 訂閱，但是為了讓使用者能夠登入 Microsoft 365 和使用其服務，必須使用位置和授權來設定帳戶。 使用下列步驟為適當的使用者帳戶新增位置和啟用授權：
  
1. 登入 Microsoft 365 系統 [管理中心](https://admin.microsoft.com)，然後按一下 [**管理**]。
    
2. 在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]。
    
3. 在使用者帳戶清單中，選取您要啟動使用者旁的核取方塊。
    
4. 在使用者的頁面上，按一下 [產品授權] 的 [編輯]。
    
5. 在 [產品授權] 頁面上，為 **位置** 的使用者選取一個位置，然後為使用者啟用適當授權。
    
6. 完成時，按一下 [儲存]，然後按兩下 [關閉]。
    
7. 針對其他使用者回到步驟 3。
    
## <a name="see-also"></a>另請參閱

[Microsoft 365 解決方案與架構中心](../solutions/index.yml)
  
[使內部部署網路與 Microsoft Azure 虛擬網路連線](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[下載 Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)
  
[設定 Microsoft 365 的目錄同步處理](set-up-directory-synchronization.md)
