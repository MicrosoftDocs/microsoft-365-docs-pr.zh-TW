---
title: 切換到 Office 365 for business 方案前先備份資料
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: 備份 Outlook、 OneDrive、 Yammer 及 SharePoint 內容之前切換 Office 365 訂閱，或如果會在使用者離開組織。
ms.openlocfilehash: 16fb6972869c3caf010c25cbe043dbf79f458531
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239563"
---
# <a name="back-up-data-before-switching-office-365-for-business-plans"></a>切換到 Office 365 for business 方案前先備份資料

如果使用者將會切換至另一個訂閱已較少資料相關的服務，或是在使用者離開組織，他們會切換至新的訂閱之前可以下載一份他們 Office 365 中儲存的資料。
  
## <a name="save-a-copy-of-outlook-information"></a>儲存一份 Outlook 資訊

如果使用者有 Outlook，他們可以[匯出或備份電子郵件、 連絡人及行事曆為 Outlook.pst 檔案無法](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)再切換其計劃。 
  
在切換至新方案完畢之後，使用者可以[匯入電子郵件、 連絡人及行事曆從 Outlook.pst 檔案](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。
  
## <a name="save-files-stored-in-onedrive-for-business"></a>將檔案儲存在商務用 OneDrive 儲存

之前切換至不同的訂閱，則使用者可以到不同的位置，例如在其電腦的硬碟上的資料夾或檔案共用的組織網路上的 [[下載檔案和資料夾從 OneDrive 或 SharePoint](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05) 。 
  
## <a name="save-yammer-information"></a>若要將 Yammer 資訊

系統管理員可以將所有郵件、 備忘稿、 檔案、 主題、 使用者和群組，都匯出至.zip 檔案。 如需詳細資訊，請參閱[匯出 Yammer Enterprise 中的資料](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)。 開發人員可用來執行此作業，以及[Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) 。 
  
## <a name="how-to-save-sharepoint-information"></a>如何儲存 SharePoint 資訊

如果使用者從具有 SharePoint Online 都不會有它的其中一個訂閱切換，[ **SharePoint** ] 磚將不再顯示在其 Office 365] 功能表。 
  
不過，只要新的訂閱已從切換的一個相同的組織內，使用者仍然能夠存取 SharePoint 小組網站。 他們可以檢視及更新 [使用直接 URL 至小組網站的 [筆記本、 文件、 工作和行事曆。
  
> [!TIP]
> 建議使用者為我的最愛或其瀏覽器中的書籤，移至小組網站前切換其訂閱及儲存的 URL。 
  
根據預設，小組網站的 URL 是這種形式：
  
```
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

其中_\<orgDomain\>_ 是組織的 URL。 
  
例如，如果組織的網域是 contoso.onmicrosoft.com，然後直接 URL 至小組網站會是https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx。
  
當然，使用者也可以下載 SharePoint Online 的文件從 SharePoint 小組網站到其本機電腦或另一個位置在任何時間。