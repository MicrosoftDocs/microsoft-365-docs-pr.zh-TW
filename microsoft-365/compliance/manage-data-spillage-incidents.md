---
title: 管理 Microsoft 365 中的数据溢出事件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍使用安全&合规性中心中的新数据调查（预览）工具来管理数据溢出事件。
ms.openlocfilehash: 53193d3bd915562037a6409766e9be9d42d272c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077220"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="24025-103">管理 Microsoft 365 中的数据溢出事件</span><span class="sxs-lookup"><span data-stu-id="24025-103">Manage a data spillage incident in Microsoft 365</span></span>

<span data-ttu-id="24025-104">数据溢出是在不受信任的环境中发布包含机密、敏感或恶意信息的文档时。</span><span class="sxs-lookup"><span data-stu-id="24025-104">Data spillage is when a document containing confidential, sensitive, or malicious information is released in an untrusted environment.</span></span> <span data-ttu-id="24025-105">检测到数据溢出事件时，必须快速控制环境、评估溢出的大小和位置、检查其周围的用户活动，然后从服务中删除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="24025-105">When a data spillage incident is detected, it's important to quickly contain the environment, assess the size and locations of the spillage, examine user activities around it, and then delete the spilled data from the service.</span></span> <span data-ttu-id="24025-106">使用"数据调查（预览）"工具，您可以在 Office 365 中搜索敏感、恶意或放错位置的数据，进行调查以找出发生了什么，然后采取适当的操作。</span><span class="sxs-lookup"><span data-stu-id="24025-106">Using the Data Investigations (Preview) tool, you can search for sensitive, malicious, or misplaced data across Office 365, investigate to find out what happened, and then take appropriate actions.</span></span>  

## <a name="scope-of-this-article"></a><span data-ttu-id="24025-107">本文的范围</span><span class="sxs-lookup"><span data-stu-id="24025-107">Scope of this article</span></span>

<span data-ttu-id="24025-108">本文提供了有关如何从 Office 365 邮箱永久删除项目以便用户或管理员不再访问或恢复这些项目的说明列表。</span><span class="sxs-lookup"><span data-stu-id="24025-108">This article provides a list of instructions on how to permanently delete items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="24025-109">当您删除位于 SharePoint 或 OneDrive 业务站点中的项目时，这些项目将从从原始位置删除时保留 93 天。</span><span class="sxs-lookup"><span data-stu-id="24025-109">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="24025-110">案例</span><span class="sxs-lookup"><span data-stu-id="24025-110">Scenario</span></span>

<span data-ttu-id="24025-111">您会收到数据溢出事件，其中一名员工在不知不觉中通过电子邮件与多人共享了高度机密的文档。</span><span class="sxs-lookup"><span data-stu-id="24025-111">You're informed of a data spillage incident where an employee unknowingly shared a highly confidential document with multiple people through email.</span></span> <span data-ttu-id="24025-112">您希望快速评估在组织内外谁收到了此文档。</span><span class="sxs-lookup"><span data-stu-id="24025-112">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="24025-113">调查事件后，您计划与其他调查人员共享您的调查结果以进行审核，然后永久删除 Office 365 组织溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="24025-113">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from your Office 365 organization.</span></span> <span data-ttu-id="24025-114">调查完成后，您希望删除所有证据。</span><span class="sxs-lookup"><span data-stu-id="24025-114">After the investigation is complete, you want to remove all evidence.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="24025-115">虽然您将能够永久删除自己组织内溢出的数据，但无法使用这些功能删除泄露到组织外部的任何数据。</span><span class="sxs-lookup"><span data-stu-id="24025-115">While you'll be able to permanently remove the spilled data within your own organization, any data spilled outside your organization can't be removed with these capabilities.</span></span>

## <a name="workflow"></a><span data-ttu-id="24025-116">工作流程</span><span class="sxs-lookup"><span data-stu-id="24025-116">Workflow</span></span>

