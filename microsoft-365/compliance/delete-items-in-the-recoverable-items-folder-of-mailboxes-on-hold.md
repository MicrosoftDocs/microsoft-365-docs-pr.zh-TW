---
title: 删除基于云的邮箱的"可恢复项目"文件夹中的项目保留 - 管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 对于管理员：删除 Exchange 联机邮箱的用户可恢复项目文件夹中的项目，即使该邮箱处于合法保留状态也是如此。 这是删除意外泄漏到 Office 365 的数据的有效方法。
ms.openlocfilehash: 9da469af900c2610762338029aa80d31c7f10363
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070732"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>删除基于云的邮箱的"可恢复项目"文件夹中的项目保留 - 管理员帮助

Exchange Online 邮箱的可恢复项目文件夹存在，以防止意外或恶意删除。 它还用于存储由 Office 365 合规性功能（如保留和电子数据展示搜索）保留和访问的项目。 但是，在某些情况下，组织可能无意中保留在必须删除的"可恢复项目"文件夹中的数据。 例如，用户可能在不知不觉中发送或转发包含敏感信息或可能造成严重业务后果的信息的电子邮件。 即使邮件被永久删除，也可能无限期地保留它，因为邮箱上已放置了法律保留。 此方案称为数据溢出，因为数据被无意中溢出到 Office 365。 在这些情况下，您可以删除 Exchange Online 邮箱的用户"可恢复项目"文件夹中的项目，即使该邮箱在 Office 365 中具有不同的保留功能之一置于保留状态。 这些类型的保留包括诉讼保留、就地保留、电子数据展示保留，以及 Office 365 保留策略，这些策略是在 Office 365 或 Microsoft 365 中的安全和合规性中心创建的 Office 365 保留策略。
  
 本文介绍如何从处于保留状态的基于云的邮箱的"可恢复项目"文件夹中删除项目。 此过程包括禁用对邮箱的访问和禁用单个项目恢复、禁用托管文件夹助理处理邮箱、临时删除保留、从"可恢复项目"文件夹中删除项目，然后恢复邮箱到其以前的配置。 过程是： 
  
