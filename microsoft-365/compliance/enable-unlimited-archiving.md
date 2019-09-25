---
title: 在 Office 365 + 管理员帮助中启用无限制存档
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 对于管理员：了解如何在 Office 365 中启用自动扩展存档，该存档为用户提供了 Exchange 联机邮箱的无限存储空间。 您可以为整个组织或仅针对特定用户启用自动扩展存档。
ms.openlocfilehash: b140cf9bed811c5af2de2e5441bd3c296ed7effe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077096"
---
# <a name="enable-unlimited-archiving-in-office-365--admin-help"></a>在 Office 365 + 管理员帮助中启用无限制存档

您可以使用 Office 365 中的 Exchange Online 自动扩展存档功能为存档邮箱启用无限的存储空间。 启用自动展开存档时，当用户接近存储限制时，会自动向用户存档邮箱添加额外的存储空间。 结果是邮箱存储容量不受限制。 您可以为组织中的每个人或仅针对特定用户打开自动展开存档。 有关自动扩展存档的详细信息，请参阅[Office 365 中无限制存档概述。](unlimited-archiving.md)

## <a name="before-you-begin"></a>開始之前

- 您必须是 Office 365 组织中的全局管理员或 Exchange Online 组织中的组织管理角色组的成员，才能为整个组织或特定用户启用自动扩展存档。 或者，您必须是分配了"邮件收件人"角色的角色组的成员，才能为特定用户启用自动扩展存档。
    
- 在启用自动展开存档之前，必须启用用户的存档邮箱。 必须为用户分配 Exchange 联机计划 2 许可证才能启用存档邮箱。 如果为用户分配了 Exchange 联机计划 1 许可证，则必须为其分配单独的 Exchange 联机存档许可证才能启用其存档邮箱。 请参阅[在"安全&合规性中心中启用存档邮箱"。](enable-archive-mailboxes.md)
    
