---
title: 在 Office 365 中恢复非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果前员工返回您的组织，或者如果雇用新员工来承担离职员工的工作职责，则可以在 Office 365 中恢复非活动邮箱的内容。 恢复非活动邮箱时，它将转换为包含非活动邮箱内容的新邮箱。 '
ms.openlocfilehash: be7935472363e406a978c09f926776e69c3024fe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078150"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>在 Office 365 中恢复非活动邮箱

非活动邮箱（一种软删除邮箱）用于在前员工离开您的组织后保留其电子邮件。 如果该员工返回您的组织，或者如果其他员工承担前员工的工作职责，则可以通过两种方式将非活动邮箱的内容提供给用户： 
  
- **恢复非活动邮箱**如果前员工返回您的组织，或者如果雇用新员工来承担前员工的工作职责，则可以恢复非活动邮箱的内容。 此方法将非活动邮箱转换为包含非活动邮箱内容的新活动邮箱。 它會復原之後，非使用中的信箱不存在。 本主题中的过程描述了此方法。 
    
- **还原非活动邮箱**如果其他员工承担前员工的工作职责，或者如果其他用户需要访问非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。 还可以从非活动邮箱还原存档。 有关此方法的过程，请参阅[在 Office 365 中还原非活动邮箱。](restore-an-inactive-mailbox.md)
    
