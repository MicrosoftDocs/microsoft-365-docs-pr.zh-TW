---
title: 将数据从一个审核集添加到另一个审核集
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
ms.openlocfilehash: bd33d57380e99225d741b9c38677c2b49694139a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076781"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>将数据从其他审阅集添加到审阅集

在某些情况下，可能需要从一个审阅集中分离出部分文档，并在另一个审阅集中单独使用它们。  如果您已筛选审阅集中的内容，并且希望对数据子集运行分析，则此功能特别有用。

按照本文中的工作流将内容从一个审阅集添加到另一个审阅集。

## <a name="before-you-begin"></a>開始之前

在开始之前，您需要创建新的审阅集以将数据添加到。  可以在案例**的"审阅集"** 选项卡上添加新审核集。 有关详细信息，请参阅[创建审阅集](managing-review-sets.md#create-a-review-set)。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>第 1 步：标识要添加到其他审阅集的内容

您可以通过在源审阅集中选择特定文档或 b 从一个审阅集向另一个审阅集添加内容，或者 b 从审阅集查询返回的所有项目进行 seletletletletletletlet。  如果要添加选定项目，请选择项目，**单击"操作"，** 然后单击"**添加到其他审阅集"。**

![添加到另一个审阅集](media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>步骤 2：指定用于添加到其他审阅集的选项

在"**添加到其他审阅集选项**弹出窗口"页中，选择要向其添加项目的审阅集。 选择是添加**所有搜索结果**还是**添加选定项目。**  其他信息提供了一些选项，用于包括项目中的所有元数据，以及是否在文档添加到新审阅集时从源审阅集中包括标记（通过**选中"标签"** 复选框）。  

![添加到另一个审阅集](media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

**单击"确定"** 后，将创建一个新作业（名为"**将数据添加到另一个审阅集"）** 以将内容添加到另一个审阅集。  您可以**转到"作业"** 选项卡并监视此作业的进度。 有关详细信息，请参阅[管理作业](managing-jobs-ediscovery20.md)。
