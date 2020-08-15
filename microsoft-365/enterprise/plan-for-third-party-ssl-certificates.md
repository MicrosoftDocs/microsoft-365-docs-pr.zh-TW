---
title: 規劃 Microsoft 365 的第三方 SSL 憑證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 摘要：說明 Exchange 內部部署和混合式 SSO （使用 AD FS、Exchange Online 服務和 Exchange Web 服務）所需的 SSL 憑證。
ms.openlocfilehash: 1738e4c316772d928138adc654372bd0b9efae65
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688504"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>規劃 Microsoft 365 的第三方 SSL 憑證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

若要加密用戶端與 Microsoft 365 環境之間的通訊，協力廠商安全通訊端層 (SSL) 憑證必須安裝在基礎結構伺服器上。

本文是 [Microsoft 365 的網路規劃和效能調整](https://aka.ms/tune)的一部分。
   
下列 Microsoft 365 元件需要憑證：
  
- Exchange 內部部署
    
- 適用于 Active Directory Federation Services (AD FS) 同盟伺服器和 AD FS 同盟伺服器 proxy 的單一登入 (SSO)  () 
    
- Exchange Online 服務，例如自動探索、Outlook 無所不在和 Exchange Web 服務
    
- Exchange 混合式伺服器
    
## <a name="certificates-for-exchange-on-premises"></a>Exchange On-Premises 的憑證

若要瞭解如何使用數位憑證來進行內部部署 Exchange 組織與 Exchange Online 之間的通訊，請參閱 TechNet 文章 [瞭解憑證需求](https://go.microsoft.com/fwlink/p/?LinkID=243657)。
  
## <a name="certificates-for-single-sign-on"></a>單一 Sign-On 的憑證

若要為您的使用者提供增強的安全性的簡化單一登入體驗，同盟伺服器或同盟伺服器 proxy 上必須要有下表所示的憑證。 下表著重于 Active Directory Federation Services (AD FS) 上，我們也提供 [使用協力廠商身分識別提供者](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)的詳細資訊。
  
| 憑證類型 | 描述 | 部署之前所需注意的事項 |
|:-----|:-----|:-----|
|**SSL 憑證 (也稱為伺服器驗證憑證) ** <br/> |這是一個標準 SSL 憑證，用來保護同盟伺服器、用戶端與同盟伺服器 proxy 電腦之間的通訊安全。  <br/> |AD FS 需要 SSL 憑證。 根據預設，AD FS 使用網際網路資訊服務 (IIS) 中設定之預設網站的 SSL 憑證。  <br/> 此 SSL 憑證的主體名稱是用來判斷您部署之每個 AD FS 實例的同盟服務 (FS) 名稱。 請考慮為任何新的憑證授權單位單位的主體名稱選擇 (CA) 頒發的憑證，該憑證最能代表您公司或組織的 Microsoft 365 的名稱。 此名稱必須是透過網際網路路由傳送。  <br/>**警告：** AD FS 要求此 SSL 憑證沒有無點 (短名稱) 主體名稱。          <br/> **建議：** 由於此憑證必須由 AD FS 的用戶端信任，因此建議您使用公用 (協力廠商) CA 所發出的 SSL 憑證，或是從屬於公開根信任的 CA，使用此憑證;例如，VeriSign 或 Thawte。  <br/> |
|**權杖簽署憑證** <br/> |這是標準的 x.509 憑證，用來安全簽署同盟伺服器所發行的所有權杖，以及 Microsoft 365 接受和驗證的所有權杖。  <br/> |權杖簽章憑證必須包含一個私密金鑰，該私密金鑰會連結至 FS 中的信任的根。 AD FS 預設會建立自我簽署憑證。 不過，您可以根據組織的需求，使用 [AD FS 管理] 嵌入式管理單元，將此憑證變更為 CA 發佈的憑證。  <br/>**警告：** 權杖簽署憑證對 FS 穩定性很重要。 如果變更了憑證，則必須通知 Microsoft 365。 若未提供通知，使用者就無法登入其 Microsoft 365 服務產品。<br/>**建議：** 建議您使用 AD FS 所產生的自我簽署權杖簽署憑證。 這樣一來，它預設會為您管理此憑證。 例如，當此憑證即將到期時，AD FS 將會產生新的自我簽署憑證。  <br/> |
   
同盟伺服器 proxy 需要下表所述的憑證。
  
| 憑證類型 | 描述 | 部署之前所需注意的事項 |
|:-----|:-----|:-----|
|SSL 憑證  <br/> |這是一個標準 SSL 憑證，用來保護同盟伺服器、同盟伺服器 proxy 和網際網路用戶端電腦之間的通訊安全。  <br/> |您必須先將此 SSL 憑證系結至 IIS 中的預設網站，才能成功執行 AD FS 同盟伺服器 Proxy 設定向導。  <br/> 此憑證必須具有與公司網路中同盟伺服器上設定之 SSL 憑證相同的主體名稱。  <br/> **建議：** 建議您使用此同盟伺服器 proxy 所連接的同盟伺服器上設定的相同伺服器驗證憑證。  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>自動探索、Outlook Anywhere 和 Active Directory 同步處理的憑證

您的對外 Exchange 2013、Exchange 2010、Exchange 2007 和 Exchange 2003 Client Access server (CASs) 需要協力廠商 SSL 憑證，以進行自動探索、Outlook 無所不在和 Active Directory 同步處理服務的安全連線。 您可能已在內部部署環境中安裝此憑證。
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Exchange 混合式伺服器的憑證

您的外部 Exchange 混合伺服器或伺服器需要協力廠商 SSL 憑證，以與 Exchange Online 服務進行安全連線。 您必須從協力廠商 SSL 提供者取得此憑證。
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 憑證鏈

本文說明您在基礎結構上安裝時可能需要的憑證。 如需 Microsoft 365 伺服器上安裝之憑證的詳細資訊，請參閱 [microsoft 365 憑證鏈](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)。
  
## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)