- 您还可以使用 PowerShell 启用存档邮箱。 有关 PowerShell 命令的示例，请参阅"[详细信息"](#more-information)部分，可用于为组织中的所有用户启用存档邮箱。 
    
- 自動展開封存也支援共用信箱。 要启用共享邮箱的存档，需要使用 Exchange 联机存档许可证的 Exchange 联机计划 2 许可证或 Exchange 联机计划 1 许可证。
    
- 不能使用 Exchange 管理中心或安全&合规性中心启用自动扩展存档。 您必须使用 Exchange 在线电源外壳。 要使用远程 PowerShell 连接到 Exchange 在线组织，请参阅[连接到 Exchange 在线 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>为整个组织启用自动扩展存档

您可以为整个组织启用自动扩展存档。 启用后，将启用对现有用户邮箱和已创建的新用户邮箱的自动展开存档。 创建用户邮箱时，请确保启用用户的主存档邮箱，以便自动展开存档功能适用于新用户邮箱。
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 在 Exchange 在线 PowerShell 中运行以下命令，为整个组织启用自动扩展存档。

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>为特定用户启用自动扩展存档

您可以只为特定用户启用自动扩展存档，而不是为组织中的每个用户启用自动扩展存档。 可以执行此操作，因为只有某些用户可能需要较大的存档存储容量。
  
当您为特定用户启用自动展开存档，并且用户邮箱处于保留状态或分配给 Office 365 保留策略时，将进行以下两个配置更改：
  
- 用户主存档邮箱的存储配额增加 10 GB（从 100 GB 增加到 110 GB）。 存档警告配额也增加了 10 GB（从 90 GB 增加到 100 GB）。
    
- 用户主邮箱中的"可恢复项目"文件夹的存储配额将增加 10 GB（也从 100 GB 增加到 110 GB）。 可恢复项目警告配额也增加了 10 GB（从 90 GB 增加到 100 GB）。 仅当处于保留状态或分配给 Office 365 保留策略的邮箱时，这些更改才适用。
    
添加此额外空间是为了防止在预配自动扩展存档之前可能出现的任何存储问题。 如上一节所述，在为整个组织启用自动扩展存档时，*不会*添加额外的存储空间。 
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 在 Exchange 在线 PowerShell 中运行以下命令，为特定用户启用自动展开存档。 如前所述，必须先启用用户的存档邮箱（主存档），然后才能为该用户启用自动展开存档。
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> 在 Exchange 混合部署中，不能**使用"启用-邮箱 - 自动扩展存档"** 命令为主邮箱位于本地且其存档邮箱基于云的特定用户启用自动扩展存档。 要在 Exchange 混合部署中启用基于云的存档邮箱的自动扩展存档，您必须在 Exchange 在线 PowerShell 中**运行"设置组织- 自动扩展存档"** 命令，以便自动扩展存档整个组织。 如果用户的主邮箱和存档邮箱都是基于云的，**则可以使用"启用邮箱-自动扩展存档"** 命令为该特定用户启用自动扩展存档。 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>验证是否启用了自动展开存档

要验证是否为您的组织启用了自动扩展存档，请运行 Exchange 联机 PowerShell 中的以下命令。

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

的值`True`指示为组织启用了自动展开存档。 
  
要验证是否为特定用户启用了自动展开存档，请运行以下命令。
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
的值`True`指示已为用户启用了自动展开存档。 
  
启用自动扩展存档后，请记住以下事项：
  
- 如果**运行"设置组织Config-自动扩展存档"** 命令为您的组织启用自动扩展存档，则不必在单个邮箱上运行**启用-邮箱 -自动扩展存档。** 运行"**设置组织Config** cmdlet"以为组织启用自动展开存档不会将用户邮箱*上的"自动展开存档启用"* 属性更改为`True`。
    
- 同样，启用自动展开存档时，*存档配额*和*存档警告配额*邮箱属性的值不会更改。 实际上，当您为用户邮箱启用自动展开存档，并且*自动展开存档启用*的属性设置为`True`时，将忽略*存档配额*和*存档警告配额*属性。 下面是为用户邮箱启用自动展开存档后这些邮箱属性的示例。 
    
    ![启用自动展开存档后，将忽略存档配额和存档警告配额属性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>詳細資訊

- 您还可以使用 PowerShell 启用存档邮箱。 例如，您可以在 Exchange Online PowerShell 中运行以下命令，为尚未启用存档邮箱的所有用户启用存档邮箱。

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 为组织或特定用户打开自动展开存档后，当存档邮箱（包括可恢复项目文件夹）达到 90 GB 时，存档邮箱将转换为自动展开的存档。 预配额外的存储空间最多可能需要 30 天。
    
- 打开自动展开存档后，无法将其关闭。
    
- Exchange 混合部署中为具有本地主邮箱的用户支持基于云的存档邮箱的自动扩展存档。 但是，在为基于云的存档邮箱启用自动扩展存档后，无法将该存档邮箱从板外重新归档回本地 Exchange 组织。 Exchange Server 2010 中的本地邮箱不支持自动展开存档。
    
- 有关用户可以用于访问其存档邮箱中其他存储区域中的项目的 Outlook 客户端列表，请参阅[Office 365 中无限制存档概述](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)中的"访问自动扩展存档中项目的 Outlook 要求"部分.
    
- 如前所述，在运行**启用邮箱 - 自动展开存档**命令时，将 10 GB 添加到用户主存档邮箱的存储配额（如果邮箱处于保留状态，则添加到可恢复项目文件夹）。 这将提供额外的存储空间，直到预配自动扩展的存储空间（最多可能需要 30 天）。 **运行"设置组织Config-自动扩展存档"** 以启用组织内所有邮箱的自动扩展存档时，不会添加此额外的存储空间。 如果为整个组织启用了自动扩展存档，但需要为特定用户添加额外的 10 GB 存储空间，则可以在该邮箱上运行**启用邮箱 -自动展开存档**命令。 您将收到一个错误，指出已启用自动展开存档，但额外的存储空间将添加到邮箱中。 

- 系統管理員無法調整儲存空間配額。

> [!IMPORTANT]
> 自动展开存档仅支持用于单个用户或共享邮箱的邮箱，其增长率每天不超过 1 GB。 不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱以进行存档。 使用者的封存信箱僅供該使用者使用。 Microsoft 保留在使用者封存信箱中用來儲存其他使用者之封存資料的執行個體中拒絕不受限封存的權限。
