---
title: 定义信息屏障策略
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
description: 了解如何定义 Microsoft 团队中的信息障碍策略。
ms.openlocfilehash: 8ad6dd5e098438de0904fb511c631afbc761ff5b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077136"
---
# <a name="define-policies-for-information-barriers"></a>定义信息障碍的策略

## <a name="overview"></a>概觀

使用信息障碍，您可以定义旨在防止某些用户段相互通信的策略，或允许特定段仅与某些其他段通信。 信息障碍策略可帮助您的组织保持对相关行业标准和法规的合规性，并避免潜在的利益冲突。 要了解更多信息，请参阅[信息障碍](information-barriers.md)。 

本文介绍如何规划、定义、实施和管理信息屏障策略。 涉及几个步骤，工作流分为几个部分。 在开始定义（或编辑）信息障碍策略之前，请确保通读[先决条件](#prerequisites)和整个过程。

> [!TIP]
> 本文包括一个[示例方案和](#example-contosos-departments-segments-and-policies)[可下载的 Excel 工作簿，](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)可帮助您规划和定义信息屏障策略。

## <a name="concepts-of-information-barrier-policies"></a>信息屏障政策的概念

定义信息障碍策略时，您将使用用户帐户属性、细分、"块"和/或"允许"策略以及策略应用程序。

- **用户帐户属性**在 Azure 活动目录（或联机交换）中定义。 这些属性可以包括部门、职务、位置、团队名称和其他作业配置文件详细信息。 

- **段**是使用所选**用户帐户属性**在 Office 365 安全&合规性中心中定义的用户集。 （请参阅[支持的属性列表。](information-barriers-attributes.md) 

- **信息障碍策略**确定通信限制或限制。 定义信息屏障策略时，可以从两种策略中进行选择：
    - "阻止"策略阻止一个段与另一个段通信。
    - "允许"策略允许一个段仅与某些其他段通信。

- **策略应用程序**在定义所有信息障碍策略后完成，并且已准备好在组织中应用它们。

## <a name="the-work-flow-at-a-glance"></a>工作流程一览

|階段    |所涉及的内容  |
|---------|---------|
|[确保满足先决条件](#prerequisites)     |- 验证您是否拥有[所需的许可证和权限](information-barriers.md#required-licenses-and-permissions)<br/>- 验证您的目录是否包含用于分段用户的数据<br/>- 为微软团队启用范围目录搜索<br/>- 确保已打开审核日志记录<br/>- 确保没有 Exchange 通讯簿策略<br/>- 使用电源外壳（提供示例）<br/>- 为微软团队提供管理员同意（包括步骤）          |
|[第 1 部分：组织中的细分用户](#part-1-segment-users)     |- 确定需要哪些策略<br/>- 制作要定义的段列表<br/>- 确定要使用的属性<br/>- 在策略筛选器方面定义细分        |
|[第 2 部分：定义信息屏障策略](#part-2-define-information-barrier-policies)     |- 定义您的策略（尚不适用）<br/>- 从两种选择（块或允许） |
|[第 3 部分：应用信息屏障策略](#part-3-apply-information-barrier-policies)     |- 将策略设置为活动状态<br/>- 运行策略应用程序<br/>- 查看策略状态         |
|（根据需要）[编辑段或策略](information-barriers-edit-segments-policies.md.md)    |- 编辑线段<br/>- 编辑或删除策略<br/>- 重新运行策略应用程序<br/>- 查看策略状态         |
|（根据需要）[故障排除](information-barriers-troubleshooting.md)|- 当事情不按预期工作时采取行动|

## <a name="prerequisites"></a>必要條件

除了[所需的许可证和权限](information-barriers.md#required-licenses-and-permissions)外，请确保满足以下要求： 
     
- **目录数据**。 确保组织的结构反映在目录数据中。 为此，请确保用户帐户属性（如组成员身份、部门名称等）在 Azure 活动目录（或联机交换）中正确填充。 要了解更多信息，请参阅以下资源：
  - [信息屏障策略的属性](information-barriers-attributes.md)
  - [使用 Azure 活动目录添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [使用 Office 365 PowerShell 中設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- **范围目录搜索**。 在定义组织的第一个信息屏障策略之前，必须在 Microsoft [Teams 中启用范围目录搜索。](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search) 在启用范围目录搜索后至少等待 24 小时，然后再设置或定义信息屏障策略。

- **审核日志记录**. 为了查找策略应用程序的状态，必须打开审核日志记录。 我们建议您在开始定义细分或策略之前执行此操作。 要了解更多信息，请参阅[打开或关闭 Office 365 审核日志搜索。](turn-audit-log-search-on-or-off.md)

- **没有通讯簿策略。** 在定义和应用信息障碍策略之前，请确保没有 Exchange 通讯簿策略。 （信息障碍基于通讯簿策略，但这两种策略不可互换。如果确实有此类策略，请确保首先[删除通讯簿策略。](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)

- **电源外壳**. 目前，使用 PowerShell cmdlet 在 Office 365 安全&合规性中心定义和管理信息屏障策略。 尽管本文提供了几个示例，但您需要熟悉 PowerShell cmdlet 和参数。 您还需要 AzureRM 模块。
    - [連接到 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    - [安装 Azure 电源外壳模块](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- **管理员同意微软团队中的信息障碍。** 策略到位后，信息障碍会将不应参与的聊天会话中删除。 这有助于确保您的组织始终遵守策略和法规。 使用以下过程使信息屏障策略在 Microsoft 团队中按预期工作。 

   1. 运行以下 PowerShell cmdlet：

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. 当出现提示时，请使用 Office 365 的工作或学校帐户登录。

   3. 在"**请求的权限"** 对话框中，查看信息，然后选择"**接受"。**

满足所有先决条件后，继续下一节。

> [!TIP]
> 为了帮助您准备计划，本文中包含一个示例方案。 [请参阅 Contoso 的部门、部门和政策](#example-contosos-departments-segments-and-policies)。<p>此外，还提供可下载的 Excel 工作簿，帮助您规划和定义细分和策略（并创建 PowerShell cmdlet）。 [获取工作簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。 

## <a name="part-1-segment-users"></a>第 1 部分：细分用户

在此阶段，您可以确定需要哪些信息屏障策略，列出要定义的段，然后定义细分。

### <a name="determine-what-policies-are-needed"></a>确定需要哪些策略

考虑到法律和行业法规，您的组织中的哪些群体需要信息屏障策略？ 制作一个列表。 是否有任何组应被阻止与其他组通信？ 是否有任何组应允许仅与一个或两个其他组通信？ 考虑您需要的策略，因为策略属于两个组之一：
- "阻止"策略阻止一个组与另一个组通信。
- "允许"策略允许组仅与某些其他特定组通信。

当您拥有组和策略的初始列表时，请继续确定所需的细分。 

### <a name="identify-segments"></a>识别细分市场

除了策略的初始列表之外，还为您的组织列出细分。 将包含在信息屏障策略中的用户应属于一个段，并且任何用户都不应属于两个或多个段。 每个段只能应用一个信息屏障策略。 

确定将用来定义段的组织目录数据中的哪些属性。 *您可以使用"部门、**成员"* 或任何受支持的属性。 请确保为用户选择的属性中具有值。 [有关信息障碍，请参阅支持的属性列表。](information-barriers-attributes.md)

> [!IMPORTANT]
> **在继续下一节之前，请确保目录数据具有可用于定义段 的属性值。** 如果目录数据没有要使用的属性的值，则必须更新用户帐户以包括该信息，然后才能继续设置信息障碍。 要获取有关此的帮助，请参阅以下资源：<br/>- [使用 Office 365 PowerShell 配置用户帐户属性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [使用 Azure 活动目录添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>使用 PowerShell 定义段

定义段不会影响用户;它只是为信息屏障策略的界定和应用提供了舞台。

1. 将"**新组织分段**cmdlet"与用户**组筛选器**参数一起使用，该参数对应于要使用的[属性。](information-barriers-attributes.md)

    |語法   |範例  |
    |---------|---------|
    |`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`     |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>在此示例中，使用*HR*定义名为*HR*的段，这是*部门*属性中的值。 cmdlet 的 **-eq**部分表示"相等"。 （或者，您可以使用 **-ne**表示"不相等"。 请参阅[在段定义中使用"等"和"不等于"。](#using-equals-and-not-equals-in-segment-definitions)        |

    运行每个 cmdlet 后，应看到有关新段的详细信息列表。 详细信息包括段的类型、创建或上次修改该段的人员等。 

2. 对要定义的每个段重复此过程。

    > [!IMPORTANT]
    > **确保您的段不重叠。** 受信息障碍影响的每个用户应属于一个（且只有一个）细分。 任何用户都不应属于两个或多个段。 （请参阅[示例：本文中康托索定义的段。](#contosos-defined-segments)


定义细分后，继续[定义信息屏障策略](#part-2-define-information-barrier-policies)。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>在段定义中使用"等"和"不等于"

在下面的示例中，我们定义一个细分，即"部门等于 HR"。 

|範例  |
|---------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>请注意，在此示例中，段定义包括一个"等"参数，表示为 **-eq**。 
  |

您还可以使用"不等于"参数定义段，表示为 **-ne，** 如下表所示：

|語法  |範例  |
|---------|---------|
|`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`    |`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` <p>在此示例中，我们定义了一*个名为"不销售"* 的细分，该细分包括不在*销售*中的每个人。 cmdlet 的 **-ne**部分表示"不相等"。  |

除了使用"等"或"不等于"定义段外，还可以同时使用"等"和"不等于"参数定义段。

|範例  |
|---------|
|`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"` <p>在此示例中，我们定义了一个名为*LocalFTE*的段，该段包括位于本地且其位置未列为*临时*的人员。    |

> [!TIP]
> 如果可能，请使用包含"-eq"或"-ne"的段定义。 尽量不要定义复杂的段定义。 

## <a name="part-2-define-information-barrier-policies"></a>第 2 部分：定义信息屏障策略

确定是否需要阻止特定段之间的通信，还是将通信限制到某些段。 理想情况下，您将使用最少数量的策略来确保您的组织符合法律和行业要求。

使用要定义的用户细分列表和信息障碍策略，选择方案，然后按照步骤操作。 

- [方案 1：阻止段之间的通信](#scenario-1-block-communications-between-segments)
- [方案 2：允许段仅与另一个段通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **请确保在定义策略时，不会为段分配多个策略。** 例如，如果为名为"*销售"* 的细分市场定义一个策略，则不为*Sales*定义其他策略。<p>此外，在定义信息障碍策略时，请确保将这些策略设置为非活动状态，直到准备好应用它们。 在将策略设置为活动状态然后应用之前，定义（或编辑）策略不会影响用户。

（请参阅本文中[的示例：Contoso 的信息屏障策略。](#contosos-information-barrier-policies)

### <a name="scenario-1-block-communications-between-segments"></a>方案 1：阻止段之间的通信

当您想要阻止段相互通信时，可以定义两个策略：每个方向一个策略。 每个策略仅以单向方式阻止通信。

例如，假设您要阻止段 A 和段 B 之间的通信。在这种情况下，定义一个策略，阻止段 A 与段 B 通信，然后定义第二个策略以防止段 B 与段 A 通信。

1. 要定义第一个阻止策略，请使用**带有"段阻止"** 参数**的新信息阻止策略**cmdlet。 

    |語法  |範例  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`     |`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p>    在此示例中，我们为一个细分市场定义了*名为"销售-研究"* 的策略。 ** 当激活和应用时，此策略会阻止*销售人员**与名为*Research 的细分市场中的人员进行通信。         |

2. 要定义第二个阻塞段，请再次使用**带有"段阻止"** 参数**的新信息策略**cmdlet，这一次段将反转。

    |範例  |
    |---------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p>    在此示例中，我们定义了*名为"研究-销售"* 的策略，以防止*Research*与*销售部*通信。     |

2. 继续以下操作之一：

   - （如果需要）[定义策略以允许段仅与其他段通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - （定义所有策略后）[应用信息屏障策略](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>方案 2：允许段仅与另一个段通信

1. 要允许一个段仅与另一个段通信，请使用**带有"段允许"** 参数**的新信息策略**cmdlet。 

    |語法  |範例  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`     |`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive` <p>    在此示例中，我们为一个*称为"制造"* 的细分市场定义了*名为"制造-HR"* 的策略。 当激活和应用时，此策略允许*制造*人员仅与称为*HR*的细分市场中的人员进行通信。 （在这种情况下，*制造*部门无法与不属于*HR*的用户通信。         |

    **如果需要，可以使用此 cmdlet 指定多个段，如以下示例所示。**

    |語法  |範例  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`     |`New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p>在此示例中，我们定义了一个策略，允许*研究*部门仅与*HR*和*制造*部门进行通信。        |

    对要定义的每个策略重复此步骤，以允许特定段仅与特定特定段通信。

2. 继续以下操作之一：

   - （如果需要）[定义策略以阻止段之间的通信](#scenario-1-block-communications-between-segments) 
   - （定义所有策略后）[应用信息屏障策略](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>第 3 部分：应用信息屏障策略

信息障碍策略在将策略设置为活动状态，然后应用策略之前不会生效。

1. 使用**获取信息障碍策略**cmdlet 查看已定义的策略列表。 请注意每个策略的状态和标识 （GUID）。

    语法：`Get-InformationBarrierPolicy`

2. 要将策略设置为活动状态，请使用具有**标识**参数**的"设置信息策略**cmdlet"和"**状态"** 参数**设置为"活动"。** 

    |語法  |範例  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Active`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p>    在此示例中，我们设置了一个信息屏障策略，该策略将 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*设置为活动状态。   |

    为每个策略根据需要重复此步骤。

3. 完成将信息屏障策略设置为活动状态后，请使用 Office 365 安全&合规性**中心的"启动-信息障碍策略应用程序**cmdlet"。

    语法：`Start-InformationBarrierPoliciesApplication`

    大约半小时后，按用户为您的组织应用策略。 如果您的组织很大，则此过程可能需要 24 小时（或更长时间）才能完成。 （作为一般准则，处理 5，000 个用户帐户大约需要一个小时。

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>查看用户帐户、细分、策略或策略应用程序的状态

使用 PowerShell，您可以查看用户帐户、细分、策略和策略应用程序的状态，如下表中列出的。

|要查看此  |執行  |
|---------|---------|
|使用者帳戶     |使用具有标识参数**的获取信息标识接收状态**cmdlet。 <p>语法：`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>您可以使用唯一标识每个用户的任何值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 <p>範例： `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此示例中，我们在 Office 365 中提到了两个用户帐户：*梅根*的*meganb*和*Alexw*的*Alexw。* <p>（您也可以将此 cmdlet 用于单个用户： `Get-InformationBarrierRecipientStatus -Identity <value>` <p>此 cmdlet 返回有关用户的信息，例如属性值和应用的任何信息屏障策略。|
|段     |使用**获取组织段**cmdlet。<p>语法：`Get-OrganizationSegment` <p>这将显示为您的组织定义的所有细分的列表。         |
|信息屏障策略     |使用**获取信息保护策略**cmdlet。 <p> 语法：`Get-InformationBarrierPolicy` <p>这将显示已定义的信息障碍策略及其状态的列表。       |
|最新的信息屏障策略应用程序     | 使用**获取信息策略应用状态**cmdlet。 <p>语法：`Get-InformationBarrierPoliciesApplicationStatus`<p>    这将显示有关策略应用程序是否已完成、失败或正在进行的信息。       |
|所有信息屏障策略应用程序|使用`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>这将显示有关策略应用程序是否已完成、失败或正在进行的信息。|

## <a name="what-if-i-need-to-remove-or-change-policies"></a>如果我需要删除或更改策略，该怎么办？

资源可帮助您管理信息屏障策略。

- 如果信息障碍出现问题，请参阅[疑难解答信息障碍](information-barriers-troubleshooting.md)。

- 要停止应用策略，请参阅[停止策略应用程序](information-barriers-edit-segments-policies.md.md#stop-a-policy-application)。

- 要删除信息障碍策略，请参阅[删除策略](information-barriers-edit-segments-policies.md.md#remove-a-policy)。

- 要更改细分或策略，请参阅[编辑（或删除）信息障碍策略](information-barriers-edit-segments-policies.md.md)。

## <a name="example-contosos-departments-segments-and-policies"></a>示例：Contoso 的部门、部门和政策

要查看组织如何定义细分和策略，请考虑以下示例。

### <a name="contosos-departments-and-plan"></a>康托索的部门和计划

Contoso 有五个部门：人力资源、销售、营销、研究和制造。 为了保持行业法规，某些部门的人不应与其他部门沟通，如下表所列：

|段  |可以交谈  |无法与  |
|---------|---------|---------|
|人力资源     |所有人         |（没有限制）         |
|销售     |人力资源、市场营销、制造         |參考資料         |
|营销     |所有人         |（没有限制）         |
|參考資料     |人力资源、市场营销、制造        |销售     |
|製造 |人力资源，市场营销 |人力资源或市场营销以外的任何人 |

考虑到这一点，Contoso 的计划包括三个信息屏障策略：

1. 旨在防止销售人员与研究部通信的策略（以及阻止研究与销售人员沟通的另一项策略）
2. 旨在允许制造部门仅与人力资源和营销部门沟通的策略 

无需为人力资源或市场营销制定政策。

### <a name="contosos-defined-segments"></a>康托索定义的段

Contoso 将使用 Azure 活动目录中的"部门"属性来定义段，如下所示：

|部門  |段定义  |
|---------|---------|
|人力资源     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|销售     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|营销     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|參考資料     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|製造     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

定义段后，Contoso 继续定义策略。 

### <a name="contosos-information-barrier-policies"></a>康托索的信息屏障政策

Contoso 定义了三个策略，如下表所述：

|原則  |原則定義  |
|---------|---------|
|政策 1：防止销售人员与研究部沟通     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 在此示例中，信息障碍策略*称为"销售研究"。* 当此策略处于活动状态并应用时，它有助于防止处于"销售"细分的用户与"研究"部分中的用户通信。 这是一个单向策略;这不会阻止 Research 与销售人员沟通。 为此，需要政策 2。      |
|政策 2：阻止研究与销售人员沟通     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 在此示例中，信息障碍策略*称为"研究-销售"。* 当此策略处于活动状态并应用时，它有助于防止"研究"部分中的用户与"销售"段中的用户通信。       |
|政策 3：允许制造部门仅与人力资源和营销部门沟通     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p>在这种情况下，信息屏障策略称为*制造-人力资源营销*。 当此策略处于活动状态并应用时，制造部门只能与人力资源和市场营销部门进行沟通。 请注意，人力资源和营销部不受与其他细分市场沟通的限制。 |

在定义段和策略后，Contoso 通过**运行"开始信息策略应用程序**cmdlet"来应用策略。 

完成后，Contoso 符合法律和行业要求。

## <a name="related-articles"></a>相關文章

- [获取信息障碍概述](information-barriers.md)

- [微软团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