有关恢复和还原非活动邮箱之间的差异的详细信息，以及有关恢复非活动邮箱时发生的情况的说明，[请参阅"详细信息"](#more-information)部分。
  
> [!NOTE]
> 我们推迟了创建新的就地保留以使邮箱处于非活动状态的截止时间。 但是，在将来的某个阶段，您将无法在 Exchange 在线中创建新的就地保留。 到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。 不過，仍會支援「就地保留」上現有的非作用中信箱，並且您可以繼續管理非作用信箱上的「就地保留」。 這包括變更就地保留期間以及透過移除就地保留以永久刪除非作用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 您必须使用 Exchange 联机电源外壳来还原非活动邮箱。 不能使用 Exchange 管理中心 （EAC）。 有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 运行以下命令以获取组织中非活动邮箱的标识信息。 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    使用此命令返回的信息可以恢复特定的非活动邮箱。
    
- 有关非活动邮箱的详细信息，请参阅 Office [365 中的非活动邮箱。](inactive-mailboxes-in-office-365.md)
    
## <a name="recover-an-inactive-mailbox"></a>復原非作用中的信箱

使用"**新邮箱**cmdlet"参数** 恢复非活动邮箱。 
  
1. 创建包含非活动邮箱属性的变量。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > 在前面的命令中，**使用"可分辨名称"****或"ExchangeGUID"** 属性的值来标识非活动邮箱。 这些属性对于组织中的每个邮箱都是唯一的，而活动邮箱和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 本示例使用在上一命令中获取的属性，并将非活动邮箱恢复到用户 Ann Beebe 的活动邮箱。 确保为*名称*和*MicrosoftOnlineServicesID*参数指定的值在您的组织中是唯一的。 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    恢复的非活动邮箱的主 SMTP 地址将具有与*MicrosoftOnlineServicesID*参数指定的地址相同的值。 
    
恢复非活动邮箱后，还会创建新的 Office 365 用户帐户。 您必須指派授權來啟用此使用者帳戶。 若要在 Microsoft 365 系統管理中心中指派授權，請參閱[指派或解除指派商務用 Office 365 的授權](https://go.microsoft.com/fwlink/p/?LinkId=276798)。
  
## <a name="more-information"></a>詳細資訊

- **恢复和恢复非活动邮箱之间的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上将转换为新邮箱，非活动邮箱的内容和文件夹结构将保留，并且邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在，对新邮箱中的内容所做的任何更改都将影响非活动邮箱中最初处于保留状态的内容。 相反，还原非活动邮箱时，内容只会复制到另一个邮箱。 非活动邮箱将保留，并保留为非活动邮箱。 对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。 仍可以使用就地电子数据展示搜索非活动邮箱，其内容可以还原到另一个邮箱，也可以在以后恢复或删除。 
    
- **恢复非活动邮箱时会发生什么情况？** 恢复非活动邮箱时，会发生以下情况： 
    
  - 诉讼保留（如果为非活动邮箱启用）将被删除。
    
  - 将删除就地保留。 这意味着非活动邮箱将作为源邮箱从任何就地保留或就地电子数据展示搜索中删除。 
    
  - 非活动邮箱将从应用于它的任何 Office 365 保留策略中删除。
    
  - 单个项目恢复期（**由"保留删除项目"邮箱**属性定义）设置为 30 天。 通常，在 Exchange Online 中创建新邮箱时，此保留期设置为 14 天。 将其设置为 30 天的最大值，可以有更多时间从非活动邮箱中恢复已永久删除（或清除）的任何数据。 您还可以禁用单个项目恢复或将单个项目恢复期设置回默认的 14 天。 如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](https://go.microsoft.com/fwlink/?linkid=856769)。
    
  - 启用保留保留，保留期限设置为 30 天。 这意味着默认 Exchange 保留策略和分配给新邮箱的任何组织范围或 Exchange 范围的 Office 365 保留策略在 30 天内不会处理。 这为返回的员工或恢复的非活动邮箱的新所有者有时间管理旧邮件。 否则，Exchange 或 Office 365 保留策略可能会删除根据为 Exchange 或 Office 365 保留策略配置的设置过期的旧邮箱项目（或将项目移动到存档邮箱（如果已启用）。 30 天后，保留保留过期，**保留保留**邮箱属性设置为**False，** 托管文件夹助理开始处理分配给邮箱的策略。 如果您不需要此额外时间，只需删除保留保留即可。 或者，**您可以使用"设置邮箱 -结束日期保留保留"** 命令来延长保留保留的持续时间。 有关详细信息，请参阅[将邮箱置于保留状态](https://go.microsoft.com/fwlink/?linkid=856300)。
    
- **如果需要保留非活动邮箱的原始状态，则保留恢复的邮箱。** 要防止新邮箱所有者或保留策略永久删除从恢复的非活动邮箱中的任何邮件，可以将邮箱置于诉讼保留状态以了解更多信息，请参阅[将邮箱置于诉讼保留上。](https://go.microsoft.com/fwlink/?linkid=856286)
    
- **恢复非活动邮箱时可以使用什么用户 ID？** 恢复非活动邮箱时，为*MicrosoftOnlineServicesID*参数指定的值可能与与非活动邮箱关联的原始邮箱不同。 您还可以使用原始用户 ID。 但是，如前所述，请确保在恢复非活动邮箱时，用于*名称*和*MicrosoftOnlineServicesID*的值在您的组织中是唯一的。 
    
- **如果非活动邮箱的邮箱保留期尚未过期，该怎么办？** 如果非活动邮箱在 30 天前被软删除，则不能使用**New-邮箱 -非活动邮箱**命令来恢复它。 您必须通过还原相应的 Office 365 用户帐户来恢复它。 有关详细信息，请参阅[删除或还原用户。](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **如何知道非活动邮箱的软删除邮箱保留期是否已过期？** 執行下列命令。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    如果**外部目录对象 Id**属性没有值，则邮箱保留期已过期，您可以通过运行**New-邮箱 -非活动邮箱**命令来恢复非活动邮箱。 如果**外部目录ObjectId**属性有值，则软删除邮箱保留期尚未过期，您必须通过还原 Office 365 用户帐户来恢复邮箱。 请参阅[删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **请考虑在恢复非活动邮箱后启用存档邮箱。** 这允许返回的用户或新员工将旧邮件移动到存档邮箱。 当保留期到期时，分配给 Exchange 联机邮箱的默认 Exchange 保留策略的存档策略将移动两年或两年以上的项目到存档邮箱。 如果不启用存档邮箱，超过两年的项目将保留在用户的主邮箱中。 有关详细信息，请参阅在[Office 365&amp;安全合规性中心中启用存档邮箱。](enable-archive-mailboxes.md)
 