<span data-ttu-id="24025-117">以下是使用数据调查（预览）管理数据溢出事件的工作流：</span><span class="sxs-lookup"><span data-stu-id="24025-117">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="24025-118">创建数据调查。</span><span class="sxs-lookup"><span data-stu-id="24025-118">Create a data investigation.</span></span>

2.  <span data-ttu-id="24025-119">搜索敏感、恶意或放错位置的数据并将其收集为证据。</span><span class="sxs-lookup"><span data-stu-id="24025-119">Search for sensitive, malicious, or misplaced data and collect them as evidence.</span></span>

3.  <span data-ttu-id="24025-120">审查和调查证据。</span><span class="sxs-lookup"><span data-stu-id="24025-120">Review and investigate the evidence.</span></span>

4.  <span data-ttu-id="24025-121">永久删除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="24025-121">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="24025-122">关闭或删除调查。</span><span class="sxs-lookup"><span data-stu-id="24025-122">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="24025-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="24025-123">Before you begin</span></span>

- <span data-ttu-id="24025-124">要创建数据调查、搜索内容和删除溢出的数据，您必须是安全&合规中心中数据调查员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="24025-124">To create a data investigation, search for content, and delete spilled data, you have to be a member of the Data Investigator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="24025-125">要控制调查人员可以搜索的用户邮箱和 OneDrive 帐户，您的组织可以设置合规性边界。</span><span class="sxs-lookup"><span data-stu-id="24025-125">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="24025-126">有关详细信息，[为电子数据展示调查设置合规性边界](tagging-and-assessment-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="24025-126">For more information, [Set up compliance boundaries for eDiscovery investigations](tagging-and-assessment-in-advanced-ediscovery.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="24025-127">第 1 步：创建数据调查</span><span class="sxs-lookup"><span data-stu-id="24025-127">Step 1: Create a data investigation</span></span>

<span data-ttu-id="24025-128">要在数据调查（预览）工具中创建调查：</span><span class="sxs-lookup"><span data-stu-id="24025-128">To create an investigation in the Data Investigations (Preview) tool:</span></span>

1. <span data-ttu-id="24025-129">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="24025-129">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="24025-130">使用数据调查员角色组成员的帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="24025-130">Sign in to Office 365 using an account that is a member of the Data Investigator role group.</span></span>
    
3. <span data-ttu-id="24025-131">在安全和合规性中心，**单击"数据调查"。**</span><span class="sxs-lookup"><span data-stu-id="24025-131">In the security and compliance center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="24025-132">在"**数据调查（预览）"** 页上，**单击"创建新调查"。**</span><span class="sxs-lookup"><span data-stu-id="24025-132">On the **Data Investigations (Preview)** page, click **Create new investigation**.</span></span>
    
5. <span data-ttu-id="24025-133">在"**新建数据调查**弹出窗口"页上，为调查指定名称（必需），然后键入可选的调查编号和说明。</span><span class="sxs-lookup"><span data-stu-id="24025-133">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="24025-134">名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="24025-134">The name must be unique in your organization.</span></span>

6. <span data-ttu-id="24025-135">在**创建此调查后配置其他设置后，** 请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="24025-135">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="24025-136">**单击"是"** 以创建调查，并在新案例中**显示"设置"** 页。</span><span class="sxs-lookup"><span data-stu-id="24025-136">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="24025-137">这允许您向调查添加成员。</span><span class="sxs-lookup"><span data-stu-id="24025-137">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="24025-138">单击"**否"** 以创建调查并将其**显示在"数据调查（预览）"** 页上的案例列表中。</span><span class="sxs-lookup"><span data-stu-id="24025-138">Click **No** to create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="24025-139">如果选择此选项，您将被添加为调查的唯一成员，并且将使用默认的搜索和分析设置。</span><span class="sxs-lookup"><span data-stu-id="24025-139">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="24025-140">创建调查后，您可以随时添加成员或更改设置。</span><span class="sxs-lookup"><span data-stu-id="24025-140">You can add members or change settings anytime after the investigation is created.</span></span>

7. <span data-ttu-id="24025-141">**单击"保存"** 以创建调查。</span><span class="sxs-lookup"><span data-stu-id="24025-141">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="24025-142">新调查**将显示在"数据调查（预览）"** 页上的列表中。</span><span class="sxs-lookup"><span data-stu-id="24025-142">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="24025-143">要打开调查，请单击调查的名称。</span><span class="sxs-lookup"><span data-stu-id="24025-143">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="24025-144">将显示**调查的"主页"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24025-144">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="24025-145">请考虑为调查建立命名约定，并在名称和说明中提供尽可能多的信息，以便将来在必要时查找和参考它们。</span><span class="sxs-lookup"><span data-stu-id="24025-145">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to them in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="24025-146">第 2 步：搜索溢出的数据</span><span class="sxs-lookup"><span data-stu-id="24025-146">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="24025-147">如果您知道要搜索溢出的数据的用户，则可以将它们添加为感兴趣的用户，以将其数据源映射到调查，并快速搜索其邮箱和 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="24025-147">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="24025-148">要向调查添加感兴趣的人员，请单击"**感兴趣的人"，** 然后单击"**添加感兴趣的人"。**</span><span class="sxs-lookup"><span data-stu-id="24025-148">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> <span data-ttu-id="24025-149">有关详细信息，请参阅[管理感兴趣的人员。](manage-people-of-interest.md)</span><span class="sxs-lookup"><span data-stu-id="24025-149">For more information, see [Manage people of interest](manage-people-of-interest.md).</span></span>

<span data-ttu-id="24025-150">在"**搜索"** 选项卡上，您可以创建搜索以查找溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="24025-150">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="24025-151">有关创建搜索的详细信息，请参阅[搜索调查中的数据。](search-for-data.md)</span><span class="sxs-lookup"><span data-stu-id="24025-151">For more information about creating searches, see [Search for data in an investigation](search-for-data.md).</span></span>

<span data-ttu-id="24025-152">运行搜索后，可以预览搜索结果示例并查看搜索统计信息以评估搜索查询的有效性。</span><span class="sxs-lookup"><span data-stu-id="24025-152">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="24025-153">标识要从 Office 365 中删除的项目后，可以将搜索结果添加到证据集。</span><span class="sxs-lookup"><span data-stu-id="24025-153">After you identify the items that you want to delete from Office 365, you can add the search results to an evidence set.</span></span> <span data-ttu-id="24025-154">为此，请单击要调查的搜索。</span><span class="sxs-lookup"><span data-stu-id="24025-154">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="24025-155">在"飞出"页上，**单击"将结果添加到证据**并按照说明进行操作"。</span><span class="sxs-lookup"><span data-stu-id="24025-155">On the flyout page, click **Add results to evidence** and follow the instructions.</span></span> <span data-ttu-id="24025-156">然后在证据集中，您可以查看单个文档，调查谁有权访问文档，然后导出文档。</span><span class="sxs-lookup"><span data-stu-id="24025-156">Then in the evidence set, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="24025-157">要删除文档（或文档子集），而不是查看它们，请转到[步骤 4](#step-4-delete-the-spilled-data)。</span><span class="sxs-lookup"><span data-stu-id="24025-157">To delete the documents (or a subset of documents) instead of reviewing them, go to [Step 4](#step-4-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="24025-158">您在搜索查询中使用关键字可能包含要搜索的实际溢出数据。</span><span class="sxs-lookup"><span data-stu-id="24025-158">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="24025-159">例如，如果搜索包含社会安全号码的文档，并将其用作搜索查询中的关键字，则必须在搜索查询之后删除查询，以避免进一步溢出。</span><span class="sxs-lookup"><span data-stu-id="24025-159">For example, if you search for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="24025-160">您可以在[步骤 5](#step-5-close-or-delete-the-investigation)中删除搜索或删除整个调查。</span><span class="sxs-lookup"><span data-stu-id="24025-160">You can delete the search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="24025-161">第 3 步：回顾和调查</span><span class="sxs-lookup"><span data-stu-id="24025-161">Step 3: Review and investigate</span></span> 

<span data-ttu-id="24025-162">在调查中，**转到"证据"** 选项卡，然后单击您在上一步中创建的证据集。</span><span class="sxs-lookup"><span data-stu-id="24025-162">In the investigation, go to the **Evidence** tab and click the evidence set that you created in the previous step.</span></span> <span data-ttu-id="24025-163">处理作业完成后，将搜索结果添加到证据中后，您可以查看各个文档的本机格式、文本格式或接近本机格式的文档。</span><span class="sxs-lookup"><span data-stu-id="24025-163">After the processing job is completed and the search results are added to the evidence, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="24025-164">您可以创建其他查询以缩小文档列表，并标记文档以指示调查结果。</span><span class="sxs-lookup"><span data-stu-id="24025-164">You can create additional queries to narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span> <span data-ttu-id="24025-165">有关详细信息，请参阅[查看证据中的数据](review-data-in-evidence.md)</span><span class="sxs-lookup"><span data-stu-id="24025-165">For more information, see [Review data in evidence](review-data-in-evidence.md)</span></span>

<span data-ttu-id="24025-166">要对文档进行分组并获取更多审阅帮助，请单击"**管理证据"。**</span><span class="sxs-lookup"><span data-stu-id="24025-166">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="24025-167">在"**分析"** 磁贴中，单击"**分析"。**</span><span class="sxs-lookup"><span data-stu-id="24025-167">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="24025-168">这将运行高级分析，如重复检测、电子邮件线程和主题分析。</span><span class="sxs-lookup"><span data-stu-id="24025-168">This runs advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="24025-169">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="24025-169">For more information, see:</span></span>

- [<span data-ttu-id="24025-170">執行分析以更快速地調查</span><span class="sxs-lookup"><span data-stu-id="24025-170">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)
- [<span data-ttu-id="24025-171">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="24025-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="24025-172">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="24025-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="24025-173">佈景主題</span><span class="sxs-lookup"><span data-stu-id="24025-173">Themes</span></span>](themes.md)

<span data-ttu-id="24025-174">要确定哪些用户涉及数据溢出，可以在证据集中创建查询，然后使用发件人/作者和收件人条件。</span><span class="sxs-lookup"><span data-stu-id="24025-174">To determine which users are involved in the data spillage, you can create a query in the evidence set and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="24025-175">这将创建添加到证据的收集数据中找到的所有发件人、收件人和作者的列表。</span><span class="sxs-lookup"><span data-stu-id="24025-175">This creates a list of all senders, recipients, and authors found in collected data that was added to the evidence.</span></span> <span data-ttu-id="24025-176">请务必检查列表以确定是否有任何外部用户。</span><span class="sxs-lookup"><span data-stu-id="24025-176">Be sure to examine the list to determine if there are any external users.</span></span> <span data-ttu-id="24025-177">有关使用条件缩小搜索结果的详细信息，请参阅[搜索条件](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="24025-177">For more information about using conditions to narrow search results, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-delete-the-spilled-data"></a><span data-ttu-id="24025-178">第 4 步：删除溢出的数据</span><span class="sxs-lookup"><span data-stu-id="24025-178">Step 4: Delete the spilled data</span></span>

<span data-ttu-id="24025-179">使用数据调查工具，可以从其原始位置删除项目。</span><span class="sxs-lookup"><span data-stu-id="24025-179">Using the data investigations tool, you can delete items from their original locations.</span></span> <span data-ttu-id="24025-180">例如，可以从整个组织的邮箱、SharePoint 站点和 OneDrive 帐户中删除项目。</span><span class="sxs-lookup"><span data-stu-id="24025-180">For example, you can delete items from mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="24025-181">请记住，由于收集项目作为证据（通过将搜索结果添加到步骤 2 中设置的证据），因此在证据中设置了项目的副本，以便进一步调查或保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="24025-181">Keep in mind that because you collected items as evidence (by adding the search results to the evidence set in Step 2), you have copies of the items in the evidence set to further investigate or preserve them.</span></span>

<span data-ttu-id="24025-182">要从原始位置删除项目：</span><span class="sxs-lookup"><span data-stu-id="24025-182">To delete items from their original locations:</span></span>

1. <span data-ttu-id="24025-183">在证据集中，选择要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="24025-183">In the evidence set, select the items that you want to delete.</span></span> <span data-ttu-id="24025-184">如果选择附加到电子邮件的项目，则父电子邮件也将被选中并删除。</span><span class="sxs-lookup"><span data-stu-id="24025-184">If you select items that are attached to an email message, the parent email message will also be selected and deleted.</span></span> 
 
2. <span data-ttu-id="24025-185">**单击"操作"，\*\*\*\*然后单击"从原始位置删除项目"。**</span><span class="sxs-lookup"><span data-stu-id="24025-185">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![单击"操作"，然后单击"从原始位置删除项目"](media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="24025-187">在弹出窗口页上，验证要删除的项目和相关子文档的数量，然后单击"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="24025-187">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

<span data-ttu-id="24025-188">此时，当您从其原始位置删除项目时，这些项目将软删除。</span><span class="sxs-lookup"><span data-stu-id="24025-188">At this time, when you delete items from their original location, the items are soft-deleted.</span></span> <span data-ttu-id="24025-189">这意味着已删除的项目将保留，直到该项目的已删除项目恢复期到期。</span><span class="sxs-lookup"><span data-stu-id="24025-189">This means that the deleted items will be retained until the deleted item recovery period for the item expires.</span></span> <span data-ttu-id="24025-190">这也意味着用户可以恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="24025-190">This also means it's possible for users to recover these items.</span></span> <span data-ttu-id="24025-191">有关从邮箱和网站中删除项目时会发生什么情况的详细信息，请参阅[从原始位置删除项目。](delete-items-from-original-locations.md)</span><span class="sxs-lookup"><span data-stu-id="24025-191">For more information about what happens when items are deleted from mailboxes and sites, see [Delete items from their original location](delete-items-from-original-locations.md).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="24025-192">第 5 步：关闭或删除调查</span><span class="sxs-lookup"><span data-stu-id="24025-192">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="24025-193">删除实时服务中的源内容位置（邮箱或网站）中的文档后，您仍将拥有作为调查的一部分添加到证据中的这些文档的副本。</span><span class="sxs-lookup"><span data-stu-id="24025-193">After you delete documents in the source content locations (mailboxes or sites) in the live service, you will still have copies of these documents that you added to evidence as part of your investigation.</span></span> <span data-ttu-id="24025-194">为了避免进一步的数据溢出，应考虑删除调查本身。</span><span class="sxs-lookup"><span data-stu-id="24025-194">To avoid further data spillage, you should consider deleting the investigation itself.</span></span>

<span data-ttu-id="24025-195">要删除调查：</span><span class="sxs-lookup"><span data-stu-id="24025-195">To delete an investigation:</span></span>

1. <span data-ttu-id="24025-196">在"**设置"** 选项卡上，**单击"调查信息"。**</span><span class="sxs-lookup"><span data-stu-id="24025-196">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="24025-197">**单击"删除调查**"。</span><span class="sxs-lookup"><span data-stu-id="24025-197">Click  **Delete investigation**.</span></span> 

<span data-ttu-id="24025-198">如果您不需要删除调查，或者要保存在调查期间收集的信息，可以**单击"关闭案例"。**</span><span class="sxs-lookup"><span data-stu-id="24025-198">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="24025-199">稍后，您可以重新打开已结束的调查。</span><span class="sxs-lookup"><span data-stu-id="24025-199">Then later, you can reopen closed investigations.</span></span>
