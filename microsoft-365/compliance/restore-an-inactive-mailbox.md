---
title: 在 Office 365 中还原非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新员工或其他用户需要访问 Office 365 中非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。
ms.openlocfilehash: 6bd147296e4324c5f75ff808768f8899cf9b59fd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078175"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>在 Office 365 中还原非活动邮箱

非活动邮箱（一种软删除邮箱）用于在前员工离开您的组织后保留其电子邮件。 如果另一名员工承担离职员工的工作职责，或者该员工返回您的组织，则可以通过两种方式将非活动邮箱的内容提供给用户： 
  
- **还原非活动邮箱**如果其他员工承担离职员工的工作职责，或者如果其他用户需要访问非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。 还可以从非活动邮箱还原存档。 还原后，非活动邮箱将保留并保留为非活动邮箱。 本主题介绍还原非活动邮箱的过程。 
    
- **恢复非活动邮箱**如果离职员工返回您的组织，或者雇用新员工来承担离职员工的工作职责，则可以恢复非活动邮箱的内容。 此方法将非活动邮箱转换为包含非活动邮箱内容的新邮箱。 它會復原之後，非使用中的信箱不存在。 有关分步过程，请参阅在 Office [365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)
    
有关还原和恢复非活动邮箱之间的差异的详细信息，请参阅本文中**的详细信息**部分。 
  
## <a name="before-you-begin"></a>開始之前

- 您必须使用 Exchange 联机电源外壳来还原非活动邮箱。 不能使用 Exchange 管理中心 （EAC）。 有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 在 Exchange 联机 PowerShell 中运行以下命令，以获取组织中非活动邮箱的标识信息。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     使用此命令返回的信息还原特定的非活动邮箱。
    
- 有关非活动邮箱的详细信息，请参阅 Office [365 中的非活动邮箱。](inactive-mailboxes-in-office-365.md)
    
## <a name="restore-an-inactive-mailbox"></a>還原非作用中的信箱

_使用"源邮箱"_ 和"_目标邮箱"_ 参数使用**New-邮箱还原请求**cmdlet 将非活动邮箱的内容还原到现有邮箱。 有关使用此 cmdlet 的详细信息，请参阅[新建邮箱还原请求](https://go.microsoft.com/fwlink/?linkid=856298)。
  
1. 创建包含非活动邮箱属性的变量。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在前面的命令中，**使用"可分辨名称"****或"ExchangeGUID"** 属性的值来标识非活动邮箱。 这些属性对于组织中的每个邮箱都是唯一的，而活动邮箱和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 将非活动邮箱的内容还原到现有邮箱。 非活动邮箱（源邮箱）的内容将合并到现有邮箱（目标邮箱）中的相应文件夹中。
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   或者，您可以在目标邮箱中指定一个顶级文件夹，用于从非活动邮箱还原内容。 如果目标邮箱中不存在指定的目标文件夹或目标文件夹结构，则在还原过程中创建该文件夹或目标文件夹结构。 
    
    本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中名为"非活动邮箱"的文件夹。
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a>从非活动邮箱还原存档

如果非活动邮箱具有存档邮箱，也可以将其还原到现有邮箱的存档邮箱。 要从非活动邮箱还原存档，必须将_SourceIsArchive_和_TargetIsAchive_开关添加到用于还原非活动邮箱的命令。 
  
1. 创建包含非活动邮箱属性的变量。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在前面的命令中，**使用"可分辨名称"****或"ExchangeGUID"** 属性的值来标识非活动邮箱。 这些属性对于组织中的每个邮箱都是唯一的，而活动邮箱和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 将存档的内容从非活动邮箱（源存档）还原到现有邮箱（目标存档）的存档。 在此示例中，源存档中的内容将复制到目标邮箱存档中名为"非活动邮箱存档"的文件夹。

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a>詳細資訊

- **恢复和恢复非活动邮箱之间的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上将转换为新邮箱，非活动邮箱的内容和文件夹结构将保留，并且邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在，对新邮箱中的内容所做的任何更改都将影响非活动邮箱中最初处于保留状态的内容。 相反，还原非活动邮箱时，内容只会复制到另一个邮箱。 非活动邮箱将保留，并保留为非活动邮箱。 对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。 仍可以使用安全&合规性中心[中的内容搜索工具](run-a-content-search-in-the-security-and-compliance-center.md)搜索非活动邮箱，其内容可以还原到另一个邮箱，也可以在以后恢复或删除。 
    
- **如何查找非活动邮箱？** 要获取组织中非活动邮箱的列表并显示对还原非活动邮箱有用的信息，可以运行此命令。 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **使用诉讼保留或 Office 365 保留策略保留非活动邮箱内容。** 如果要在还原非活动邮箱后保留其状态，则可以将目标邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)状态，或在还原非活动邮箱之前应用[Office 365 保留策略。](retention-policies.md) 这将阻止在将项目还原到目标邮箱后从非活动邮箱永久删除这些项目。 
    
- **在还原非活动邮箱之前，启用目标邮箱的保留保留。** 由于非活动邮箱中的邮箱项目可能已旧，因此在还原非活动邮箱之前，可以考虑在目标邮箱上启用保留保留。 将邮箱置于保留保留状态时，在删除保留保留或保留期到期之前，不会处理分配给该邮箱的保留策略。 这为目标邮箱的所有者提供了管理来自非活动邮箱的旧邮件的时间。 否则，保留策略可能会删除根据为目标邮箱配置的保留设置过期的旧项目（或将项目移动到存档邮箱（如果已启用）。" 有关详细信息，请参阅在[Exchange 联机中放置保留邮箱。](https://go.microsoft.com/fwlink/?linkid=856300)
    
- **允许传统DN不匹配开关的作用是什么？** 在前面还原非活动邮箱的示例中，**允许旧邮箱不匹配**开关用于允许将非活动邮箱还原到其他目标邮箱。 在典型的还原方案中，目标是还原源邮箱和目标邮箱是同一邮箱的内容。 因此，**默认情况下，New-邮箱还原请求**cmdlet 检查以确保源邮箱和目标邮箱上的**LegacyExchangeDN**属性的值相同。 这有助于防止意外将源邮箱还原到错误的目标邮箱中。 如果尝试还原非活动邮箱而不**使用"允许遗留DN 不匹配"** 开关，则如果源邮箱和目标邮箱具有**旧版ExchangeDN**属性的不同值，则该命令可能会失败。 
    
- **您可以将其他参数与 New-邮箱还原请求 cmdlet 一起实现非活动邮箱的不同还原方案。** 例如，可以运行此命令将存档从非活动邮箱还原到目标邮箱的主邮箱中。 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  还可以通过运行此命令将非活动主邮箱还原到目标邮箱的存档中。

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **目标根文件夹参数的作用是什么？** 如前所述，可以使用**TargetRootFolder**参数在目标邮箱中的文件夹结构（也称为根）顶部指定文件夹，用于还原非活动邮箱的内容。 如果不使用此参数，则非活动邮箱中的邮箱项目将合并到目标邮箱的相应默认文件夹中，并在目标邮箱的根目录中重新创建自定义文件夹。 下图突出显示了不使用和使用**TargetRootFolder**参数之间的这些差异。 
    
    **未使用目标根文件夹参数时的目标邮箱中的文件夹层次结构**
    
    ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **使用目标根文件夹参数时的目标邮箱中的文件夹层次结构**
    
    ![使用 TargetRootFolder 參數時的螢幕擷取畫面](media/300da592-7323-48db-b8a4-07012259d113.png)

  

