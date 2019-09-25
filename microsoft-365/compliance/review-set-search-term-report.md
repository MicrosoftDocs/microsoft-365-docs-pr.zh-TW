---
title: 为审阅集生成搜索词报告
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078148"
---
# <a name="generate-search-term-report-for-a-review-set"></a>为审阅集生成搜索词报告

在电子数据展示中，查询文档最常用的条件之一是使用关键字搜索词。 通过识别包含对案例很重要的特定关键字（也称为*术语）* 的文档，审阅者可以开始深入了解他们所面临的问题。 在 Microsoft 365 中的高级电子数据展示中，您可以通过在审阅集中生成搜索字词报告来执行此操作。

## <a name="step-1-create-a-saved-query-in-the-review-set"></a>步骤 1：在审阅集中创建保存的查询

要生成有意义的搜索词报表，请创建一个保存的查询，该查询定义要为其生成搜索词报表的审阅集中的文档集。 例如，可以使用日期范围或实际搜索词集（通过使用关键字条件卡）来创建查询。 要了解有关审阅集查询的更多详细信息，请参阅[查询审阅集中的数据。](review-set-search.md)

## <a name="step-2-generate-a-search-term-report"></a>第 2 步：生成搜索词报告

生成搜索字词报表的方法有两种：通过在步骤 1 中创建的已保存查询的上下文菜单，或通过搜索词报表管理控制台。

- 要使用上下文菜单，请打开在步骤 1 中创建的已保存查询的上下文菜单，**然后单击"生成搜索词报告"。**

- 要使用管理控制台，请**转到"管理审阅集>查看搜索词报告，****单击"新建"，** 然后选择您在步骤 1 中创建的已保存查询。

然后，输入您要报告的术语，用排行分隔;如果在步骤 1 中创建的已保存查询使用了关键字条件卡，则弹出窗口将预填充来自已保存查询中使用的第一个关键字条件卡中的字词。

然后，选择最多三个要报告的透视，**然后单击"生成"，** 这将启动搜索词报表生成作业。

### <a name="what-is-a-pivot"></a>什么是枢轴？

数据透视是报表的组织方式。 请考虑以下示例。

- 保存的查询检索 10 个文档：doc1 到 doc10。

- doc1、doc2、doc3、doc4、doc5、doc6 和 doc7 包含术语"电子数据展示"。

- doc6、doc7、doc8、doc9 和 doc10 包含术语"调查"。

- 单1、doc3、doc5、doc7、doc9均来自保管人A。

- doc2、doc4、doc6、doc8、doc10 均来自保管人 B。

在这种情况下，如果您要生成关于术语"电子数据展示"和"调查"的搜索字词报告，并基于保管人，则搜索字词报告将组织如下：

- "电子数据展示" - 保管人 A：4 份文件

- "电子数据展示" - 保管人 B：3 份文件

- "调查" - 保管人 A：2份文件

- "调查" - 保管人 B：3份文件

## <a name="step-3-download-report"></a>第 3 步：下载报告

在搜索字词管理控制台中，可以跟踪以前创建的搜索词报表作业的状态。 作业完成后，您可以单击搜索词报告的行并单击"下载"，这将以 CSV 格式下载搜索词报告。 每个组（搜索术语、枢轴）组组将有一行，每行将包含以下信息：

- 检索了多少文档？

- 在文档中找到搜索字词多少次？

- 检索到的文档的总数量是多少？

- 被找回了多少个家庭？

- 这些系列的文档总数是多少，包括没有搜索字词的文档？

- 上述总体积是多少？