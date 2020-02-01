---
title: Microsoft 365 中的資料調查 （預覽） 的版本資訊
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明 Microsoft 365 的新資料調查 （預覽） 工具。
ms.openlocfilehash: 57605566a8847a3630e1c4656f98f71ebb414f86
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595410"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 中的資料調查 （預覽） 的版本資訊

您可以使用新的資料調查 （預覽） 工具在 Microsoft 365 分級、 調查及修復資料相關事件，例如資料外洩事件或內部調查。 資料調查公用預覽為您提供搶先即將推出的功能和更新。 若要搶先使用最新功能，請在安全 & 與規範中心中的資料調查 （預覽） 建立新的調查。 若要深入了解，請參閱[管理 Microsoft 365 中的資料外洩事件](manage-data-spillage-incidents.md)。

## <a name="whats-new"></a>新功能 

- **調查**-您可以藉由建立調查群組搜尋和事件。 管理誰可以存取調查藉由新增或移除成員。  您也可以選取並標記您最愛的調查。 追蹤及監視活動內和使用新的儀表板調查之間。 完成您調查之後，您可以關閉或刪除它。

- **人員感興趣的**– 當您將使用者新增至調查上為感興趣的人員時，您可以查看他們的信箱，OneDrive 商務帳戶及 Microsoft Teams 網站。 您可以使用它們來調查的內容搜尋範圍。 若要進一步調查感興趣的人員，您也可以檢視稽核記錄相關的 Office 365 和其他 Microsoft 服務中其活動。

- **搜尋**– 建立整個組織搜尋使用各種搜尋條件。 如果您知道使用者或您想要搜尋的網站，您可以新增這些使用者人員感興趣或搜尋建立精靈] 中指定的網站 」 位置，以執行。 

- **辨識項**– 建立新的辨識項集合，並新增您想要檢閱的搜尋結果。 您可以檢閱個別文件、 留下調查備忘稿，加上註解和匯出結果，以移至不同的環境。 

- **檢閱**– 使用原生、 文字和附近原生檢視檢閱新增至事件的文件。 您也可以套用至文件以群組項目的分析的重複項目、 電子郵件執行緒和佈景主題，可協助協助您檢閱事件。 

- **Redact，加上標籤，並加上註解**– Redact 文字、 套用標記，以及當您檢閱文件註釋。
  
- **進階編製索引**– 如果有任何已局部編製索引的項目，它們會視需要重新編製索引，讓所有資料都將可供搜尋。

- **錯誤修復**– 修復或下載處理錯誤。 這包括修復支援大型檔案類型、 受密碼保護的檔案及編製索引的錯誤與相關的其他問題。 

- **工作**– 長時間執行程序的追蹤狀態。

- **硬碟刪除信箱項目**-在緊急情況下，您可能需要永久刪除 [找不到的項目。 若要這麼做，您可以執行**New-compliancesearchaction-清除-PurgeType HardDelete**命令中安全性 & 合規性中心 PowerShell 可永久移除信箱中的項目。 如需詳細資訊，請參閱 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) (英文)。
