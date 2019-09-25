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
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="cf70d-104">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="cf70d-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="cf70d-105">在 Office 365 中，可以使用数据丢失防护 （DLP） 策略来标识、监视和保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="cf70d-105">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information.</span></span> <span data-ttu-id="cf70d-106">许多组织已经使用 Windows 服务器文件分类基础结构 （FCI）、SharePoint 中的文档属性或文档属性中的分类属性来识别和分类敏感信息由第三方系统应用。</span><span class="sxs-lookup"><span data-stu-id="cf70d-106">Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system.</span></span> <span data-ttu-id="cf70d-107">如果这描述了您的组织，则可以在 Office 365 中创建 DLP 策略，该策略可识别 Windows Server FCI 或其他系统已应用于文档的属性，以便可以在具有特定 FCI 或其他功能的 Office 文档上强制实施 DLP 策略属性值。</span><span class="sxs-lookup"><span data-stu-id="cf70d-107">If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![圖表顯示 Office 365 及外部的分類系統](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="cf70d-109">例如，您的组织可能使用 Windows Server FCI 来标识包含个人身份信息 （PII） 的文档（如社会保险号），然后通过设置**个人身份信息**对文档进行分类属性**为"高、\*\*\*\*中、\*\*\*\*低、\*\*\*\*公共"\*\*\*\*或"不是 PII"，** 具体取决于文档中的 PII 发生类型和次数。</span><span class="sxs-lookup"><span data-stu-id="cf70d-109">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document.</span></span> <span data-ttu-id="cf70d-110">在 Office 365 中，您可以创建一个 DLP 策略，用于标识将该属性设置为特定值（**如"高"** 和"**中"）** 的文档，然后执行阻止访问这些文件等操作。</span><span class="sxs-lookup"><span data-stu-id="cf70d-110">In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="cf70d-111">如果属性设置为**Low，** 则同一策略可以具有另一个执行不同操作的规则，例如发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="cf70d-111">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="cf70d-112">通过这种方式，Office 365 中的 DLP 与 Windows 服务器 FCI 集成，并可帮助保护从基于 Windows 服务器的文件服务器上载或共享到 Office 365 的 Office 文档。</span><span class="sxs-lookup"><span data-stu-id="cf70d-112">In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="cf70d-113">DLP 策略只需查找特定的属性名称/值对。</span><span class="sxs-lookup"><span data-stu-id="cf70d-113">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="cf70d-114">只要该属性具有用于 SharePoint 搜索的相应托管属性，就可以使用任何文档属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-114">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="cf70d-115">例如，SharePoint 网站集可能使用**名为"行程报告"** 的内容类型，其必填字段名为"**客户"。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-115">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="cf70d-116">每当有人创建行程报告时，他们必须输入客户姓名。</span><span class="sxs-lookup"><span data-stu-id="cf70d-116">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="cf70d-117">此属性名称/值对也可以在 DLP 策略中使用 ， 例如，如果想要一个规则，**在"客户"** 字段包含**Contoso**时阻止外部用户对文档的访问。</span><span class="sxs-lookup"><span data-stu-id="cf70d-117">This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="cf70d-118">请注意，如果要将 DLP 策略应用于具有特定 Office 365 标签的内容，则不应执行此处的步骤。</span><span class="sxs-lookup"><span data-stu-id="cf70d-118">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="cf70d-119">相反，了解如何在[DLP 策略中使用标签作为条件。](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)</span><span class="sxs-lookup"><span data-stu-id="cf70d-119">Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="cf70d-120">创建 DLP 策略之前</span><span class="sxs-lookup"><span data-stu-id="cf70d-120">Before you create the DLP policy</span></span>

<span data-ttu-id="cf70d-121">在 DLP 策略中使用 Windows Server FCI 属性或其他属性之前，需要在 SharePoint 管理中心中创建托管属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-121">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="cf70d-122">原因如下。</span><span class="sxs-lookup"><span data-stu-id="cf70d-122">Here's why.</span></span>
  
