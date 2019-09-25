---
title: 設定內容搜尋的權限篩選
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
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 使用内容搜索权限筛选允许电子数据展示管理器仅搜索 Office 365 组织中的邮箱和网站的子集。
ms.openlocfilehash: a5dcdd450a974cab476a1b31fc82c78bdda84b2b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077554"
---
# <a name="configure-permissions-filtering-for-content-search"></a>設定內容搜尋的權限篩選

您可以使用搜索权限筛选来允许电子数据展示管理器仅搜索 Office 365 组织中的邮箱和站点子集。 您也可以使用權限篩選，讓相同的 eDiscovery 管理員僅搜尋符合特定搜尋準則的信箱或網站內容。 例如，您可以讓 eDiscovery 管理員只在特定位置或部門中搜尋使用者的信箱。 为此，可以通过创建一个筛选器，该筛选器使用受支持的收件人筛选器来限制特定用户或用户组可以搜索的邮箱。 您也可以建立篩選器，指定可搜尋的信箱內容。 可以藉由建立篩選器來完成這個動作，該篩選器會使用可搜尋的郵件屬性。 同样，您可以让电子数据展示管理器仅搜索组织中的特定 SharePoint 网站。 您可以藉由建立篩選器來完成這個動作，該篩選器會限制可搜尋的網站。 您也可以建立篩選器，指定可搜尋的網站內容。 可以藉由建立篩選器來完成這個動作，該篩選器會使用可搜尋的網站屬性。

您还可以使用搜索权限筛选在 Office 365 组织中创建逻辑边界（称为*合规性边界），* 以控制用户内容位置（如邮箱、SharePoint 网站和 OneDrive 帐户），这些边界用于控制用户内容位置（如邮箱、SharePoint 网站和 OneDrive 帐户），特定的电子数据展示管理器可以搜索。 有关详细信息，请参阅在[Office 365 中为电子数据展示调查设置合规性边界。](tagging-and-assessment-in-advanced-ediscovery.md)
  
安全&合规性中心的内容搜索功能支持搜索权限筛选。 这四个 cmdlet 允许您配置和管理搜索权限筛选器：
  
