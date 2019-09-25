---
title: 微软 365 中数据调查（预览）的发行说明
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
description: 本文介绍了 Microsoft 365 中新的数据调查（预览）工具。
ms.openlocfilehash: 200b1c6c08d0fdb1c4af5da59fa75836b4b1fab3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076398"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>微软 365 中数据调查（预览）的发行说明

您可以使用 Microsoft 365 中的新数据调查 （预览） 工具对数据相关事件（如数据泄露事件或内部调查）进行会审、调查和修复。 数据调查的公共预览版使您能够提前访问即将推出的功能和更新。 要尽早访问最新功能，请在安全&合规性中心的数据调查（预览）中创建新的调查。 要了解如何，请参阅[管理 Microsoft 365 中的数据溢出事件。](manage-data-spillage-incidents.md)

## <a name="whats-new"></a>新功能 

- **调查**- 您可以通过创建调查对搜索和事件进行分组。 通过添加或删除成员来管理可以访问调查的人员。  您还可以选择并标记您最喜爱的调查。 使用新的仪表板跟踪和监视调查内部和跨调查的活动。 完成调查后，可以关闭或删除调查。

- **感兴趣的人员**– 当您将用户作为感兴趣的人员添加到调查时，可以看到其邮箱、企业帐户的 OneDrive 和 Microsoft Teams 网站。 您可以使用它们来设置调查内容搜索的范围。 要进一步调查感兴趣的人员，还可以查看与其在 Office 365 和其他 Microsoft 服务中的活动相关的审核记录。

- **搜索**– 使用各种搜索条件创建组织范围的搜索。 如果您知道要搜索的用户或网站，则可以通过将这些用户添加为感兴趣的用户或在搜索创建向导中指定网站位置来执行此操作。 

- **证据**– 创建新的证据集并添加要查看的搜索结果。 您可以查看单个文档，注释以留下调查说明，并导出结果以移动到其他环境。 

- **审阅**— 使用本机视图、文本视图和接近本机视图来查看添加到事件的文档。 您还可以将分析应用于文档，以便按重复项、电子邮件线程和主题对项目进行分组，这有助于您查看事件。 

- **在审阅文档时，编字、标记和批注**- 编辑文本、应用标记和进行批注。
  
- **高级索引**- 如果存在任何部分索引项，则它们将按需重新编制索引，以便所有数据都可用于搜索。

- **错误修正**= 修复或下载处理错误。 这包括对大型文件类型、受密码保护的文件以及与索引错误相关的其他问题的修正支持。 

- **作业**= 跟踪长时间运行的进程的状态。

- **硬删除邮箱项目**- 在紧急情况下，您可能需要永久删除错放的项目。 为此，您可以在"安全&合规性中心 PowerShell 中**运行"新建合规性搜索操作 - Purge- PurgeType HardDelete"** 命令，以便从邮箱中永久删除项目。 有关详细信息，请参阅[新合规性搜索操作](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)。
