---
title: Azure 中的 Microsoft 365 高可用性同盟驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: 摘要：在 Microsoft Azure 中為您的 Microsoft 365 訂閱設定高可用性同盟驗證。
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919149"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a>Azure 中的 Microsoft 365 高可用性同盟驗證

本文提供使用下列虛擬機器在 Azure 基礎結構服務中部署 Microsoft Microsoft 365 高可用性同盟驗證的逐步指示連結：
  
- 兩個 Web 應用程式 Proxy 伺服器
    
- 兩個 Active Directory Federation Services (AD FS) 伺服器
    
- 兩個複本網域控制站
    
- 一個執行 Azure AD Connect 的目錄同步處理伺服器
    
組態如下，包含每部伺服器的預留位置名稱。
  
**Azure 中 Microsoft 365 基礎結構的高可用性同盟驗證**

![Azure 中高可用性 Microsoft 365 同盟驗證基礎結構的最終設定](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
所有虛擬機器位於單一跨單位 Azure 虛擬網路中 (VNet)。 
  
> [!NOTE]
> 個別使用者的聯盟驗證不會仰賴任何內部部署資源。不過，如果跨單位連線無法使用，VNet 中的網域控制站就不會收到使用者帳戶和群組在內部部署 Active Directory Domain Services (AD DS) 中的更新。若要確保不會發生這個情況，您可以設定跨場所連線的高可用性。如需詳細資訊，請參閱[高度可用的跨單位和 VNet-VNet 連線](/azure/vpn-gateway/vpn-gateway-highlyavailable)。
  
特定角色的每個虛擬機器配對都是位於它自己的子網路和可用性設定組中。
  
> [!NOTE]
> 因為此 VNet 會連線到內部部署網路，所以此組態不包含管理子網路上的 Jumpbox 或監視虛擬機器。如需詳細資訊，請參閱＜[執行 N 層架構的 Windows VM](/azure/guidance/guidance-compute-n-tier-vm)＞。 
  
這項設定的結果是您將具備所有 Microsoft 365 使用者的同盟驗證，讓他們可以使用其 AD DS 認證來登入，而不是其 Microsoft 365 帳戶。 聯盟驗證基礎結構會使用一組多餘的伺服器，能更輕鬆部署在 Azure 基礎結構服務而不是內部部署邊緣網路中。
  
## <a name="bill-of-materials"></a>物料單

此基準組態需要下列 Azure 服務和元件集合：
  
- 九部虛擬機器
    
- 具有四個子網路的一個跨單位虛擬網路
    
- 四個資源群組
    
- 三個可用性設定組
    
- 一個 Azure 訂用帳戶
    
以下是此組態的虛擬機器與其預設大小。
  
|**項目**|**虛擬機器描述**|**Azure 圖庫影像**|**預設大小**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |第一個網域控制站  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|2.  <br/> |第二個網域控制站  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|3.  <br/> |Azure AD Connect 伺服器  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|4.  <br/> |第一個 AD FS 伺服器  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|5.  <br/> |第二個 AD FS 伺服器  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|6.  <br/> |第一個 Web 應用程式 Proxy 伺服器  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|7.  <br/> |第二個 Web 應用程式 Proxy 伺服器  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
   
若要計算此組態的估計成本，請參閱 [Azure 價格計算機](https://azure.microsoft.com/pricing/calculator/)
  
## <a name="phases-of-deployment"></a>部署階段

您可以在下列階段部署此工作負載：
  
- [階段 1：設定 Azure](high-availability-federated-authentication-phase-1-configure-azure.md)。建立資源群組、儲存體帳戶、可用性設定組和跨單位虛擬網路。
    
- [階段 2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)。 建立並設定複本 AD DS 網域控制站和目錄同步處理伺服器。
    
- [階段 3：設定 AD FS 伺服器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)。建立並設定兩個 AD FS 伺服器。
    
- [階段 4：設定 Web 應用程式 Proxy](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)。建立並設定兩個 Web 應用程式 Proxy 伺服器。
    
- [階段5：設定 Microsoft 365 的同盟驗證](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)。 為您的 Microsoft 365 訂閱設定同盟驗證。
    
這兩篇文章針對 Azure 基礎結構服務中的 Microsoft 365，提供預先定義之架構的分階段指南，以建立功能、高可用性同盟驗證。 請記住下列事項：
  
- 如果您是有經驗的 AD FS 實作者，請自行適應階段 3 至 4 中的指示，並建置最符合您需求的伺服器組。
    
- 如果您已擁有的現有 Azure 混合式雲端部署具有現有跨單位虛擬網路，請依需要調整或略過階段 1 和 2 中的指示，並將 AD FS 和 Web 應用程式 Proxy 伺服器置於適當的子網路中。
    
若要建立開發/測試環境或此設定的概念證明，請參閱[Microsoft 365 開發/測試環境](federated-identity-for-your-microsoft-365-dev-test-environment.md)的同盟身分識別。
  
## <a name="next-step"></a>下一步

使用[階段 1：設定 Azure](high-availability-federated-authentication-phase-1-configure-azure.md) 開始設定此工作負載。 
