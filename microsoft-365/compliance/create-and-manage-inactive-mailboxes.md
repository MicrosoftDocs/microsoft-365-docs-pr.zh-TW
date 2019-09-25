---
title: 在 Office 365 中创建和管理非活动邮箱
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
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: 您可以通过将保留或 Office 365 保留策略应用于邮箱，然后删除相应的 Office 365 用户帐户，在 Office 365 中创建非活动邮箱。 非活动邮箱中的项目在非活动之前应用于它的保留或保留策略的持续时间内保留。 要永久删除非活动邮箱，只需删除保留或保留策略。
ms.openlocfilehash: ca6fc5b579b6974ce89db14d318a6dc5a50f3f5c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076493"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>在 Office 365 中创建和管理非活动邮箱

Office 365 使您能够保留已删除邮箱的内容。 此功能称为[非活动邮箱。](inactive-mailboxes-in-office-365.md) 非活动邮箱允许您在员工离开组织后保留他们的电子邮件。 在删除相应的 Office 365 用户帐户之前，当诉讼保留或 Office 365 保留策略（在 Office 365 或 Microsoft 365 中的安全和合规性中心创建）应用于邮箱时，邮箱将变为非活动状态。 非活动邮箱的内容在邮箱处于非活动状态之前放在邮箱上的保留期间保留。 这允许管理员、合规性官和记录管理员使用内容搜索来搜索和导出非活动邮箱的内容。 非作用中的信箱無法接收電子郵件，也不會顯示於貴組織的共用通訊錄或其他清單中。
  