<span data-ttu-id="cf70d-123">在 SharePoint 在线和 OneDrive 业务中，搜索索引是通过对网站上的内容进行爬网而建立的。</span><span class="sxs-lookup"><span data-stu-id="cf70d-123">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites.</span></span> <span data-ttu-id="cf70d-124">爬网程序以已爬网属性的形式从文档中拾取内容和元数据。</span><span class="sxs-lookup"><span data-stu-id="cf70d-124">The crawler picks up content and metadata from the documents in the form of crawled properties.</span></span> <span data-ttu-id="cf70d-125">搜索架构可帮助爬网程序决定要选取的内容和元数据。</span><span class="sxs-lookup"><span data-stu-id="cf70d-125">The search schema helps the crawler decide what content and metadata to pick up.</span></span> <span data-ttu-id="cf70d-126">元数据的示例包括文档的作者和标题。</span><span class="sxs-lookup"><span data-stu-id="cf70d-126">Examples of metadata are the author and the title of a document.</span></span> <span data-ttu-id="cf70d-127">但是，要将内容和元数据从文档获取到搜索索引中，必须将爬网属性映射到托管属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-127">However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties.</span></span> <span data-ttu-id="cf70d-128">只有托管属性保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="cf70d-128">Only managed properties are kept in the index.</span></span> <span data-ttu-id="cf70d-129">例如，与作者相关的爬网属性映射到与作者相关的托管属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-129">For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="cf70d-130">这一点很重要，因为 Office 365 中的 DLP 使用搜索爬网程序来标识和分类网站上的敏感信息，然后将该敏感信息存储在搜索索引的安全部分。</span><span class="sxs-lookup"><span data-stu-id="cf70d-130">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="cf70d-131">将文档上载到 Office 365 时，SharePoint 会根据文档属性自动创建已爬网的属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-131">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="cf70d-132">但是，要在 DLP 策略中使用 FCI 或其他属性，需要将爬网属性映射到托管属性，以便将包含该属性的内容保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="cf70d-132">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="cf70d-133">有关搜索和托管属性的详细信息，请参阅在[SharePoint Online 中管理搜索架构。](http://go.microsoft.com/fwlink/p/?LinkID=627454)</span><span class="sxs-lookup"><span data-stu-id="cf70d-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="cf70d-134">步骤 1：将包含所需属性的文档上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="cf70d-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="cf70d-135">您首先需要上传包含要在 DLP 策略中引用的属性的文档。</span><span class="sxs-lookup"><span data-stu-id="cf70d-135">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="cf70d-136">Office 365 将检测该属性，并自动从该属性创建已爬网的属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-136">Office 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="cf70d-137">在下一步中，您将创建一个托管属性，然后将托管属性映射到此已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-137">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="cf70d-138">步骤 2：创建托管属性</span><span class="sxs-lookup"><span data-stu-id="cf70d-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="cf70d-139">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="cf70d-139">Sign in to the Microsoft 365 admin center.</span></span>
    
