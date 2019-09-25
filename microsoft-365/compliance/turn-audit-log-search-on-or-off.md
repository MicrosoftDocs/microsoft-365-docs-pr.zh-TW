---
title: 開啟或關閉 Office 365 稽核記錄搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以在安全&合规性中心中打开审核日志搜索功能。 如果你改变主意，你可以随时关闭。 关闭审核日志搜索后，管理员无法搜索 Office 365 审核日志以查找组织中的用户和管理员活动。
ms.openlocfilehash: c5e1106617aa4828ec2db5afcc44ac55e91f2383
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078146"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>開啟或關閉 Office 365 稽核記錄搜尋

您（或其他管理员）必须先打开审核日志记录，然后才能开始搜索 Office 365 审核日志。 启用安全&合规性中心的审核日志搜索后，组织的用户和管理活动将记录在审核日志中，并保留 90 天。 但是，您的组织可能不希望记录和保留审核日志数据。 或者，您可能正在使用第三方安全信息和事件管理 （SIEM） 应用程序来访问您的审核数据。 在这些情况下，全局管理员可以在 Office 365 中关闭审核日志搜索。
  
## <a name="before-you-begin"></a>開始之前

- 您必须在 Exchange Online 中分配审核日志角色，才能在 Office 365 组织中打开或关闭审核日志搜索。 默认情况下，此角色分配给 Exchange 管理中心"**权限"** 页上的"合规性管理和组织管理"角色组。 Office 365 中的全局管理员是 Exchange 联机中的组织管理角色组的成员。 
    
    > [!IMPORTANT]
    > 必须在 Exchange Online 中为用户分配权限才能打开或关闭审核日志搜索。 如果向用户分配了"安全&合规性中心""**权限"** 页上的"审核日志"角色，则用户将无法打开或关闭审核日志搜索。 这是因为基础 cmdlet 是交换联机 cmdlet。 
  
- 如果在 Office 365 中关闭审核日志搜索，您将无法使用 Office 365 管理活动 API 访问组织的审核数据。 按照本文中的步骤关闭审核日志搜索意味着当您使用安全&合规性中心搜索审核日志时，或者当您在 Exchange 在线 PowerShell 中运行**搜索统一审核日志**cmdlet 时，将不会返回任何结果. 这也意味着您的审核日志无法通过 Office 365 管理活动 API 提供。  
    
- 有关搜索 Office 365 审核日志的分步说明，请参阅[在安全&合规性中心中搜索审核日志。](search-the-audit-log-in-security-and-compliance.md)
    
## <a name="turn-on-audit-log-search"></a>打开审核日志搜索

您可以使用安全&合规性中心或 PowerShell 在 Office 365 中打开审核日志搜索。 在打开审核日志搜索后，可能需要几个小时才能在搜索审核日志时返回结果。 您必须在 Exchange 联机中分配审核日志角色才能打开审核日志搜索。
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>使用安全&合规性中心打开审核日志搜索

1. 在安全&合规性中心，转到**搜索**\>**审核日志搜索**。
    
2. **单击"开始录制用户和管理活动"。**
    
    ![单击"开始记录用户和管理活动"以打开审核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    将显示一个对话框，指出组织中的用户和管理员活动将记录到 Office 365 审核日志中，并可在报表中查看。 
    
3. 按一下 [開啟]****。
    
    将显示一条消息，指出审核日志正在准备中，您可以在准备完成后的几个小时内运行搜索。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 打开审核日志搜索

1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 运行以下 PowerShell 命令以在 Office 365 中打开审核日志搜索。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    将显示一条消息，指出更改最多可能需要 60 分钟才能生效。
  
## <a name="turn-off-audit-log-search"></a>关闭审核日志搜索

您必须使用连接到 Exchange 在线组织的远程 PowerShell 来关闭审核日志搜索。 与打开审核日志搜索类似，您必须在 Exchange Online 中分配审核日志角色才能关闭审核日志搜索。
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 运行以下 PowerShell 命令以在 Office 365 中关闭审核日志搜索。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 一段时间后，验证审核日志搜索是否关闭（禁用）。 方法有兩種：
    
    - 在 PowerShell 中，运行以下命令：

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        "`False`_统一审核登录启用"_ 属性的值指示已关闭审核日志搜索。 
    
    - 在安全&合规性中心，**转到"搜索**\>**审核日志搜索"，** 然后单击"**搜索"。**
    
      将显示一条消息，指出审核日志搜索未打开。 
    
      ![如果关闭审核，将显示一条消息](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
