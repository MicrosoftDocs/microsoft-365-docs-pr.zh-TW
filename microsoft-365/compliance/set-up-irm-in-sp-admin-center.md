---
title: 在 SharePoint 系統管理中心中設定資訊版權管理 (IRM)
f1.keywords:
- NOCSH
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
description: 瞭解如何透過 Microsoft Azure Active Directory Rights Management Services (RMS) 使用 SharePoint Online IRM，以保護 SharePoint 清單和文件庫。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919399"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>在 SharePoint 系統管理中心中設定資訊版權管理 (IRM)

在 SharePoint Online 中，IRM 保護套用於清單和文件庫級別的檔案。 貴組織必須先設定權限管理，然後才能使用 IRM 保護。 IRM 依賴來自 Azure 資訊保護的 Azure Rights Management 服務來加密和指派使用限制。 有些 Microsoft 365 方案包含 Azure 版權管理，但並非全部。 若要深入瞭解，請參閱[Office 應用程式和服務對 Azure 版權管理的支援方式](/azure/information-protection/understand-explore/office-apps-services-support)。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>使用 SharePoint 系統管理中心開啟 IRM 服務

您的組織必須先為組織啟用 Rights Management 服務，才能 SharePoint 清單和文件庫進行 IRM 保護。 若要深入瞭解，請參閱 [啟用 Azure Rights Management](/information-protection/deploy-use/activate-service)。 您必須使用具有全域系統管理員許可權的工作或學校帳戶，才能啟用 Rights Management 服務。 否則，您將無法在 SharePoint 線上使用 IRM 功能。
  
在啟動 Rights Management 服務後，請登入 SharePoint 系統管理中心，以開啟 IRM。
  
1. 以全域管理員身分登入，或 SharePoint 管理員登入。
    
2. 在左上角選取應用程式啟動器圖示 ![Office 365 中的應用程式啟動器圖示](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png)，然後選擇 [系統管理員] 來開啟 Microsoft 365 系統管理中心。  (如果您沒有看到 [系統管理] 磚，表示您的組織不具備系統管理員許可權。 )  
    
3. 在左窗格中，選擇 [系統 **管理中心**] \> **SharePoint**。
    
4. 在左窗格中，選擇 [ **設定**]，然後選擇 [ **傳統設定] 頁面**。
    
5. 在 [**資訊版權管理 (irm)** ] 區段中，選擇 [**使用您設定中指定的 IRM 服務**]，然後選擇 [重新整理 **irm 設定**]。 重新整理 IRM 設定之後，您組織中的人員可以在其 SharePoint 清單和文件庫中開始使用 IRM。 不過，若要執行此動作的選項，可能需要長達一個小時才能出現在 Library 設定和清單設定中。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM-啟用 SharePoint 文件庫與清單
<a name="__toc220831191"> </a>

重新整理 IRM 設定之後，網站擁有者便可對其 SharePoint 清單和文件庫進行 IRM 保護。 如需詳細資訊，請參閱 [將資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
當網站擁有者對清單或文件庫啟用 IRM 時，他們可以保護該清單或文件庫中任何支援的檔案類型。 針對文件庫啟用 IRM 時，版權管理會套用至該文件庫中的所有檔案。 當您為清單啟用 IRM 時，版權管理只會套用至清單專案附加的檔案，而非實際的清單專案。
  
當使用者在已啟用 IRM 的清單或文件庫中下載檔案時，這些檔案會進行加密，只有經過授權的人員才能加以查看。 每個版權管理檔案也包含發行授權，對查看檔案的人員有限制。 一般限制包括將檔案設為唯讀、停用文字的複製、防止使用者儲存本機副本，以及防止使用者列印檔案。 可讀取 IRM 支援之檔案類型的用戶端程式會使用版權管理檔案中的發行授權，以強制執行這些限制。 這是版權管理檔案在下載之後，如何保留其保護。 若要在清單或文件庫上啟用 IRM，請參閱 [將資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
您無法使用瀏覽器中的 Office，在已啟用 IRM 的文件庫中建立或編輯檔。 相反地，一次只能有一個人下載及編輯 IRM 加密的檔案。 使用存回及取出，以管理  *共同撰寫*  或在多個使用者中製作。 
  
當您從受 IRM 保護的文件庫下載 PDF 檔案時，Microsoft 365 會建立受保護的 pdf 檔案。 檔案的副檔名不會變更，但檔會受到保護。 若要查看此檔案，您需要有 Azure 資訊保護檢視器、完整 Azure 資訊保護用戶端或其他支援查看受保護 PDF 檔案的應用程式。 
  
SharePoint線上支援下列檔案類型的加密：
  
- PDF
    
- 下列 Microsoft Office 程式的97-2003 檔案格式： Word、Excel 及 PowerPoint
    
- 下列 Microsoft Office 程式的 Office Open XML 格式： Word、Excel 及 PowerPoint
    
- XML 紙張規格 (XPS) 格式
 
> [!NOTE]
> IRM 保護無法套用至受保護的檔 (例如數位簽署的 PDF 檔案) SharePoint 需要在上傳時開啟檔。 

## <a name="next-steps"></a>後續步驟
<a name="__toc220831191"> </a>

在您為線上 SharePoint 啟用 IRM 之後，您可以開始將 rights management 套用至清單和文件庫。 如需詳細資訊，請參閱 [將資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
Windows 的新 OneDrive 同步處理用戶端現在支援同步處理受 irm 保護的 SharePoint 文件庫及 OneDrive 位置，只要該庫的 IRM 設定不會設為 [到期檔存取許可權] (。 如需詳細資訊，或若要開始部署新的同步處理用戶端，請參閱[部署 Windows 的新 OneDrive 同步用戶端](/onedrive/deploy-on-windows)。
  
[頁首](set-up-irm-in-sp-admin-center.md)