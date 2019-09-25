---
title: 删除 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 当您不再需要保留 Office 365 非活动邮箱的内容时，可以通过删除保留来永久删除非活动邮箱。 删除保留后，非活动邮箱将被标记为删除，并在处理后永久删除。
ms.openlocfilehash: b6cea7284ccb930ef10ec96c082291acb9f66f2f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070624"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>删除 Office 365 中的非活动邮箱

在前任員工離開您的組織之後，可透過非使用中信箱來保留其電子郵件。 当您不再需要保留非活动邮箱的内容时，可以通过删除保留来永久删除非活动邮箱。 此外，有可能在非活动邮箱上放置多个保留。 例如，非活动邮箱可能放在诉讼保留和一个或多个就地保留上。 此外，Office 365 保留策略（在 Office 365 或 Microsoft 365 中的安全和合规性中心创建）可能应用于非活动邮箱。 您必须从非活动邮箱中删除所有保留和 Office 365 保留策略才能将其删除。 删除保留和保留策略后，非活动邮箱将被标记为删除，并在处理后永久删除。
  
> [!IMPORTANT]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
有关从非活动邮箱中删除保留后发生的情况的说明，[请参阅"详细信息"](#more-information)部分。 
  
## <a name="before-you-begin"></a>開始之前

- 您必须使用 Exchange 在线 PowerShell 从非活动邮箱中删除诉讼保留。 不能使用 Exchange 管理中心 （EAC）。 有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。 您可以使用 Exchange 在线电源外壳或 EAC 从非活动邮箱中删除就地保留。 
    
- 在删除保留并删除非活动邮箱之前，可以将非活动邮箱的内容复制到其他邮箱。 有关详细信息，请参阅[在 Office 365 中还原非活动邮箱。](restore-an-inactive-mailbox.md)
    
- 如果从非活动邮箱中删除保留或 Office 365 保留策略，并且邮箱的软删除邮箱保留期已过期，则邮箱将被永久删除。 删除后，无法恢复。 在删除保留之前，请确保不再需要邮箱中的内容。 如果要重新激活非活动邮箱，可以恢复它。 有关详细信息，请参阅[在 Office 365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)
    
- 有关非活动邮箱的详细信息，请参阅 Office [365 中的非活动邮箱。](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步骤 1：识别非活动邮箱上的保留

如前所述，诉讼保留、就地保留或 Office 365 保留策略可能放置在非活动邮箱中。 第一步是标识非活动邮箱上的保留。
  
运行以下命令以显示组织中所有非活动邮箱的保留信息。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**诉讼保留**属性的**True**值表示非活动邮箱处于诉讼保留状态。 如果将就地保留放在非活动邮箱上，则保留的 GUID 将显示为**InPlaceHolds**属性的值。 例如，两个非活动邮箱的以下结果显示，在 Ann Beebe 上放置了诉讼保留，在 Pilar Pinilla 上放置了两个就地保留。 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 如果将大量就地保留放在非活动邮箱上，则并非所有就地保留 GUID 都会显示。 可以运行以下命令以显示所有就地保持 GUID：`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>步骤 2：从非活动邮箱中删除保留

确定非活动邮箱上放置的保留类型（以及是否存在多个保留）后，下一步是删除邮箱上的保留。 如前所述，您必须删除所有保留才能永久删除非活动邮箱。 
  
### <a name="remove-a-litigation-hold"></a>删除诉讼保留

如前所述，您必须使用 Windows PowerShell 从非活动邮箱中删除诉讼保留。 不能使用 EAC。 运行以下命令以删除诉讼保留。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 标识非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。 使用这些值之一有助于防止意外指定错误的邮箱。 
  
### <a name="remove-in-place-holds"></a>移除就地保留

 有两种方法可以从非活动邮箱中删除就地保留： 
  
- **删除就地保留对象**如果要永久删除的非活动邮箱是就地保留的唯一源邮箱，则只需删除就地保留对象即可。 
    
    > [!NOTE]
    > 您必须禁用保留，然后才能删除就地保留对象。 如果尝试删除启用了保留的就地保留对象，您将收到一条错误消息。 
  
- **将非活动邮箱作为就地保留的源邮箱删除**如果要保留其他源邮箱以进行就地保留，可以从源邮箱列表中删除非活动邮箱，并保留就地保留对象。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>使用 EAC 删除就地保留

1. 如果您知道要删除的就地保留的名称，则可以转到下一步。 否则，请运行以下命令以获取放置在要永久删除的非活动邮箱上的就地保留的名称。 使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。
    
3. 选择要删除的就地保持，然后单击"**编辑**![编辑"图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在"**就地"电子数据&amp;展示保留**属性页上，**单击"就地保留"，** 取消选中与**所选邮箱中的搜索查询匹配的"保留"框中的"放置内容"，****然后单击"保存"。**
    
5. 在**就地电子&amp;数据展示保留**页上，再次选择就地保持，然后单击"**删除"**![图标](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。
    
6. 在警告中，单击"**是"** 以删除就地保留。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>使用 Exchange 在线电源外壳删除就地保留

1. 创建一个变量，其中包含要删除的就地保留的属性。 使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 禁用就地保留。
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. 删除就地保留。
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 EAC 从就地保留中删除非活动邮箱

1. 如果您知道放置在非活动邮箱上的就地保留的名称，则可以转到下一步。 否则，运行以下命令以获取放置在邮箱上的就地保留的名称。 使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。
    
3. 选择放置在非活动邮箱上的就地保持，然后单击"**编辑**![编辑"图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地电子数据展示&amp;保留**属性页上，单击"**源"。**
    
5. 在源邮箱列表中，单击要删除的非活动邮箱的名称，然后单击"**删除"**![图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)。
    
6. **单击"保存"** 以保存更改。 将显示一条消息，指出操作已成功完成。 
    
7. 重复步骤 1 到 6 以删除放置在非活动邮箱上的其他就地保留。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 Exchange 在线 PowerShell 从就地保留中删除非活动邮箱

如果就地保留包含大量源邮箱，则非活动邮箱可能不会列在 EAC**中的"源"** 页上。 编辑就地保留时，"**源"** 页上最多显示 3，000 个邮箱。 **如果"源"** 页上未列出非活动邮箱，则可以使用 Exchange 在线 PowerShell 将其从就地保留中删除。 
  
1. 创建一个变量，其中包含放置在非活动邮箱上的就地保留的属性。 使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 验证非活动邮箱是否列为就地保留的源邮箱。 
    
```
  $InPlaceHold.Sources
```

   **注意：**"就地保留"的*源*属性通过*源 ExchangeDN*属性标识源邮箱。 由于此属性唯一标识非活动邮箱，因此使用"就地保留"中的*源*属性有助于防止删除错误的邮箱。 如果两个邮箱具有相同的别名或 SMTP 地址，这也有助于避免出现问题。 
   
3. 从变量中的源邮箱列表中删除非活动邮箱。 请确保使用上一步中命令返回的非活动邮箱的**LegacyExchangeDN。** 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. 验证非活动邮箱是否从变量中的源邮箱列表中删除。
    
```
  $InPlaceHold.Sources
```

5. 使用更新的源邮箱列表修改就地保留，该列表不包括非活动邮箱。
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. 验证非活动邮箱是否已从就地保留的源邮箱列表中删除。
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a>詳細資訊

- **非活动邮箱是软删除邮箱的类型。** 在 Exchange Online 中，软删除邮箱是已删除但可在特定保留期内恢复的邮箱。 Exchange 联机中的软删除邮箱保留期为 30 天。 这意味着邮箱可以在软删除后的 30 天内恢复。 30 天后，软删除邮箱被标记为永久删除，无法恢复。 
    
- **删除非活动邮箱上的保留后会发生什么情况？** 该邮箱被视为其他软删除邮箱，并在 30 天软删除邮箱保留期到期后标记为永久删除。 此保留期从首次使邮箱处于非活动状态的日期开始。 此日期称为软删除日期，即相应的 Office 365 用户帐户被删除的日期，或**使用"删除**邮箱"cmdlet 删除 Exchange Online 邮箱的日期。 软删除日期不是您删除保留的日期。 
    
- **在删除保留后，非活动邮箱是否立即永久删除？** 如果非活动邮箱的软删除日期超过 30 天，则删除保留后不会永久删除该邮箱。 该邮箱将被标记为永久删除，并在下次处理时将其删除。 
    
- **软删除邮箱保留期如何影响非活动邮箱？** 如果非活动邮箱的软删除日期比删除保留的日期早 30 天，则邮箱将被标记为永久删除。 但是，如果非活动邮箱在过去 30 天内具有软删除日期，而您删除了保留，则可以恢复邮箱，直到软删除邮箱保留期到期。 有关详细信息，请参阅[联机交换中删除或还原用户邮箱。](https://go.microsoft.com/fwlink/?linkid=856835) 软删除邮箱保留期到期后，您已按照恢复非活动邮箱的过程。 有关详细信息，请参阅[在 Office 365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)
    
- **删除保留后，如何显示有关非活动邮箱的信息？** 删除保留并将非活动邮箱还原回软删除邮箱后，不会使用"*非活动邮箱"* 参数与**Get-邮箱**cmdlet 一起返回。 但是，您可以使用**获取邮箱 -软删除邮箱**命令显示有关邮箱的信息。 例如： 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
在上面的*示例中，WhenSoftDeletedd*属性标识软删除日期，在此示例中为 2014 年 10 月 30 日。 如果此软删除邮箱以前是已为其删除保留的非活动邮箱，则将在*WhenSoftDeleteds*属性的值后 30 天永久删除该邮箱。 在这种情况下，邮箱在 2014 年 11 月 30 日之后将永久删除。

