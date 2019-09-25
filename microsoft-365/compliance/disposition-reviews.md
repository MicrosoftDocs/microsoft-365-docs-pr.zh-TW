---
title: 处置审查概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 创建在 Microsoft 365 中保留内容的保留标签时，可以选择在保留期结束时触发处置审核。
ms.openlocfilehash: 22079fc92cabc902cd7afee7e187b7e186aa2328
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076328"
---
# <a name="overview-of-disposition-reviews"></a>处置审查概述

当内容达到其保留期结束时，您可能需要查看该内容以决定是否可以安全地删除（"已释放"）的原因有多种。 例如，您可能需要：
  
- 在发生诉讼或审计时，暂停删除（"处置"）相关内容。
    
- 如果内容具有研究或历史价值，请从处置列表中删除以将其存储在存档中的内容。
    
- 如果原始策略是临时或临时解决方案，则为内容分配不同的保留期。
    
- 将内容返回给客户端或将其传输到其他组织。
    
当您在 Microsoft 365 合规性中心、Microsoft 365 安全中心或 Office 365 安全&合规性中心创建保留标签时，可以选择在保留期结束时触发处置审核。 在处置审查中：
  
- 您选择的人员会收到一封电子邮件通知，告知他们具有要查看的内容。 这些审阅者可以是单个用户、分发或安全组，也可以是 Office 365 组。 请注意，通知每周发送一次。
    
- 审阅者转到安全&amp;合规性**中心的"处置"** 页以审阅内容。 审阅者可以看到每个保留标签等待处置的项目数，然后选择保留标签以查看带有该标签的所有内容。
    
- 对于每份文档或电子邮件，审阅者可以：
    
  - 应用其他保留标签。
    
  - 延长其保留期。
    
  - 永久删除它。
    
- 审阅者可以查看挂起或已完成的处置，并将该列表导出为 .csv 文件。

> [!NOTE]
> 处置审核需要 Office 365 企业版 E5 订阅。
  
处置审核可以包括 Exchange 邮箱、SharePoint 网站、OneDrive 帐户和 Office 365 组中的内容。 只有在审阅者选择永久删除内容后，才会删除这些位置等待处置审核的内容。
  
![安全和合规中心中的处置页面](media/Retention-Dispositions-v2-page.png)

## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a>通过创建保留标签设置处置审核

这是设置处置审核的基本工作流。 请注意，此流显示正在发布并由用户手动应用的保留标签;因此，将发布保留标签。或者，可以自动将触发处置审核的保留标签应用于内容。
  
![显示处置流程流程的图表](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
在 Office 365 中创建保留标签时，处置审核是一个选项。 请注意，此选项在保留策略中不可用，但仅在配置为保留内容的保留标签中可用。
  
有关保留标签的详细信息，请参阅[保留标签概述](labels.md)。
  
![标签的保留设置](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>释放内容

当审阅者通过电子邮件收到内容已准备好审阅的通知时，他们可以转到安全&amp;合规性**中心的"处置"** 页。 审阅者可以看到每个保留标签等待处置的项目数，然后选择保留标签以查看带有该标签的所有内容。

选择保留标签后，下一页将显示该标签的所有待处理项。

![处置选项](media/Retention-Disposition-options-v2.png)

然后，审阅者可以： 
  
- 应用其他保留标签。
    
- 延长保留期。
    
- 永久删除该项目。

请注意，审阅者可以选择多个项目并同时释放它们。
    
如果审阅者具有该位置的权限，则审阅者还可以使用该链接在其原始位置查看文档。 在处置审核期间，内容永远不会从其原始位置移动，并且直到审阅者选择这样做才会删除。
  
请注意，电子邮件通知每周自动发送给审阅者。 因此，当内容达到其保留期结束时，审阅者最多可能需要 7 天才能收到内容正在等待处置的电子邮件通知。
  
另请注意，所有处置操作都经过审核。 为了确保这一点，您必须在第一次处置操作之前至少一天打开审核 - 有关详细信息，请参阅[在 Office 365&amp;安全合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。 
  
## <a name="permissions-for-disposition"></a>处置权限

要**访问"处置"** 页，审阅者**必须是"处置管理"** 角色**和"仅查看审核日志"** 角色的成员。 我们建议创建一个名为"处置审阅者"的新角色组，将这两个角色添加到该角色组，然后将成员添加到角色组。 
  
有关详细信息，请参阅[向用户授予对 Office 365 安全&amp;合规性中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>永久删除已释放内容的时间

只有在审阅者选择永久删除内容后，才会删除等待处置审核的内容。 当审阅者选择此选项时，SharePoint 网站或 OneDrive 帐户中的内容将有资格享受本节中描述的标准清理过程：[保留策略如何处理内容。](retention-policies.md#how-a-retention-policy-works-with-content-in-place)
  
这意味着：
  
- 文档库中的内容将在处置后的**7 天内**移动到第一阶段回收站，然后在**93 天后**永久删除。 回收站不按搜索编制索引，因此其内容不适用于电子数据展示保留。

- 保留保留库中的内容将在处置后的**7 天内**永久删除。

- 交换邮箱中的项目将在处置后的**14 天内**永久删除。 （请注意，14 天是默认设置，但最多可配置 30 天。
    
## <a name="view-pending-dispositions-and-disposed-items"></a>查看待处理处置和已处置项目

在"**待处理处置"** 页上，您可以查看特定保留标签的待处理和已完成处置： 
  
- **待处理显示**已达到其保留期末尾且需要处置审核的项目。 查看每个项目后，决定是否要对其应用不同的保留标签、延长其保留期或永久删除它。 您可以选择多个项目。
    
- "**已处置项目"** 选项卡显示处置在处置审核期间已批准删除，目前正在永久删除的过程中。 应用了不同的保留标签或延长其保留期作为审核的一部分的项目不会在此处显示。

![处置选项卡](media/Retention-Disposition-tabs.png)
    
### <a name="filter-the-disposition-views"></a>筛选处置视图

您可以按保留标签或时间范围筛选这些视图。 对于待处理，时间范围基于到期日期。 对于已处置的项目，时间范围基于删除日期。
  
![处置过滤器选项](media/Retention-filter-options.png)

### <a name="export-the-disposition-items"></a>导出处置项目

此外，您可以将任一视图中的项目导出为可在 Excel 中打开的 .csv 文件。
  
![Excel 中导出的处置数据](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

