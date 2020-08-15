---
title: >
  Microsoft 雲端供應項目的訂用帳戶、授權、帳戶及租用戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/25/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: 了解所有 Microsoft 雲端產品上的組織、訂閱、授權、使用者帳戶、租用戶之間的關係。
ms.openlocfilehash: 7b19c2d6a870f53642d37ee98276f7b6a9e1febf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688373"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a>Microsoft 雲端供應項目的訂用帳戶、授權、帳戶及租用戶


Microsoft 提供組織、訂閱、授權、使用者帳戶的階層，讓所有雲端產品都能使用一致的身分識別和計費方式：
  
- Microsoft 365 和 Microsoft Office 365
- Microsoft Azure
- Microsoft Dynamics 365

## <a name="elements-of-the-hierarchy"></a>階層的元素

以下是階層的元素：
  
### <a name="organization"></a>組織

組織代表正在使用 Microsoft 雲端供應項目的商業實體，通常是用一個或多個公用網域名稱 (DNS)，例如 contoso.com 加以識別。組織是訂用帳戶的容器。
  
### <a name="subscriptions"></a>訂閱

訂閱是與 Microsoft 簽訂使用一或多個 Microsoft 雲端平台或服務的合約，其費用會根據每位使用者的授權費用或雲端資源使用量而產生。 

- Microsoft 的軟體即服務 (SaaS) 型雲端產品 (Microsoft 365 和 Dynamics 365) 是按照每個使用者授權來收費。 
- Microsoft 的平台即服務 (PaaS) 和基礎結構即服務 (IaaS) 雲端供應項目 (Azure) 是根據雲端資源的使用量來收費。
 
您也可以使用試用版的訂用帳戶，但在使用特定一段時間或耗用量之後，訂用帳戶便到期。您可以將試用版訂用帳戶轉換為付費訂用帳戶。
  
組織可有多個訂用帳戶，用於 Microsoft 的多個雲端供應項目。 圖 1 顯示單一組織擁有多個 Microsoft 365 訂閱、一個 Dynamics 365 訂閱和多個 Azure 訂閱。

**圖 1：組織的多個訂用帳戶範例**

