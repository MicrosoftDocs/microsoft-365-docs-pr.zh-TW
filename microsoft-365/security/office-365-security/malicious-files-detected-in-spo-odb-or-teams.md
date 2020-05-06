---
title: 查看 Office 365 ATP 所偵測到之惡意檔案的相關資訊
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
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
description: 深入瞭解在 SharePoint、OneDrive 或小組中偵測到之惡意檔案的相關資訊，以及如何對這些檔案採取動作。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47b1fea4b3b5713a8f69e8f4b2c0e2ad0f6dd6b8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036641"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊

[SharePoint、OneDrive 和 Microsoft 團隊的 Office 365 ATP](atp-for-spo-odb-and-teams.md) ，可保護您的組織，避免文件庫和小組網站中的惡意檔。 偵測到惡意檔案時，該檔案會遭到封鎖，因此在組織的安全性小組採取進一步動作之前，任何人都無法開啟、複製、移動或共用該檔案。 請閱讀本文以瞭解如何查看偵測到檔案的相關資訊，以及要採取的動作。 

為了執行本文所述的工作，您必須具備[安全性&amp;與合規性中心](permissions-in-the-security-and-compliance-center.md)的必要許可權。 
  
## <a name="view-reports-with-information-about-detected-files"></a>以偵測到的檔案的相關資訊來查看報告

若要查看 Office 365 ATP 所偵測到之檔案的狀態和詳細資訊，您可以使用威脅防護狀態報表。
  
1. 在 [[安全性&amp;與合規性中心](https://protection.office.com)] 中，選擇 [**報告** \> ]**儀表板** \> **威脅防護狀態**。
    
2. 在報表的右上角，選擇 [ **View details table**]。
    
3. 查看報告中偵測到的檔案清單。
    
4. 選取清單中的專案，以查看詳細資訊，包括採取的動作、檔案名、檔路徑等等。
    
5. 選擇 [**高級分析**] 索引標籤，以查看資訊，例如觀察行為和分析詳細資料。 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>針對隔離區中的檔案，查看並採取動作

1. 在 [安全性&amp;與合規性中心] 中，選擇 [**威脅管理** \> **檢查** \> **隔離區**]。 （您也可以直接前往[https://protection.office.com/quarantine](https://protection.office.com/quarantine)。）
    
2. 在左上角，將**電子郵件**的下拉式功能表**變更為檔案**。 如果結果清單中包含太多專案，請使用**篩選**功能縮小選取範圍。
    
3. 選取清單中的專案，以查看詳細資訊，包括檔案的 URL。
    
4. 選擇可用的動作。
    
    - 選擇 [**發行**檔案] 以解除封鎖檔。 

      選取 [**傳送報告給 microsoft** ]，將檔案報告為對 microsoft 的 false 陽性。 

    - 選擇 [**下載**檔案] 以進一步調查檔案。 

    - 選擇 [**從隔離區移除**]，以從隔離的專案清單中移除檔案。 如果您選擇此選項，您也必須在 SharePoint Online、商務用 OneDrive 或 Microsoft 小組中，從各自的文件庫中刪除檔案。 此選項不會解除封鎖檔的開啟或共用。 
    
5. 選擇 [**關閉**]，關閉所選取專案的詳細資料。 
  
  