[新合规性安全过滤器](#new-compliancesecurityfilter)

[获取合规性安全筛选器](#get-compliancesecurityfilter)

[设置合规性安全筛选器](#set-compliancesecurityfilter)

[删除合规性安全筛选器](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>開始之前

- 要运行合规性安全筛选器 cmdlet，您必须是安全&合规性中心中的组织管理角色组的成员。 有关详细信息，请参阅[安全&合规性中心的权限](/security/office-365-security/protect-against-threats.md)。
    
- 您必须将 Windows PowerShell 连接到安全&合规性中心以及 Exchange 在线组织才能使用合规性安全筛选器 cmdlet。 这是必要的，因为这些 cmdlet 需要访问邮箱属性，这就是为什么您必须连接到 Exchange Online 的原因。 請參閱下一節中的步驟。 
    
- 請參閱[More information](#more-information)一節以取得搜尋權限篩選器的詳細資訊。 
    
- 搜索权限筛选适用于非活动邮箱，这意味着您可以使用邮箱和邮箱内容筛选来限制可以搜索非活动邮箱的人员。 有关权限筛选和非活动邮箱的其他信息，[请参阅"详细信息"](#more-information)部分。 
    
-  搜索权限筛选不能用于限制谁可以搜索 Exchange 中的公用文件夹。 
    
- 可以在组织中创建的搜索权限筛选器的数量没有限制。 但是，当有超过 100 个搜索权限筛选器时，搜索性能将受到影响。 要使组织中的搜索权限筛选器数量尽可能小，请尽可能创建将 Exchange、SharePoint 和 OneDrive 的规则组合在单个筛选器中的筛选器。
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>在单个远程 PowerShell 会话中连接到安全&合规性中心和在线交换

1. 使用文件名后缀 **.ps1**将以下文本保存到 Windows PowerShell 脚本文件。 例如，您可以将其保存到名为**ConnectEXO-CC.ps1**的文件。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在本地计算机上，打开 Windows PowerShell，转到您在上一步中创建的脚本所在的文件夹，然后运行该脚本;然后，打开 Windows PowerShell。"例如：
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
如何知道這是否正常運作？ 运行脚本后，来自安全&合规性中心和联机交换的 cmdlet 将导入到本地 Windows PowerShell 会话中。 如果您未收到任何錯誤，便已順利連線。 快速测试是运行安全&合规性中心 cmdlet 和 Exchange 在线 cmdlet。 例如，可以运行**安装统一合规性先决条件**和**获取邮箱**。 
  
如果您收到錯誤，請檢查下列需求：
  
- 密碼錯誤是常見的問題。再次執行這兩個步驟，並密切注意您在步驟 1 中輸入的使用者名稱和密碼。
    
- 验证您的帐户是否有权访问安全&合规中心。 有关详细信息，请参阅[授予用户对安全&合规性中心的访问权限。](/security/office-365-security/grant-access-to-the-security-and-compliance-center.md)
    
- 为了帮助防止拒绝服务 （DoS） 攻击，您只能与安全&合规性中心建立三个开放的远程 PowerShell 连接。
    
- 必须将 Windows PowerShell 配置为运行脚本。 这只需要做一次，而不是每次连接。 若要讓 Windows PowerShell 執行經過簽署的指令碼，請在提高權限的 Windows PowerShell 視窗 (藉由選取 **[以管理員身分執行]** 開啟的 Windows PowerShell 視窗) 中執行下列命令。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- 本機電腦與 Office 365 之間必須開啟 TCP 連接埠 80 流量。 該連接埠可能已開啟，但必須考量您的組織是否有限制性網際網路存取原則。

  
## <a name="new-compliancesecurityfilter"></a>新合规性安全过滤器

**新合规性安全筛选器**用于创建搜索权限筛选器。 下表描述了此 cmdlet 的参数。 建立符合性安全性篩選器需要所有參數。 
  
|**參數**|**描述**|
|:-----|:-----|
| _Action_ <br/> | _Action_参数指定筛选器应用于的搜索操作的类型。 可能的內容搜尋動作是︰  <br/><br/> **导出：** 导出搜索结果时应用筛选器。  <br/> **预览：** 预览搜索结果时应用筛选器。  <br/> **清除：** 清除搜索结果时应用筛选器。  <br/> **搜索：** 运行搜索时应用筛选器。  <br/> **所有：** 筛选器将应用于所有搜索操作。  <br/> |
| _FilterName_ <br/> |_FilterName_参数指定权限筛选器的名称。 此名稱是用來在使用 **Get-ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter,** 和 **Remove-ComplianceSecurityFilter** Cmdlet 時識別篩選器。  <br/> |
| _篩選_ <br/> | _筛选器_参数指定合规性安全筛选器的搜索条件。 您可以创建三种不同类型的筛选器：  <br/><br/> **邮箱筛选：** 这种类型的筛选器指定分配的用户（由_Users_参数指定）可以搜索的邮箱。 这种类型的筛选器的语法是**邮箱_** _邮箱属性名称，_ 其中_邮箱属性_指定用于设置可搜索邮箱范围的邮箱属性。 例如，邮箱筛选器`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`将允许分配此筛选器的用户仅搜索自定义属性10属性中具有值为"渥太华用户"的邮箱。  <br/>  任何受支持的可筛选收件人属性都可用于_邮箱属性属性。_ 有关受支持的属性的列表，请参阅[-收件人筛选器参数 的可筛选属性。](https://go.microsoft.com/fwlink/p/?LinkId=784903)  <br/><br/> **邮箱内容筛选：** 这种类型的筛选器应用于可搜索的内容。 它指定分配用户可以搜索的邮箱内容。 这种类型的筛选器的语法是**邮箱内容_** _可搜索属性名称：值_，其中_可搜索属性名称_指定可在内容搜索中指定的关键字查询语言 （KQL） 属性。 例如，邮箱内容筛选器`MailboxContent_recipients:contoso.com`将允许分配此筛选器的用户仅搜索发送到contoso.com域中的收件人的邮件。  <br/>  有关可搜索邮件属性的列表，[请参阅"内容搜索"的关键字查询和搜索条件。](keyword-queries-and-search-conditions.md) <br/> <br/> **重要提示：** 单个搜索筛选器不能包含邮箱筛选器和邮箱内容筛选器。 要将它们组合到单个筛选器中，必须使用[筛选器列表](#using-a-filters-list-to-combine-filter-types)。  但是，筛选器可以包含相同类型的更复杂的查询。 例如，  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **网站和网站内容筛选：** 有两个 SharePoint 和 OneDrive 用于业务网站相关筛选器，可用于指定分配用户可以搜索的网站或网站内容：  <br/><br/> - **站点***_可搜索网站属性_ <br/> - **网站内容***_可搜索网站属性_ <br/><br/>  这两个过滤器是可互换的。 例如，`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`并`"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`返回相同的结果。 但是，为了帮助您确定筛选器的作用，可以使用`Site_`指定与网站相关的属性（如网站 URL）和`SiteContent_`指定与内容相关的属性（如文档类型）。 例如，筛选器`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`将允许用户分配此筛选器以仅搜索https://contoso.sharepoint.com/sites/doctors网站集中的内容。 筛选器`"SiteContent_FileExtension -eq 'docx'"`将允许分配此筛选器的用户仅搜索 Word 文档（Word 2007 及更高版本）。  <br/><br/>  有关可搜索网站属性的列表，请参阅[SharePoint 中已爬网和托管属性的概述。](https://go.microsoft.com/fwlink/p/?LinkId=331599) **在"可查询"** 列中**标记为"是"** 的属性可用于创建网站或网站内容筛选器。  <br/><br/> **重要提示：** 您必须创建搜索权限筛选器，以显式阻止用户搜索特定 Office 365 服务中的内容位置（例如阻止用户搜索任何 Exchange 邮箱或任何 SharePoint 网站）。 换句话说，创建允许用户搜索组织中的所有 SharePoint 网站的搜索权限筛选器不会阻止该用户搜索邮箱。 例如，要允许 SharePoint 管理员仅搜索 SharePoint 网站，必须创建一个筛选器，以防止他们搜索邮箱。 同样，要允许 Exchange 管理员仅搜索邮箱，您必须创建一个筛选器，以防止他们搜索网站。           |
| _Users_ <br/> |_"用户"_ 参数指定将此筛选器应用于其内容搜索的用户。 依其別名或主要 SMTP 位址識別使用者。 您可以指定以逗號分隔的多個值，或者您也可以使用值 **All** 將篩選器指派給所有使用者。  <br/> _您还可以使用"用户"_ 参数指定安全&合规性中心角色组。 這可讓您建立自訂角色群組，然後為該角色群組指派搜尋權限篩選器。 例如，假設您有多國公司的美國子公司的 eDiscovery 管理員的自訂角色群組。 可以使用_Users_参数指定此角色组（通过使用角色组的 Name 属性），然后使用_Filter_参数只允许搜索美国中的邮箱。  <br/> 使用此參數，無法指定通訊群組。  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>使用筛选器列表组合筛选器类型

*筛选器列表*是一个筛选器，其中包括邮箱筛选器和由逗号分隔的站点筛选器。 使用筛选器列表是组合不同类型的筛选器的唯一受支持方法。 在下面的示例中，请注意逗号分隔**邮箱**和**站点**筛选器：

```
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

在运行内容搜索期间处理包含筛选器列表的筛选器时，将从筛选器列表中创建两个搜索权限筛选器：每个筛选器一个，由逗号分隔。 因此，在前面的示例中，将创建一个邮箱搜索权限筛选器和一个站点搜索权限筛选器。 

使用筛选器列表的替代方案是创建两个单独的搜索权限筛选器。 因此，在前面的示例中，您将为邮箱属性创建一个筛选器，为站点属性创建一个筛选器。 在这两种情况下，结果都是一样的。 使用筛选器列表或创建单独的搜索权限筛选器是一个首选项。

在使用筛选器列表时，请记住以下事项：

- 您必须使用筛选器列表来创建包含**邮箱**筛选器和**邮箱内容**筛选器的筛选器。 

- 如前所述，您不必使用筛选器列表在单个搜索权限筛选器中包括**网站**和**SiteContent**筛选器。 例如，可以使用 **- 或**运算符组合**网站**和**网站内容**筛选器。

   ```
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- 筛选器列表的每个组件可以包含复杂的筛选器语法。 例如，邮箱和站点筛选器可以包含由 **-or**运算符分隔的多个筛选器：

   ```
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>创建搜索权限筛选器的示例

以下是使用 **New-ComplianceSecurityFilter** Cmdlet 來建立搜尋權限篩選器的範例。 
  
此示例允许用户annb@contoso.com仅对加拿大的邮箱执行所有内容搜索操作。 此篩選器包含根據 ISO 3166-1 的三位數數字加拿大國碼。

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

此示例允许用户的 donh 和 suzanf 仅搜索具有自定义属性 1 邮箱属性的值"市场营销"的邮箱。

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
此範例允許「美國探索管理員」角色群組的成員僅針對美國的信箱執行所有內容搜尋動作。此篩選器包含根據 ISO 3166-1 的三位數數字美國國碼。
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

此示例允许电子数据展示管理器角色组的成员仅搜索渥太华用户通讯组成员的邮箱。 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
此範例可防止任何使用者從 Executive Team 通訊群組成員的信箱刪除內容。

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
此示例允许 OneDrive 电子数据展示管理器自定义角色组的成员仅搜索 OneDrive 中针对组织中的业务位置的内容。

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> 要将用户限制为搜索特定网站，请使用筛选器`Site_Path`，如上例所示。 使用`Site_Site`将不起作用。 
  
此範例會限制使用者只能對 2015 年期間傳送的電子郵件執行所有內容搜尋動作。

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
類似於先前的範例，此範例會限制使用者對於在 2015 年進行最後變更的文件執行所有內容搜尋動作。

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
本示例可防止"OneDrive 发现管理器"角色组的成员对组织中的任何邮箱执行内容搜索操作。 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

本示例可防止组织中的任何人搜索由 janets 或 sarad 发送或接收的电子邮件。

```
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

本示例使用筛选器列表合并邮箱和站点筛选器。

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>获取合规性安全筛选器

**获取合规性安全筛选器**用于返回搜索权限筛选器的列表。 使用_FilterName_参数返回特定搜索筛选器的信息。 
  
## <a name="set-compliancesecurityfilter"></a>设置合规性安全筛选器

**设置合规性安全筛选器**用于修改现有搜索权限筛选器。 唯一必需的参数是_筛选器名称_。 
  
|**參數**|**描述**|
|:-----|:-----|
| _Action_| _Action_参数指定筛选器应用于的搜索操作的类型。 可能的內容搜尋動作是︰ <br/><br/> **导出：** 导出搜索结果时应用筛选器。  <br/> **预览：** 预览搜索结果时应用筛选器。  <br/> **清除：** 清除搜索结果时应用筛选器。  <br/> **搜索：** 运行搜索时应用筛选器。  <br/> **所有：** 筛选器将应用于所有搜索操作。  <br/> |
| _FilterName_|_FilterName_参数指定权限筛选器的名称。 |
| _篩選_| _筛选器_参数指定合规性安全筛选器的搜索条件。 您可以创建两种不同类型的筛选器： <br/><br/>**邮箱筛选：** 这种类型的筛选器指定分配的用户（由_Users_参数指定）可以搜索的邮箱。 这种类型的筛选器的语法是**邮箱_** _邮箱属性名称，_ 其中_邮箱属性_指定用于设置可搜索邮箱范围的邮箱属性。 例如，邮箱筛选器`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`将允许分配此筛选器的用户仅搜索自定义属性10属性中具有值为"渥太华用户"的邮箱。  任何受支持的可筛选收件人属性都可用于_邮箱属性属性。_ 有关受支持的属性的列表，请参阅[-收件人筛选器参数 的可筛选属性。](https://go.microsoft.com/fwlink/p/?LinkId=784903) <br/><br/>**邮箱内容筛选：** 这种类型的筛选器应用于可搜索的内容。 它指定分配用户可以搜索的邮箱内容。 这种类型的筛选器的语法是**邮箱Content_** _可搜索属性名称：value_，其中_可搜索属性名称_指定可在内容搜索中指定的关键字查询语言 （KQL） 属性。 例如，邮箱内容筛选器`MailboxContent_recipients:contoso.com`将允许分配此筛选器的用户仅搜索发送到contoso.com域中的收件人的邮件。  有关可搜索邮件属性的列表，请参阅[内容搜索的关键字查询。](keyword-queries-and-search-conditions.md) <br/><br/>**网站和网站内容筛选：** 有两个 SharePoint 和 OneDrive 用于业务网站相关筛选器，可用于指定分配用户可以搜索的网站或网站内容： <br/><br/>- **站点****可搜索网站属性* <br/>- **网站内容**=*可搜索网站属性*<br/><br/>这两个过滤器是可互换的。 例如，`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`并`"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`返回相同的结果。 但是，为了帮助您确定筛选器的作用，可以使用`Site_`指定与网站相关的属性（如网站 URL）和`SiteContent_`指定与内容相关的属性（如文档类型）。 例如，筛选器`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`将允许用户分配此筛选器以仅搜索https://contoso.spoppe.com/sites/doctors网站集中的内容。 筛选器`"SiteContent_FileExtension -eq 'docx'"`将允许分配此筛选器的用户仅搜索 Word 文档（Word 2007 及更高版本）。  <br/><br/>有关可搜索网站属性的列表，请参阅[SharePoint 中已爬网和托管属性的概述。](https://go.microsoft.com/fwlink/p/?LinkId=331599) **在"可查询"** 列中**标记为"是"** 的属性可用于创建网站或网站内容筛选器。 <br/><br/>          |
| _Users_|_"用户"_ 参数指定将此筛选器应用于其内容搜索的用户。 由于这是一个多值属性，因此使用此参数指定用户或用户组覆盖现有用户列表。 有关添加和删除所选用户的语法，请参阅以下示例。 <br/><br/>_您还可以使用"用户"_ 参数指定安全&合规性中心角色组。 這可讓您建立自訂角色群組，然後為該角色群組指派搜尋權限篩選器。 例如，假設您有多國公司的美國子公司的 eDiscovery 管理員的自訂角色群組。 可以使用_Users_参数指定此角色组（通过使用角色组的 Name 属性），然后使用_Filter_参数只允许搜索美国中的邮箱。 <br/><br/>使用此參數，無法指定通訊群組。 |

## <a name="examples-of-changing-search-permissions-filters"></a>更改搜索权限筛选器的示例

这些示例演示如何使用**获取合规性安全筛选器**和**设置合规性安全筛选器**cmdlet 将用户添加到筛选器分配到的现有用户列表中。 當您新增或移除篩選器的使用者時，使用其 SMTP 位址指定使用者。 
  
此範例會將使用者新增至篩選器。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```
```
$filterusers.users.add("pilarp@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
   
此範例會從篩選器移除使用者。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```
$filterusers.users.remove("annb@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
  
## <a name="remove-compliancesecurityfilter"></a>删除合规性安全筛选器

**删除合规性安全筛选器**用于删除搜索筛选器。 使用"_筛选名称"_ 参数指定要删除的筛选器。 
  
## <a name="more-information"></a>其他資訊

- **搜尋權限篩選如何運作？** 當執行內容搜尋時，權限篩選器會新增至搜尋查詢。 权限筛选器由**and**布尔运算符加入到搜索查询。 例如，您有一个权限筛选器，允许 Bob 对工作人员通讯组成员的邮箱执行所有搜索操作。 然后，Bob 使用搜索查询`sender:jerry@adatum.com`对组织中的所有邮箱运行内容搜索。 由于权限筛选器和搜索查询由**AND**运算符逻辑组合，因此搜索将返回jerry@adatum.com发送到工作人员组的任何成员的任何消息。 
    
- **如果您有多個搜尋權限篩選器會發生什麼情況？** 在內容搜尋查詢中，多個權限篩選器會藉由 **OR** 布林運算子合併。 因此任何篩選器為 true，則會傳回結果。 在內容搜尋中，所有篩選器 (由 **OR** 運算子合併) 隨後會與 **AND** 運算子的搜尋查詢合併。 让我们以前面的示例为例，其中搜索筛选器允许 Bob 仅搜索工作人员通讯组成员的邮箱。 然後我們建立另一個篩選器，防止 Bob 搜尋 Phil 的信箱 ("Mailbox_Alias -ne 'Phil'")。 同時假設 Phil 是 Workers 群組的成員。 当 Bob 在组织中的所有邮箱上运行内容搜索（从上一个示例中），即使您应用了筛选器来阻止 Bob 搜索 Phil 的邮箱，也会为 Phil 的邮箱返回搜索结果。 原因是允許 Bob 搜尋 Workers 群組的第一個篩選器為 true。 且由於 Phil 是 Workers 群組的成員，因此 Bob 可搜尋 Phil 的信箱。 
    
- **搜索权限筛选是否适用于非活动邮箱？** 可以，您可以使用邮箱和邮箱内容筛选器来限制谁可以搜索组织中的非活动邮箱。 与常规邮箱一样，非活动邮箱必须配置用于创建权限筛选器的收件人属性。 如有必要，**可以使用"获取邮箱 -非活动邮箱Only"** 命令来显示非活动邮箱的属性。 有关详细信息，请参阅在[Office 365 中创建和管理非活动邮箱。](create-and-manage-inactive-mailboxes.md)
    
- **搜索权限筛选是否适用于公用文件夹？** 否。 如前所述，搜索权限筛选不能用于限制谁可以在 Exchange 中搜索公用文件夹。 例如，权限筛选器无法将公用文件夹位置中的项目从搜索结果中排除。 
    
- **允许用户搜索特定服务中的所有内容位置是否也会阻止他们搜索其他服务中的内容位置？** 否。 如前所述，您必须创建搜索权限筛选器，以显式阻止用户搜索特定 Office 365 服务中的内容位置（例如阻止用户搜索任何 Exchange 邮箱或任何 SharePoint 网站）。 换句话说，创建允许用户搜索组织中的所有 SharePoint 网站的搜索权限筛选器不会阻止该用户搜索邮箱。 例如，要允许 SharePoint 管理员仅搜索 SharePoint 网站，必须创建一个筛选器，以防止他们搜索邮箱。 同样，要允许 Exchange 管理员仅搜索邮箱，您必须创建一个筛选器，以防止他们搜索网站。
