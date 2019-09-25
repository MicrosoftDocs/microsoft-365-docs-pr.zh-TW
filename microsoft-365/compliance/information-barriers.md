---
title: 信息障碍概述
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
description: 使用信息障碍确保在组织内使用 Microsoft 团队确保通信合规性。
ms.openlocfilehash: c4a9213e74129126da0cbc41b7bc210a10b34db2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077130"
---
# <a name="information-barriers"></a>信息障碍

## <a name="overview"></a>概觀

Microsoft 云服务包括强大的通信和协作功能。 但是，假设您要限制两个组之间的通信，以避免在组织中发生利益冲突。 或者，您可能希望限制组织内某些人员之间的通信，以保护内部信息。 Microsoft 365 支持跨组和组织之间的通信和协作，因此是否有方法在必要时限制特定用户组之间的通信？ 有了信息障碍，你可以！ 

信息障碍正在推出，从微软团队开始。 假设[您的订阅](#required-licenses-and-permissions)包含信息障碍，合规性管理员或信息障碍管理员可以定义策略以允许或阻止 Microsoft Teams 中的用户组之间的通信。 信息屏障策略可用于以下情况：

- 日交易者不能呼叫营销团队中的某个人
- 处理公司机密信息的财务人员无法接收组织内某些团体的电话
- 具有商业机密材料的内部团队无法与组织内某些组中的人在线通话或聊天
- 研究团队只能与产品开发团队在线通话或聊天

对于所有这些示例方案（以及更多），可以定义信息屏障策略，以防止或允许 Microsoft 团队中的通信。 此类策略可以防止人们呼叫或聊天，或阻止人们与 Microsoft Teams 中的特定组通信。 在信息障碍策略生效后，每当受这些策略保护的用户尝试与 Microsoft Teams 中的其他人通信时，都会进行检查以阻止（或允许）通信（由信息屏障策略定义）。 要了解有关具有信息障碍的用户体验的详细信息，请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!IMPORTANT]
> 目前，信息障碍不适用于电子邮件通信或通过 SharePoint 在线或 OneDrive 进行文件共享。 此外，信息障碍独立于[合规性边界。](tagging-and-assessment-in-advanced-ediscovery.md)<p>在定义和应用信息障碍策略之前，请确保您的组织没有有效的[Exchange 通讯簿策略。](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) （信息障碍基于通讯簿策略。 

## <a name="what-happens-with-information-barriers"></a>信息障碍会发生什么情况

当信息障碍策略到位时，不应与其他特定用户通信的用户将无法查找、选择、聊天或呼叫这些用户。 在存在信息障碍时，会进行检查，以防止未经授权的通信。

最初，信息障碍仅适用于 Microsoft 团队聊天和渠道。 在 Microsoft 团队中，信息障碍策略确定并防止以下类型的未经授权的通信：
- 搜索用户
- 将成员添加到团队
- 与某人启动聊天会话
- 开始群聊
- 邀请某人加入会议
- 共享屏幕
- 拨打电话 

如果相关人员包含在信息屏障策略中以防止活动，则他们将无法继续。 此外，信息障碍策略中包含的每个人可能会被阻止与 Microsoft 团队中的其他人通信。 当受信息障碍策略影响的人员属于同一团队或群聊时，他们可能会从这些聊天会话中删除，并且可能不允许与群组进一步通信。

要了解有关具有信息障碍的用户体验的详细信息，请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

信息障碍正在推出，并包含在订阅中，例如：

- Microsoft 365 E5
- 办公室 365 E5
- Office 365 進階合規性
- 微软 365 E5 信息保护和合规性

有关详细信息，请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。

要[定义或编辑信息障碍策略，](information-barriers-policies.md)必须为您分配以下角色之一：

- 微软 365 全球管理员
- Office 365 全域系統管理員
- 合規性系統管理員
- IB 合规管理（这是一个新角色！

（要了解有关角色和权限的列表，请参阅[Office 365 安全&合规性中心的权限。](../security/office-365-security/protect-against-threats.md)

您必须熟悉 PowerShell cmdlet，才能定义、验证或编辑信息屏障策略。 尽管我们[在"工作方式"一文](information-barriers-policies.md)中提供了几个 PowerShell cmdlet 示例，但您需要了解组织的其他详细信息（如参数）。

## <a name="next-steps"></a>後續步驟

- [了解有关 Microsoft 团队中信息障碍的详细信息](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [查看可用于信息屏障策略的属性](information-barriers-attributes.md)

- [定义信息障碍的策略](information-barriers-policies.md)

- [编辑（或删除）信息屏障策略](information-barriers-edit-segments-policies.md.md) 

