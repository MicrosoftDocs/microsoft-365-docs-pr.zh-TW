---
title: 進階的監管人資料索引
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
description: ''
ms.openlocfilehash: ba85ef90570dfbf2228148bf5211a4b041a1cb61
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076253"
---
# <a name="advanced-indexing-of-custodian-data"></a>進階的監管人資料索引

将保管人添加到高级电子数据展示案例时，将重新处理 Office 365 中被视为部分索引的任何内容，使其完全可搜索。  此过程称为*高级索引。* 内容可以部分编制索引，原因有很多，包括存在图像、不支持的文件类型或遇到索引文件大小限制。

要了解有关 Office 365 和部分索引项中的处理支持的更多内容，请参阅：

- [高级电子数据展示中支持的文件类型](supported-filetypes-ediscovery20.md)
- [位於 Office 365 中內容搜尋的已局部編製索引項目](partially-indexed-items-in-content-search.md)
- [Exchange 搜尋編製索引的檔案格式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高级索引结果

完成高级索引过程后，您可以了解重新处理的有效性。  在"保管人索引"视图中，该图列出了添加到*混合索引*中的所有项。  混合索引是高级电子数据展示存储重新处理的内容的位置。

该图还包括需要修正的项数以及按文件类型划分的另一个错误图表。 有关详细信息，请参阅[处理数据时的错误修正。](error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a>更新保管人的高级索引

将保管人添加到高级电子数据展示案例时，将重新处理所有部分索引的项目。 但是，随着时间的推移，可能会将更多部分索引的项目添加到用户的邮箱或 OneDrive 帐户中。  如果需要，可以更新索引。

> [!NOTE]
> 更新保管人索引是一个长时间运行的过程。 建议您每天更新索引多次。
