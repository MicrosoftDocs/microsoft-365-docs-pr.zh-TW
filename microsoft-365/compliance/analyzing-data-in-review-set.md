---
title: 在高级电子数据展示中分析审阅集中的数据
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
ms.openlocfilehash: b331bba76f45a11a4d1c8c0552b27759cf49608a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076744"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>在高级电子数据展示中分析审阅集中的数据

当收集的文档数量很大时，要查看所有文档可能相当困难。 高级电子数据展示提供了多种工具来分析文档，以减少要审阅的文档数量，而不会丢失任何信息，并帮助您以连贯的方式组织文档。 要了解有关这些功能的信息，请参阅：

- [近似重複項偵測](near-duplicates.md)

- [電子郵件執行緒](email-threading.md)

- [佈景主題](themes.md)

要分析审阅集中的数据，请：

1. 为您的案例配置分析设置。 有关详细信息，请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。

2. 打开要分析的审阅集。

3. **单击"管理审阅集"。**

4. **单击"为审阅集运行分析"。**

您可以在案例的"**作业"** 选项卡上检查分析进度。

 分析完成后，您可以查看分析报告，在审阅集中对分析的输出运行查询（请参阅[审阅集中的查询），](review-set-search.md)并查看给定文档的相关文档（请参阅[审阅集中的数据）。](reviewing-data-in-review-set.md)

## <a name="analytics-report"></a>分析报告

要查看审核集的分析报告：

1. 打开审阅集。

2. **单击"管理审阅集"。**

3. **单击"查看报表**"。

该报告有四个分析内容：

- **细分**- 在审阅集中找到的电子邮件、附件和松散文档数。

- **文档（不包括附件）** - 有多少松散文档是透视、枢轴的几乎副本或另一个文档的精确副本。

- **电子邮件**- 包含的电子邮件数量、包含副本、包含数减数或上述任何内容均无。

- **附件**- 审阅集中的另一个电子邮件附件中有多少电子邮件附件是唯一的或重复的。