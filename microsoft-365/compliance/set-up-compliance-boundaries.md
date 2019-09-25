---
title: 設定 Office 365 中電子文件探索調查的合規性界限
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 使用合规性边界在 Office 365 组织中创建逻辑边界，以控制电子数据展示经理可以搜索的用户内容位置。 合规性边界使用搜索权限筛选（也称为合规性安全筛选器）来控制特定用户可以搜索的邮箱、SharePoint 站点和 OneDrive 帐户。
ms.openlocfilehash: 1e87926910ad7dd356696368ad6759bfacfe37c2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077391"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>設定 Office 365 中電子文件探索調查的合規性界限

合规性边界在 Office 365 组织内创建逻辑边界，控制电子数据展示经理可以搜索的用户内容位置（如邮箱、SharePoint 站点和 OneDrive 帐户）。 此外，合规性边界控制谁可以访问用于管理组织内的法律、人力资源或其他调查的电子邮件数据案例。 对于必须尊重地域董事会和条例的跨国公司和政府来说，遵守边界往往是必要的，因为政府往往被划分为不同的机构。 在 Office 365 中，合规性边界可帮助您在使用电子数据展示案例执行内容搜索和管理调查时满足这些要求。
  
我们使用下图中的示例来解释合规性边界的工作原理。
  
