---
title: 執行分析以更快速地調查
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
ms.openlocfilehash: 7462b415c2e5b0a66c08bb9b5abb647f366e9785
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077572"
---
# <a name="run-analytics-to-investigate-faster"></a>執行分析以更快速地調查

当证据收集规模较大时，很难审查所有证据。 一组证据通常包括相同或类似的电子邮件或文档的多个副本。 数据调查 （预览版） 提供了许多分析工具，可帮助您减少需要审阅的文档数量，而不会丢失任何信息。 要了解有关这些功能的信息，请参阅：

- [近似重複項偵測](near-duplicates.md)

- [電子郵件執行緒](email-threading.md)

- [佈景主題](themes.md)

要分析证据集中的数据，请：

1. 为调查配置分析设置。 有关详细信息，请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。

2. 打开证据集。

3. **单击"管理证据"。**

4. **在"分析"** 下，单击"**分析"。**

您可以在调查中的"**作业"** 选项卡上检查分析进度。 触发的作业类型**名为"运行分析"。**

 分析完成后，您可以看到右侧面板中正在查看的文档的确切重复项或接近重复项的列表。 要选择要查看的文档的所有副本，您可以轻松地使用此面板执行此操作。 要了解有关此面板中其他功能的更多详细信息，请参阅[查看证据中的数据。](review-data-in-evidence.md) 

您还可以使用分析的输出（如主题）在证据中运行其他查询。 有关详细信息，请参阅[查询证据中的数据。](evidence-query.md)

## <a name="analytics-report"></a>分析报告

要查看分析报告以提供证据：

1. 打开证据集。

2. **单击"管理证据"。**

3. **在"分析"** 下，**单击"查看报告"。**

该报告有四个分析内容：

- **细分**- 在证据集中找到的原始电子邮件、附件和文档的数量。

- **电子邮件**- 包含、包含减数、包含副本或上述任何内容的 eamil 邮件数量。
   - 包含内容：电子邮件线程中包含所有以前历史记录且需要审阅的最后一条消息。
   - 包含减数：线程中包含一个或多个需要审阅的不同附件的邮件。
   - 包含副本：是另一个包含或包含的减消息（主题和正文）的副本。

- **附件**- 相同证据中不同电子邮件附件的唯一或重复的电子邮件附件数。

- **文档（不包括电子邮件附件）** - 需要审阅的唯一文档的数量，例如，几乎重复集最具代表性的文档或另一文档的精确副本）。