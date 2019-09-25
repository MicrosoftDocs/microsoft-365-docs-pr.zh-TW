---
title: 建立 DLP 原則來保護具有 FCI 或其他屬性的文件
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 许多组织已经使用 Windows 服务器文件分类基础结构 （FCI）、SharePoint 中的文档属性或文档属性中的分类属性来识别和分类敏感信息由第三方系统应用。 如果这描述了您的组织，则可以在 Office 365 中创建 DLP 策略，该策略可识别 Windows Server FCI 或其他系统已应用于文档的属性，以便可以在具有特定 FCI 或其他功能的 Office 文档上强制实施 DLP 策略属性值。
ms.openlocfilehash: 5f464c2918d7ea91fa5c65b28bc477ee7cc768e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077810"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>建立 DLP 原則來保護具有 FCI 或其他屬性的文件

在 Office 365 中，可以使用数据丢失防护 （DLP） 策略来标识、监视和保护敏感信息。 许多组织已经使用 Windows 服务器文件分类基础结构 （FCI）、SharePoint 中的文档属性或文档属性中的分类属性来识别和分类敏感信息由第三方系统应用。 如果这描述了您的组织，则可以在 Office 365 中创建 DLP 策略，该策略可识别 Windows Server FCI 或其他系统已应用于文档的属性，以便可以在具有特定 FCI 或其他功能的 Office 文档上强制实施 DLP 策略属性值。
  
