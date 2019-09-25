---
title: 增加保留信箱的可復原項目配額
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '启用存档邮箱并启用自动展开存档，以增加 Office 365 中邮箱的可恢复项目文件夹的大小。 '
ms.openlocfilehash: 4c2e36dae3c8677579569d55a9c5b88efb5c54e5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076264"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>增加保留信箱的可復原項目配額

自动应用于 Exchange Online 中新邮箱的默认保留策略（名为"默认 MRM 策略"）包含名为"可恢复项目"的保留标记，14 天移动到存档状态。 此保留标记在 14 天的保留期过期后将项目从用户主邮箱中的"可恢复项目"文件夹中移动到用户存档邮箱中的"可恢复项目"文件夹中。 为此，必须启用用户的存档邮箱。 如果未启用存档邮箱，则不执行任何操作，这意味着在 14 天保留期到期后，保留邮箱的"可恢复项目"文件夹中的项目不会移动到存档邮箱。 由于保留的邮箱中未删除任何内容，因此可能会超出"可恢复项目"文件夹的存储配额，尤其是在未启用用户的存档邮箱时。 
  
为了帮助减少超出此限制的可能性，在 Exchange Online 中的邮箱上放置保留时，"可恢复项目"文件夹的存储配额将自动从 30 GB 增加到 100 GB。 如果启用了存档邮箱，则存档邮箱中的"可恢复项目"文件夹的存储配额也将从 30 GB 增加到 100 GB。 如果启用了 Exchange Online 中的自动扩展存档功能，则用户存档中的"可恢复项目"文件夹的存储配额将不受限制。
  
 下表汇总了"可恢复项目"文件夹的存储配额。 
  
|**可恢复项目文件夹的位置**|**邮箱未保持**|**邮箱保持**|
|:-----|:-----|:-----|
|主邮箱  <br/> |30 GB  <br/> |100 GB  <br/> |
|存档邮箱<sup>\*</sup> <br/> |無限制  <br/> |無限制  <br/> |
|**可恢复项目文件夹的总存储配额** <br/> |無限制  <br/> |無限制  <br/> |
   
> [!NOTE]
> <sup>\*</sup>对于具有 Exchange Online（计划 2）许可证的用户，存档邮箱的初始存储配额为 100 GB。 但是，当为保留的邮箱启用自动展开存档时，存档邮箱和可恢复项目文件夹的存储配额将增加到 110 GB。 必要时将预配额外的存档存储空间，从而导致无限量的存档存储。 有关自动扩展存档的详细信息，请参阅[Office 365 中无限制存档概述。](unlimited-archiving.md) 
  
当保留邮箱的主邮箱中的"可恢复项目"文件夹的存储配额接近其限制时，可以执行以下操作：
  
