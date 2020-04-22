---
title: Microsoft 365 中的資料調查（預覽）版本附注
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
description: 本文說明 Microsoft 365 中的新資料調查（預覽）工具。
ms.openlocfilehash: 813877151f538bc07a0460fdd702ab37ebcc5a1a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637733"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 中的資料調查（預覽）版本附注

您可以使用 Microsoft 365 中的「新增資料調查（預覽）」工具來會審、調查和修正資料相關的事件，例如資料外泄事件或內部調查。 資料調查的公開預覽可讓您及早存取即將推出的功能和更新。 若要取得最新功能的初期存取，請在安全性 & 規範中心建立新調查（預覽）。 若要深入瞭解，請參閱[管理 Microsoft 365 中的資料外泄事件](manage-data-spillage-incidents.md)。

## <a name="whats-new"></a>新功能 

- **調查**-您可以建立調查，以群組搜尋和事件。 新增或移除成員，以管理可以存取調查的人員。  您也可以選取及標示您最愛的調查。 使用新的儀表板，追蹤並監控在調查內和跨調查的活動。 完成調查之後，您可以關閉或刪除。

- **感興趣的人員**-當您將使用者新增至調查的相關人員時，您可以查看其信箱、OneDrive 商務用帳戶，以及 Microsoft 小組網站。 您可以使用它們來限定調查內容搜尋的範圍。 若要進一步調查感興趣的人員，您也可以在 Microsoft 365 和其他 Microsoft 服務中查看與其活動相關的審計記錄。

- **搜尋**–使用各種搜尋條件建立組織範圍的搜尋。 如果您知道想要搜尋的使用者或網站，您可以將這些使用者新增為感興趣的人員，或是在 [搜尋建立] 中指定網站位置。 

- **證據**–建立新的證據集，並新增您要查看的搜尋結果。 您可以查看個別檔、批註以留下調查附注，以及匯出結果以移至不同的環境。 

- **回顧**–使用原生、文字和近原生的視圖，檢查新增至事件的檔。 您也可以將分析套用至檔，以依重複、電子郵件執行緒及主題群組專案，這有助於協助您複查事件。 

- **標記密文、標記和批註**–在您審閱檔時標記密文、套用標記，並做為批註。
  
- **高級索引**–如果有任何部分編制索引的專案，將會根據需要重新編制索引，這樣所有的資料就會可供搜尋使用。

- **錯誤修正**–修正或下載處理錯誤。 這包括對大型檔案類型的補救支援、受密碼保護的檔案，以及與索引錯誤相關的其他問題。 

- **工作**–追蹤長時間執行程式的狀態。

- **硬性刪除信箱專案**-在緊急情況下，您可能需要永久刪除錯放的專案。 若要這麼做，您可以在安全性 & 規範中心 PowerShell 中執行**New-ComplianceSearchAction-Purge PurgeType HardDelete**命令，以從信箱中永久移除專案。 如需詳細資訊，請參閱 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) (英文)。
