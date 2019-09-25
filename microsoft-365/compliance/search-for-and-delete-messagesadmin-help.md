---
title: 搜尋並刪除郵件 - 管理中心說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 管理员可以使用搜索邮箱 cmdlet 搜索用户邮箱，然后从邮箱中删除邮件。
ms.openlocfilehash: bb375bc7a3273e78acb44807e51a1cee0261e7af
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077566"
---
# <a name="search-for-and-delete-messages---admin-help"></a>搜尋並刪除郵件 - 管理中心說明
  
管理员可以使用**搜索邮箱**cmdlet 搜索用户邮箱，然后从邮箱中删除邮件。 
  
要在一个步骤中搜索和删除邮件，请_使用"删除内容"_ 开关运行**搜索邮箱**cmdlet。 但是，执行此操作时，无法预览搜索结果或生成搜索将返回的邮件日志，并且可能会无意中删除您不打算删除的邮件。 要在删除邮件之前预览搜索中的邮件的日志，请_使用"仅 LogOnly"_ 开关运行**搜索邮箱**cmdlet。 
  
作为附加保护，您可以首先使用_目标邮箱_和目标_文件夹_参数将邮件复制到另一个邮箱。 通过执行此操作，您可以保留已删除邮件的副本，以防需要再次访问它们。 
  
## <a name="before-you-begin"></a>開始之前

- 預估完成時間：10 分鐘。 实际时间可能因邮箱大小和搜索查询而异。
    
- 不能使用 Exchange 管理中心 （EAC） 执行这些过程。 您必須使用命令介面。
    
- 您需要分配以下两个管理角色来搜索和删除用户邮箱中的邮件：
    
  - **邮箱搜索**- 此角色允许您跨组织中的多个邮箱搜索邮件。 根據預設，系統管理員不會被指派這個角色。 要为自己分配此角色以便可以搜索邮箱，请将自己添加为"发现管理"角色组的成员。 请参阅[将用户添加到发现管理角色组](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。
    
  - **邮箱导入导出**- 此角色允许您从用户的邮箱中删除邮件。 默认情况下，此角色不会分配给任何角色组。 要从用户的邮箱中删除邮件，可以将邮箱导入导出角色添加到组织管理角色组。 有关详细信息，请参阅[管理角色组中](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)的"将角色添加到角色组"部分。 
    
- 如果要从中删除邮件的邮箱启用了单个项目恢复，则必须首先禁用该功能。 如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。
    
- 如果要删除邮件的邮箱处于保留状态，我们建议您在删除保留和删除邮箱内容之前咨询记录管理或法律部门。 获得批准后，请按照"[清理可恢复项目文件夹"](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)主题中列出的步骤进行操作。
    
- 您可以使用**搜索邮箱**cmdlet 搜索最多 10，000 个邮箱。 如果您是 Exchange 在线组织，并且邮箱超过 10，000 个，则可以使用合规性搜索功能（或相应的**New 合规性搜索**cmdlet）搜索无限数量的邮箱。 然后，**您可以使用"新合规性搜索**操作"cmdlet 删除合规性搜索返回的邮件。 有关详细信息，请参阅[搜索和删除来自 Office 365 组织的电子邮件。](https://go.microsoft.com/fwlink/p/?LinkId=786856)
    
- 如果包含搜索查询（通过使用*搜索查询*参数），**搜索邮箱**cmdlet 将在搜索结果中返回最多 10，000 个项目。 因此，如果包含搜索查询，则可能需要多次运行**搜索邮箱**命令才能删除 10，000 多个项目。 
    
- 运行**搜索邮箱**cmdlet 时，还将搜索用户的存档邮箱。 同样，当您使用"_删除内容"_ 开关的**搜索邮箱**cmdlet 时，主存档邮箱中的项目将被删除。 为了防止这种情况，您可以*包括"不包含存档"* 开关。
    
## <a name="search-messages-and-log-the-search-results"></a>搜索消息并记录搜索结果

本示例在"主题"字段中搜索 4 月 Stewart 的邮箱，查找包含短语"您的银行对帐单"的邮件，并将搜索结果记录在管理员邮箱的"搜索和删除日志"文件夹中。 邮件不会复制到目标邮箱或从目标邮箱中删除。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

本示例搜索组织中的所有邮箱，以寻找文件名中包含单词"特洛伊木马"的任何类型的附加文件的邮件，并将日志邮件发送到管理员的邮箱。
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。
  
 
## <a name="search-and-delete-messages"></a>搜索和删除邮件

本示例在"主题"字段中搜索 April Stewart 的邮箱，查找包含短语"您的银行对帐单"的邮件，并从源邮箱中删除邮件，而无需将搜索结果复制到其他文件夹。 如前所述，您需要分配邮箱导入导入管理角色，以便从用户的邮箱中删除邮件。
  
> [!IMPORTANT]
> 当您将**搜索邮箱**cmdlet_与"删除内容"_ 开关一起使用时，邮件将从源邮箱中永久删除。 在永久删除邮件之前，我们建议您使用_LogOnly_开关在删除邮件之前生成搜索中的邮件的日志，或者在从源邮箱中删除邮件之前将邮件复制到其他邮箱。 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

本示例在 4 月 Stewart 的邮箱中搜索包含"主题"字段中短语"您的银行对帐单"的邮件，将搜索结果复制到邮箱备份邮箱中的文件夹 AprilStewart-DeleteDMessages，并从中删除邮件。四月的邮箱
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

本示例搜索组织中的所有邮箱，查找主题行为"下载此文件"的邮件，然后永久删除它们。 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。

## <a name="using-the--loglevel-full-parameter"></a>使用 -日志级别完整参数

在前面的一些示例中，LogLevel__ 参数（带 值）`Full`用于记录有关**搜索邮箱**cmdlet 返回的结果的详细信息。 包含此参数后，将创建一封电子邮件并将其发送到_由 TargetMailbox_参数指定的邮箱。 日志文件（是名为搜索结果.csv 的 CSV 格式文件）附加到此电子邮件，并将位于_由 TargetFolder_参数指定的文件夹中。 日志文件包含运行**搜索邮箱**cmdlet 时搜索结果中包含的每封邮件的行。 