2. <span data-ttu-id="cf70d-140">在左侧导航中，选择**管理中心**\> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="cf70d-140">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="cf70d-141">You're now in the SharePoint admin center.</span><span class="sxs-lookup"><span data-stu-id="cf70d-141">You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="cf70d-142">在左侧导航中，在**搜索管理**\>**页面"管理搜索架构"** 中选择**搜索。** \></span><span class="sxs-lookup"><span data-stu-id="cf70d-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![SharePoint 系統管理中心的搜尋管理頁面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="cf70d-144">在"**托管属性"** 页上\>**新建托管属性**。</span><span class="sxs-lookup"><span data-stu-id="cf70d-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![受管理屬性頁面上有以反白顯示的新增受管理的屬性按鈕](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="cf70d-146">输入属性的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="cf70d-146">Enter a name and description for the property.</span></span> <span data-ttu-id="cf70d-147">此名称将显示在 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="cf70d-147">This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="cf70d-148">**对于"类型"，\*\*\*\*选择"文本"。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="cf70d-149">在**主要特征**下，**选择"可查询**和**可检索"。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="cf70d-150">**在"映射到已爬网属性"**\>下**添加映射。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="cf70d-151">在**已爬网的属性选择**对话框\>中查找并选择与 Windows Server FCI 属性或将在 DLP\>**策略中**要使用的其他属性对应的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![選取編目屬性對話方塊](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="cf70d-153">在页面\>底部**确定**。</span><span class="sxs-lookup"><span data-stu-id="cf70d-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="cf70d-154">创建使用 FCI 属性或其他属性的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="cf70d-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="cf70d-155">在此示例中，组织在其基于 Windows 服务器的文件服务器上使用 FCI;因此，组织正在使用 FCI。具体来说，他们使用的是**名为"个人身份信息"** 的FCI分类属性，其可能值**为"高、\*\*\*\*中、\*\*\*\*低、\*\*\*\*公共"\*\*\*\*和"不是PII"。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-155">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="cf70d-156">现在，他们希望在 Office 365 中的 DLP 策略中利用其现有的 FCI 分类。</span><span class="sxs-lookup"><span data-stu-id="cf70d-156">Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="cf70d-157">首先，他们按照上述步骤在 SharePoint Online 中创建托管属性，该属性映射到从 FCI 属性自动创建的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="cf70d-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="cf70d-158">接下来，他们创建一个 DLP 策略，其中包含两个规则，这两个规则都使用条件**文档属性包含这些值中的任何一个：**</span><span class="sxs-lookup"><span data-stu-id="cf70d-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="cf70d-159">**FCI PII 内容 - 高、中**如果 FCI 分类**属性"个人可识别信息"\*\*\*\*等于"高"** 或"**中**度"，并且文档与组织外部人员共享，则第一条规则将限制对文档的访问。</span><span class="sxs-lookup"><span data-stu-id="cf70d-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="cf70d-160">**FCI PII 内容 - 低**如果 FCI 分类**属性"个人可识别信息"\*\*\*\*等于"低"，** 并且文档与组织外部人员共享，则第二个规则会向文档所有者发送通知。</span><span class="sxs-lookup"><span data-stu-id="cf70d-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="cf70d-161">使用 PowerShell 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="cf70d-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="cf70d-162">请注意，**包含这些值的条件文档属性**在安全&amp;合规性中心的 UI 中暂时不可用，但您仍可以使用 PowerShell 使用此条件。</span><span class="sxs-lookup"><span data-stu-id="cf70d-162">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="cf70d-163">您可以使用`New\Set\Get-DlpCompliancePolicy`cmdlet 处理 DLP 策略，并使用带有`New\Set\Get-DlpComplianceRule``ContentPropertyContainsWords`参数的 cmdlet 添加**包含这些值中的任何一个条件文档属性。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-163">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="cf70d-164">有关这些 cmdlet 的详细信息，请参阅[Office 365&amp;安全合规性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="cf70d-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="cf70d-165">使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="cf70d-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="cf70d-166">使用`New-DlpCompliancePolicy`创建策略。</span><span class="sxs-lookup"><span data-stu-id="cf70d-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="cf70d-167">下面是一个 PowerShell 示例，该示例创建适用于所有位置的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="cf70d-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="cf70d-168">使用`New-DlpComplianceRule`创建上述两个规则，其中一条规则**用于"低"** 值，另一个规则**用于"高"** 和"**中值"。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="cf70d-169">下面是创建这两个规则的 PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="cf70d-169">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="cf70d-170">请注意，属性名称/值对以引号括起来，属性名称可以指定多个用逗号分隔的不带空格的值，例如`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="cf70d-170">Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="cf70d-171">请注意，Windows Server FCI 包含许多内置属性，包括此示例中使用的**个人身份信息。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-171">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="cf70d-172">每个属性的可能值对于每个组织可能不同。</span><span class="sxs-lookup"><span data-stu-id="cf70d-172">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="cf70d-173">此处**使用的"高、\*\*\*\*中"** 和"**低"** 值仅是一个示例。</span><span class="sxs-lookup"><span data-stu-id="cf70d-173">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="cf70d-174">对于您的组织，您可以在基于 Windows 服务器的文件服务器上的文件服务器资源管理器中查看 Windows Server FCI 分类属性及其可能的值。</span><span class="sxs-lookup"><span data-stu-id="cf70d-174">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="cf70d-175">有关详细信息，请参阅[创建分类属性](http://go.microsoft.com/fwlink/p/?LinkID=627456)。</span><span class="sxs-lookup"><span data-stu-id="cf70d-175">For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="cf70d-176">完成后，策略应具有两个新规则，这两个新规则都使用**Document 属性，其中包含任何这些值**条件。</span><span class="sxs-lookup"><span data-stu-id="cf70d-176">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="cf70d-177">请注意，此条件不会显示在 UI 中，但将显示其他条件、操作和设置。</span><span class="sxs-lookup"><span data-stu-id="cf70d-177">Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="cf70d-178">一条规则阻止访问个人**可识别信息**属性**等于"高"\*\*\*\*或"中**度"的内容。</span><span class="sxs-lookup"><span data-stu-id="cf70d-178">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="cf70d-179">第二个规则发送有关个人**可识别信息**属性**等于"低"** 的内容的通知。</span><span class="sxs-lookup"><span data-stu-id="cf70d-179">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![新的 DLP 原則對話方塊顯示剛才建立的兩個規則](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="cf70d-181">创建 DLP 策略后</span><span class="sxs-lookup"><span data-stu-id="cf70d-181">After you create the DLP policy</span></span>