- **启用存档邮箱并启用自动展开存档**- 只需启用存档邮箱，然后在 Exchange 中打开自动扩展存档功能，即可为"可恢复项目"文件夹启用无限存储容量在线。 这将导致主邮箱中的可恢复项目文件夹的 110 GB 和用户存档中的可恢复项目文件夹的无限容量的存储容量。 查看方法：[在"安全&合规性中心启用存档邮箱，](enable-archive-mailboxes.md)并在[Office 365 中启用无限制存档。](enable-unlimited-archiving.md)
    
    > [!NOTE]
    > 启用接近超出"可恢复项目"文件夹的存储配额的邮箱的存档后，可能需要运行托管文件夹助手以手动触发助手以处理邮箱，以便移动过期邮件。存档邮箱中的可恢复项目文件夹。 有关说明，请参阅[步骤 4。](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 请注意，用户邮箱中的其他项目可能会移动到新的存档邮箱。 请考虑在启用存档邮箱后告诉用户可能发生这种情况。 
  
- **为保留邮箱创建自定义保留策略**- 除了启用存档邮箱和自动扩展对诉讼保留或就地保留的邮箱的存档外，您可能还希望为上的邮箱创建自定义保留策略保持。 这样，您就将保留策略应用于保留邮箱，该保留策略与应用于未处于保留状态的邮箱的默认 MRM 策略不同。 这允许您应用专为保留邮箱设计的保留标记。 这包括为"可恢复项目"文件夹创建新的保留标记。 
    
本主题的其余部分介绍为保留邮箱创建自定义保留策略的分步过程。
  
[步骤 1：为"可恢复项目"文件夹创建自定义保留标记](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

•[步骤 2：为保留的邮箱创建新的保留策略](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[步骤 3：将新的保留策略应用于保留的邮箱](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[（可选）步骤 4：运行托管文件夹助手以应用新的保留设置](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>步骤 1：为"可恢复项目"文件夹创建自定义保留标记

第一步是为"可恢复项目"文件夹创建自定义保留标记（称为保留策略标记或 RPT）。 如前所述，此 RPT 将项目从用户主邮箱中的"可恢复项目"文件夹移动到用户存档邮箱中的"可恢复项目"文件夹。 您必须使用 PowerShell 为"可恢复项目"文件夹创建 RPT。 不能使用 Exchange 管理中心 （EAC）。 
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. 运行以下命令为"可恢复项目"文件夹创建新的 RPT： 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    例如，以下命令为名为"可恢复项目 30 天，邮箱保留期"的可恢复项目文件夹创建 RPT，保留期为 30 天。 这意味着，在项目在"可恢复项目"文件夹中保留 30 天后，它将移动到用户存档邮箱中的"可恢复项目"文件夹中。
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 我们建议可恢复项目 RPT 的保留期（由_期限保留_参数定义）与将应用于 RPT 的邮箱的已删除项目保留期相同。 这允许用户在将已删除的项目移动到存档邮箱之前恢复已删除的项目。 在前面的示例中，保留期设置为 30 天，其假设邮箱的已删除项目保留期也是 30 天。 Exchange Online 信箱預設會將刪除的項目保留 14 天。 但是，您可以将此设置更改为最多 30 天。 有关详细信息，请参阅更改[Exchange Online 中邮箱的已删除项目保留期。](https://go.microsoft.com/fwlink/p/?LinkId=286940) 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>步骤 2：为保留的邮箱创建新的保留策略

下一步是创建新的保留策略，并向其添加保留标记，包括您在步骤 1 中创建的可恢复项目 RPT。 此新策略将在下一步中应用于保留的邮箱。 
  
在创建新的保留策略之前，请确定要添加的其他保留标记。 有关添加到默认 MRM 策略的保留标记的列表以及有关创建新保留标记的信息，请参阅以下内容：
  
- [在线交换中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [支援保留原則標記的預設資料夾](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- [创建保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404422)主题中的"创建保留标记"部分。
    
您可以使用 EAC 或 Exchange 在线电源外壳创建保留策略。
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>使用 EAC 创建保留策略
  
1. 在 EAC 中，转到**合规性管理**\>**保留策略，****然后单击"添加**![添加图标"。](media/ITPro-EAC-AddIcon.gif)
    
2. 在"**新建保留策略"** 页上，**在"名称"** 下键入描述保留策略用途的名称;在"名称"下键入名称。"例如，**保留邮箱的 MRM 策略**。 
    
3. **在"保留"标记**下，**单击"添加**![图标"。](media/ITPro-EAC-AddIcon.gif)
    
4. 在保留标记列表中，选择在步骤 1 中创建的可恢复项目 RPT，然后单击"**添加"。**
    
    ![選取自訂的 [可復原的項目] 保留標記](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. 选择要添加到保留策略的其他保留标记。 例如，您可能希望添加默认 MRM 策略中包含的相同标记。
    
6. 添加完保留标记后，单击"**确定"。**
    
7. **单击"保存"** 以创建新的保留策略。 
    
    请注意，链接到保留策略的保留标记将显示在详细信息窗格中。
    
    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>使用 Exchange 在线电源外壳创建保留策略
  
运行以下命令为保留邮箱创建新的保留策略。 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

例如，以下命令创建保留策略和链接保留标记，这些标记显示在上图中。
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>步骤 3：将新的保留策略应用于保留的邮箱

最后一步是将您在步骤 2 中创建的新保留策略应用于组织中处于保留状态的邮箱。 您可以使用 EAC 或 Exchange 在线 PowerShell 将保留策略应用于单个邮箱或多个邮箱。 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>使用 EAC 应用新的保留策略
  
1. 转到**收件人**\>**邮箱**。
    
2. 在列表视图中，选择要应用保留策略的邮箱，然后单击"**编辑"**![图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
3. 在"**用户邮箱"** 页上，**单击"邮箱功能"。**
    
4. **在"保留策略"** 下，选择在步骤 2 中创建的保留策略，**然后单击"保存"。**
    
您还可以使用 EAC 将保留策略应用于多个邮箱。
  
1. 转到**收件人**\>**邮箱**。
    
2. 在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。
    
3. 在詳細資料窗格中，按一下 [其他選項]****。
    
4. 在 [保留原則]**** 下方，按一下 [更新]****。
    
5. 在**批量分配保留策略**页上，选择在步骤 2 中创建的保留策略，**然后单击"保存"。** 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>使用 Exchange 在线电源外壳应用新的保留策略
  
您可以使用 Exchange 在线 PowerShell 将新的保留策略应用于单个邮箱。 但是，PowerShell 的真正功能是，您可以使用它快速标识组织中处于"诉讼保留"或"就地保留"中的所有邮箱，然后在单个命令中将新的保留策略应用于保留中的所有邮箱。 下面是使用 Exchange PowerShell 将保留策略应用于一个或多个邮箱的一些示例。 所有示例都应用在步骤 2 中创建的保留策略。
  
本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中处于诉讼保留状态的所有邮箱。
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中的所有邮箱，这些邮箱处于就地保留状态。
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

您可以使用**获取邮箱**cmdlet 来验证是否已应用新的保留策略。 
  
下面是一些示例，用于验证上述示例中的命令是否将"保留邮箱的 MRM 策略"保留策略应用于诉讼保留上的邮箱和就地保留的邮箱。
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>（可选）步骤 4：运行托管文件夹助手以应用新的保留设置

将新的保留策略应用于保留的邮箱后，托管文件夹助理最多可能需要 7 天时间才能使用新保留策略中的设置处理这些邮箱。 **您可以使用"开始管理文件夹**助手"cmdlet 手动触发助手以处理应用新保留策略的邮箱，而不是等待托管文件夹助手运行。 
  
运行以下命令以启动 Pilar Pinilla 邮箱的托管文件夹助手。
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

运行以下命令以启动保留的所有邮箱的托管文件夹助手。
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>詳細資訊

- 启用用户的存档邮箱后，请考虑告诉用户其邮箱中的其他项目（而不仅仅是"可恢复项目"文件夹中的项目）可能会移动到存档邮箱。 这是因为分配给 Exchange Online 邮箱的默认 MRM 策略包含保留标记（名为"默认 2 年移动到存档"），该标记在项目传递到邮箱或由用户。 有关详细信息，请参阅[联机交换中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- 启用用户的存档邮箱后，还可以告诉用户，他们可以在其存档邮箱的"可恢复项目"文件夹中恢复已删除的项目。 他们可以在 Outlook 中执行此操作，为此可以在"主页"选项卡上选择"**已删除项目"** 文件夹，然后单击"**从主"** 选项卡**上的"从服务器恢复已删除项目"。** 有关恢复已删除项目的详细信息，请参阅[Windows Outlook 中恢复已删除的项目。](https://go.microsoft.com/fwlink/p/?LinkId=624829) 
