---
title: 更改 Office 365 中非活动邮箱的保留持续时间
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: 使 Office 365 邮箱处于非活动状态后，可以更改分配给非活动邮箱的保留或 Office 365 保留策略的持续时间。 保留持续时间定义"可恢复项目"文件夹中的项目持有时间。
ms.openlocfilehash: 7840131af3df32b8b8e5a0faa1b101f9ec8ef541
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076647"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>更改 Office 365 中非活动邮箱的保留持续时间

非活动邮箱用于在前员工离开您的组织后保留其电子邮件。 当在邮箱上放置诉讼保留、就地保留、Office 365 保留策略或与电子数据展示案例关联的保留时，邮箱将变为非活动状态，并且相应的 Office 365 用户帐户将被删除。 非活动邮箱的内容在邮箱处于非活动状态之前放在邮箱上的保留期间保留。 保留持续时间定义"可恢复项目"文件夹中的项目持有时间。 当"可恢复项目"文件夹中的项目的保留持续时间过期时，该项目将从非活动邮箱中永久删除（清除）。 使邮箱处于非活动状态后，可以更改分配给非活动邮箱的保留或 Office 365 保留策略的持续时间。
  
> [!IMPORTANT]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 您必须使用 Exchange 在线 PowerShell 更改非活动邮箱的诉讼保留的保留持续时间。 不能使用 Exchange 管理中心 （EAC）。 但是，您可以使用 Exchange 在线 PowerShell 或 EAC 来更改就地保留的保留持续时间。 您可以使用安全和合规性中心或安全&合规性中心 PowerShell 更改 Office 365 保留策略的保留持续时间。
    