<span data-ttu-id="cf70d-182">执行前几节中的步骤将创建一个 DLP 策略，该策略将快速检测包含该属性的内容，但前提是该内容是新上载的（以便内容已编制索引），或者如果该内容已旧但刚刚编辑（以便内容重新编制索引）.</span><span class="sxs-lookup"><span data-stu-id="cf70d-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="cf70d-183">要在任何地方检测包含该属性的内容，您可能需要手动请求重新编制库、网站或网站集索引，以便 DLP 策略了解该属性的所有内容。</span><span class="sxs-lookup"><span data-stu-id="cf70d-183">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property.</span></span> <span data-ttu-id="cf70d-184">在 SharePoint Online 中，内容将根据定义的爬网计划自动爬网。</span><span class="sxs-lookup"><span data-stu-id="cf70d-184">In SharePoint Online, content is automatically crawled based on a defined crawl schedule.</span></span> <span data-ttu-id="cf70d-185">爬网程序选取自上次爬网以来已更改的内容并更新索引。</span><span class="sxs-lookup"><span data-stu-id="cf70d-185">The crawler picks up content that has changed since the last crawl and updates the index.</span></span> <span data-ttu-id="cf70d-186">如果您需要 DLP 策略在下一次计划爬网之前保护内容，可以执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="cf70d-186">If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="cf70d-187">重新索引站点可能会导致搜索系统上的负载很大。</span><span class="sxs-lookup"><span data-stu-id="cf70d-187">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="cf70d-188">除非方案绝对需要，否则不要重新索引您的网站。</span><span class="sxs-lookup"><span data-stu-id="cf70d-188">Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="cf70d-189">有关详细信息，请参阅[手动请求对站点、库或列表进行爬网和重新编制索引。](http://go.microsoft.com/fwlink/p/?LinkID=627457)</span><span class="sxs-lookup"><span data-stu-id="cf70d-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="cf70d-190">重新索引站点（可选）</span><span class="sxs-lookup"><span data-stu-id="cf70d-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="cf70d-191">在网站上，**选择"设置"（** 右上角的齿轮图标）\>**站点设置**。</span><span class="sxs-lookup"><span data-stu-id="cf70d-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="cf70d-192">在"**搜索"** 下，**选择"搜索和脱机可用性**\>**重新索引网站"。**</span><span class="sxs-lookup"><span data-stu-id="cf70d-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="cf70d-193">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="cf70d-193">More information</span></span>

- [<span data-ttu-id="cf70d-194">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="cf70d-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="cf70d-195">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="cf70d-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="cf70d-196">发送通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="cf70d-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="cf70d-197">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="cf70d-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="cf70d-198">敏感信息类型清单</span><span class="sxs-lookup"><span data-stu-id="cf70d-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

