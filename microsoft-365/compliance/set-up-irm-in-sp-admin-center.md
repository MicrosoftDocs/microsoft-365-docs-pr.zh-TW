---
title: Set up Information Rights Management (IRM) in SharePoint admin center
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: 了解如何使用 SharePoint Online IRM 透過 Microsoft Azure Active Directory Rights Management Services (RMS) 來保護 SharePoint 清單與文件庫。
ms.openlocfilehash: 4ed50b5c683215394222628153c03c58ee23e6a0
ms.sourcegitcommit: e2ed110c4c3a8434f9fcc9d610069bc77bc39220
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2019
ms.locfileid: "38685553"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) in SharePoint admin center

## <a name="introduction"></a>簡介

在 SharePoint Online 中，IRM 保護會套用至清單與文件庫層級的檔案。 您的組織可以使用 IRM 保護之前，您必須先設定版權管理。 IRM 會取決於從 Azure 資訊保護來加密及指派流量限制的 Azure 版權管理服務。 某些 Office 365 方案包含 Azure Rights Management，但並非所有。 若要了解更多，請閱讀[如何 Office 應用程式和服務支援 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>開啟 IRM 使用 SharePoint 管理中心的 [服務]

您的組織可以 IRM 保護的 SharePoint 清單與文件庫之前，您必須先啟動您的組織的版權管理服務。 若要了解如何查看[啟動 Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service)。 您必須使用公司或學校帳戶已啟用的版權管理服務的 Office 365 全域系統管理員權限。 否則，您無法使用 SharePoint Online 中使用 IRM 功能。
  
之後啟動版權管理服務，登入 SharePoint 系統管理中心來開啟 IRM。
  
1. 以全域管理員或 SharePoint 系統管理員身分登入 Office 365。
    
2. 在左上角選取應用程式啟動器圖示 ![Office 365 中的應用程式啟動器圖示](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)，然後選擇 [系統管理員]**** 來開啟 Microsoft 365 系統管理中心。 (如果您沒有看到 [系統管理員] 磚，則您沒有組織中的 Office 365 系統管理員權限。) 
    
3. 在左窗格中，選擇 [**系統管理中心** \> **SharePoint**。
    
4. 在左窗格中，選擇 [**設定**]，然後選擇**傳統設定] 頁面**。
    
5. 在 [**資訊版權管理 (IRM)** ] 區段中，選擇 [**使用您的組態中指定的 IRM 服務**，，然後選擇 [**重新整理 IRM 設定**。 重新整理 IRM 設定後，您組織中的人員可以開始在其 SharePoint 清單與文件庫中使用 IRM。 不過，若要這麼做的選項可能會佔用 1 小時的時間來顯示在文件庫設定與清單設定。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>啟用 IRM 功能 SharePoint 文件庫與清單
<a name="__toc220831191"> </a>

在重新整理 IRM 設定之後, 網站擁有人可以 IRM 保護其 SharePoint 清單及文件庫。 如需詳細資訊，請參閱[資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
當網站擁有者的清單或文件庫啟用 IRM 時，請他們可以保護該清單或文件庫中任何支援的檔案類型。 文件庫啟用 IRM 時，版權管理套用至所有該文件庫中的檔案。 當您啟用 IRM 的清單時，版權管理僅適用於檔案附加至清單項目，不實際清單項目。
  
當人員下載中啟用 IRM 的清單或文件庫的檔案時，檔案加密，因此只有授權的使用者可以檢視它們。 每個受版權管理檔案也包含會限制檢視檔案的人員的發行授權。 一般限制包括唯讀屬性，停用複製文字，防止人員從儲存本機複本，並列印檔案時，防止人員進行檔案。 可以讀取 IRM 支援的檔案類型的用戶端程式會使用受版權管理檔案內的發行授權，以強制執行這些限制。 這是如何受版權管理檔案會保留其保護即使之後就會下載。 若要在清單或文件庫啟用 IRM，請參閱[資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
您無法建立或編輯文件中啟用 IRM 的文件庫的瀏覽器中使用 Office。 相反地，一次一個人可以下載並編輯之中 IRM 加密的檔案。 使用 [存回和取出管理*共同撰寫*，或製作跨多個使用者。 
  
當您從受 IRM 保護文件庫下載 PDF 檔案時，Office 365 會建立受保護的 PDF 檔案。 也不會變更檔案的副檔名，但受保護的檔案。 若要檢視此檔案中，您將需要 Azure 資訊保護檢視器中，完整的 Azure 資訊保護用戶端，或支援檢視的另一個應用程式保護 PDF 檔案。 
  
SharePoint Online 支援下列檔案類型的加密：
  
- PDF
    
- 下列的 Microsoft Office 程式的 97-2003年檔案格式： Word、 Excel 及 PowerPoint
    
- Office Open XML 格式的下列的 Microsoft Office 程式： Word、 Excel 及 PowerPoint
    
- XML Paper Specification (XPS) 格式
    
## <a name="next-steps"></a>後續步驟
<a name="__toc220831191"> </a>

一旦您已啟用 IRM 的 SharePoint Online，您可以開始將版權管理套用至清單和文件庫。 如需資訊，請參閱[資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
Windows 的新版 OneDrive 同步處理用戶端現在可支援同步處理受 IRM 保護的 SharePoint 文件庫和 OneDrive 位置 （只要程式庫的 IRM 設定不設過期文件的存取權限）。 如需詳細資訊，或若要開始部署新的同步處理用戶端，請參閱[部署 Windows 的新版 OneDrive 同步處理用戶端](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)。
  
[頁首](#introduction)  

