---
title: Microsoft 365 與內部部署環境的整合
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: 在本文中，您將瞭解如何將 Microsoft 365 與您現有的目錄服務和內部部署環境整合。
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688818"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 與內部部署環境的整合

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以將 Microsoft 365 與現有的目錄服務整合，並使用 Exchange Server、商務用 Skype Server 2015 或 SharePoint 伺服器的內部部署安裝。
  
 - 當您與目錄服務整合時，您可以同步處理及管理這兩種環境的使用者帳戶。 您也可以在 SSO) 上新增密碼雜湊同步處理或單一登入 (，讓使用者可以使用內部部署認證登入這兩種環境。
 - 當您整合內部部署伺服器產品時，您會建立混合式環境。 當您將使用者或資訊遷移至 Microsoft 365 時，混合式環境可以協助您，也可以繼續在內部部署中和某些使用者或部分資訊，在雲端中。 如需混合式環境的詳細資訊，請參閱 [混合式 cloud 一覽](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview)。

您也可以使用 Azure Active Directory (Azure AD) 顧問以取得自訂安裝指導， (您必須登入 Microsoft 365) ：

- [從您的組織目錄同步處理使用者](https://aka.ms/aadconnectpwsync)
- [AD FS 部署顧問](https://aka.ms/adfsguidance)
- [Azure AD 安裝指南](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a>在您開始之前

整合 Microsoft 365 和內部部署環境之前，您也需要參加 [網路規劃和效能調整](network-planning-and-performance.md)。 您也會想要瞭解可用的身分 [識別模型](about-microsoft-365-identity.md)。 

如需管理 microsoft 365 使用者和帳戶的可用工具清單，請參閱 [管理 microsoft 365 帳戶的位置](manage-microsoft-365-accounts.md) 。 
  
## <a name="integrate-microsoft-365-with-directory-services"></a>整合 Microsoft 365 與目錄服務
如果您在內部部署目錄中有現有的使用者帳戶，您不想要在 Microsoft 365 中重新建立所有這些帳戶，以及在環境間引入差異或錯誤的風險。 目錄同步處理可協助您在您的線上和內部部署環境間鏡像這些帳戶。 透過目錄同步作業，您的使用者不需要記住每個環境的新資訊，而且您不需要建立或更新帳戶兩次。 您將需要 [準備內部部署目錄](prepare-for-directory-synchronization.md) ，以進行目錄同步處理。
  
![使用目錄同步處理將內部部署和線上使用者帳戶資訊同步處理](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
如果您想要讓使用者能夠使用內部部署認證登入 Microsoft 365，您也可以設定 SSO。 透過 SSO，Microsoft 365 會設定為信任內部部署環境以進行使用者驗證。
  
![使用單一登入時，在內部部署環境和線上環境中皆可使用相同的帳戶。](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
不同的使用者帳戶管理技術為您的使用者提供不同的體驗，如下表所示。
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a>使用或不使用密碼雜湊同步處理或未經過驗證的目錄同步處理

使用者使用使用者帳戶登入其內部部署環境 (網域 \ 使用者名稱) 。 當他們移至 Microsoft 365 時，他們必須使用其工作或學校帳戶 (user@domain.com) 登入。 這兩個環境中的使用者名稱相同。 當您新增密碼雜湊同步處理或通過驗證時，使用者會在兩個環境上都有相同的密碼，但在登入 Microsoft 365 時，必須提供這些認證。 與密碼雜湊同步處理的目錄同步處理是最常使用的目錄同步案例。

若要設定目錄同步處理，請使用 Azure Active Directory Connect。 如需相關指示，請參閱[設定 Microsoft 365 的目錄同步](set-up-directory-synchronization.md)[處理和 Azure AD Connect with express 設定](https://go.microsoft.com/fwlink/p/?LinkId=698537)。

深入瞭解 [準備目錄同步處理至 Microsoft 365](prepare-for-directory-synchronization.md) ，並 [整合您的內部部署識別與 Azure Active directory](https://go.microsoft.com/fwlink/?LinkId=518101)。

### <a name="directory-synchronization-with-sso"></a>與 SSO 同步處理的目錄

使用者可以使用其使用者帳戶登入其內部部署環境。 當他們移至 Microsoft 365 時，他們要麼是自動登入，要麼是使用其內部部署環境所用的相同認證（ (網域 \ 使用者名稱」) ）登入。

若要設定 SSO，您也可以使用 Azure AD Connect。 如需相關指示，請參閱 [AZURE AD Connect 的自訂安裝](https://go.microsoft.com/fwlink/p/?LinkID=698430)。

深入瞭解 [Azure Active Directory 中的單一登入應用程式](https://go.microsoft.com/fwlink/p/?LinkId=698604)。

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect 取代舊版本的身分識別整合工具，例如 DirSync 和 Azure AD Sync。如需詳細資訊，請參閱 [什麼是使用 Azure Active Directory 的混合式身分識別？](https://go.microsoft.com/fwlink/p/?LinkId=527969)。 如果您想要從 Azure Active Directory 同步更新至 Azure AD Connect，請參閱 [升級指示](https://go.microsoft.com/fwlink/p/?LinkId=733240)。 

另請參閱 [在 Microsoft Azure 中部署 Microsoft 365 目錄同步](https://go.microsoft.com/fwlink/?LinkId=517887)處理。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)
