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
description: 當保管人新增至高級 eDiscovery 案例時，被視為部分索引的任何內容都會重新處理，使其完全可供搜尋。
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911207"
---
# <a name="advanced-indexing-of-custodian-data"></a>進階的監管人資料索引

當保管人新增至高級 eDiscovery 案例時，被視為部分索引的任何內容都會重新處理，使其完全可供搜尋。  此處理程式稱為「 *高級索引*」。 內容可能會因原因而部分編制索引，包括映射的存在、不支援的檔案類型，或是遇到索引檔案大小限制。

若要深入瞭解處理支援和部分索引項目目的詳細資訊，請參閱：

- [高級 eDiscovery 中支援的檔案類型](supported-filetypes-ediscovery20.md)

- [位於 Office 365 中內容搜尋的已局部編製索引項目](partially-indexed-items-in-content-search.md)

- [Exchange 搜尋編製索引的檔案格式](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高級索引結果

在高級索引處理常式完成之後，您就可以深入瞭解重新處理的有效性。  在案例的 [ **處理** ] 索引標籤上，在 [高級索引結果] 視圖中，圖表會列出新增至 *混合索引* 的專案數。  混合索引是指 Advanced eDiscovery 儲存重新處理內容的位置。

此視圖也包含需要修正的專案數，以及另一個依檔案類型的錯誤圖表。 如需詳細資訊，請參閱：

- [處理資料時發生補救錯誤](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [單一項目錯誤補救](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>更新保管人的高級索引

當系統管理員新增至高級 eDiscovery 案例時，會重新處理所有部分索引項目目。 不過，隨著時間的推移，可將更多的索引項目目新增至使用者的信箱或 OneDrive 帳戶。  如有必要，您可以更新特定保管人的索引。 如需詳細資訊，請參閱 [Manage 保管人 In Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data)。 您也可以在案例中，按一下 [**處理**] 索引標籤上的 [**更新索引**]，以更新所有保管人的索引。

> [!NOTE]
> 更新保管人索引是一個長時間的處理常式。 建議您不要在案例中一天更新一次索引。