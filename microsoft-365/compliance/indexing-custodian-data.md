---
title: 進階的監管人資料索引
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
description: 當保管人加入 Advanced eDiscovery 案例時，被視為部分索引的任何內容都會重新處理，使其完全可供搜尋。
ms.openlocfilehash: f510b7e9c0fa2c5c181709c96907610066a4b1cf
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430502"
---
# <a name="advanced-indexing-of-custodian-data"></a>進階的監管人資料索引

當系統管理員加入 Advanced eDiscovery 案例時，任何被視為已做為部分索引的內容或是具有索引錯誤，都是重新編制索引，讓它完全可供搜尋。  這種重建索引過程稱為「 *高級索引*」。 內容已部分編制索引或出現索引錯誤的原因有許多。 這包括圖像檔案或檔中的圖像、不支援的檔案類型或檔案大小的索引限制。 若為 SharePoint 檔案，則只有在專案上執行的高級索引程式會標示為已部分編制索引或具有索引錯誤。 在 Exchange 中，具有影像附件的電子郵件將不會標示為已部分編制索引或具有索引錯誤。 這表示將不會重新編制索引高級索引處理常式的檔案。

若要深入瞭解處理支援和部分索引項目目的詳細資訊，請參閱：

- [Advanced eDiscovery 中支援的檔案類型](supported-filetypes-ediscovery20.md)

- [位於 Office 365 中內容搜尋的已局部編製索引項目](partially-indexed-items-in-content-search.md)

- [Exchange 搜尋編製索引的檔案格式](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高級索引結果

在高級索引處理常式完成之後，您就可以深入瞭解重新處理的有效性。  在案例的 [ **處理** ] 索引標籤上，在 [高級索引結果] 視圖中，圖表會列出新增至 *混合索引* 的專案數。  混合索引是指 Advanced eDiscovery 儲存重新處理內容的位置。

此視圖也包含需要修正的專案數，以及另一個依檔案類型的錯誤圖表。 如需詳細資訊，請參閱：

- [處理資料時發生補救錯誤](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [單一項目錯誤補救](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>更新保管人的高級索引

當保管人加入 Advanced eDiscovery 案例時，會重新處理所有部分索引項目目。 不過，隨著時間的推移，可將更多的索引項目目新增至使用者的信箱或 OneDrive 帳戶。  如有必要，您可以更新特定保管人的索引。 如需詳細資訊，請參閱[在 Advanced eDiscovery 案例中管理保管人](manage-new-custodians.md#re-index-custodian-data)。 您也可以在案例中，按一下 [**處理**] 索引標籤上的 [**更新索引**]，以更新所有保管人的索引。

> [!NOTE]
> 更新保管人索引是一個長時間的處理常式。 建議您不要在案例中一天更新一次索引。
