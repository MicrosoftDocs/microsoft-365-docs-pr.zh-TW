---
title: 如何找出位於 Exchange Online 信箱的保留類型
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
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何标识可放置在 Office 365 邮箱上的不同类型的保留。 这些类型的保留包括诉讼保留、电子数据展示保留和 Office 365 保留策略。 您还可以确定用户是否已被从组织范围的保留策略中排除
ms.openlocfilehash: 47e7ffff1703c0de94f014dc18e249cc9775e3e2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076288"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何找出位於 Exchange Online 信箱的保留類型

本文介绍如何识别放在 Office 365 中的 Exchange 联机邮箱上的保留。

Office 365 提供了多种方法，您的组织可以防止邮箱内容被永久删除。 这使您的组织能够保留内容以满足合规性法规，或在法律和其他类型的调查期间。 下面是 Office 365 中的保留功能（也称为*保留）* 的列表：

- **[诉讼保留](create-a-litigation-hold.md)：** 应用于联机交换中的用户邮箱的保留。

- **[电子数据展示持有](ediscovery-cases.md#step-4-place-content-locations-on-hold)：** 与安全和合规性中心中的电子数据展示案例关联的保留。 电子数据展示保留可应用于用户邮箱和 Office 365 组和 Microsoft 团队的相应邮箱。

- **[就地保持](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 使用 Exchange 管理中心中的 Exchange 管理中心中的"就地"电子数据&保留工具应用于用户邮箱的保留。

- ** [Office 365 保留策略](retention-policies.md)：** 可以配置为在 Exchange 联机用户邮箱中以及 Office 365 组和 Microsoft 团队的相应邮箱中保留（或保留和删除）用户邮箱中的内容。 您还可以创建保留策略以保留存储在用户邮箱中的 Skype 业务对话。

  可以分配给邮箱的 Office 365 保留策略有两种类型。

    - **特定位置保留策略：** 这些是分配给特定用户的内容位置的策略。 您可以使用 Exchange 在线 PowerShell 中的**获取邮箱**cmdlet 获取有关分配给特定邮箱的保留策略的信息。

    - **组织范围的保留策略：** 这些是分配给组织中所有内容位置的策略。 您可以使用 Exchange 在线 PowerShell 中的**获取组织 Config** cmdlet 来获取有关组织范围保留策略的信息。
  有关详细信息，请参阅[Office 365 保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)中的"将保留策略应用于整个组织或特定位置"部分。

- **[Office 365 保留标签：](labels.md)** 如果用户将 Office 365 保留标签（配置为保留内容或保留内容，然后删除内容）*应用于其*邮箱中的任何文件夹或项目，则会在邮箱上放置保留，就像邮箱是置于诉讼保留或分配给 Office 365 保留策略。 有关详细信息，请参阅[保留中的标识邮箱，因为保留标签已应用于本文中的文件夹或项目](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)部分。

要管理保留邮箱，您可能需要标识放置在邮箱上的保留类型，以便可以执行诸如更改保留持续时间、临时或永久删除保留或从 Office 365 保留策略中排除邮箱等任务。 在这些情况下，第一步是标识放置在邮箱上的保留类型。 由于可以将多个保留（和不同类型的保留）放置在单个邮箱上，因此如果要删除或更改保留，必须标识放置在邮箱上的所有保留。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>步骤 1：获取放置在邮箱上的保留的 GUID

您可以在 Exchange 在线 PowerShell 中运行以下两个 cmdlet，以获取放置在邮箱上的保留的 GUID。 获取 GUID 后，可以使用它来标识步骤 2 中的特定保留。 GUID 未识别诉讼保留。 对于邮箱启用或禁用诉讼保留。

- **获取邮箱：** 使用此 cmdlet 可确定是否已为邮箱启用诉讼保留，并获取电子数据展示保留、就地保留和 Office 365 保留策略的 GUID，这些策略专门分配给邮箱。 此 cmdlet 的输出还将指示邮箱是否已显式从组织范围的保留策略中排除。

- **获取组织配置：** 使用此 cmdlet 获取组织范围保留策略的 GUID。

若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

### <a name="get-mailbox"></a>Get-Mailbox

运行以下命令以获取有关应用于邮箱的保留和 Office 365 保留策略的信息。

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值太多，并且并非所有值都显示，则可以运行该`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个 GUID。

下表介绍在运行**Get-Mailbox** cmdlet 时，如何根据*InPlaceHolds*属性中的值识别不同类型的保留。


|保持类型  |範例值  |如何识别保持  |
|---------|---------|---------|
|诉讼保留     |    `True`     |     *当"诉讼保留"* 属性设置为`True`时，将启用邮箱的"诉讼保留"。    |
|电子数据展示保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 属性*包含与安全和合规性中心中的电子数据展示案例关联的任何保留的 GUID。 可以判断这是一个电子数据展示保留，因为 GUID 以`UniH`前缀开头（表示统一保留）。      |
|原有範圍暫止     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*属性包含放置在邮箱上的就地保持的 GUID。 您可以判断这是一个就地保留，因为 GUID 要么不以前缀开头，要么以`cld`前缀开头。     |
|专门应用于邮箱的 Office 365 保留策略     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 GUID。 您可以标识保留策略，因为 GUID 以`mbx`或`skp`前缀开头。 前`skp`缀表示保留策略应用于用户邮箱中的 Skype 业务对话。    |
|从组织范围的 Office 365 保留策略中排除     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果邮箱从组织范围的 Office 365 保留策略中排除，则邮箱从中删除的保留策略的 GUID 将显示在 InPlaceHolds 属性中，并由`-mbx`前缀标识。    |

### <a name="get-organizationconfig"></a>获取组织配置
如果在运行**Get-Mailbox** cmdlet*时，InPlaceHolds*属性为空，则仍有一个或多个组织范围的 Office 365 保留策略应用于邮箱。 在 Exchange 在线 PowerShell 中运行以下命令，以获取组织范围 Office 365 保留策略的 GUID 列表。

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值太多，并且并非所有值都显示，则可以运行该`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个 GUID。

下表描述了不同类型的组织范围保留，以及如何在运行**Get-组织 Config** cmdlet 时根据*InPlaceHolds*属性中包含的 GUID 标识每种类型。


|保持类型  |範例值  |描述  |
|---------|---------|---------|
|Office 365 保留策略应用于 Exchange 邮箱、Exchange 公用文件夹和团队聊天    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   应用于 Exchange 邮箱、Exchange 公用文件夹和 Microsoft 团队中的 1xN 聊天的组织范围保留策略由以`mbx`前缀开头的 GUID 标识。 注意 1xN 聊天存储在各个聊天参与者的邮箱中。      |
|Office 365 保留策略应用于 Office 365 组和 Teams 频道邮件     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    应用于 Office 365 组和 Microsoft 团队中的渠道消息的组织范围保留策略由以`grp`前缀开头的 GUID 标识。 注意通道邮件存储在与 Microsoft 团队关联的组邮箱中。     |

有关应用于 Microsoft 团队的详细信息保留策略，请参阅[保留策略的"](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)团队位置"部分概述 。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留策略的 InPlace 保留值的格式

除了前缀（mbx、skp 或 grp）将 InPlaceHolds 属性中的项标识为 Office 365 保留策略之外，该值还包含一个后缀，用于标识为策略配置的保留操作的类型。 例如，以下示例中以粗体突出显示操作后缀：

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

下表定义了三种可能的保留操作：

|值  |描述  |
|---------|---------|
|**1**     | 指示保留策略配置为删除项目。 策略不保留项目。        |
|**2**    |    指示保留策略配置为保留物料。 保留期到期后，策略不会删除项目。     |
|**3**     |   指示保留策略配置为保留项目，然后在保留期到期后将其删除。      |

有关保留操作的详细信息，请参阅[保留策略概述](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的"保留特定时间段的内容"部分。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>步骤 2：使用 GUID 标识保持

获取应用于邮箱的保留的 GUID 后，下一步是使用该 GUID 标识保留。 以下各节演示如何使用保留 GUID 标识保留的名称（和其他信息）。

### <a name="ediscovery-holds"></a>电子数据展示保留

在安全&合规性中心 PowerShell 中运行以下命令，以标识应用于邮箱的电子数据展示保留。 使用 GUID（不包括 UniH 前缀）执行您在步骤 1 中标识的"电子数据展示"保留。 第一个命令创建一个变量，其中包含有关保留的信息。 此变量用于其他命令。 第二个命令显示保留关联的电子数据展示案例的名称。 第三个命令显示保留的名称和保留应用于的邮箱的列表。

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

要连接到安全&合规性中心 PowerShell，请参阅[连接到安全&合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="in-place-holds"></a>就地保留

在 Exchange 联机 PowerShell 中运行以下命令，以标识应用于邮箱的就地保留。 使用 GUID 进行步骤 1 中标识的就地保持。 该命令显示保留的名称和保留应用于的邮箱的列表。

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
如果就地保留的 GUID 以`cld`前缀开头，请确保在运行上一个命令时包含前缀。

### <a name="office-365-retention-policies"></a>Office 365 保留策略

在"安全&合规性中心 PowerShell 中运行以下命令，以标识应用于邮箱的 Office 365 保留策略（组织范围或特定位置）。 使用您在步骤 1 中标识的 GUID（不包括 mbx、skp 或 grp 前缀或操作后缀）。

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>标识保留邮箱，因为保留标签已应用于文件夹或项目

每当用户应用配置为保留内容或保留内容，然后将内容删除到其邮箱中的任何文件夹或项目时，*符合性标记应用*邮箱属性将设置为**True**。 发生这种情况时，邮箱将被视为处于保留状态，就像邮箱被置于诉讼保留或分配给 Office 365 保留策略一样。 当*符合性标记应用*属性设置为**True**时，可能会出现以下情况：

- 如果邮箱或用户的 Office 365 用户帐户被删除，则邮箱将成为[非活动邮箱](inactive-mailboxes-in-office-365.md)。
- 无法禁用邮箱（主邮箱或存档邮箱（如果已启用）。
- 邮箱中的项目保留时间可能比预期长。 这是因为邮箱处于保留状态，因此不会永久删除（清除）任何项目。

要查看*符合性标记应用*属性的值，在 Exchange 在线 PowerShell 中运行以下命令：

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

有关保留标签的详细信息，请参阅[Office 365 保留标签概述](labels.md)。

## <a name="managing-mailboxes-on-delay-hold"></a>管理延迟保留的邮箱

从邮箱中删除任何类型的保留*后，DelayHold 应用*邮箱属性的值将设置为**True**。 下次托管文件夹助理处理邮箱并检测到保留已被删除时，将发生这种情况。 这称为*延迟保留，* 这意味着实际删除保留将延迟 30 天，以防止数据从邮箱永久删除（清除）。 这使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。 在邮箱上放置延迟保留时，邮箱仍被视为无限期处于保留状态，就像邮箱处于诉讼保留状态一样。 30 天后，延迟保留将过期，Office 365 将自动尝试删除延迟保留（通过将*DelayHold 应用*属性设置为**False），** 以便删除保留。 在"*延迟应用"* 属性为**False**后，在托管文件夹助理下一次处理邮箱时，将清除标记为要删除的项目。

要查看邮箱的*DelayHold 应用*属性的值，在 Exchange 联机 PowerShell 中运行以下命令。

```
Get-Mailbox <username> | FL DelayHoldApplied
```

要在延迟过期之前删除延迟保留，可以在 Exchange 在线 PowerShell 中运行以下命令： 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
您必须在联机交换中分配"法律保留"角色才能*使用"删除延迟应用"* 参数 

要删除非活动邮箱的延迟保留，请运行 Exchange 在线 PowerShell 中的以下命令：

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> 在前面的命令中指定非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。 使用这些值之一有助于防止意外指定错误的邮箱。 

## <a name="next-steps"></a>後續步驟

标识应用于邮箱的保留后，可以执行诸如更改保留持续时间、临时或永久删除保留或从 Office 365 保留策略中排除非活动邮箱等任务。 有关执行与保留相关的任务的详细信息，请参阅以下主题之一：

- 在安全&合规性中心 PowerShell 中[运行"\<设置保留合规性策略 - 添加ExchangeLocationException 用户邮箱>"](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令，以从组织范围的 Office 365 保留策略中排除邮箱。 此命令只能用于*ExchangeLocation*属性的值等于 的`All`保留策略。

- 在 Exchange Online PowerShell 中[运行"设置邮箱 - 排除 FromOrgHolds"\<保留 GUID，不带前缀或后缀>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)命令，以便从组织范围的 Office 365 保留策略中排除非活动邮箱。

- [更改 Office 365 中非活动邮箱的保留持续时间](change-the-hold-duration-for-an-inactive-mailbox.md)

- [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)

- [刪除雲端式信箱中可復原的項目資料夾中的保留項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