> [!NOTE]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 要使邮箱处于非活动状态，必须为其分配 Exchange 联机计划 2 许可证，以便在删除邮箱之前将诉讼保留或 Office 365 保留策略应用于该邮箱。 Exchange 在线计划 2 许可证是 Office 365 企业版 E3 和 E5 订阅的一部分。 如果邮箱被分配了 Exchange 在线计划 1 或 Exchange 在线 Kiosk 许可证（分别属于 Office 365 E1 和 F1 订阅），则您必须为其分配单独的 Exchange 联机存档许可证，以便保留可以应用于邮箱 b因此，它被删除。 有关详细信息，请参阅[交换联机存档](https://go.microsoft.com/fwlink/p/?LinkId=286153)。
    
- 删除相应的 Office 365 用户帐户后，与已删除的 Exchange Online 邮箱关联的许可证将可用。 然后，您可以将[这些许可证分配给其他用户。](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 
    
- 如果诉讼保留或 Office 365 保留策略（配置为保留或保留然后删除内容）在删除之前未应用于邮箱，则邮箱的内容将不会保留或可发现。 但是，删除的邮箱可以在删除后的 30 天内恢复，但如果邮箱及其内容未恢复，则该邮箱及其内容将在 30 天后永久删除。
    
- 有关诉讼保留的详细信息，请参阅[就地保留和诉讼保留](https://go.microsoft.com/fwlink/p/?LinkId=846124)。 有关 Office 365 保留策略的详细信息，请参阅[Office 365 中的保留策略概述。](retention-policies.md)
  
## <a name="create-an-inactive-mailbox"></a>创建非活动邮箱

使邮箱处于非活动状态需要两个步骤：1） 将邮箱置于诉讼保留状态或对邮箱 365 保留策略应用，2） 删除邮箱或相应的 Office 365 用户帐户。 邮箱处于非活动状态后，其内容将保留，直到删除保留或保留策略。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>第 1 步：将邮箱置于诉讼保留或应用 Office 365 保留策略

将邮箱置于诉讼保留或应用 Office 365 保留策略（配置为保留或保留然后删除内容）在删除之前保留邮箱中的内容。 这两种类型的保留将保留所有邮箱内容，包括已删除的项目和已修改项目的原始版本。 已删除和修改的项目将保留在非活动邮箱中指定一段时间，或者直到您通过删除应用于非活动邮箱的保留或保留策略永久删除非活动邮箱。
  
如果邮箱上已放置保留，或者 Office 365 保留策略已应用于邮箱，则所有操作就是删除步骤 2 中所述的相应的 Office 365 用户帐户。
  
有关将邮箱置于诉讼保留或应用 Office 365 保留策略的分步过程，请参阅：
  
- [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Office 365 中的保留策略概述](retention-policies.md)
    
> [!NOTE]
> 对于诉讼保留和 Office 365 保留策略，您可以创建无限期保留或基于时间的保留。 在无限期保留中，非活动邮箱的内容将永久保留，或直到删除保留或更改保留持续时间。 删除保留或保留策略后（假设邮箱在 30 天前已删除），将非活动邮箱标记为永久删除，并且将不再保留或发现邮箱的内容。 在基于时间的保留或 Office 365 保留策略中，指定保留的持续时间。 此持續時間視個別項目而定，會從接收或建立信箱項目的日期開始計算。 邮箱项目的保留过期，并且该项目移动到或位于非活动邮箱中的"可恢复项目"文件夹中后，在已删除的项目保留期到期后，该项目将从非活动邮箱中永久删除（清除）。 
  
### <a name="step-2-delete-the-mailbox"></a>步驟 2：刪除信箱

将邮箱置于保留状态或向其应用 Office 365 保留策略后，下一步是删除邮箱。 删除邮箱的最佳方法是删除 Microsoft 365 管理中心中的相应 Office 365 用户帐户。 有关删除 Office 365 用户帐户的信息，请参阅[从组织中删除用户。](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)
  
> [!NOTE]
> 您还可以使用 Exchange 在线电源外壳**中的"删除邮箱"** 删除邮箱。 有关详细信息，请参阅[联机交换中删除或还原用户邮箱。](https://go.microsoft.com/fwlink/?linkid=856287) 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>查看非活动邮箱的列表

要查看组织中非活动邮箱的列表，请以下操作：
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中管理员帐户的凭据登录。 
    
2. **单击"数据治理** > **保留"。**
    
3. 在"**保留"** 页上，**单击"更多**![导航栏"](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)椭圆，**然后单击"非活动邮箱"。**
    
    ![在"保留"页上，单击"更多"，然后单击"非活动邮箱"以显示非活动邮箱列表](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    将显示"**非活动邮箱"** 页。 请注意，将显示组织中非活动邮箱的总数。 
    
    ![将显示组织中所有非活动邮箱的列表](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
或者，您可以在 Exchange 联机 PowerShell 中运行以下命令以显示非活动邮箱列表。

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

您可以单击"![导出搜索结果"](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**图标"导出"** 以查看或下载包含组织中非活动邮箱的其他信息的 CSV 文件。 
  
还可以运行以下命令，将非活动邮箱列表和其他信息导出到 CSV 文件。 在此示例中，CSV 文件在当前目录中创建。

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> 非活动邮箱可能具有与活动用户邮箱相同的 SMTP 地址。 在这种情况下，可用于唯一标识非活动邮箱**的"可分辨名称"****或"ExchangeGuid"** 属性的值。 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>搜索并导出非活动邮箱的内容

您可以使用安全&合规性中心中的内容搜索工具访问非活动邮箱的内容。 在搜尋非使用中的信箱時，您可以建立關鍵字搜尋查詢以搜尋特定項目，也可以傳回非使用中信箱的完整內容。 您可以预览搜索结果或将搜索结果导出到 Outlook 数据 （PST） 文件或作为单个电子邮件。 有关搜索邮箱和导出搜索结果的分步过程，请参阅以下主题：
  
- [Office 365 中的内容搜索](content-search.md)
    
- [匯出內容搜尋結果](export-search-results.md)
    
在搜索非活动邮箱时，需要记住一些事项。
  
- 如果内容搜索包含用户邮箱，然后该邮箱处于非活动状态，则当您在非活动后重新运行搜索时，内容搜索将继续搜索该非活动邮箱。
    
- 在某些情况下，用户可能具有活动邮箱和非活动邮箱具有相同的 SMTP 地址。 在这种情况下，将仅搜索您选择作为内容搜索位置的特定邮箱。 换句话说，如果将用户的邮箱添加到搜索中，则不能假定将搜索其活动邮箱和非活动邮箱;如果将用户的邮箱添加到搜索中，则不能假定用户邮箱的邮箱和非活动邮箱都将被搜索。只会搜索您显式添加到搜索中的邮箱。
    
- 我们强烈建议您避免使用具有相同 SMTP 地址的活动邮箱和非活动邮箱。 如果需要重用当前分配给非活动邮箱的 SMTP 地址，我们建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱（或活动邮箱的存档），然后删除非活动邮箱。
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>變更非作用中信箱的保留持續時間

使邮箱处于非活动状态后，可以更改应用于非活动邮箱的保留期或 Office 365 保留策略的持续时间。 有关分步过程，请参阅[更改 Office 365 中非活动邮箱的保留持续时间。](change-the-hold-duration-for-an-inactive-mailbox.md)
  
## <a name="recover-an-inactive-mailbox"></a>復原非作用中的信箱

如果前员工返回您的组织，或者如果雇用新员工来承担离职员工的工作职责，则可以恢复非活动邮箱的内容。 當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 有关恢复非活动邮箱时的分步过程和详细信息，请参阅[在 Office 365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>将非活动邮箱的内容还原到另一个邮箱

如果其他员工承担前员工的工作职责，或者如果其他人需要访问非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 仍可以使用电子数据展示搜索非活动邮箱，其内容可以还原到另一个邮箱，也可以在以后恢复或删除。 有关分步过程，请参阅[在 Office 365 中还原非活动邮箱。](restore-an-inactive-mailbox.md)
  
## <a name="delete-an-inactive-mailbox"></a>刪除非作用中的信箱

如果不再需要保留非活动邮箱的内容，则可以通过删除保留或删除应用于非活动邮箱的 Office 365 保留策略来永久删除非活动邮箱。 如果邮箱在 30 天前被删除，则在删除保留后，该邮箱将被标记为永久删除，并且邮箱将变得不可恢复。 如果邮箱在过去 30 天内被删除，您仍然可以在删除保留或保留策略后恢复邮箱。 有关删除保留或 Office 365 保留策略以永久删除非活动邮箱的分步过程，请参阅删除 Office [365 中的非活动邮箱。](delete-an-inactive-mailbox.md)