---
title: 管理 Microsoft 365 使用者帳戶的工具
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 瞭解使用哪些工具，以及如何管理 Microsoft 365 帳戶。
ms.openlocfilehash: 205c61c0cff896f93069d225c84dc3086ca30eb5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688747"
---
# <a name="tools-to-manage-microsoft-365-user-accounts"></a>管理 Microsoft 365 使用者帳戶的工具

您可以根據您的設定，以數種不同的方式管理 Microsoft 365 使用者。 您可以在 [Microsoft 365 系統管理中心](https://admin.microsoft.com)、Windows PowerShell、Active Directory 網域服務 (AD DS) 或 Azure Active Directory (azure AD) 管理入口網站中管理使用者。 

一旦您購買 Microsoft 365，系統管理中心和 Windows PowerShell 便可用於管理帳戶。 在管理雲端身分識別時，組織中的每個人都有個別的使用者識別碼和密碼，適用于 Microsoft 365。 如果您想要與您的內部部署基礎結構整合，並讓使用者帳戶與 Microsoft 365 同步，您可以使用 Azure AD Connect，針對單一登入功能，提供身分識別和密碼的同步處理。
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>規劃管理使用者帳戶的位置和方式

您可以管理使用者帳戶的位置和方式，取決於您要用於 Microsoft 365 的身分識別模型。 這兩個整體模型為雲端驗證及同盟驗證。
  
### <a name="cloud-authentication"></a>雲端驗證

- 雲端驗證-建立及管理 Microsoft 365 系統管理中心中的使用者。 您也可以使用 Windows PowerShell 或 Azure AD。 
    
- 密碼雜湊同步處理 (PHS) 具有無縫單一登入-在 Azure AD 中啟用 AD DS 物件的驗證的最簡單方式。 透過 PHS，您可以將 AD DS 使用者帳戶物件與 Microsoft 365 同步處理，並管理您的使用者內部部署。 
    
- 透過無縫單一登入的傳遞驗證 (PTA) 使用一或多個內部部署伺服器上執行的軟體代理程式，為 Azure AD 驗證服務提供簡單的密碼驗證，以直接在您的 AD DS 驗證使用者。 
    
### <a name="federated-authentication"></a>同盟驗證

- 同盟驗證選項-主要針對具有更複雜驗證需求的大型企業組織，AD DS 物件會與 Microsoft 365 同步處理，而且使用者帳戶是在內部部署管理。 
    
- [協力廠商驗證和身分識別提供者](about-microsoft-365-identity.md) -AD DS 物件可同步處理至 Microsoft 365，而雲端資源存取主要是由協力廠商身分識別提供者 (IDP) 所管理。 
    
## <a name="managing-accounts"></a>管理帳戶

決定組織建立及管理帳戶的方式時，請考慮下列需求：
  
- 在內部部署環境中的伺服器上，必須安裝目錄同步作業軟體，以連接 Microsoft 365 和您的 AD DS 之間的身分識別。
    
- 任何目錄同步處理選項（包括 SSO 選項）都需要您的 AD DS 屬性符合標準。 您的目錄中所使用之屬性的詳細資訊，以及 (如果需要的任何) ，將在 [準備透過目錄同步作業將使用者布建至 Microsoft 365](prepare-for-directory-synchronization.md)時所述的清除作業。 
    
- 規劃如何建立 Microsoft 365 帳戶。
    
    下表列出不同的帳戶管理工具。
    
|**選項**|**附註**|
|:-----|:-----|
|系統管理中心  <br/> |[個別或大量新增使用者](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  提供簡單的 web 介面來新增及變更使用者帳戶。  <br/>  如果啟用目錄同步處理，則無法用來變更使用者 (位置和授權指派可以設定) 。  <br/>  無法與 SSO 選項搭配使用。  <br/> |
|Windows PowerShell  <br/> |[使用 Windows PowerShell 管理 Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  可讓您使用 Windows PowerShell 腳本，在大量使用者中新增使用者。  <br/>  可用於將位置和授權指派給帳戶，不論帳戶是如何建立的。  <br/> |
|大量匯入  <br/> |[同時新增多個使用者](add-several-users-at-the-same-time.md) <br/>  可讓您匯入 CSV 檔案，將使用者群組新增至 Microsoft 365。  <br/>  無法與 SSO 選項搭配使用。  <br/> |
|Azure AD  <br/> |您可以使用 Microsoft 365 訂閱取得免費的 Azure AD 版本。 您可以執行雲端使用者自助密碼重設的功能，以及使用免費版本自訂登入和存取面板頁面。 若要取得增強的功能，您可以升級至 basic edition、Azure AD Premium P1 或 Azure AD Premium P2。 如需支援的功能清單，請參閱 [AZURE AD edition](https://go.microsoft.com/fwlink/p/?LinkId=698465) 。  <br/> |
|目錄同步處理  <br/> |[整合您的內部部署身分識別與 Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  若要使用或不使用密碼同步處理的目錄同步處理，請使用 [AZURE AD Connect with express 設定](https://go.microsoft.com/fwlink/p/?LinkID=698537)。  <br/>  若為多個樹系和 SSO 選項，請使用 [自訂的 AZURE AD Connect 安裝](https://go.microsoft.com/fwlink/p/?LinkId=698430)。  <br/>  提供啟用 SSO 所需的基礎結構。  <br/>  許多混合式案例的必要專案：  <br/>  分段移轉  <br/>  混合式 Exchange  <br/>  從 AD DS 同步處理安全性和擁有郵件功能的群組。  <br/> |
   
- 不論您要如何將使用者帳戶新增至 Microsoft 365，您需要管理多個帳戶功能，例如指派授權、指定位置等等。 您可以從系統管理中心管理這些功能，也可以 [使用 PowerShell 建立使用者帳戶](https://go.microsoft.com/fwlink/p/?LinkId=717083)。
    
    如果您選擇透過系統管理中心新增及管理所有使用者，您會指定位置並指派授權，建立 Microsoft 365 帳戶時。 因此，不需要進行許多規劃。
    
    > [!IMPORTANT]
    > 在 Microsoft 365 中建立帳戶，但未指派授權 (給 SharePoint 線上，) 表示帳戶擁有者可以查看 Microsoft 365 center，但無法存取公司訂閱內的任何服務。 在您指派位置和授權後，系統會將帳戶複製到您指派的服務或服務。 使用者可以登入其帳戶，並使用您指派給他們的服務。 
  
## <a name="next-steps"></a>後續步驟

[Microsoft 365 與內部部署環境的整合](microsoft-365-integration.md)
  
## <a name="see-also"></a>另請參閱

[管理 Microsoft 365 中的使用者和群組](https://docs.microsoft.com/microsoft-365/admin/add-users)
  
