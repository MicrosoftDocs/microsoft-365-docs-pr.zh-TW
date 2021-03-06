---
title: Azure 與 Microsoft 365 整合
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: 如果您想要使用您的內部部署環境進行密碼同步處理或單一登入，請將 Microsoft 365 與 Azure AD 整合。
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905329"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure 與 Microsoft 365 整合

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 會使用 Azure Active Directory (Azure AD) 管理幕後的使用者身分識別。 您的 Microsoft 365 訂閱包含免費的 Azure AD 訂閱，因此您可以整合內部部署 Active Directory 網域服務 (AD DS) ，以同步處理使用者帳戶和密碼或設定單一登入。 您也可以購買高級功能，以更好地管理帳戶。
  
Azure AD 也提供其他功能（如管理整合式應用程式），您可以用來擴充和自訂您的 Microsoft 365 訂閱。
  
您可以在 Microsoft 365 系統管理中心使用 Azure AD 部署顧問，以進行引導安裝和設定體驗 (您必須登入 Microsoft 365) ：

 - [Azure AD 連線顧問](https://aka.ms/aadconnectpwsync)
 - [AD FS 部署顧問](https://aka.ms/adfsguidance)
 - [Azure AD 安裝指南](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD 版本和 Microsoft 365 身分識別管理

如果您已付費訂閱 Microsoft 365，您也會有免費的 Azure AD 訂閱。 您可以使用 Azure AD 建立及管理使用者和群群組帳戶。 若要啟動此訂閱，您必須完成一次性註冊。 之後，您就可以從您的 Microsoft 365 系統管理中心存取 Azure AD。 

如需註冊免費 Azure AD 訂閱的指示，請參閱 [使用免費 AZURE ad 訂閱](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。 請勿直接移至 azure.microsoft.com 進行註冊，否則您將會使用試用版或付費訂閱 Microsoft Azure，與免費的 azure AD 訂閱搭配 Microsoft 365 不同。 
  
使用免費訂閱，您可以同步處理內部部署目錄、設定單一登入，並與許多軟體（例如 Salesforce、DropBox 及其他許多軟體）同步處理。
  
如果您想要增強的 AD DS 功能、雙向同步處理及其他管理功能，您可以將免費訂閱升級為付費的特優訂閱。 如需詳細資訊，請參閱[Azure Active Directory edition](https://azure.microsoft.com/pricing/details/active-directory/)。
  
如需 Microsoft 365 和 Azure AD 的詳細資訊，請參閱[Microsoft 365 識別模型](about-microsoft-365-identity.md)。
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>擴充 Microsoft 365 租使用者的功能

|**功能**|**描述**|
|:-----|:-----|
|整合式應用程式  <br/> |您可以將個別應用程式的存取權授與您的 Microsoft 365 資料，例如郵件、行事曆、連絡人、使用者、群組、檔案及資料夾。 您也可以在全域系統管理員層級授權這些應用程式，並在 Azure AD 中註冊應用程式，以將其提供給整個公司。 Formore 資訊，請參閱[Microsoft 365 系統管理員的整合式應用程式和 Azure AD](integrated-apps-and-azure-ads.md)。  <br/> 另請參閱 [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on)。  <br/> |
|PowerApps  <br/> | Power app 是可連接到現有資料來源（如 SharePoint 清單和其他資料應用程式）的行動裝置應用程式。 如需詳細資訊，請參閱[在 SharePoint Online 中建立清單的 PowerApp](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab)和[PowerApps 頁面](https://powerapps.microsoft.com/)。  <br/> |
   
## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)