[第 1 步：收集有关邮箱的信息](#step-1-collect-information-about-the-mailbox)

[第 2 步：准备邮箱](#step-2-prepare-the-mailbox)

[步骤 3：从邮箱中删除所有保留](#step-3-remove-all-holds-from-the-mailbox)

[步骤 4：从邮箱中删除延迟保留](#step-4-remove-the-delay-hold-from-the-mailbox)

[步骤 5：删除"可恢复项目"文件夹中的项目](#step-5-delete-items-in-the-recoverable-items-folder)

[步骤 6：将邮箱还原到其以前的状态](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 本文中概述的过程将导致数据从 Exchange 联机邮箱永久删除（清除）。 这意味着无法恢复从"可恢复项目"文件夹中删除的邮件，并且无法用于法律发现或其他合规性目的。 如果要从作为诉讼保留、就地保留、电子数据展示保留或在安全和合规性中心创建的 Office 365 保留策略的一部分而从保留的邮箱中删除邮件，请咨询您的记录管理或法律部门在拆下保持。 您的组织可能具有一个策略，用于定义邮箱处于保留状态还是数据溢出事件是否具有优先级。 
  
## <a name="before-you-begin"></a>開始之前

- 您必须在 Exchange Online 中分配以下两个管理角色，以便从步骤 5 中的"可恢复项目"文件夹中搜索和删除邮件。
    
  - **邮箱搜索**- 此角色允许您搜索组织中的邮箱。 默认情况下，Exchange 管理员不会分配此角色。 要分配此角色，请将自己添加为 Exchange 联机中的发现管理角色组的成员。 
    
  - **邮箱导入导出**- 此角色允许您从用户的邮箱中删除邮件。 默认情况下，此角色不会分配给任何角色组。 要从用户的邮箱中删除邮件，可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 
    
- 对于非活动邮箱，不支持本文中描述的过程。 这是因为在删除非活动邮箱后，无法将保留（或 Office 365 保留策略）重新应用于该邮箱。 从非活动邮箱中删除保留时，该保留将更改为正常的软删除邮箱，并在托管文件夹助理处理后从组织永久删除。
    
- 对于已分配给已锁定使用保留锁的 Office 365 保留策略的邮箱，无法执行此过程。 这是因为保留锁阻止您从 Office 365 保留策略中删除或删除邮箱，以及禁用邮箱上的托管文件夹助手。 有关锁定保留策略的详细信息，请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。
    
- 如果邮箱未置于保留状态（或未启用单个项目恢复），则只需从"可恢复项目"文件夹中删除这些项目即可。 有关如何执行此操作的详细信息，请参阅[搜索和删除邮件](https://go.microsoft.com/fwlink/?linkid=852453)。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>第 1 步：收集有关邮箱的信息

第一步是从目标邮箱收集将影响此过程的选定属性。 请务必记下这些设置或将其保存到文本文件中，因为您将更改其中一些属性，然后在从"可恢复项目"文件夹中删除项目后恢复为步骤 6 中的原始值。 下面是需要收集的邮箱属性的列表。
  
-  *单项恢复启用*和*保留删除项为*.如有必要，您将禁用单个恢复，并延长步骤 3 中已删除的项目保留期。 
    
-  *诉讼保留*和*原位保留;* 您需要标识放置在邮箱上的所有保留，以便在步骤 3 中暂时删除它们。 有关如何标识可能放置在邮箱上的类型保留的提示，[请参阅"详细信息"](#more-information)部分。 
    
此外，您需要获取邮箱客户端访问设置，以便可以暂时禁用这些设置，以便所有者（或其他用户）无法在此过程中访问邮箱。 最后，您可以在"可恢复项目"文件夹中获取当前大小和项目数。 删除步骤 5 中的"可恢复项目"文件夹中的项目后，将使用此信息来验证项目是否实际已删除。
  
1. [連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。 请确保对在 Exchange 联机中分配了相应管理角色的管理员帐户使用用户名和密码。 
    
2. 运行以下命令以获取有关单个项目恢复和已删除项目保留期的信息。

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   如果启用了单个项目恢复，您必须在步骤 2 中禁用它。 如果已删除的项目保留期未设置为 30 天（Exchange Online 中的最大值），则可以在步骤 2 中增加该期限。 
    
3. 运行以下命令以获取邮箱的邮箱访问设置。 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   您将在步骤 2 中禁用所有这些访问方法。
    
4. 运行以下命令以获取有关应用于邮箱的保留和 Office 365 保留策略的信息。
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > 如果*InPlaceHolds*属性中的值太多，并且并非所有值都显示，则可以运行该`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个值。 
  
5. 运行以下命令以获取有关任何组织范围的 Office 365 保留策略的信息。 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   如果您的组织具有任何组织范围的 Office 365 保留策略，则必须从步骤 3 中的这些策略中排除邮箱。

   > [!TIP]
    > 如果*InPlaceHolds*属性中的值太多，并且并非所有值都显示，则可以运行该`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个值。 
  
6. 运行以下命令以获取用户主邮箱中可恢复项目文件夹中的文件夹和子文件夹中的当前大小和项目总数。 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   如果启用了用户的存档邮箱，则运行以下命令以获取其存档邮箱中的可恢复项目文件夹中文件夹和子文件夹中的项目大小和总数。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   删除步骤 5 中的项目时，可以选择删除或不删除用户主存档邮箱中的"可恢复项目"文件夹中的项目。 请注意，如果为邮箱启用了自动展开存档，则不会删除辅助存档邮箱中的项目。
  
## <a name="step-2-prepare-the-mailbox"></a>第 2 步：准备邮箱

收集和保存有关邮箱的信息后，下一步是通过执行以下任务来准备邮箱： 
  
- **禁用客户端对邮箱的访问，** 以便邮箱所有者无法访问其邮箱，并在此过程期间对邮箱数据进行任何更改。 
    
- **将已删除的项目保留期增加到**30 天（Exchange Online 中的最大值），以便在步骤 5 中删除项目之前，不会从"可恢复项目"文件夹中清除这些项目。 
    
- **禁用单个项目恢复，** 以便在从步骤 5 中的"可恢复项目"文件夹中删除项目后，不会保留项目（在已删除项目保留期的持续时间内）。 
    
- **禁用托管文件夹助手，** 使其不处理邮箱并保留您在步骤 5 中删除的项目。 
    
在 Exchange 在线电源外壳中执行以下步骤。
  
1. 运行以下命令以禁用对邮箱的所有客户端访问。 命令语法假定邮箱上启用了所有客户端访问方法。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > 最多可能需要 60 分钟才能禁用对邮箱的所有客户端访问方法。 请注意，禁用这些访问方法不会断开他们当前登录的邮箱所有者的连接。 如果所有者未登录，则禁用这些访问方法后，他们将无法访问其邮箱。 
  
2. 运行以下命令，将已删除的项目保留期最多增加 30 天。 这假定当前设置小于 30 天。 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 运行以下命令以禁用单个项目恢复。
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 禁用单个项目恢复可能需要长达 60 分钟。 在此时间段过后，不要删除"可恢复项目"文件夹中的项目。 
  
4. 运行以下命令以防止托管文件夹助理处理邮箱。 如前所述，仅当具有保留锁的 Office 365 保留策略未应用于邮箱时，才能禁用托管文件夹助手。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>步骤 3：从邮箱中删除所有保留

从"可恢复项目"文件夹中删除项目的最后一步是删除放置在邮箱上的所有保留（您在步骤 1 中标识）。 必须删除所有保留，以便在从"可恢复项目"文件夹中删除项目后，不会保留这些项目。 以下部分包含有关删除邮箱上的不同类型的保留的信息。 有关如何标识可能放置在邮箱上的类型保留的提示，[请参阅"详细信息"](#more-information)部分。 有关详细信息，请参阅[如何识别在 Exchange 联机邮箱上放置的保留类型。](identify-a-hold-on-an-exchange-online-mailbox.md)
  
> [!CAUTION]
> 如前所述，在从邮箱中删除保留之前，请咨询您的记录管理或法律部门。 
  
 ### <a name="litigation-hold"></a>诉讼保留
  
在 Exchange 联机 PowerShell 中运行以下命令，从邮箱中删除诉讼保留。

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> 与禁用客户端访问方法和单个项目恢复类似，删除诉讼保留可能需要长达 60 分钟。 在此时间段过后，不要从"可恢复项目"文件夹中删除项目。 
  
 ### <a name="in-place-hold"></a>原有範圍暫止
  
在 Exchange 联机 PowerShell 中运行以下命令，以标识放置在邮箱上的就地保持。 使用 GUID 进行步骤 1 中标识的就地保持。 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
识别就地保留后，可以使用 Exchange 管理中心 （EAC） 或 Exchange 在线 PowerShell 从保留中删除邮箱。 有关详细信息，请参阅[创建或删除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>应用于特定邮箱的 Office 365 保留策略
  
[在"安全&合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以标识应用于邮箱的 Office 365 保留策略。 对步骤 1 中标识的`mbx`保留`skp`策略使用 GUID（不包括 或前缀）。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
确定保留策略后，转到安全&合规中心**中的"日期治理**\>**保留"** 页，编辑您在上一步中标识的保留策略，并从保留策略中包含的收件人。 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>组织范围的 Office 365 保留策略
  
组织范围和 Exchange 范围的 Office 365 保留策略应用于组织中的每个邮箱。 它们在组织级别（而不是邮箱级别）应用，并在步骤 1 中运行**Get-组织 Config** cmdlet 时返回。 在[安全&合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以标识组织范围的 Office 365 保留策略。 对步骤 1 中标识的组织`mbx`范围保留策略使用 GUID（不包括前缀）。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

确定组织范围的 Office 365 保留策略后，请转到安全&合规性中心**中的"日期治理**\>**保留"** 页，编辑您在上一步，并将邮箱添加到排除的收件人列表中。 这样做会从保留策略中删除用户的邮箱。 

### <a name="office-365-retention-labels"></a>Office 365 保留標籤

每当用户应用配置为保留内容或保留内容，然后将内容删除到其邮箱中的任何文件夹或项目时，*符合性标记应用*邮箱属性将设置为**True**。 发生这种情况时，邮箱将被视为处于保留状态，就像将其置于诉讼保留或分配给 Office 365 保留策略一样。

要查看*符合性标记应用*属性的值，在 Exchange 在线 PowerShell 中运行以下命令：

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

确定邮箱因保留标签应用于文件夹或项目而处于保留状态后，可以使用安全和合规性中心中的内容搜索工具使用"合规性标记"搜索条件搜索标记的项目。 有关详细信息，请参阅关键字查询中的"搜索条件"部分[和内容搜索的搜索条件。](keyword-queries-and-search-conditions.md#conditions-for-common-properties)

有关标签的详细信息，请参阅[Office 365 标签概述](labels.md)。

 ### <a name="ediscovery-case-holds"></a>电子数据展示案例保留
  
[在"安全&合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以标识与应用于邮箱的电子数据展示案例关联的保留。 使用 GUID（不包括`UniH`前缀）执行您在步骤 1 中标识的"电子数据展示"保留。 请注意，第二个命令显示保留关联的电子数据展示案例的名称;第二个命令显示保留与保存关联的案例的名称。第三个命令显示保留的名称。 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

确定电子数据展示案例的名称和保留后，转到合规性中心**中的电子数据展示**\>**电子数据展示**页面，打开案例，然后从保留中删除邮箱。 有关详细信息，请参阅[电子数据展示案例](ediscovery-cases.md)。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>步骤 4：从邮箱中删除延迟保留

从邮箱中删除任何类型的保留*后，DelayHold 应用*邮箱属性的值将设置为**True**。 下次托管文件夹助理处理邮箱并检测到保留已被删除时，将发生这种情况。 这称为*延迟保留，* 这意味着实际删除保留将延迟 30 天，以防止数据从邮箱永久删除。 （延迟保留的目的是让管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。 在邮箱上放置延迟保留时，邮箱仍被视为无限期处于保留状态，就像邮箱处于诉讼保留状态一样。 30 天后，延迟保留将过期，Office 365 将自动尝试删除延迟保留（通过将*DelayHold 应用*属性设置为**False），** 以便实际删除保留。 

在删除步骤 5 中的项目之前，必须从邮箱中删除延迟保留。 首先，通过在 Exchange 在线 PowerShell 中运行以下命令，确定是否将延迟保留应用于邮箱：

```
Get-Mailbox <username> | FL DelayHoldApplied
```

如果*DelayHold 应用*属性的值设置为**False，** 则邮箱上尚未放置延迟保留。 您可以转到步骤 5 并删除"可恢复项目"文件夹中的项目。

如果*DelayHold 应用*属性的值设置为**True，** 则运行以下命令以删除延迟保留：

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
请注意，您必须在"联机交换"中分配"法律保留"角色才能*使用"删除延迟应用"* 参数。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>步骤 5：删除"可恢复项目"文件夹中的项目

现在，您可以使用 Exchange 在线 PowerShell 中的[搜索邮箱](https://go.microsoft.com/fwlink/?linkid=852595)cmdlet 实际删除"可恢复项目"文件夹中的项目。 运行**搜索邮箱**cmdlet 时，有三个选项。 
  
- 在删除项目之前，将项目复制到目标邮箱，以便在必要时在删除项目之前查看这些项目。
    
- 将项目复制到目标邮箱，并在同一命令中删除它们。
    
- 删除项目而不将其复制到目标邮箱。 
    
请注意，在运行**搜索邮箱**cmdlet 时，用户主存档邮箱中的"可恢复项目"文件夹中的项目也将被删除。 为了防止这种情况，您可以*包括"不包含存档"* 开关。 如前所述，如果为邮箱启用了自动展开存档，则 [搜索邮箱 ] cmdlet 不会删除辅助存档邮箱中的项目。 有关自动扩展存档的详细信息，请参阅 Office [365 中无限制存档概述。](unlimited-archiving.md)
  
> [!NOTE]
> 如果包含搜索查询（通过使用*搜索查询*参数），**搜索邮箱**cmdlet 将在搜索结果中返回最多 10，000 个项目。 因此，如果包含搜索查询，则可能需要多次运行**搜索邮箱**命令才能删除 10，000 多个项目。 
  
以下示例显示了每个选项的命令语法。 这些示例使用`-SearchQuery size>0`参数值，该值从"可恢复项目"文件夹中的所有子文件夹中删除所有项目。 如果只需要删除符合特定条件的项目，还可以使用*SearchQuery*参数指定其他条件，例如邮件的主题或日期范围。 请参阅下面的[使用搜索查询参数的其他示例。](#other-examples-of-using-the-searchquery-parameter) 
  
### <a name="example-1"></a>範例 1

本示例将用户可恢复项目文件夹中的所有项目复制到组织的发现搜索邮箱中的文件夹。 这允许您在永久删除项目之前查看它们。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

在前面的示例中，不需要将项目复制到发现搜索邮箱。 您可以将邮件复制到任何目标邮箱。 但是，为了防止访问可能敏感的邮箱数据，我们建议将邮件复制到访问仅限于授权人员的邮箱。 默认情况下，对默认发现搜索邮箱的访问仅限于 Exchange 联机中的发现管理角色组的成员。 
  
### <a name="example-2"></a>範例 2

本示例将用户"可恢复项目"文件夹中的所有项目复制到组织的"发现搜索邮箱"中的文件夹，然后从用户的"可恢复项目"文件夹中删除这些项目。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>範例 3

本示例删除用户可恢复项目文件夹中的所有项目，而不将它们复制到目标邮箱。 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>使用搜索查询参数的其他示例

下面是使用*SearchQuery*参数查找特定消息的几个示例。 如果使用*SearchQuery*参数搜索特定项目，请考虑将搜索结果复制到目标邮箱，以便可以查看搜索结果，然后在必要时修改查询，然后再删除搜索结果。 
  
此示例返回在"主题"字段中包含特定短语的消息。
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

此示例返回在指定日期范围内发送的消息。
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
此示例返回发送给指定人员的消息。

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>验证项目是否已删除

要验证是否已成功从邮箱的"可恢复项目"文件夹中删除项目，请使用 Exchange 在线 PowerShell 中的**获取邮箱文件夹统计**cmdlet 来检查可恢复项目文件夹中的项目大小和数量。 您可以将这些统计信息与步骤 1 中收集的统计信息进行比较。 
  
运行以下命令以获取用户主邮箱中可恢复项目文件夹中的文件夹和子文件夹中的当前大小和项目总数。 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
运行以下命令以获取用户存档邮箱中可恢复项目文件夹中文件夹和子文件夹中的项目大小和总数。 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>步骤 6：将邮箱还原到其以前的状态

最后一步是将邮箱还原回其以前的配置。 这意味着重置您在步骤 2 中更改的属性，并重新应用在步骤 3 中删除的保留。 其中包括：
  
- 将已删除的物料保留期更改回其以前的值。 或者，您可以只保留此集为 30 天，这是 Exchange 在线中的最大值。
    
- 重新启用单个项目恢复。
    
- 重新启用客户端访问方法，以便所有者可以访问其邮箱。
    
- 重新应用已删除的保留和 Office 365 保留策略。
    
- 重新启用托管文件夹助理以处理邮箱。
    
> [!IMPORTANT]
> 我们建议您在重新应用保留或 Office 365 保留策略（并验证其是否就位）后等待 24 小时，然后再重新启用托管文件夹助理以处理邮箱。 
  
在 Exchange 在线电源外壳中执行以下步骤（按指定顺序）。
  
1. 运行以下命令，将已删除的物料保留期更改回其原始值。 这假定以前的设置小于 30 天;如果此设置小于 30 天，则为例如14天。 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. 运行以下命令以重新启用单个项目恢复。
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 运行以下命令以重新启用邮箱中的所有客户端访问方法。
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. 重新应用您在步骤 3 中删除的保留。 根据保留的类型，使用以下过程之一。
    
    **诉讼保留**
    
    运行以下命令以重新启用邮箱的诉讼保留。
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **原有範圍暫止**
    
    使用 EAC（或交换在线电源外壳）将邮箱添加回就地保留。 
    
    **应用于特定邮箱的 Office 365 保留策略**
    
    使用安全&合规性中心将邮箱添加回保留策略。 转到安全&合规性中心**中的"日期治理**\>**保留"** 页，编辑保留策略，并将邮箱重新添加到应用保留策略的收件人列表中。 
    
    **组织范围的 Office 365 保留策略**
    
    如果通过从策略中排除而删除了组织范围或 Exchange 范围的保留策略，则使用安全&合规性中心从排除的用户列表中删除邮箱。 转到安全&合规性中心**中的"日期治理**\>**保留"** 页，编辑组织范围的保留策略，并从排除的收件人列表中删除邮箱。 这样做会将保留策略重新应用于用户的邮箱。 
    
    **电子数据展示案例保留**
    
    使用安全&合规性中心将邮箱添加回与电子数据展示案例关联的保留状态。 转到**电子数据展示**\>**页面，** 打开案例，并将邮箱添加回保留状态。 
    
5. 运行以下命令以允许托管文件夹助理再次处理邮箱。 如前所述，我们建议您在重新应用保留或 Office 365 保留策略（并验证其是否就位）后等待 24 小时，然后再重新启用托管文件夹助理。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. 要验证邮箱是否已还原到以前的配置，可以运行以下命令，然后将这些设置与步骤 1 中收集的设置进行比较。

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>詳細資訊

下表描述了在运行**获取邮箱**或**获取组织 Config** cmdlet 时，如何根据*InPlaceHolds*属性中的值识别不同类型的保留。 有关详细信息，请参阅[如何识别放在 Exchange 联机邮箱上的保留类型。](identify-a-hold-on-an-exchange-online-mailbox.md)

如前所述，您必须从邮箱中删除所有保留和 Office 365 保留策略，然后才能成功删除"可恢复项目"文件夹中的项目。 
  
|**保持类型**|**範例值**|**如何识别保持**|
|:-----|:-----|:-----|
|诉讼保留  <br/> | `True` <br/> |*诉讼保留属性*设置为`True`。  <br/> |
|原有範圍暫止  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*属性包含放置在邮箱上的就地保持的 GUID。 您可以判断这是就地保留，因为 GUID 不以前缀开头。  <br/> 您可以使用 Exchange`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`联机 PowerShell 中的命令来获取有关邮箱就地保留的信息。  <br/> |
| 安全&合规性中心的 Office 365 保留策略应用于特定邮箱  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 或  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |运行**获取邮箱**cmdlet 时，InPlaceHolds 属性还包含应用于邮箱的 Office 365 保留策略的 GUID。 ** 您可以标识保留策略，因为 GUID 以`mbx`前缀开头。 请注意，如果保留策略的 GUID 以`skp`前缀开头，则表示保留策略应用于 Skype 业务对话。  <br/> 要标识应用于邮箱的 Office 365 保留策略，在安全&合规性中心 PowerShell 中运行以下命令： <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>运行此命令时，`mbx`请确保`skp`删除 或 前缀。  <br/> |
|安全&合规性中心中的组织范围 Office 365 保留策略  <br/> |无值  <br/> 或  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`（指示邮箱从组织范围的策略中排除）  <br/> |即使运行**Get-Mailbox** cmdlet 时*InPlaceHolds*属性为空，仍可能将一个或多个组织范围的 Office 365 保留策略应用于邮箱。  <br/> 为了验证这一点，您可以在`Get-OrganizationConfig | FL InPlaceHolds`Exchange Online PowerShell 中运行该命令，以获取组织范围 Office 365 保留策略的 GUID 列表。 应用于 Exchange 邮箱的组织范围保留策略的 GUID 以`mbx`前缀开头;例如`mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> 要标识应用于邮箱的组织范围 Office 365 保留策略，在"安全&合规性中心 PowerShell 中运行以下命令： <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>请注意，如果邮箱从组织范围的 Office 365 保留策略中排除，则在运行**Get-邮箱**cmdlet 时，保留策略的 GUID 将显示在用户邮箱的 InPlaceHolds 属性中;如果邮箱从组织范围的 Office 365 保留策略中排除，则保留策略的 GUID 将显示在用户邮箱的*InPlaceHolds*属性中。由前缀`-mbx`标识;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|安全&合规中心持有电子数据展示案例  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*属性还包含与可能放置在邮箱的安全&合规性中心中电子数据展示案例关联的任何保留的 GUID。 可以判断这是一个电子数据展示案例保留，因为 GUID 以`UniH`前缀开头。  <br/> 您可以使用安全&合规性`Get-CaseHoldPolicy`中心 PowerShell 中的 cmdlet 来获取有关邮箱保留关联的电子数据展示案例的信息。 例如，可以运行该命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`来显示邮箱上的案例保留的名称。 运行此命令时，`UniH`请确保删除前缀。  <br/><br/> 要标识邮箱上的保留与之关联的电子数据展示案例，应运行以下命令：<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


