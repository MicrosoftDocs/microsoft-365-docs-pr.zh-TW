---
title: 编辑信息障碍策略
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 了解如何编辑或删除信息障碍的策略。
ms.openlocfilehash: 20a1dd62fa80469a7a31db9b5541064ae16b4e02
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076240"
---
# <a name="edit-or-remove-information-barrier-policies"></a>编辑（或删除）信息屏障策略

[定义信息屏障策略](information-barriers-policies.md)后，您可能需要更改这些策略或用户细分，作为[故障排除](information-barriers-troubleshooting.md)的一部分或作为常规维护。 使用本文作为指南。

## <a name="what-do-you-want-to-do"></a>您要執行的工作

|動作  |描述 |
|---------|---------|
|[编辑用户帐户属性](#edit-user-account-attributes)     |在 Azure 活动目录中填充可用于定义段的属性。<br/>当用户未包含在用户应包含的细分中时，编辑用户帐户属性，更改用户位于哪个细分，或使用不同的属性定义细分。         |
|[编辑线段](#edit-a-segment)     |当您希望更改线段的定义方式时，请编辑线段。 <br/>例如，您可能最初*使用"部门"* 定义段，现在想要使用另一个属性，如*成员。*         |
|[编辑策略](#edit-a-policy)     |当您希望更改策略的工作方式时，编辑信息障碍策略。<br/>例如，您可能决定只允许仅在特定段之间发生通信，而不是阻止两个段之间的通信。         |
|[将策略设置为非活动状态](#set-a-policy-to-inactive-status)     |当您要对策略进行更改或不希望策略生效时，将策略设置为非活动状态。         |
|[删除策略](#remove-a-policy)     |当您不再需要特定策略时，请删除信息屏障策略。         |
|[停止策略应用程序](#stop-a-policy-application)     |如果要停止应用信息屏障策略的过程，可以执行此操作。<br/>请注意，停止策略应用程序不是即时的，也不会撤消已应用于用户的策略。         |
|[定义信息障碍的策略](information-barriers-policies.md)     |当您尚未实施此类策略时，请定义信息屏障策略，并且必须限制或限制特定用户组之间的通信。         |
|[排除信息障碍](information-barriers-troubleshooting.md)     |遇到信息障碍的意外问题时，请参阅本文。         |

> [!IMPORTANT]
> 要执行本文中描述的任务，必须为您分配适当的角色，例如：<br/>- 微软365企业全球管理员<br/>- Office 365 全局管理员<br/>- 合规管理员<br/>- IB合规管理（这是一个新角色！<p>要了解有关信息障碍先决条件的详细信息，请参阅[先决条件（有关信息障碍策略）。](information-barriers-policies.md#prerequisites)<p>请确保连接到[Office 365 安全&合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="edit-user-account-attributes"></a>编辑用户帐户属性

使用此过程可以编辑用于分段用户的属性。 

例如，如果您使用的是"部门"属性，并且一个或多个用户帐户当前没有为"部门"列出任何值，则必须编辑这些用户帐户以包括部门信息。 

用户帐户属性用于定义段，以便可以分配信息屏障策略。

1. 要查看特定用户帐户的详细信息（如属性值和分配的段），请使用具有标识参数的**获取信息系统接收状态**cmdlet。 

    |語法  |範例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   您可以使用唯一标识每个用户的任何值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 <p>   （您也可以将此 cmdlet 用于单个用户： `Get-InformationBarrierRecipientStatus -Identity <value>`      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   在此示例中，我们在 Office 365 中提到了两个用户帐户：*梅根*的*meganb*和*Alexw*的*Alexw。*         |

2. 确定要为用户帐户配置文件编辑的属性。 有关详细信息，请参阅[属性信息屏障策略。](information-barriers-attributes.md) 

3. 编辑一个或多个用户帐户以包括您在上一步中选择的属性的值。 为此，请使用以下过程之一：

    - 要编辑单个帐户，请参阅[使用 Azure 活动目录 添加或更新用户的配置文件信息。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

    - 要编辑多个帐户（或使用 PowerShell 编辑单个帐户），请参阅[使用 Office 365 PowerShell 配置用户帐户属性。](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

## <a name="edit-a-segment"></a>编辑线段

使用此过程编辑用户段的定义。 例如，您可以更改段的名称，或用于确定段中包括谁的筛选器。

1. 要查看所有现有段，请使用**获取组织段**cmdlet。
    
    语法：`Get-OrganizationSegment`

    您将看到每个段和详细信息的列表，例如段类型、其 UserGroupFilter 值、创建或上次修改该值的人员、GUID 等。

    > [!TIP]
    > 打印或保存段列表以供以后参考。 例如，如果要编辑段，则需要知道其名称或标识值（这与"标识"参数一起使用）。

2. 要编辑段，请使用具有**标识**参数和相关详细信息**的"设置组织段**cmdlet"。 

    |語法  |範例  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p>在此示例中，对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段，我们将部门名称更新为"HRDept"。         |

完成为组织编辑细分后，可以[定义](information-barriers-policies.md#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息障碍策略。

## <a name="edit-a-policy"></a>编辑策略

1. 要查看当前信息障碍策略的列表，请使用**获取信息障碍策略**cmdlet。

    语法：`Get-InformationBarrierPolicy`

    在结果列表中，标识要更改的策略。 请注意策略的 GUID 和名称。

2. 使用具有**标识**参数**的"设置信息障碍策略**cmdlet"，并指定要进行更改。

    示例：假设定义了策略以阻止*研究*部分与*销售*和*市场营销*部门通信。 该策略是使用此 cmdlet 定义的：`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    假设我们想要更改它，以便*研究*部分的人只能与*HR*部门中的人员进行通信。 要进行此更改，我们使用此 cmdlet：`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    在此示例中，我们将"段阻止"更改为"允许分段"，并指定了*HR*段。

3. 编辑完策略后，请确保应用更改。 （请参阅[应用信息屏障策略。](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="set-a-policy-to-inactive-status"></a>将策略设置为非活动状态

1. 要查看当前信息障碍策略的列表，请使用**获取信息障碍策略**cmdlet。

    语法：`Get-InformationBarrierPolicy`

    在结果列表中，标识要更改（或删除）的策略。 请注意策略的 GUID 和名称。

2. 要将策略的状态设置为非活动状态，请使用具有标识参数和状态参数设置为"非活动"**的"设置信息保护策略**cmdlet"。

    |語法  |範例  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p>在此示例中，我们将 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*设置为非活动状态的信息屏障策略。         |

3. 要应用更改，**请使用"开始信息策略**应用程序"cmdlet。

    语法：`Start-InformationBarrierPoliciesApplication`

    更改将（按用户）应用于您的组织。 如果您的组织很大，则此过程可能需要 24 小时（或更长时间）才能完成。 （作为一般准则，处理 5，000 个用户帐户大约需要一个小时。

此时，一个或多个信息障碍策略设置为非活动状态。 在此处，您可以执行以下任何操作：
- 保持现状（设置为非活动状态的策略对用户没有影响）
- [编辑策略](#edit-a-policy) 
- [删除策略](#remove-a-policy)

## <a name="remove-a-policy"></a>删除策略

1. 要查看当前信息障碍策略的列表，请使用**获取信息障碍策略**cmdlet。

    语法：`Get-InformationBarrierPolicy`

    在结果列表中，标识要删除的策略。 请注意策略的 GUID 和名称。 确保策略设置为非活动状态。

2. 使用具有标识参数**的删除信息策略**cmdlet。

    |語法  |範例  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p>在此示例中，我们将删除具有 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*的策略。          |

    当出现提示时，请确认更改。

3. 对要删除的每个策略重复步骤 1-2。

4. 删除策略完成后，应用更改。 为此，请使用**启动信息策略应用程序**cmdlet。

    语法：`Start-InformationBarrierPoliciesApplication`

    更改将（按用户）应用于您的组织。 如果您的组织很大，则此过程可能需要 24 小时（或更长时间）才能完成。

## <a name="stop-a-policy-application"></a>停止策略应用程序

如果要在开始应用信息障碍策略后，要停止应用这些策略，请使用以下过程。 请记住，该过程大约需要 30-35 分钟。

1. 要查看最新的信息障碍策略应用程序的状态，请使用**获取信息障碍策略应用程序状态**cmdlet。

    语法：`Get-InformationBarrierPoliciesApplicationStatus`

    请注意应用程序的 GUID。

2. 使用具有标识参数的**停止信息策略应用程序**cmdlet。

    |語法  |範例  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p>在此示例中，我们将阻止应用信息屏障策略。         |

## <a name="related-articles"></a>相關文章

[获取信息障碍概述](information-barriers.md)

[定义信息障碍的策略](information-barriers-policies.md)

[了解有关 Microsoft 团队中信息障碍的详细信息](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[信息屏障策略的属性](information-barriers-attributes.md)

[排除信息障碍](information-barriers-troubleshooting.md)
