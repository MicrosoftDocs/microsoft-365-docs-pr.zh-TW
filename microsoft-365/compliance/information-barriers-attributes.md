---
title: 信息屏障策略的属性
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
description: 使用本文作为可用于信息屏障策略的各种属性的参考。
ms.openlocfilehash: 4198728d412062edced6238604b2b891da22aeac
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077135"
---
# <a name="attributes-for-information-barrier-policies"></a>信息屏障策略的属性

Azure 活动目录中的某些属性可用于对用户进行分段。 定义段后，这些段可用作信息屏障策略的筛选器。 例如，**您可以使用"部门"** 按组织内部门定义用户细分（假设没有一名员工同时为两个部门工作）。 

本文介绍如何使用具有信息障碍的属性，并提供可以使用的属性列表。 要了解有关信息障碍的详细信息，请参阅以下资源：
- [信息障碍](information-barriers.md)
- [定义 Microsoft 团队中信息障碍的策略](information-barriers-policies.md)
- [编辑（或删除）信息屏障策略](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>如何在信息屏障策略中使用属性

本文中列出的属性可用于定义或编辑用户段。 在[信息屏障策略](information-barriers-policies.md)中，定义的段用作参数（称为*UserGroupFilter*值）。

1. 确定要用于定义段的属性。 （请参阅本文中的[参考](#reference)部分。

2. 确保用户帐户已为您在步骤 1 中选择的属性填充了值。 查看用户帐户详细信息，如有必要，编辑用户帐户以包括属性值。 

    - 要编辑多个帐户（或使用 PowerShell 编辑单个帐户），请参阅[使用 Office 365 PowerShell 配置用户帐户属性。](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

    - 要编辑单个帐户，请参阅[使用 Azure 活动目录 添加或更新用户的配置文件信息。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

3. [使用 PowerShell 定义段，](information-barriers-policies.md#define-segments-using-powershell)类似于以下示例：

    |範例  |Cmdlet  |
    |---------|---------|
    |使用"部门"属性定义称为"段 1"的段     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |使用成员Of属性定义称为段A的段（假设此属性包含组名称，如"BlueGroup"）     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |使用扩展属性1 定义名为 DayTrader 的段（假设此属性包含作业标题，如"DayTrader"）|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > 定义线段时，对所有线段使用相同的属性。 例如，*如果使用"部门"* 定义某些细分，则*使用"部门"* 定义所有段。 不要*使用"部门"* 定义某些细分，*使用"成员"* 定义其他细分。 确保您的细分不重叠;每个用户应分配给一个段。 

## <a name="reference"></a>參考

下表列出了可用于信息障碍的属性。

|Azure 活动目录属性名称<br/>（LDAP 显示名称）  |交换属性名称  |
|---------|---------|
|Co       | Co        |
|Company     |Company         |
|部門     |部門         |
|扩展属性1 |自定义属性1  |
|扩展属性2 |自定义属性2  |
|扩展属性3 |自定义属性3  |
|扩展属性4 |自定义属性4  |
|扩展属性5 |自定义属性5  |
|扩展属性6 |自定义属性6  |
|扩展属性7 |自定义属性7  |
|扩展属性8 |自定义属性8  |
|扩展属性9 |自定义属性9  |
|扩展属性10 |自定义属性10  |
|扩展属性11 |自定义属性11  |
|扩展属性12 |自定义属性12  |
|扩展属性13 |自定义属性13  |
|扩展属性14 |自定义属性14  |
|扩展属性15 |自定义属性15  |
|MSExch扩展自定义属性1 |扩展自定义属性1 |
|MSExch扩展自定义属性2 |扩展自定义属性2 |
|MSExch扩展自定义属性3 |扩展自定义属性3 |
|MSExch 扩展自定义属性4 |扩展自定义属性4 |
|MSExch扩展自定义属性5 |扩展自定义属性5 |
|邮件昵称 |別名 |
|物理交付办公室名称 |Office |
|PostalCode |PostalCode |
|代理地址 |电子邮件地址 |
|StreetAddress |StreetAddress |
|目标地址 |外部电子邮件地址 |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|郵件   |窗口电子邮件地址    |
|描述    |描述    |
|成员   |小组成员  |

## <a name="related-topics"></a>相關主題

[定义 Microsoft 团队中信息障碍的策略](information-barriers-policies.md)

[排除信息障碍](information-barriers-troubleshooting.md)

[信息障碍](information-barriers.md)



