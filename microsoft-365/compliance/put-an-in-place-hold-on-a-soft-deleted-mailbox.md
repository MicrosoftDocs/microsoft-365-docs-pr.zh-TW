---
title: 在 Exchange 在线中对软删除邮箱进行就地保留
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何为软删除邮箱创建就地保留，使其处于非活动状态并保留其内容。 然后，您可以使用 Microsoft 电子数据展示工具搜索非活动邮箱。
ms.openlocfilehash: ce4121e6187a765b5a9e23d6e6e11d8cc2640161
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077800"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>在 Exchange 在线中对软删除邮箱进行就地保留

了解如何为软删除邮箱创建就地保留，使其处于非活动状态并保留其内容。 然后，您可以使用 Microsoft 电子数据展示工具搜索非活动邮箱。
  
> [!NOTE]
> 我们推迟了在 Exchange 在线中创建新的就地保留（在 Office 365 和 Exchange 在线独立计划中）的截止时间。 但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。 作为使用就地保留的替代方法，您可以在安全&合规中心中使用[电子数据展示案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留策略。](https://go.microsoft.com/fwlink/?linkid=827811) 停用新的就地保留后，您仍可以修改现有的就地保留，并在 Exchange Server 2013 中创建新的就地保留，并且仍支持 Exchange 混合部署。 而且，您仍然可以将邮箱置于诉讼保留状态。 
  
您可能有这样的情况：某人已离开您的组织，其相应的用户帐户和邮箱已被删除。 之后，您意识到邮箱中的信息需要保留。 你能做什么？ 如果已删除的邮箱保留期尚未过期，则可以在已删除的邮箱（称为软删除邮箱）上放置一个就地保留，并将其作为非活动邮箱。 *非活动邮箱*用于在前员工离开您的组织后保留其电子邮件。 非活动邮箱的内容在软删除邮箱处于非活动状态时保留在原位保留期间。 使邮箱处于非活动状态后，可以使用"交换在线"中的就地电子数据展示、安全&合规性中心的内容搜索或 SharePoint 在线中的电子数据展示中心来搜索邮箱。 
  
> [!NOTE]
> 在 Exchange Online 中，软删除邮箱是已删除但可在特定保留期内恢复的邮箱。 Exchange 联机中的软删除邮箱保留期为 30 天。 这意味着可以在删除后的 30 天内恢复（或使邮箱成为非活动邮箱）。 30 天后，软删除邮箱被标记为永久删除，无法恢复或处于非活动状态。 
  
## <a name="before-you-begin"></a>開始之前

- 您必须使用 Windows PowerShell 中的**New-邮箱搜索**cmdlet 将原位保留放在软删除的邮箱上。 不能使用 Exchange 管理中心 （EAC） 或共享点在线中的电子数据展示中心。 
    
- 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 运行以下命令以获取有关组织中软删除邮箱的标识信息。 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 有关非活动邮箱的详细信息，请参阅 Office [365 中非活动邮箱的概述。](inactive-mailboxes-in-office-365.md)
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>在软删除的邮箱上放置就地保留，使其成为非活动邮箱

使用**New-邮箱搜索**cmdlet 将软删除邮箱变为非活动邮箱。 有关详细信息，请参阅[新建邮箱搜索](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。
  
1. 创建包含软删除邮箱属性的变量。 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 在前面的命令中，**使用"可分辨名称"****或"ExchangeGuid"** 属性的值来标识软删除的邮箱。 这些属性对于组织中的每个邮箱都是唯一的，而活动邮箱和软删除邮箱可能具有相同的主 SMTP 地址。 
  
2. 创建就地保留并将其放置在软删除邮箱上。 在此示例中，未指定保留持续时间。 这意味着项目将被无限期保留，或直到从非活动邮箱中删除保留。
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   您还可以在创建就地保留时指定保留持续时间。 本示例在非活动邮箱中保留项目大约 7 年。
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. 几分钟后，运行以下命令之一，以验证软删除邮箱是否为非活动邮箱。
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    或
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>詳細資訊

将软删除邮箱制作为非活动邮箱后，可通过多种方式管理该邮箱。 如需詳細資訊，請參閱：
  
- [變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [復原非使用中的信箱](recover-an-inactive-mailbox.md)
    
- [還原非使用中的信箱](restore-an-inactive-mailbox.md)
    
- [删除非活动邮箱](delete-an-inactive-mailbox.md)（通过拆下保持）
