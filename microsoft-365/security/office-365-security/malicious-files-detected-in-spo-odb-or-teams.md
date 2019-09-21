---
title: 檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: 了解要移至檢視中 SharePoint、 OneDrive 或小組，偵測到的惡意檔案的相關資訊，以及如何對這些檔案採取動作。
ms.openlocfilehash: b16ba88cd4984754f92fac2917f0f2b393600692
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078126"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊

[適用於 SharePoint、 OneDrive 及 Microsoft Teams 的 office 365 ATP](atp-for-spo-odb-and-teams.md)會保護您的組織在文件庫和小組網站中的惡意檔案。 偵測到惡意檔案時，該檔案被封鎖，讓任何人可以開啟、 複製、 移動或共用直到由組織的安全性小組會採取進一步的動作。 閱讀本篇文章以了解如何檢視關於偵測到檔案的資訊以及要採取的動作。 

若要執行本文所述的工作，您必須具有所需之[Office 365 安全性的權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="view-reports-with-information-about-detected-files"></a>檢視報告與偵測到檔案的相關資訊

若要檢視狀態和偵測到由 Office 365 ATP 的檔案的詳細的資訊，您可以使用威脅保護狀態報表。
  
1. 在[Office 365 安全性&amp;合規性中心](https://protection.office.com)，選擇 [**報告**] \> **儀表板** \> **威脅保護狀態**。
    
2. 在報表的右上角，選擇 [**檢視詳細資料] 表格**。
    
3. 檢視報表中偵測到的檔案的清單。
    
4. 若要檢視的詳細的資訊，包括採取的動作、 檔案名稱、 檔案路徑，以及更多在清單中選取項目。
    
5. 選擇 [**進階分析**] 索引標籤來檢視資訊，例如觀察到的行為與分析詳細資料]。 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>檢視並採取檔案中的巨集指令，在隔離區中

1. 在 Office 365 安全性&amp;合規性中心，選擇 [**威脅管理** \> **檢閱** \> **隔離**。
    
2. 在左上角，變更篩選從**電子郵件**到**內容**。
    
3. 若要檢視的詳細的資訊，包括之檔案的 URL 清單中選取項目。
    
4. 選擇 [可用的動作。
    
  - 選擇 [**版本&amp;報表**解除封鎖的檔案。 
    
    選取 [**傳送報告給 Microsoft**向 Microsoft 報告為誤判的檔案。 
    
  - 選擇 [**檔案下載**調查進一步的檔案。 
    
  - 選擇 [**刪除**] 以從隔離的項目清單中移除檔案。 如果您選擇此選項，您也必須針對商務或 Microsoft Teams 刪除從其各自的文件庫中 SharePoint Online、 OneDrive 檔案。 此選項不會解除封鎖正在將檔案開啟或共用。 
    
5. 選擇 [**關閉**] 以關閉 [選取的項目詳細資料。 
  
  

