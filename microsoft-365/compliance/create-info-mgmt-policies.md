---
title: 创建和应用信息管理策略
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
description: 信息管理策略使您的组织能够控制保留内容的时间、审核人员如何处理内容以及向文档添加条形码或标签。 策略可帮助强制遵守法律和政府法规或内部业务流程。 作为管理员，您可以设置策略来控制如何跟踪文档以及保留文档的时间。
ms.openlocfilehash: 85113393f534a6b17f75962d02518a5a8c65dd8b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076484"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="46873-105">创建和应用信息管理策略</span><span class="sxs-lookup"><span data-stu-id="46873-105">Create and apply information management policies</span></span>

<span data-ttu-id="46873-106">信息管理策略使您的组织能够控制保留内容的时间、审核人员如何处理内容以及向文档添加条形码或标签。</span><span class="sxs-lookup"><span data-stu-id="46873-106">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="46873-107">策略可帮助强制遵守法律和政府法规或内部业务流程。</span><span class="sxs-lookup"><span data-stu-id="46873-107">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="46873-108">作为管理员，您可以设置策略来控制如何跟踪文档以及保留文档的时间。</span><span class="sxs-lookup"><span data-stu-id="46873-108">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="46873-109">您可以创建信息管理策略可以在站点层次结构中的三个不同位置（从最宽到最窄）：</span><span class="sxs-lookup"><span data-stu-id="46873-109">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="46873-110">创建用于网站集中的多种内容类型的策略。</span><span class="sxs-lookup"><span data-stu-id="46873-110">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="46873-111">为网站内容类型创建策略。</span><span class="sxs-lookup"><span data-stu-id="46873-111">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="46873-112">为列表或库创建策略。</span><span class="sxs-lookup"><span data-stu-id="46873-112">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="46873-113">有关详细信息，请参阅[信息管理策略简介](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="46873-113">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="46873-114">为网站集中的多种内容类型创建策略</span><span class="sxs-lookup"><span data-stu-id="46873-114">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="46873-115"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-115"></span></span>

<span data-ttu-id="46873-116">为确保信息策略应用于网站集中特定类型的所有文档，请考虑在网站集级别创建策略，然后将策略应用于内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-116">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="46873-117">这些称为网站集策略。</span><span class="sxs-lookup"><span data-stu-id="46873-117">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="46873-118">在标题栏上的网站集\>**主页"设置**![SharePoint 2016 设置"按钮上。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="46873-118">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="46873-119">\> [網站設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46873-119">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="46873-120">在 SharePoint 组连接的站点中，单击"**设置"，\*\*\*\*单击"网站内容"，\*\*\*\*然后单击"网站设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-120">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="46873-121">在"网站设置"页上，**在"网站集管理**\>**内容类型策略模板"** 下。</span><span class="sxs-lookup"><span data-stu-id="46873-121">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![网站设置页面上的内容类型策略模板链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="46873-123">在"创建策略"页上\>**创建**。</span><span class="sxs-lookup"><span data-stu-id="46873-123">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="46873-124">输入策略的名称和说明，然后编写一个简短的策略语句，向用户解释策略的用点。</span><span class="sxs-lookup"><span data-stu-id="46873-124">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="46873-125">请参阅有关为网站内容类型创建策略的下一节，了解如何设置要与策略关联的功能。</span><span class="sxs-lookup"><span data-stu-id="46873-125">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="46873-126">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46873-126">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="46873-127">为网站内容类型创建策略</span><span class="sxs-lookup"><span data-stu-id="46873-127">Create a policy for a site content type</span></span>
<span data-ttu-id="46873-128"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-128"></span></span>

<span data-ttu-id="46873-129">将信息管理策略添加到内容类型，可以轻松地将策略功能与多个列表或库相关联。</span><span class="sxs-lookup"><span data-stu-id="46873-129">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="46873-130">您可以选择将现有信息管理策略添加到内容类型，或创建特定于单个内容类型的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="46873-130">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="46873-131">您还可以将信息管理策略添加到特定于列表的内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-131">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="46873-132">这具有仅将策略应用于该列表中使用内容类型的项目的效果。</span><span class="sxs-lookup"><span data-stu-id="46873-132">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="46873-133">在标题栏上的网站集\>**主页"设置**![SharePoint 2016 设置"按钮上。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="46873-133">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="46873-134">\> [網站設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46873-134">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="46873-135">在 SharePoint 组连接的站点中，单击"**设置"，\*\*\*\*单击"网站内容"，\*\*\*\*然后单击"网站设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-135">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="46873-136">在"网站设置"页上，**在"网页设计器库**\>**网站"内容类型**下。</span><span class="sxs-lookup"><span data-stu-id="46873-136">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![网站内容类型链接位于"网站设置"页上](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="46873-138">在"网站内容类型设置"页上，选择要向其添加策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-138">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="46873-139">在"网站内容类型"页上，**在"设置**\>**信息管理策略设置"** 下。</span><span class="sxs-lookup"><span data-stu-id="46873-139">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="46873-140">在"编辑策略"页上，输入策略的名称和说明，然后编写简要说明，向用户说明策略的用向。</span><span class="sxs-lookup"><span data-stu-id="46873-140">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="46873-141">在下一节中，选择要添加到信息管理策略中的单个策略功能。</span><span class="sxs-lookup"><span data-stu-id="46873-141">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![内容策略的类型](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="46873-143">要为受此策略约束的文档和物料指定保留期，请选择"**启用保留"，** 然后指定保留期和项目过期时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="46873-143">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="46873-144">指定保留期</span><span class="sxs-lookup"><span data-stu-id="46873-144">To specify a retention period</span></span>
    
||||||<span data-ttu-id="46873-145">**1.**</span><span class="sxs-lookup"><span data-stu-id="46873-145">**1.**</span></span>|<span data-ttu-id="46873-146">[选择 [为记录添加保留阶段..."]</span><span class="sxs-lookup"><span data-stu-id="46873-146">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="46873-147">2.</span><span class="sxs-lookup"><span data-stu-id="46873-147">2.</span></span>  <br/> | <span data-ttu-id="46873-148">选择保留期选项以指定文档或项目何时过期。</span><span class="sxs-lookup"><span data-stu-id="46873-148">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="46873-149">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="46873-149">Do one of the following:</span></span>  <br/>  <span data-ttu-id="46873-150">要基于日期属性设置到期日期，在**事件**\>**此阶段下基于项目上的日期属性，** 然后选择文档或项目操作（例如，创建或修改）和此操作后的时间增量（例如，您希望项目过期时的天数、月数或年数。</span><span class="sxs-lookup"><span data-stu-id="46873-150">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="46873-151">要使用自定义保留公式来确定过期，**请选择"按此服务器上安装的自定义保留公式设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-151">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="46873-152">> [!NOTE]> 此选项仅在管理员设置了自定义公式时可用。</span><span class="sxs-lookup"><span data-stu-id="46873-152">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="46873-153">3.</span><span class="sxs-lookup"><span data-stu-id="46873-153">3.</span></span>  <br/> |<span data-ttu-id="46873-154">仅当为已与其关联的工作流的列表、库或内容类型定义策略时，"**开始工作流"** 选项才可用。</span><span class="sxs-lookup"><span data-stu-id="46873-154">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="46873-155">然后，您可以选择工作流。</span><span class="sxs-lookup"><span data-stu-id="46873-155">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="46873-156">4.</span><span class="sxs-lookup"><span data-stu-id="46873-156">4.</span></span>  <br/> |<span data-ttu-id="46873-157">在"**重复"** 部分中，**选择"重复此阶段的操作..."** 并输入您希望操作再次发生的频率。</span><span class="sxs-lookup"><span data-stu-id="46873-157">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="46873-158">> [!NOTE]>此选项仅在所选操作可以重复时才可用。</span><span class="sxs-lookup"><span data-stu-id="46873-158">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="46873-159">例如，您不能**为"永久删除"** 操作设置重复。</span><span class="sxs-lookup"><span data-stu-id="46873-159">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="46873-160">5.</span><span class="sxs-lookup"><span data-stu-id="46873-160">5.</span></span>  <br/> |<span data-ttu-id="46873-161">选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="46873-161">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="46873-162">要启用受此策略约束的文档和项的审核，**请选择"启用审核"，** 然后指定要审核的事件。</span><span class="sxs-lookup"><span data-stu-id="46873-162">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="46873-163">启用审核</span><span class="sxs-lookup"><span data-stu-id="46873-163">To enable auditing</span></span>
    
||||||<span data-ttu-id="46873-164">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="46873-164">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="46873-165">在"编辑策略"页上，\***\>\*\*\*\*在"\*\*\*\*审核\*\*\*\*启用审核"** 下，然后选择要为其保留审核跟踪的事件旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="46873-165">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="46873-166">**2.**</span><span class="sxs-lookup"><span data-stu-id="46873-166">**2.**</span></span> <br/> |<span data-ttu-id="46873-167">**要提示用户将这些条形码插入到文档中，\*\*\*\*选择\*\*\*\*提示用户在保存或打印之前插入条形码\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="46873-167">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="46873-168">**3.**</span><span class="sxs-lookup"><span data-stu-id="46873-168">**3.**</span></span> <br/> |<span data-ttu-id="46873-169">**选择\*\*\*\*确定**= 将审核功能应用于策略。</span><span class="sxs-lookup"><span data-stu-id="46873-169">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="46873-170">审核策略功能使组织能够创建和分析文档的审核跟踪，并列出任务列表、问题列表、讨论组和日历等项目。</span><span class="sxs-lookup"><span data-stu-id="46873-170">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="46873-171">此策略功能提供记录事件的审核日志，例如查看、编辑或删除内容时。</span><span class="sxs-lookup"><span data-stu-id="46873-171">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="46873-172">当作为信息管理策略的一部分启用审核时，管理员可以在基于 Microsoft Excel 的策略使用情况报告中查看审核数据，并汇总当前使用情况。</span><span class="sxs-lookup"><span data-stu-id="46873-172">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="46873-173">管理员可以使用这些报告来确定信息在组织内的使用方式。</span><span class="sxs-lookup"><span data-stu-id="46873-173">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="46873-174">这些报告还可以帮助组织验证和记录其法规遵从性或调查潜在问题。</span><span class="sxs-lookup"><span data-stu-id="46873-174">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="46873-175">审核日志记录以下信息：事件名称、事件的日期和时间以及执行操作的用户的系统名称。</span><span class="sxs-lookup"><span data-stu-id="46873-175">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="46873-176">当条形码作为策略的一部分启用时，它们将添加到文档属性中，并显示在应用条形码的文档的页眉区域中。</span><span class="sxs-lookup"><span data-stu-id="46873-176">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="46873-177">与标签一样，条形码也可以从文档中手动删除。</span><span class="sxs-lookup"><span data-stu-id="46873-177">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="46873-178">您可以指定在打印或保存项目时，是否应提示用户包含条形码，或者是否应使用 2010 Office 下达程序中的"**插入"** 选项卡手动插入条形码。</span><span class="sxs-lookup"><span data-stu-id="46873-178">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="46873-179">启用条形码</span><span class="sxs-lookup"><span data-stu-id="46873-179">To enable barcodes</span></span>
    
||||||<span data-ttu-id="46873-180">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="46873-180">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="46873-181">**在"编辑策略"页上，**在"条形码**\>**启用条形码"\*\* 下。\*\*</span><span class="sxs-lookup"><span data-stu-id="46873-181">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="46873-182">**2.**</span><span class="sxs-lookup"><span data-stu-id="46873-182">**2.**</span></span> <br/> |<span data-ttu-id="46873-183">要提示用户将这些条形码插入到文档中，**请选择"提示用户在保存或打印之前插入条形码"。**</span><span class="sxs-lookup"><span data-stu-id="46873-183">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="46873-184">**3.**</span><span class="sxs-lookup"><span data-stu-id="46873-184">**3.**</span></span> <br/> |<span data-ttu-id="46873-185">**选择"确定"** 将条形码功能应用于策略。</span><span class="sxs-lookup"><span data-stu-id="46873-185">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="46873-186">条形码策略生成代码 39 标准条形码。</span><span class="sxs-lookup"><span data-stu-id="46873-186">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="46873-187">每个条形码图像都包含表示条形码值的条形码符号下方的文本。</span><span class="sxs-lookup"><span data-stu-id="46873-187">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="46873-188">这样，即使扫描硬件不可用，也能使用条形码数据。</span><span class="sxs-lookup"><span data-stu-id="46873-188">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="46873-189">用户可以手动在搜索框中键入条形码编号以查找网站上的项目。</span><span class="sxs-lookup"><span data-stu-id="46873-189">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="46873-190">要要求受此策略约束的文档具有标签，**请选择"启用标签"，** 然后指定标签所需的设置。</span><span class="sxs-lookup"><span data-stu-id="46873-190">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="46873-191">启用标签</span><span class="sxs-lookup"><span data-stu-id="46873-191">To enable labels</span></span>
    
||||||<span data-ttu-id="46873-192">**1.**</span><span class="sxs-lookup"><span data-stu-id="46873-192">**1.**</span></span>|<span data-ttu-id="46873-193">•若要要求用户向文档添加标签，**请选择"提示用户在保存或打印 之前插入标签"。**</span><span class="sxs-lookup"><span data-stu-id="46873-193">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="46873-194">> [!NOTE]>如果希望标签是可选的，请不要选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="46873-194">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="46873-195">2.</span><span class="sxs-lookup"><span data-stu-id="46873-195">2.</span></span>  <br/> |<span data-ttu-id="46873-196">要锁定标签，使其在插入后无法更改，请选择"**在添加标签后防止更改标签"。**</span><span class="sxs-lookup"><span data-stu-id="46873-196">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="46873-197">此设置可防止标签文本在标签插入到客户端应用程序（如 Word、Excel 或 PowerPoint）中的项后进行更新。</span><span class="sxs-lookup"><span data-stu-id="46873-197">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="46873-198">如果希望在此文档或项目的属性更新时更新标签，请不要选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="46873-198">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="46873-199">3.</span><span class="sxs-lookup"><span data-stu-id="46873-199">3.</span></span>  <br/> |<span data-ttu-id="46873-200">在"标签格式"框中，输入标签的文本，希望显示它。</span><span class="sxs-lookup"><span data-stu-id="46873-200">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="46873-201">标签最多包含 10 列引用，每个引用最多长 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="46873-201">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="46873-202">要为标签创建格式，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="46873-202">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="46873-203">按希望列的显示顺序键入要包含在标签中的列的名称。</span><span class="sxs-lookup"><span data-stu-id="46873-203">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="46873-204">将列名称括在大括号 （ ）{}中，如"编辑策略"页上的示例所示。</span><span class="sxs-lookup"><span data-stu-id="46873-204">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="46873-205">键入单词以标识括号外的列，如"编辑策略"页上的示例所示。</span><span class="sxs-lookup"><span data-stu-id="46873-205">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="46873-206">4.</span><span class="sxs-lookup"><span data-stu-id="46873-206">4.</span></span>  <br/> |<span data-ttu-id="46873-207">要添加换行符，请输入**\n，** 在希望换行符显示的位置。</span><span class="sxs-lookup"><span data-stu-id="46873-207">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="46873-208">5.</span><span class="sxs-lookup"><span data-stu-id="46873-208">5.</span></span>  <br/> |<span data-ttu-id="46873-209">选择所需的字体大小和样式，并指定是否要在文档中向左、向左或向右放置标签。</span><span class="sxs-lookup"><span data-stu-id="46873-209">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="46873-210">选择用户计算机上可用的字体和样式。</span><span class="sxs-lookup"><span data-stu-id="46873-210">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="46873-211">字体的大小会影响标签上可以显示多少文本。</span><span class="sxs-lookup"><span data-stu-id="46873-211">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="46873-212">6.</span><span class="sxs-lookup"><span data-stu-id="46873-212">6.</span></span>  <br/> |<span data-ttu-id="46873-213">输入标签的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="46873-213">Enter the height and width of the label.</span></span> <span data-ttu-id="46873-214">标签高度范围为 0.25 英寸到 20 英寸，标签宽度范围为 0.25 英寸到 20 英寸。</span><span class="sxs-lookup"><span data-stu-id="46873-214">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="46873-215">标签文本始终垂直居中在标签图像中。</span><span class="sxs-lookup"><span data-stu-id="46873-215">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="46873-216">7.</span><span class="sxs-lookup"><span data-stu-id="46873-216">7.</span></span>  <br/> |<span data-ttu-id="46873-217">**选择"刷新"** 以预览标签内容。</span><span class="sxs-lookup"><span data-stu-id="46873-217">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="46873-218">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46873-218">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="46873-219">建立清單、文件庫或資料夾的原則 (位置保留原則)</span><span class="sxs-lookup"><span data-stu-id="46873-219">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="46873-220"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-220"></span></span>

<span data-ttu-id="46873-221">您可以定义仅适用于特定列表、库或文件夹的保留策略。</span><span class="sxs-lookup"><span data-stu-id="46873-221">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="46873-222">但是，如果以这种方式创建保留策略，则无法在其他列表、库、文件夹或网站上重用此策略，也不能将网站集策略应用于基于位置的策略。</span><span class="sxs-lookup"><span data-stu-id="46873-222">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="46873-223">如果要将单个保留策略应用于单个位置中的所有类型的内容，则很可能希望使用基于位置的保留。</span><span class="sxs-lookup"><span data-stu-id="46873-223">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="46873-224">在大多数其他情况下，您需要验证是否为所有内容类型指定了保留策略。</span><span class="sxs-lookup"><span data-stu-id="46873-224">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="46873-225">每个子文件夹继承其父文件夹的保留策略，除非您选择中断继承并在子级别定义新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="46873-225">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="46873-226">如果要定义信息管理策略，而不是保留到列表或库，则需要为与该列表或库关联的每个列表内容类型定义信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="46873-226">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="46873-227">如果您在任何时候决定为列表或库从内容类型切换到基于位置的策略，则仅保留策略将用作基于位置的策略。</span><span class="sxs-lookup"><span data-stu-id="46873-227">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="46873-228">所有其他管理策略（审核、条形码和条形码）将从关联的内容类型继承。</span><span class="sxs-lookup"><span data-stu-id="46873-228">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="46873-229">通过停用"库"和"基于文件夹的保留"功能，可以禁用网站集的基于位置的策略。</span><span class="sxs-lookup"><span data-stu-id="46873-229">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="46873-230">这使网站集管理员能够确保其内容类型策略不会被列表管理员基于位置的策略覆盖。</span><span class="sxs-lookup"><span data-stu-id="46873-230">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="46873-231">至少需要"管理列表"权限才能更改列表或库的信息管理策略设置。</span><span class="sxs-lookup"><span data-stu-id="46873-231">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="46873-232">导航到要为其指定信息管理策略的列表或库。</span><span class="sxs-lookup"><span data-stu-id="46873-232">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="46873-233">在功能区上，**选择"库"** 或"**列表"**\>**选项卡""库设置"** 或"**列表设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-233">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="46873-234">在"共享点**联机"中，单击"设置"，\*\*\*\*然后单击"列表设置"\*\*\*\*或"库设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-234">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="46873-235">**在"权限和管理**\>**信息管理策略"下设置**。</span><span class="sxs-lookup"><span data-stu-id="46873-235">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![文档库设置页面上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="46873-237">在"信息管理策略设置"页上，确保列表或库的保留源设置为"库"和"文件夹"。</span><span class="sxs-lookup"><span data-stu-id="46873-237">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="46873-238">如果**内容类型**显示为源，请单击"**更改源"，\*\*\*\*然后单击"库"和"文件夹"。**</span><span class="sxs-lookup"><span data-stu-id="46873-238">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="46873-239">您会收到内容类型保留策略将被忽略的提醒。</span><span class="sxs-lookup"><span data-stu-id="46873-239">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="46873-240">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46873-240">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="46873-241">在"编辑策略"页上，在**基于库的保留计划**下，输入要创建的策略的简要说明。</span><span class="sxs-lookup"><span data-stu-id="46873-241">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="46873-242">**选择"添加保留阶段..."...**</span><span class="sxs-lookup"><span data-stu-id="46873-242">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="46873-243">请注意，在"记录"下，您可以选择为记录定义不同的保留策略，为此选择"为记录定义不同的保留阶段"选项。</span><span class="sxs-lookup"><span data-stu-id="46873-243">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="46873-244">在"阶段属性"对话框中，选择保留期选项以指定文档或项目何时设置为过期。</span><span class="sxs-lookup"><span data-stu-id="46873-244">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="46873-245">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="46873-245">Do one of the following:</span></span>
    
  - <span data-ttu-id="46873-246">要基于日期属性设置到期日期，在**事件**\>**此阶段下基于项目上的日期属性，** 然后选择文档或项目操作（例如，创建或修改）和此操作后的时间增量（例如，您希望项目过期时的天数、月数或年数。</span><span class="sxs-lookup"><span data-stu-id="46873-246">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="46873-247">要使用自定义保留公式来确定过期，**请选择"按此服务器上安装的自定义保留公式设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-247">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="46873-248">仅当管理员设置了自定义公式时，此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="46873-248">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="46873-249">**在"操作"** 下，指定文档或项目过期时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="46873-249">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="46873-250">要使文档或项目执行特定操作（如删除），请从列表中选择一个操作。</span><span class="sxs-lookup"><span data-stu-id="46873-250">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="46873-251">仅当为已与其关联的工作流的列表、库或内容类型定义策略时，"**开始工作流"** 选项才可用。</span><span class="sxs-lookup"><span data-stu-id="46873-251">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="46873-252">然后，您可以选择工作流。</span><span class="sxs-lookup"><span data-stu-id="46873-252">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="46873-253">**在"重复"** 下，**选择"重复此阶段的操作..."** 并输入您希望操作再次发生的频率。</span><span class="sxs-lookup"><span data-stu-id="46873-253">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="46873-254">仅当可以选择的操作可以重复时，此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="46873-254">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="46873-255">例如，您不能**为"永久删除"** 操作设置重复。</span><span class="sxs-lookup"><span data-stu-id="46873-255">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="46873-256">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46873-256">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="46873-257">将网站集策略应用于内容类型</span><span class="sxs-lookup"><span data-stu-id="46873-257">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="46873-258"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-258"></span></span>

<span data-ttu-id="46873-259">如果已为您的网站创建信息管理策略作为网站收集策略，则可以将其中一个策略应用于内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-259">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="46873-260">通过执行此操作，可以将相同的策略应用于网站集中不共享相同父内容类型的多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-260">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="46873-261">如果要将策略应用于网站集中的多个内容类型，并且配置了托管元数据服务，则可以使用"内容类型发布"将信息管理策略发布到多个网站集。</span><span class="sxs-lookup"><span data-stu-id="46873-261">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="46873-262">有关详细信息，请参阅[跨网站集应用策略](#apply-a-policy-across-site-collections)一节。</span><span class="sxs-lookup"><span data-stu-id="46873-262">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="46873-263">导航到包含要应用策略的内容类型的列表或库。</span><span class="sxs-lookup"><span data-stu-id="46873-263">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="46873-264">在功能区上，**选择"库"** 或"**列表"**\>**选项卡""库设置"** 或"**列表设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-264">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="46873-265">在"共享点**联机"中，单击"设置"，\*\*\*\*然后单击"列表设置"\*\*\*\*或"库设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-265">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="46873-266">**在"权限和管理**\>**信息管理策略"下设置**。</span><span class="sxs-lookup"><span data-stu-id="46873-266">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![文档库设置页面上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="46873-268">验证策略源是否**设置为"内容类型"，\*\*\*\*并在"内容类型策略"** 下选择要应用策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-268">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="46873-269">在"**指定策略**\>**使用网站集策略"** 下，然后从列表中选择要应用的策略。</span><span class="sxs-lookup"><span data-stu-id="46873-269">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="46873-270">如果"**使用网站集策略"** 选项不可用，则尚未为网站集定义任何网站集策略。</span><span class="sxs-lookup"><span data-stu-id="46873-270">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="46873-271">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46873-271">Choose **OK**.</span></span>
    
     <span data-ttu-id="46873-272">如果您使用的列表或库支持多种内容类型的管理，则可以**在"内容类型"** 下选择要为其指定信息管理策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-272">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="46873-273">这将直接带您到上面的步骤 5。</span><span class="sxs-lookup"><span data-stu-id="46873-273">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="46873-274">跨网站集应用策略</span><span class="sxs-lookup"><span data-stu-id="46873-274">Apply a policy across site collections</span></span>
<span data-ttu-id="46873-275"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-275"></span></span>

<span data-ttu-id="46873-276">通过使用托管元数据服务应用程序设置内容类型发布，跨网站集共享内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-276">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="46873-277">内容类型发布可帮助您在网站中一致地管理内容和元数据，因为内容类型可以集中创建和更新，并且更新可以发布到多个订阅网站集或 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="46873-277">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="46873-278">从现有策略创建模板，以便跨网站集使用</span><span class="sxs-lookup"><span data-stu-id="46873-278">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="46873-279"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-279"></span></span>

<span data-ttu-id="46873-280">您可以定义信息管理策略，然后从其中创建模板，以便根据需要跨多个网站集使用。</span><span class="sxs-lookup"><span data-stu-id="46873-280">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="46873-281">如果要备份信息策略，也可以将其用作使用内容类型发布跨网站集应用策略的替代方法，则可以使用此方法。</span><span class="sxs-lookup"><span data-stu-id="46873-281">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="46873-282">通过将策略从一个网站集导出，然后将其导入到保存的位置或另一个网站集，可以创建策略的模板或备份。</span><span class="sxs-lookup"><span data-stu-id="46873-282">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="46873-283">如果使用导出/导入功能来制作一组策略模板，请记住策略 .xml 文件中存在唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="46873-283">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="46873-284">因此，如果不更改此唯一标识符，则无法多次将该策略导入网站。</span><span class="sxs-lookup"><span data-stu-id="46873-284">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="46873-285">导出策略</span><span class="sxs-lookup"><span data-stu-id="46873-285">Export a policy</span></span>
<span data-ttu-id="46873-286"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-286"></span></span>

1. <span data-ttu-id="46873-287">在网站集主页上，选择取代"网站设置"**的"设置""**![小设置"](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\*\*\*\* 网站设置\>.</span><span class="sxs-lookup"><span data-stu-id="46873-287">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="46873-288">在 SharePoint 组连接的站点中，单击"**设置"，\*\*\*\*单击"网站内容"，\*\*\*\*然后单击"网站设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-288">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="46873-289">在"网站设置"页上，**在"网站集管理**\>**内容类型策略模板"** 下。</span><span class="sxs-lookup"><span data-stu-id="46873-289">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![网站设置页面上的内容类型策略模板链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="46873-291">选择要导出\>滚动到底部\>**导出**的策略。</span><span class="sxs-lookup"><span data-stu-id="46873-291">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="46873-292">在保存或打开文件的提示中，**选择"保存"，** 然后选择要保存到的位置。</span><span class="sxs-lookup"><span data-stu-id="46873-292">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="46873-293">请确保选择可用于导入策略的网站集的位置。</span><span class="sxs-lookup"><span data-stu-id="46873-293">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="46873-294">显示"下载完成"对话框时，**选择"关闭"。**</span><span class="sxs-lookup"><span data-stu-id="46873-294">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="46873-295">将策略导入其他网站集</span><span class="sxs-lookup"><span data-stu-id="46873-295">Import a policy to a different site collection</span></span>
<span data-ttu-id="46873-296"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="46873-296"></span></span>

<span data-ttu-id="46873-297">通过导入信息管理策略，您可以将其应用于任何给定网站集中的网站或列表级别的多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-297">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="46873-298">这样做的好处是双重的：您不必在每个内容类型上重新定义和应用策略，并且只需在一个位置更改策略，即可更轻松地管理策略修改。</span><span class="sxs-lookup"><span data-stu-id="46873-298">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="46873-299">在要应用策略的网站集的主页上，选择取代"网站设置"**的"设置""**![小设置"](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\*\*\*\* 网站设置\>.</span><span class="sxs-lookup"><span data-stu-id="46873-299">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="46873-300">在 SharePoint 组连接的站点中，单击"**设置"，\*\*\*\*单击"网站内容"，\*\*\*\*然后单击"网站设置"。**</span><span class="sxs-lookup"><span data-stu-id="46873-300">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="46873-301">在"网站设置"页上，**在"网站集管理**\>**内容类型策略模板"** 下。</span><span class="sxs-lookup"><span data-stu-id="46873-301">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="46873-302">在"策略"\>页上**导入**\>**浏览**以查找策略的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="46873-302">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="46873-303">选择策略已保存在\>其中的 XML 文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="46873-303">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="46873-304">在"导入网站集策略"页上\>**导入**以将策略添加到网站集。</span><span class="sxs-lookup"><span data-stu-id="46873-304">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="46873-305">导入的策略现在可以应用于网站或列表级别的一个或多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="46873-305">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="46873-306">信息管理策略使您的组织能够控制保留内容的时间、审核人员如何处理内容以及向文档添加条形码或标签。</span><span class="sxs-lookup"><span data-stu-id="46873-306">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="46873-307">策略可帮助强制遵守法律和政府法规或内部业务流程。</span><span class="sxs-lookup"><span data-stu-id="46873-307">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="46873-308">作为管理员，您可以设置策略来控制如何跟踪文档以及保留文档的时间。</span><span class="sxs-lookup"><span data-stu-id="46873-308">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="46873-309">您可以创建信息管理策略可以在站点层次结构中的三个不同位置（从最宽到最窄）：</span><span class="sxs-lookup"><span data-stu-id="46873-309">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="46873-310">创建用于网站集中的多种内容类型的策略。</span><span class="sxs-lookup"><span data-stu-id="46873-310">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="46873-311">为网站内容类型创建策略。</span><span class="sxs-lookup"><span data-stu-id="46873-311">Create a policy for a site content type.</span></span>
- <span data-ttu-id="46873-312">为列表或库创建策略。</span><span class="sxs-lookup"><span data-stu-id="46873-312">Create a policy for a list or library.</span></span>

<span data-ttu-id="46873-313">有关详细信息，请参阅[信息管理策略简介](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="46873-313">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

