---
title: 用于调查的数据的高级索引
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
ms.openlocfilehash: 3d562dbc1fc696b1e6d2acccc92f69385da49510
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076255"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>用于调查的数据的高级索引

由于多种原因，包括存在图像、不支持的文件类型或遇到索引文件大小限制时，实时系统中的内容可以部分编制索引。 在处理高风险数据溢出时，需要确保搜索捕获要调查的所有数据。 将感兴趣的人员添加到数据调查时，将重新处理 Office 365 中被视为部分索引的任何内容，使其完全可搜索。 此过程称为*高级索引。* 

要了解有关 Office 365 和部分索引项中的处理支持的更多内容，请参阅：

- [数据调查中支持的文件类型](supported-filetypes-datainvestigations.md)

- [位於 Office 365 中內容搜尋的已局部編製索引項目](partially-indexed-items-in-content-search.md)

- [Exchange 搜尋編製索引的檔案格式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高级索引结果

完成高级索引过程后，您可以了解重新处理的有效性。  在"感兴趣的人"索引视图中，该图列出了添加到*混合索引*中的所有项。  混合索引是数据调查（预览）存储重新处理的内容的位置。

该图还包括需要修正的项数以及按文件类型划分的另一个错误图表。 有关详细信息，请参阅[处理数据时的错误修正。](error-remediation.md)

## <a name="updating-advanced-indexes-for-people-of-interest"></a>为感兴趣的人更新高级索引

将感兴趣的人员添加到数据调查时，将重新处理所有部分索引的项目。 但是，随着时间的推移，可能会将更多部分索引的项目添加到用户的邮箱或 OneDrive 帐户中。  如果需要，可以更新索引。

> [!NOTE]
> 更新感兴趣的人员索引是一个长时间运行的过程。 建议您在调查中每天更新索引多次。
