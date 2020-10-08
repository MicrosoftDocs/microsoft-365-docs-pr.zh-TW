---
title: Microsoft 365 系統管理員的整合式應用程式和 Azure AD
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: 瞭解如何在 Azure AD 中登錄和管理 Office 365 整合型應用程式，允許全域系統管理員層級的應用程式授權。
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384900"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Microsoft 365 系統管理員的整合式應用程式和 Azure AD

若要管理的整合式應用程式比 [管理使用者對應用程式的同意](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)更多。 隨著 Microsoft 365 REST APIs 的出現，使用者可以將應用程式的存取權授與他們的 Microsoft 365 資料，例如郵件、行事曆、連絡人、使用者、群組、檔案及資料夾。 根據預設，使用者必須個別授與每個應用程式的許可權。 

不過，如果您想要在全域系統管理員層級授權應用程式一次，並透過應用程式啟動器將其推廣至整個組織，這種方式不會很好地擴充。 若要這麼做，您必須在 Azure Active Directory (Azure AD) 中註冊應用程式。 在註冊 Azure AD 中的應用程式之前，必須先執行一些步驟，以及您應該知道的一些背景資訊，才能協助您管理 Microsoft 365 組織中的應用程式。
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Microsoft 365 系統管理員的 Azure AD 資源

您必須先執行這兩項工作，才能管理 Azure AD 中的 Microsoft 365 應用程式。
  
|必要條件|註解|
|:-----|:-----|
|[使用免費 Azure AD 訂閱](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Microsoft 365 的每一次付費訂閱隨附 Azure AD 的免費訂閱。 您可以使用 Azure AD 來管理您的應用程式，以及建立及管理使用者和群組帳戶。 若要使用 Azure AD，請移至 Azure 入口網站， [https://portal.azure.com](https://portal.azure.com) 並使用您的 Microsoft 365 帳戶登入。  <br/> |
|[管理使用者同意的應用程式](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |您必須將使用者同意的應用程式管理，以允許協力廠商應用程式存取使用者 Microsoft 365 資訊，並讓您在 Azure AD 中註冊應用程式。 例如，當有人使用協力廠商應用程式時，該應用程式可能會要求行事曆的存取權限，以編輯 OneDrive 資料夾中的檔案。  <br/> |
   
管理 Microsoft 365 應用程式需要您知道 Azure AD 中的應用程式。 使用這些文章可提供您所需的背景。
  
|文章|註解|
|:-----|:-----|
|[符合 Microsoft 365 應用程式啟動器](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |如果您是新的應用程式啟動器，您可能會想知道它是什麼，以及如何使用它。 App 啟動器的設計目的是協助您從 Microsoft 365 的任何地方取得您的應用程式。  <br/> |
|[Office 365 管理 APIs 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365 管理 APIs 可讓您提供對您的 Microsoft 365 資料的存取，包括他們最關心的郵件、行事曆、連絡人、使用者和群組、檔案及資料夾。 <br/> |
|[整合 Azure AD 中的應用程式](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | 深入瞭解與 Azure AD 整合的應用程式，以及如何註冊您的應用程式、瞭解已註冊應用程式背後的概念，以及瞭解多承租人應用程式的品牌指導方針。  <br/> |
|[將自訂圖格新增至應用程式啟動器](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |Microsoft 365 中的應用程式啟動器可讓使用者輕鬆地找到和存取其應用程式。 本文說明您做為開發人員可以在使用者的應用程式啟動器中顯示您的應用程式的方式，同時也讓他們具備單一登入 (SSO) 使用其 Microsoft 365 認證的經驗。  <br/> |
|[Azure AD 整合教學課程](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |這些教程的目的是示範如何為協力廠商 SaaS 應用程式設定 Azure AD SSO。  <br/> |
|[Azure AD 的驗證案例](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD 透過提供身分識別做為服務，以支援業界標準通訊協定（例如 OAuth 2.0 和 OpenID Connect）和開放來源庫（如使用不同平臺來協助您快速開始編碼），簡化開發人員的驗證。 這份檔可協助您瞭解 Azure AD 支援的各種案例，並說明如何開始著手。  <br/> |
|[應用程式存取](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD 可輕鬆整合至當今流行軟體的許多服務 (SaaS) 應用程式。 它會提供身分識別和存取管理，並為使用者提供存取面板，讓使用者能夠探索哪些應用程式存取權，以及可以使用 SSO 存取其應用程式的位置。 本文提供相關資源的連結，可讓您深入瞭解 Azure AD 的應用程式存取增強功能，以及您可以如何參與這些功能。  <br/> |
|[個人化 Office 365 體驗](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |您可以透過在 Microsoft 365 應用程式啟動器中新增或移除應用程式，快速存取您每天使用的應用程式。  <br/> |