![具有多個 Microsoft 雲端供應項目訂用帳戶的組織範例。](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a>授權

針對 Microsoft SaaS 雲端供應項目，授權可讓特定使用者帳戶使用雲端供應項目服務。 會向您收取每月固定的訂閱費用。 系統管理員會將授權指派給訂閱中的個別使用者帳戶。 如圖 2 所示範例，Contoso Corporation 擁有包含 100 個授權的 Microsoft 365 E5 訂閱，可讓最多 100 個個別使用者帳戶使用 Microsoft 365 E5 功能與服務。
  
**圖 2：SaaS 型訂用帳戶中的組織授權**

![Microsoft SaaS 型雲端供應項目訂用帳戶中多個授權的範例。](../media/Subscriptions/Subscriptions-Fig2.png)
  
使用 Azure PaaS 型雲端服務時，服務費用已包含軟體授權。
  
使用 Azure IaaS  型虛擬機器時，可能會需要額外的授權來使用安裝在虛擬機器映像上的軟體或應用程式。部分虛擬機器映像已安裝軟體的授權版本，費用是由伺服器的每一分鐘費率涵蓋。例如 SQL Server 2014 和 SQL Server 2016 的虛擬機器映像。 
  
部分虛擬機器映像已安裝試用版應用程式，在試用期間過後需要額外的軟體應用程式授權。例如，SharePoint Server 2016 試用版的虛擬機器映像包含預先安裝的 SharePoint Server 2016 試用版。若要在試用到期日之後繼續使用 SharePoint Server 2016，您必須向 Microsoft 購買 SharePoint Server 2016 授權和用戶端授權。這些費用和 Azure 訂用帳戶是分開的，且仍需支付執行虛擬機器的每一分鐘費率。
  
### <a name="user-accounts"></a>使用者帳戶

所有 Microsoft 雲端供應項目的使用者帳戶都儲存在 Azure Active Directory (Azure AD) 租用戶中，其中包含使用者帳戶和群組。 Azure AD 租用戶可以使用 Azure AD Connect 這個 Windows 伺服器型服務，與您現有的 Active Directory 網域服務 (AD DS) 帳戶進行同步。 這稱為目錄同步處理。
  
圖 3 顯示組織的多個訂用帳戶使用同一個 Azure AD 租用戶，租用戶包含組織的帳戶。
  
**圖 3：組織的多個訂用帳戶使用相同 Azure AD 租用戶的範例。**

![多個訂用帳戶皆使用相同 Azure AD 租用戶的組織範例。](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a>租用戶

針對 SaaS 雲端產品，租用戶是指存放提供雲端服務之伺服器的區域位置。 例如，Contoso Corporation 選擇歐洲區域來裝載它的 Microsoft 365、EMS 和 Dynamics 365 租用戶，供巴黎總公司的 15,000 名員工使用。
  
Azure PaaS 服務和虛擬機器的工作負載裝載於 Azure IaaS 中，可以將租用戶放在世界各地的 Azure 資料中心內。當您建立 Azure PaaS 應用程式或服務或 IaaS 工作負載的元素時，由您指定 Azure 資料中心 (稱為「位置」)。
  
Azure AD 租用戶是包含帳戶和群組之 Azure AD 的特定執行個體。 Microsoft 365 或 Dynamics 365 的付費或試用訂閱包括免費的 Azure AD 租用戶。 這個 Azure AD 租用戶不包括其他 Azure 服務，和 Azure 試用或付費訂閱不同。
  
### <a name="summary-of-the-hierarchy"></a>階層摘要

以下是重點複習：
  
- 組織可以有多個訂用帳戶。
    
  - 訂用帳戶可以有多個授權。
    
  - 授權可以指派給個別使用者帳戶。
    
  - 使用者帳戶儲存在 Azure AD 租用戶。
    
以下是組織、訂用帳戶、授權、使用者帳戶的關係範例：
  
- 組織由其公用網域名稱加以識別。

    
  - Microsoft 365 E3 訂閱包含使用者授權。
    
    Microsoft 365 E5 訂閱包含使用者授權。
    
    Dynamics 365 訂用帳戶包含使用者授權。
    
    多個 Azure 訂用帳戶。

    
  - 組織的使用者帳戶在同一 Azure AD 租用戶中。
    
多個 Microsoft 雲端供應項目訂用帳戶可以使用作為共同身分識別提供者的相同 Azure AD 租用戶。 內含內部部署 AD DS 的同步處理帳戶的中央 Azure AD 租用戶，可為組織提供雲端型的身分識別即服務 (IDaaS)。 
  
**圖 4： 組織同步處理的內部部署帳戶和 IDaaS**

![組織的身分識別即服務 (IaaS) IDaaS。](../media/Subscriptions/Subscriptions-Fig4.png)
  
在圖 4 中，Microsoft 的 SaaS 雲端供應項目、Azure PaaS 應用程式、使用 Azure AD 網域服務的 Azure IaaS 中的虛擬機器，三者使用同一個 Azure AD 租用戶。Azure AD Connect 將內部部署的 AD DS 樹系和 Azure AD 租用戶同步。
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a>合併多個 Microsoft 雲端供應項目的訂用帳戶

下表說明如何以已有的一種雲端供應項目的一個訂用帳戶為本，合併多個 Microsoft 雲端供應項目 (表中的第一個直列)，以及如何為不同的雲端供應項目新增訂用帳戶 (表中的橫行)。
  
||**Microsoft 365**|**Azure**|**Dynamics 365**|
|:-----|:-----|:-----|:-----|:-----|
|**Microsoft 365** <br/> |NA  <br/> |您在 Azure 入口網站中為組織新增 Azure 訂用帳戶。  <br/> |您可以透過 Microsoft 365 系統管理中心為組織新增 Dynamics 365 訂閱。  <br/> |
|**Azure** <br/> |您為貴組織新增 Microsoft 365 訂閱。  <br/> |NA  <br/> |您為組織新增 Dynamics 365 訂用帳戶。  <br/> |
|**Dynamics 365** <br/> |您為貴組織新增 Microsoft 365 訂閱。  <br/> |您在 Azure 入口網站中為組織新增 Azure 訂用帳戶。  <br/> |NA  <br/> |
   
要將 Microsoft SaaS 服務的訂用帳戶新增到組織，簡單的做法是透過系統管理中心：
  
1. 使用您的全域系統管理員帳戶登入 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))。
    
2. 在 **[管理中心]** 首頁的導覽窗格中，按一下 **[計費]**，然後按一下 **[購買服務]**。
    
3. 在 **[購買服務]** 頁面上，購買新的訂用帳戶。
    
系統管理中心會將組織和 Microsoft 365 訂閱的 Azure AD 租用戶，指派給 SaaS 型雲端產品的新訂閱。
  
使用與 Microsoft 365 訂閱相同的組織和 Azure AD 租用戶來新增 Azure 訂閱：
  
1. 使用 Microsoft 365 全域系統管理員帳戶登入 Azure 入口網站 ([https://portal.azure.com](https://portal.azure.com))。
    
2. 在左側導覽窗格中，按一下 **[訂用帳戶]**，然後按一下 **[新增]**。
    
3. 在 **[新增訂用帳戶]** 頁面上，選取供應項目，並填寫付款資訊和合約。
    
如果您已另外購買 Azure 與 Microsoft 365 訂閱，並想要從您的 Azure 訂閱存取 Microsoft 365 Azure AD 租用戶，請參閱[將現有的 Azure 訂閱新增至您的 Azure Active Directory 租用戶](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory)中的指示。
 
## <a name="see-also"></a>另請參閱

[Microsoft Cloud for Enterprise Architects 圖例](../solutions/cloud-architecture-models.md)
  
[適用於 SharePoint、Exchange、商務用 Skype 和 Lync 的架構模型](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[混合式解決方案](hybrid-solutions.md)

## <a name="next-step"></a>下一步

[評定 Microsoft 365 網路連線](assessing-network-connectivity.md)
  