![圖表顯示 Office 365 及外部的分類系統](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
例如，您的组织可能使用 Windows Server FCI 来标识包含个人身份信息 （PII） 的文档（如社会保险号），然后通过设置**个人身份信息**对文档进行分类属性**为"高、****中、****低、****公共"****或"不是 PII"，** 具体取决于文档中的 PII 发生类型和次数。 在 Office 365 中，您可以创建一个 DLP 策略，用于标识将该属性设置为特定值（**如"高"** 和"**中"）** 的文档，然后执行阻止访问这些文件等操作。 如果属性设置为**Low，** 则同一策略可以具有另一个执行不同操作的规则，例如发送电子邮件通知。 通过这种方式，Office 365 中的 DLP 与 Windows 服务器 FCI 集成，并可帮助保护从基于 Windows 服务器的文件服务器上载或共享到 Office 365 的 Office 文档。
  
DLP 策略只需查找特定的属性名称/值对。 只要该属性具有用于 SharePoint 搜索的相应托管属性，就可以使用任何文档属性。 例如，SharePoint 网站集可能使用**名为"行程报告"** 的内容类型，其必填字段名为"**客户"。** 每当有人创建行程报告时，他们必须输入客户姓名。 此属性名称/值对也可以在 DLP 策略中使用 ， 例如，如果想要一个规则，**在"客户"** 字段包含**Contoso**时阻止外部用户对文档的访问。
  
请注意，如果要将 DLP 策略应用于具有特定 Office 365 标签的内容，则不应执行此处的步骤。 相反，了解如何在[DLP 策略中使用标签作为条件。](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)
  
## <a name="before-you-create-the-dlp-policy"></a>创建 DLP 策略之前

在 DLP 策略中使用 Windows Server FCI 属性或其他属性之前，需要在 SharePoint 管理中心中创建托管属性。 原因如下。
  
在 SharePoint 在线和 OneDrive 业务中，搜索索引是通过对网站上的内容进行爬网而建立的。 爬网程序以已爬网属性的形式从文档中拾取内容和元数据。 搜索架构可帮助爬网程序决定要选取的内容和元数据。 元数据的示例包括文档的作者和标题。 但是，要将内容和元数据从文档获取到搜索索引中，必须将爬网属性映射到托管属性。 只有托管属性保留在索引中。 例如，与作者相关的爬网属性映射到与作者相关的托管属性。
  
这一点很重要，因为 Office 365 中的 DLP 使用搜索爬网程序来标识和分类网站上的敏感信息，然后将该敏感信息存储在搜索索引的安全部分。 将文档上载到 Office 365 时，SharePoint 会根据文档属性自动创建已爬网的属性。 但是，要在 DLP 策略中使用 FCI 或其他属性，需要将爬网属性映射到托管属性，以便将包含该属性的内容保留在索引中。
  
有关搜索和托管属性的详细信息，请参阅在[SharePoint Online 中管理搜索架构。](http://go.microsoft.com/fwlink/p/?LinkID=627454)
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>步骤 1：将包含所需属性的文档上载到 Office 365

您首先需要上传包含要在 DLP 策略中引用的属性的文档。 Office 365 将检测该属性，并自动从该属性创建已爬网的属性。 在下一步中，您将创建一个托管属性，然后将托管属性映射到此已爬网属性。
  
### <a name="step-2-create-a-managed-property"></a>步骤 2：创建托管属性

1. 登录到 Microsoft 365 管理中心。
    
2. 在左侧导航中，选择**管理中心**\> **SharePoint**。 You're now in the SharePoint admin center.
    
3. 在左侧导航中，在**搜索管理**\>**页面"管理搜索架构"** 中选择**搜索。** \>
    
    ![SharePoint 系統管理中心的搜尋管理頁面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. 在"**托管属性"** 页上\>**新建托管属性**。
    
    ![受管理屬性頁面上有以反白顯示的新增受管理的屬性按鈕](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. 输入属性的名称和说明。 此名称将显示在 DLP 策略中。
    
6. **对于"类型"，****选择"文本"。** 
    
7. 在**主要特征**下，**选择"可查询**和**可检索"。**
    
8. **在"映射到已爬网属性"**\>下**添加映射。**
    
9. 在**已爬网的属性选择**对话框\>中查找并选择与 Windows Server FCI 属性或将在 DLP\>**策略中**要使用的其他属性对应的已爬网属性。
    
    ![選取編目屬性對話方塊](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. 在页面\>底部**确定**。
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>创建使用 FCI 属性或其他属性的 DLP 策略

在此示例中，组织在其基于 Windows 服务器的文件服务器上使用 FCI;因此，组织正在使用 FCI。具体来说，他们使用的是**名为"个人身份信息"** 的FCI分类属性，其可能值**为"高、****中、****低、****公共"****和"不是PII"。** 现在，他们希望在 Office 365 中的 DLP 策略中利用其现有的 FCI 分类。
  
首先，他们按照上述步骤在 SharePoint Online 中创建托管属性，该属性映射到从 FCI 属性自动创建的已爬网属性。
  
接下来，他们创建一个 DLP 策略，其中包含两个规则，这两个规则都使用条件**文档属性包含这些值中的任何一个：**
  
- **FCI PII 内容 - 高、中**如果 FCI 分类**属性"个人可识别信息"****等于"高"** 或"**中**度"，并且文档与组织外部人员共享，则第一条规则将限制对文档的访问。 
    
- **FCI PII 内容 - 低**如果 FCI 分类**属性"个人可识别信息"****等于"低"，** 并且文档与组织外部人员共享，则第二个规则会向文档所有者发送通知。 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>使用 PowerShell 创建 DLP 策略

请注意，**包含这些值的条件文档属性**在安全&amp;合规性中心的 UI 中暂时不可用，但您仍可以使用 PowerShell 使用此条件。 您可以使用`New\Set\Get-DlpCompliancePolicy`cmdlet 处理 DLP 策略，并使用带有`New\Set\Get-DlpComplianceRule``ContentPropertyContainsWords`参数的 cmdlet 添加**包含这些值中的任何一个条件文档属性。**
  
有关这些 cmdlet 的详细信息，请参阅[Office 365&amp;安全合规性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。
  
1. [使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用`New-DlpCompliancePolicy`创建策略。
    
    下面是一个 PowerShell 示例，该示例创建适用于所有位置的 DLP 策略。
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. 使用`New-DlpComplianceRule`创建上述两个规则，其中一条规则**用于"低"** 值，另一个规则**用于"高"** 和"**中值"。** 
    
    下面是创建这两个规则的 PowerShell 示例。 请注意，属性名称/值对以引号括起来，属性名称可以指定多个用逗号分隔的不带空格的值，例如`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    请注意，Windows Server FCI 包含许多内置属性，包括此示例中使用的**个人身份信息。** 每个属性的可能值对于每个组织可能不同。 此处**使用的"高、****中"** 和"**低"** 值仅是一个示例。 对于您的组织，您可以在基于 Windows 服务器的文件服务器上的文件服务器资源管理器中查看 Windows Server FCI 分类属性及其可能的值。 有关详细信息，请参阅[创建分类属性](http://go.microsoft.com/fwlink/p/?LinkID=627456)。
    
完成后，策略应具有两个新规则，这两个新规则都使用**Document 属性，其中包含任何这些值**条件。 请注意，此条件不会显示在 UI 中，但将显示其他条件、操作和设置。 
  
一条规则阻止访问个人**可识别信息**属性**等于"高"****或"中**度"的内容。 第二个规则发送有关个人**可识别信息**属性**等于"低"** 的内容的通知。
  
![新的 DLP 原則對話方塊顯示剛才建立的兩個規則](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>创建 DLP 策略后

执行前几节中的步骤将创建一个 DLP 策略，该策略将快速检测包含该属性的内容，但前提是该内容是新上载的（以便内容已编制索引），或者如果该内容已旧但刚刚编辑（以便内容重新编制索引）.
  
要在任何地方检测包含该属性的内容，您可能需要手动请求重新编制库、网站或网站集索引，以便 DLP 策略了解该属性的所有内容。 在 SharePoint Online 中，内容将根据定义的爬网计划自动爬网。 爬网程序选取自上次爬网以来已更改的内容并更新索引。 如果您需要 DLP 策略在下一次计划爬网之前保护内容，可以执行这些步骤。
  
> [!CAUTION]
> 重新索引站点可能会导致搜索系统上的负载很大。 除非方案绝对需要，否则不要重新索引您的网站。 
  
有关详细信息，请参阅[手动请求对站点、库或列表进行爬网和重新编制索引。](http://go.microsoft.com/fwlink/p/?LinkID=627457)
  
### <a name="re-index-a-site-optional"></a>重新索引站点（可选）

1. 在网站上，**选择"设置"（** 右上角的齿轮图标）\>**站点设置**。
    
2. 在"**搜索"** 下，**选择"搜索和脱机可用性**\>**重新索引网站"。**
    
## <a name="more-information"></a>詳細資訊

- [資料外洩防護原則概觀](data-loss-prevention-policies.md)
    
- [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)
    
- [发送通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
    
- [DLP 原則範本包含哪些內容](what-the-dlp-policy-templates-include.md)
    
- [敏感信息类型清单](what-the-sensitive-information-types-look-for.md)
    