![合规性边界由搜索权限筛选器组成，这些筛选器控制对控制对电子数据展示案例的访问的机构和管理角色组的访问](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
在此示例中，Contoso LTD 是一个 Office 365 组织，由两个子公司，第四咖啡和科霍酒厂组成。 业务要求电子数据展示经理和调查人员只能搜索其代理中的 Exchange 邮箱、OneDrive 帐户和 SharePoint 网站。 此外，电子数据展示经理和调查人员只能在其代理中看到电子数据展示案例，并且他们只能访问他们所参与的案例。 以下是合规性边界如何满足这些要求。
  
- 内容搜索中的搜索权限筛选功能控制电子数据展示经理和调查人员可以搜索的内容位置。 这意味着第四咖啡机构中的电子数据展示经理和调查人员只能搜索第四咖啡子公司的内容位置。 同样的限制也适用于科霍酒厂的子公司。
    
    角色组控制谁可以在安全&合规中心中查看电子数据展示案例。 这意味着电子数据展示经理和调查人员只能在其机构中看到电子数据展示案例。
    
- 角色组还控制谁可以将成员分配到电子数据展示案例。 这意味着电子数据展示经理和调查人员只能将成员分配到他们自己属于的案件。
    
以下是设置合规性边界的过程：
  
[第 1 步：标识用户属性以定义您的机构](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步骤 2： 向 Microsoft 支持提交请求，将用户属性同步到 OneDrive 帐户](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[第 3 步：为每个机构创建角色组](#step-3-create-a-role-group-for-each-agency)

[步骤 4：创建搜索权限筛选器以强制执行合规性边界](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[第 5 步：为机构内调查创建电子数据展示案例](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>第 1 步：标识用户属性以定义您的机构

第一步是选择一个 Azure 活动目录属性，用于定义您的机构。 此属性用于创建搜索权限筛选器，该筛选器将电子数据展示管理器限制为仅搜索为此属性分配特定值的用户的内容位置。 例如，假设 Contoso 决定**使用"部门"** 属性。 第四咖啡子公司中用户的属性值为`FourthCoffee`， Coho 酒厂子公司的用户值为`CohoWinery`。 在步骤 4 中，`attribute:value`使用此对（例如，*部门：第四个咖啡店）* 来限制电子数据展示管理器可以搜索的用户内容位置。 
  
下面是可用于合规性边界的 Azure 活动目录用户属性的列表：
  
- Company
    
- 自定义属性1 = 自定义属性15
    
- 部門
    
- 辦公室

- C（两个字母的国家代码）
    
尽管有更多的用户属性可用，特别是对于 Exchange 邮箱，但上面列出的属性是 OneDrive 目前唯一支持的属性。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步骤 2： 向 Microsoft 支持提交请求，将用户属性同步到 OneDrive 帐户

下一步是向 Microsoft 支持机构提交请求，以将步骤 1 中选择的 Azure 活动目录属性同步到组织中的所有 OneDrive 帐户。 发生此同步后，您在步骤 1 中选择的属性（及其值）将映射到名为`ComplianceAttribute`的 SharePoint 中的隐藏托管属性。 使用此属性在步骤 4 中为 OneDrive 创建搜索权限筛选器。
  
向 Microsoft 支持人员提交请求时，请包括以下信息：
  
- Office 365 组织的默认域名
    
- Azure 活动目录属性的名称（从步骤 1 中）
    
- 支持请求用途的以下标题或说明："启用与 Azure 活动目录进行业务同步的 OneDrive，以便获得符合性安全筛选器"。 这有助于将请求路由到实现该请求的 Office 365 电子数据展示工程团队。
    
进行工程更改并将属性同步到 OneDrive 后，Microsoft 支持将向您发送进行更改的生成号和估计的部署日期。 在提交支持请求后，部署过程通常需要 4 到 6 周。
  
 **重要提示：** 在部署更改之前，可以完成步骤 3 到步骤 5。 但是，在部署更改之前，运行内容搜索不会返回搜索权限筛选器中指定的 OneDrive 网站的文档。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>第 3 步：为每个机构创建角色组

下一步是在安全&合规中心创建与您的机构保持一致的角色组。 我们建议您通过复制内置电子数据展示管理器组、添加适当的成员以及删除可能不适用于您的需要的角色来创建角色组。 有关与电子数据展示相关角色的详细信息，请参阅[在 Office 365 安全&合规性中心中分配电子数据展示权限。](assign-ediscovery-permissions.md)
  
要创建角色组，请转到"安全&合规**中心"中的"权限"** 页，并为每个机构中将使用合规性边界和电子数据展示案例来管理调查的每个团队创建一个角色组。 
  
使用 Contoso 合规性边界方案，需要创建四个角色组，并将相应的成员添加到每个角色组中。
  
- 第四位咖啡电子展示经理
    
- 第四咖啡调查员
    
- 科霍酒厂电子展示经理
    
- 科霍酒厂调查员
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步骤 4：创建搜索权限筛选器以强制执行合规性边界

为每个代理创建角色组后，下一步是创建搜索权限筛选器，将每个角色组与其特定代理相关联并定义合规性边界本身。 您需要为每个机构创建一个搜索权限筛选器。 有关创建安全权限筛选器的详细信息，请参阅[为内容搜索配置权限筛选。](permissions-filtering-for-content-search.md)
  
下面是用于创建用于合规性边界的搜索权限筛选器的语法。

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```
  
下面是命令中每个参数的说明：
  
-  `FilterName`：指定筛选器的名称。 使用描述或标识筛选器所使用的代理的名称。 
    
-  `Users`：指定将此筛选器应用于他们执行的内容搜索操作的用户或组。 对于符合性边界，此参数指定要为其创建筛选器的机构中创建的角色组（在步骤 3 中创建）。 请注意，这是一个多值参数，因此您可以包括一个或多个角色组，用逗号分隔。 
    
-  `Filters`：指定筛选器的搜索条件。 对于符合性边界，您可以定义以下筛选器。 每个都适用于内容位置。 
    
    -  `Mailbox`：指定`Users`参数中定义的角色组可以搜索的邮箱。 对于合规性边界，*合规性属性*与您在步骤 1 中标识的属性相同，*属性值*指定代理。 此筛选器允许角色组的成员仅搜索特定机构中的邮箱;例如， `"Mailbox_Department -eq 'FourthCoffee'"`. 
    
    -  `Site`：指定`Users`参数中定义的角色组可以搜索的 OneDrive 帐户。 对于 OneDrive 筛选器，请使用实际字符串`ComplianceAttribute`。 这将映射到您在步骤 1 中标识的相同属性，该属性由于您在步骤 2 中提交的支持请求而同步到 OneDrive 帐户;*属性值*指定代理。 此筛选器允许角色组的成员仅搜索特定机构中的 OneDrive 帐户;例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.
    
    -  `Site_Path`：指定`Users`参数中定义的角色组可以搜索的 SharePoint 站点。 *SharePointURL*指定角色组成员可以搜索的代理中的站点。 例如，  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 请注意`Site`，`Site_Path`和 筛选器由 **- 或**运算符连接。
    
     > [!NOTE]
     > 参数`Filters`的语法包括*筛选器列表。* 筛选器列表是一个筛选器，其中包括邮箱筛选器和由逗号分隔的站点筛选器。 在前面的示例中，请注意逗号分隔**邮箱_合规性属性**和**站点_合规性属性**： `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"`。 在运行内容搜索期间处理此筛选器时，将从筛选器列表中创建两个搜索权限筛选器：一个邮箱筛选器和一个站点筛选器。 使用筛选器列表的替代方法是为每个代理创建两个单独的搜索权限筛选器：一个邮箱属性的搜索权限筛选器和一个站点属性的筛选器。 在这两种情况下，结果都是一样的。 使用筛选器列表或创建单独的搜索权限筛选器是一个首选项。

-  `Action`：指定筛选器应用于的符合性搜索操作的类型。 例如，仅当`-Action Search``Users`参数中定义的角色组成员运行内容搜索时，才会应用筛选器。 在这种情况下，在导出搜索结果时不会应用筛选器。 对于符合性边界，请使用，`-Action All`以便筛选器应用于所有搜索操作。 
    
    有关内容搜索操作的列表，[请参阅"内容搜索配置权限筛选"](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的"新合规性安全筛选"部分。

下面是为支持 Contoso 合规性边界方案而创建的两个搜索权限筛选器的示例。 这两个示例都包括逗号分隔的筛选器列表，其中邮箱和站点筛选器包含在相同的搜索权限筛选器中，并用逗号分隔。
  
 **第四杯咖啡**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **科霍酒厂**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>第 5 步：为机构内部调查创建电子数据展示案例

最后一步是在安全&合规中心创建电子数据展示案例，然后将您在步骤 3 中创建的角色组添加为案例成员。 这就产生了使用合规性边界的两个重要特征：
  
- 只有添加到案例的角色组成员才能在安全&合规中心查看和访问案例。 例如，如果第四个咖啡调查员角色组是案例的唯一成员，则第四个咖啡电子数据展示经理角色组的成员（或任何其他角色组的成员）将无法查看或访问案例。
    
- 当分配给案例的角色组的成员运行与案例关联的搜索时，他们只能搜索其代理内的内容位置（由您在步骤 4 中创建的搜索权限筛选器定义）。

要创建案例并分配成员，请：
    
1. 转到安全&合规中心**中的电子数据展示**页面并创建案例。 
    
2. 在电子数据展示案例列表中，单击您创建的案例的名称。
    
3. 在"**管理这种情况"** 弹出窗口页中，**在"管理角色组"**![下，](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)单击"添加"**图标"添加**"。
    
    ![将角色组添加为电子数据展示案例的成员](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 在角色组列表中，选择在步骤 3 中创建的角色组之一，然后单击"**添加"。**
    
5. 单击"**在管理此案例**弹出窗口上**保存"** 以保存更改。 

## <a name="compliance-boundary-limitations"></a>合规性边界限制

在管理使用合规性边界的第一个数据展示案例和调查时，请记住以下限制。
  
- 创建和运行内容搜索时，您可以选择机构外部的内容位置。 但是，由于搜索权限筛选器，来自这些位置的内容不会包含在搜索结果中。
    
- 合规性边界不适用于电子数据展示案例中的保留。 这意味着一个机构中的电子数据展示经理可以将另一个机构中的用户置于保留状态。 但是，如果电子数据展示管理器搜索被置于保留状态的用户的内容位置，则将强制执行合规性边界。 这意味着电子数据展示管理器将无法搜索用户的内容位置，即使他们能够将用户置于保留状态。
    
    此外，保留统计信息仅适用于机构中的内容位置。
    
- 搜索权限筛选器不应用于 Exchange 公用文件夹。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>在多地理位置环境中搜索和导出内容

搜索权限筛选器还允许您控制在[SharePoint 多地理位置环境中](https://go.microsoft.com/fwlink/?linkid=860840)搜索内容位置时，内容的路由位置以及可以搜索哪个数据中心。
  
- **导出搜索结果：** 可以从特定数据中心导出 Exchange 邮箱、SharePoint 站点和 OneDrive 帐户的搜索结果。 这意味着您可以指定搜索结果将从中导出的数据中心位置。

    使用"**区域"** 参数进行**新合规性安全筛选器**或**设置合规性安全筛选器**cmdlet 创建或更改导出将路由到的数据中心。
  
    |**參數值**|**数据中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美（数据中心位于美国）  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN <br/> |加拿大|
    |||
    
- **路由内容搜索：** 您可以将 SharePoint 网站和 OneDrive 帐户的内容搜索路由到卫星数据中心。 这意味着您可以指定将运行搜索的数据中心位置。
    
    **对"区域"** 参数使用以下值之一来控制搜索 SharePoint 站点和 OneDrive 帐户时将运行的数据中心位置。 
  
    |**參數值**|**SharePoint 的数据中心路由位置**|
    |:-----|:-----|
    |NAM  <br/> |我们  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN  <br/> |我们  <br/> |
    |AUS  <br/> |亞太地區  <br/> |
    |KOR  <br/> |组织的默认数据中心  <br/> |
    |GBR  <br/> |歐洲  <br/> |
    |JPN  <br/> |亞太地區  <br/> |
    |IND  <br/> |亞太地區  <br/> |
    |议员  <br/> |我们  <br/> |
    |||

   如果不为搜索权限筛选器**指定"区域"** 参数，则将搜索组织的默认 SharePoint 区域。 搜索结果将导出到最近的数据中心。

> [!TIP]
> 为了简化概念，**区域**参数控制用于在 SharePoint 和 OneDrive 中搜索内容的数据中心。 这不适用于在 Exchange 中搜索内容，因为 Exchange 内容搜索不受数据中心地理位置的约束。 此外，相同的**Region**参数值也可能指示导出的数据中心通过。 这通常是控制数据在地理棋盘之间移动所必需的。<br/><br/>如果您使用的是高级电子数据展示，则在 SharePoint 和 OneDrive 中搜索内容不受数据中心地理位置的约束。 搜索所有数据中心。 有关高级电子数据展示的详细信息，请参阅[Microsoft 365 中高级电子数据展示解决方案的概述。](overview-ediscovery-20.md)

以下是在为合规性边界创建搜索权限筛选器时**使用"区域"** 参数的示例。 这假定第四咖啡子公司位于北美，科霍酒厂位于欧洲。 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
在多地理位置环境中搜索和导出内容时，请记住以下事项。
  
- **"区域"** 参数不控制 Exchange 邮箱的搜索。 搜索邮箱时将搜索所有数据中心。 要限制搜索 Exchange 邮箱的范围，请使用**筛选器**参数在创建或更改搜索权限筛选器时。 
    
- 如果电子数据展示管理器需要跨多个 SharePoint 区域进行搜索，则需要为该电子数据展示管理器创建一个不同的用户帐户，以便在搜索权限筛选器中指定 SharePoint 网站或 OneDrive 的区域帐户的位置。 有关设置此设置的详细信息，请参阅[Office 365 中的内容搜索中的"](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)在 SharePoint 多地理位置环境中搜索内容"部分。
    
- 在 SharePoint 和 OneDrive 中搜索内容时，"**区域"** 参数会将搜索定向到电子数据展示管理器将执行电子数据展示调查的主位置或卫星位置。 如果电子数据展示管理器在搜索权限筛选器中指定的区域之外搜索 SharePoint 和 OneDrive 网站，则不返回任何搜索结果。 
    
- 导出搜索结果时，来自所有内容位置的内容（包括 Exchange、Skype 业务、SharePoint、OneDrive 和其他可以使用内容搜索工具搜索的 Office 365 服务）将上载到 中的 Azure 存储位置。**由"区域"** 参数指定的数据中心。 这帮助组织通过不允许跨受控边界导出内容来保持合规性。 如果在搜索权限筛选器中未指定区域，则内容将上载到组织的默认区域。 
    
- 您可以通过运行以下命令编辑现有搜索权限筛选器以添加或更改区域：

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>常見問題集

 **谁可以创建和管理搜索权限筛选器（使用新合规性安全筛选器和设置合规性安全筛选器 cmdlet）？**
  
要创建、查看和修改搜索权限筛选器，您必须是安全&合规性中心中的组织管理角色组的成员。
  
 **如果电子数据展示经理被分配到多个跨多个机构的角色组，他们如何在一个机构或另一个机构中搜索内容？**
  
电子数据展示管理器可以向其搜索查询添加参数，将搜索限制为特定机构。 例如，如果组织指定**了 CustomAttribute10**属性来区分代理，则可以将以下内容追加到搜索查询中，以搜索特定代理中的邮箱和 OneDrive 帐户： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。
  
 **如果用作搜索权限筛选器中的符合性属性的属性的值发生更改，会发生什么情况？**
  
如果筛选器中使用的属性的值发生更改，则搜索权限筛选器最多需要三天时间才能强制执行符合性边界。 例如，在 Contoso 场景中，假设第四咖啡代理公司中的用户被转移到 Coho 酒厂代理。 因此，用户对象**上的"部门"** 属性的值*从"第四咖啡"* 更改为*CohoWinery*。 在这种情况下，第四咖啡电子数据展示和投资者将获得该用户的搜索结果后三天，属性被更改。 同样，科霍酒厂电子数据展示经理和调查人员最多需要三天时间才能为用户获取搜索结果。 
  
 **电子数据展示经理能否查看来自两个独立合规性边界的内容？**
  
是。 这可以通过将用户添加到对两个机构具有可见性的角色组来实现。
  
 **搜索权限筛选器是否适用于电子数据展示案例保留、Office 365 保留策略或 DLP？**
  
不，现在不。
  
 **如果我指定一个区域来控制内容的导出位置，但该区域中没有 SharePoint 组织，我是否可以搜索 SharePoint？**
  
如果组织中不存在搜索权限筛选器中指定的区域，则将搜索默认区域。
  
 **可在组织中创建的搜索权限筛选器的最大数量是多少？**
  
可以在组织中创建的搜索权限筛选器的数量没有限制。 但是，当有超过 100 个搜索权限筛选器时，搜索性能将受到影响。 要使组织中的搜索权限筛选器数量尽可能小，请创建筛选器，尽可能将 Exchange、SharePoint 和 OneDrive 的规则合并到单个搜索权限筛选器中。
