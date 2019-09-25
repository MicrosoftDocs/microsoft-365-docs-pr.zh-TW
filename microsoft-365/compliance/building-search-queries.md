---
title: 建立搜尋查詢
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
description: 在 Microsoft 365 中使用高级电子数据展示时，使用关键字和条件来缩小搜索范围。
ms.openlocfilehash: c4b2c5b6983b556ad87b553dde767c2160674a78
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076666"
---
# <a name="build-search-queries"></a>建立搜尋查詢

构建搜索查询时，可以使用关键字查找特定内容和条件，以缩小搜索范围，以返回与您的法律调查最相关的项目。

![使用关键字和条件缩小搜索结果范围](media/SearchQueryBox.png)

## <a name="keyword-searches"></a>关键字搜索

在搜索查询**的"关键字"** 框中键入关键字查询。 您可以指定关键字、电子邮件属性（如发送和接收日期）或文档属性（如文件名或文档上次更改的日期）。 您可以使用使用布尔运算符的更复杂的查询，例如**** AND、OR、NOT 和******NEAR** ****。 您还可以在 SharePoint 和 OneDrive 中的文档中搜索敏感信息（如社会保险号），或者搜索外部共享的文档。 如果将**关键字**框留空，则位于指定内容位置的所有内容都在搜索结果中。
    
或者，您可以**单击"显示关键字列表"** 复选框，并在每行中键入关键字或关键字短语。 如果这样做，则每行中的关键字由逻辑运算符（在搜索查询语法中表示为*c：s）* 连接，该逻辑运算符的功能与创建的搜索查询中的**OR**运算符类似。 这意味着包含任何行中的任何关键字的项目都在搜索结果中。

![使用关键字列表获取查询中每个关键字的统计信息](media/KeywordListSearch.png)

为什么要使用关键字列表？ 您可以获取显示关键字列表中每个关键字匹配的项目数的统计信息。 这可以帮助您快速识别最有效（也是最不有效）的关键字。 您还可以在关键字列表中的一行中使用关键字短语（用括号括起来）。 有关搜索统计信息的详细信息，请参阅[搜索统计信息](search-statistics.md)。

> [!NOTE]
> 为了帮助减少由大型关键字列表引起的问题，关键字列表中最多只能有 20 行。

## <a name="conditions"></a>條件
    
您可以添加搜索条件以缩小搜索范围并返回更精细的结果集。 每个条件都会向启动搜索时创建和运行的搜索查询添加一个子句。 条件由逻辑运算符（在搜索查询语法中表示为*c：c）* 逻辑连接到关键字查询（在关键字框中指定），该逻辑运算符的功能与**AND**运算符类似。 这意味着项必须满足关键字查询和搜索结果中包含的一个或多个条件。 這就是條件如何協助您縮小搜尋結果。 有关可在搜索查询中使用的条件的列表和说明，请参阅[关键字查询和搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的"搜索条件"部分。
