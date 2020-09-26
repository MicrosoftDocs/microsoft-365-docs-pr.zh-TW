---
title: 調查的高級資料索引
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
description: 瞭解如何使用高級索引，確定您的搜尋會捕獲您要調查的所有資料。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b0bb1a757ac70466fb43f2385485ce6da1dc741
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285959"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>調查的高級資料索引

即時系統中的內容可以部分編制索引，原因很多，包括影像存在、不支援的檔案類型，或是在遇到索引檔案大小限制時。 當您處理高風險資料溢出時，您想要確保搜尋已捕獲所有想要調查的資料。 在資料調查中加入感興趣的人員時，會重新處理被視為部分索引的任何內容，使其完全可供搜尋。 此處理程式稱為「 *高級索引*」。 

若要深入瞭解處理支援和部分索引項目目的詳細資訊，請參閱：

- [資料調查中支援的檔案類型](supported-filetypes-datainvestigations.md)

- [位於 Office 365 中內容搜尋的已局部編製索引項目](partially-indexed-items-in-content-search.md)

- [Exchange 搜尋編製索引的檔案格式](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高級索引結果

在高級索引處理常式完成之後，您就可以深入瞭解重新處理的有效性。  在重要的 [索引視圖人員] 中，圖表會列出新增至 *混合索引*的所有專案。  混合索引是資料調查 (預覽) 儲存重新處理內容的所在位置。

此圖也包含需要修正的專案數，以及另一個依檔案類型的錯誤圖表。 如需詳細資訊，請參閱 [在處理資料時進行錯誤修正](error-remediation.md)。

## <a name="updating-advanced-indexes-for-people-of-interest"></a>更新感興趣人員的高級索引

當相關人員加入資料調查時，會重新處理所有部分索引項目目。 不過，隨著時間的推移，可將更多的索引項目目新增至使用者的信箱或 OneDrive 帳戶。  如有需要，您可以更新索引。

> [!NOTE]
> 更新感興趣的索引人員會執行很長的處理常式。 建議您不要在調查中每日更新一次以上的索引。