- 要连接到 Exchange 在线 PowerShell 或安全&合规性中心 PowerShell，请参阅以下主题之一：
    
  - [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [连接到 Office 365 安全&合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 请注意，与电子数据展示案例关联的保留是无限保留，这意味着没有可以更改的保留持续时间。 项目将永久保留，或直到删除保留并删除非活动邮箱。
    
- 有关非活动邮箱的详细信息，请参阅 Office [365 中的非活动邮箱。](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步骤 1：识别非活动邮箱上的保留

由于不同类型的保留或一个或多个 Office 365 保留策略可能放置在非活动邮箱上，因此第一步是标识非活动邮箱上的保留。
  
在 Exchange 联机 PowerShell 中运行以下命令，以显示组织中所有非活动邮箱的保留信息。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
**诉讼保留**属性的**True**值表示非活动邮箱处于诉讼保留状态。 如果将就地保留、电子数据展示保留或 Office 365 保留策略放在非活动邮箱上，则保留或保留策略的 GUID 将显示为**InPlaceHolds**属性的值。 例如，下面显示 5 个非活动邮箱的结果。 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
下表标识了用于使每个邮箱处于非活动状态的五种不同的保留类型。
  
|**非活动邮箱**|**保持类型**|**如何识别非活动邮箱的保留**|
|:-----|:-----|:-----|
|安·比比  <br/> |诉讼保留  <br/> |*诉讼保留属性*设置为`True`。  <br/> |
|皮拉尔·皮尼拉  <br/> |原有範圍暫止  <br/> |*InPlaceHolds*属性包含放置在非活动邮箱上的就地保留的 GUID。 您可以判断这是就地保留，因为 ID 不以前缀开头。  <br/> 您可以使用 Exchange`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`联机 PowerShell 中的命令获取有关非活动邮箱的就地保留的信息。  <br/> |
|马里奥·内塞塞  <br/> |安全&合规性中心中的组织范围 Office 365 保留策略  <br/> |*"InPlaceHolds"* 属性为空。 这表示一个或多个组织范围或（Exchange 范围）Office 365 保留策略应用于非活动邮箱。 在这种情况下，您可以在 Exchange Online `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` PowerShell 中运行该命令，以获取组织范围 Office 365 保留策略的 GUID 列表。 应用于 Exchange 邮箱的组织范围保留策略的 GUID 以`mbx`前缀开头;例如`mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>要标识应用于非活动邮箱的 Office 365 保留策略，在"安全&合规性中心 PowerShell 中运行以下命令。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|卡罗尔·奥尔森  <br/> |安全&合规性中心中的 Office 365 保留策略应用于特定邮箱  <br/> |*InPlaceHolds*属性包含应用于非活动邮箱的 Office 365 保留策略的 GUID。 可以判断这是应用于特定邮箱的保留策略，因为 GUID 以`mbx`前缀开头。 请注意，如果应用于非活动邮箱的保留策略 GUID 以`skp`前缀开头，则表示保留策略应用于 Skype 业务对话。  <br/><br/> 要标识应用于非活动邮箱的 Office 365 保留策略，在"安全&合规性中心 PowerShell 中运行以下命令。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>运行此命令时，`mbx`请确保`skp`删除 或 前缀。  <br/> |
|亚伯拉罕·麦克马洪  <br/> |安全&合规中心持有电子数据展示案例  <br/> |*InPlaceHolds*属性包含放置在非活动邮箱上的第一数据展示案例保留的 GUID。 可以判断这是一个电子数据展示案例保留，因为 GUID 以`UniH`前缀开头。  <br/> 您可以使用安全&合规性`Get-CaseHoldPolicy`中心 PowerShell 中的 cmdlet 获取有关非活动邮箱保留关联的电子数据展示案例的信息。 例如，可以运行该命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`来显示非活动邮箱上的案例保留的名称。 运行此命令时，`UniH`请确保删除前缀。  <br/><br/> 要标识非活动邮箱上的保留与电子数据展示情况，应运行以下命令。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **注意：** 我们不建议对非活动邮箱使用电子数据展示保留。 That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. 在某个时候，法律案例可能会结束，与案例关联的保留将被删除，电子数据展示案例将关闭（或删除）。 事实上，如果放置在非活动邮箱上的保留与电子数据展示案例相关联，并且保留被释放或电子数据展示案例已关闭或删除，则非活动邮箱将被永久删除。 

有关 Office 365 保留策略的详细信息，请参阅[保留策略概述](retention-policies.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>步骤 2：更改非活动邮箱的保留持续时间

确定非活动邮箱上放置的保留类型（以及是否存在多个保留）后，下一步是更改保留的持续时间。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>更改诉讼保留的持续时间

下面讨论如何使用 Exchange Online PowerShell 更改放置在非活动邮箱上的诉讼保留的保留持续时间。 不能使用 EAC。 运行以下命令以更改保留持续时间。 在此示例中，保留持续时间更改为无限时间。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

结果是，非活动邮箱中的项目将无限期保留，或者直到删除保留或保留持续时间更改为其他值。
  
> [!TIP]
> 标识非活动邮箱的最佳方法是使用其**可分辨名称**或 Exchange **GUID**值。 使用这些值之一有助于防止意外指定错误的邮箱。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>更改就地保留的持续时间

 您可以使用 EAC 或 Exchange 在线电源外壳更改就地保留的保留持续时间。 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>使用 EAC 更改保留持续时间

1. 如果您知道要更改的就地保留的名称，则转到下一步。 否则，运行以下命令以获取放置在非活动邮箱上的就地保留的名称。 使用[您在步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保持 GUID。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。
    
3. 选择要更改的就地保持，然后单击"**编辑"**![图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地电子数据&amp;展示保留**属性页上，**单击"就地保留"。** 
    
5. 根据当前保留持续时间执行以下操作之一：
    
1. **单击"无限期保留"** 以无限期保留项目。 
    
2. **单击"指定相对于其接收日期保留物料的天数"** 以保留特定期间的物料。 键入要为其保留项目的天数。 
    
    ![變更就地保留之持續期間的螢幕擷取畫面](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. 按一下 [儲存]****。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>使用 Exchange 在线电源外壳更改保留持续时间

1. 如果您知道要更改的就地保留的名称，则转到下一步。 否则，运行以下命令以获取放置在非活动邮箱上的就地保留的名称。 使用[您在步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保持 GUID。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 运行以下命令以更改保留持续时间。 在此示例中，保留持续时间更改为 2，555 天（约 7 年）。 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     要将保留持续时间更改为无限制的时间，请使用 _-ItemHoldS 无限期限。_
  
## <a name="more-information"></a>詳細資訊

- **如何为非活动邮箱中的项目计算保留持续时间？** 持续时间从接收或创建邮箱项目的原始日期开始计算。 
    
- **当保留持续时间到期时会发生什么情况？** 当"可恢复项目"文件夹中的邮箱项目的保留持续时间过期时，该项目将从非活动邮箱中永久删除（清除）。 如果没有为在非活动邮箱上放置的保留指定持续时间，则"可恢复项目"文件夹中的项目永远不会被清除（除非更改非活动邮箱的保留持续时间）。 
    
- **是否仍在非活动邮箱上处理 Exchange 保留策略？** 如果 Exchange 保留策略（邮件记录管理或 Exchange Online 中的 MRM 功能）在邮箱处于非活动状态时应用于该邮箱，则删除策略（**配置为"删除**保留"操作的保留标记）将继续在非活动邮箱上处理。 这意味着在保留期到期时，使用删除策略标记的项目将移动到"可恢复项目"文件夹。 然后，当项目的保留期限到期时，将从非活动邮箱中清除这些项目。 
    
    相反，分配给非活动邮箱的保留策略中包含的任何存档策略（即配置了使用**MoveToArchive**保留操作的保留标记）都将被忽略。 这意味着在保留期到期时，使用存档策略标记的非活动邮箱中的项目将保留在主邮箱中。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 由于用户无法登录到非活动邮箱，因此没有理由使用数据中心资源来处理存档策略。 
    
- **要检查新的保留持续时间，请运行以下命令之一。** 第一个命令是诉讼保留;第二个用于就地保持。 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **与常规邮箱一样，托管文件夹助理 （MFA） 也处理非活动邮箱。** 在 Exchange 在线中，MFA 大约每 7 天处理一次邮箱。 更改非活动邮箱的保留持续时间后，**可以使用"开始管理文件夹助理**cmdlet"立即开始处理非活动邮箱的新保留持续时间。 執行下列命令。 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果在非活动邮箱上放置了许多保留，则并非所有保留 GUID 都会显示。** 可以运行以下命令来显示放置在非活动邮箱上的所有保留（诉讼保留除外）的 GUID。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
