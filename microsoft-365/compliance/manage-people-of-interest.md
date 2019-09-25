---
title: 管理数据调查感兴趣的人员（预览）
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e374509dccd235ef689609acc1c4f99db6594d4c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077177"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a><span data-ttu-id="920a4-102">管理数据调查感兴趣的人员（预览）</span><span class="sxs-lookup"><span data-stu-id="920a4-102">Manage people of interest in Data Investigations (Preview)</span></span>

<span data-ttu-id="920a4-103">数据调查通常涉及感兴趣的人员。</span><span class="sxs-lookup"><span data-stu-id="920a4-103">Data investigations often involve people of interest.</span></span> <span data-ttu-id="920a4-104">通常，他们拥有您正在调查或希望修复的错位、敏感或恶意数据。</span><span class="sxs-lookup"><span data-stu-id="920a4-104">Usually they are people who own the misplaced, sensitive or malicious data that you're investigating or looking to remediate.</span></span> <span data-ttu-id="920a4-105">**在"数据调查（预览）"** 中，可以添加它们以发现其数据源，以便用于界定搜索范围或查看其他信息，如联系人、位置和活动日志。</span><span class="sxs-lookup"><span data-stu-id="920a4-105">In **Data Investigations (Preview)**, you can add them to discover their data sources to use in scoping your search or view additional information such as contact, location and activity logs.</span></span> 


## <a name="add-people-of-interest"></a><span data-ttu-id="920a4-106">添加感兴趣的人员</span><span class="sxs-lookup"><span data-stu-id="920a4-106">Add people of interest</span></span>

<span data-ttu-id="920a4-107">**在"感兴趣的人"** 选项卡中，您可以添加感兴趣的人员并发现其数据源，如 Exchange 邮箱或可用于搜索范围的 OneDrive 业务网站。</span><span class="sxs-lookup"><span data-stu-id="920a4-107">In **People of interest** tab, you can add people of interest and discover their data sources such as Exchange mailboxes or OneDrive for Business site that you can use to scope your search.</span></span> <span data-ttu-id="920a4-108">当被感兴趣的人缩小范围时，搜索更具有执行性和准确性，因为该工具会重新处理任何未编制索引的数据，如图像或不受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="920a4-108">When scoped down by people of interest, searches are more performant and accurate because the tool re-processes any unindexed data such as images or unsupported file types.</span></span> <span data-ttu-id="920a4-109">您还可以查看他们的联系信息、位置信息和活动日志，您可以使用这些信息来启动通信或进一步调查其活动。</span><span class="sxs-lookup"><span data-stu-id="920a4-109">You can also see their contact information, location information and activity logs that you can use to initiate communications or further investigate their activities.</span></span> 

<span data-ttu-id="920a4-110">要将感兴趣的人员添加到调查中：</span><span class="sxs-lookup"><span data-stu-id="920a4-110">To add people of interest to an investigation:</span></span>

1. <span data-ttu-id="920a4-111">从"**数据调查（预览）"** 页转到您的调查。</span><span class="sxs-lookup"><span data-stu-id="920a4-111">From the **Data Investigations (Preview)** page, go to your investigation.</span></span>
 
2. <span data-ttu-id="920a4-112">选择调查后，**转到"感兴趣的人"** 选项卡，**然后单击"添加感兴趣的人员"。**</span><span class="sxs-lookup"><span data-stu-id="920a4-112">After you have selected a investigation, go to the **People of interest** tab and click **+ Add people of interest**.</span></span> 
 
3. <span data-ttu-id="920a4-113">选择要添加到调查中的人员。</span><span class="sxs-lookup"><span data-stu-id="920a4-113">Choose people that you want to add to the investigation.</span></span> <span data-ttu-id="920a4-114">可以先键入以搜索并从组织的 Azure 活动目录中选择用户。</span><span class="sxs-lookup"><span data-stu-id="920a4-114">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="920a4-115">完成感兴趣的人员列表后，**单击"下一步"** 以映射其数据源。</span><span class="sxs-lookup"><span data-stu-id="920a4-115">After you have finalized the list of people of interest, click **Next** to map their data sources.</span></span> 

5. <span data-ttu-id="920a4-116">[可选]对于每个人，**选择"Exchange"** 以添加人员的主交换邮箱，选择**OneDrive**以添加人员的主 OneDrive 业务网站。</span><span class="sxs-lookup"><span data-stu-id="920a4-116">[Optional] For each person, select **Exchange** to add person's primary Exchange mailbox, and **OneDrive** to add person's primary OneDrive for Business site.</span></span>

6. <span data-ttu-id="920a4-117">[可选]单击"**下一步"** 可添加要与感兴趣的人员关联的任何其他数据源。</span><span class="sxs-lookup"><span data-stu-id="920a4-117">[Optional] Click **Next** to add any additional data sources that you want to associate with your people of interest.</span></span>

7. <span data-ttu-id="920a4-118">[可选]**选择"更新"** 可将内容位置（如邮箱、网站和团队）分配给人员。</span><span class="sxs-lookup"><span data-stu-id="920a4-118">[Optional] Select **Update** to assign content locations, like mailboxes, sites, and Teams to a person.</span></span> 

8. <span data-ttu-id="920a4-119">[可选]在弹出窗口中：</span><span class="sxs-lookup"><span data-stu-id="920a4-119">[Optional] In the flyout:</span></span>
   
    -  <span data-ttu-id="920a4-120">**交换邮箱**-**单击"选择用户、组或团队"，** 然后再次**单击"选择用户、组或团队"。**</span><span class="sxs-lookup"><span data-stu-id="920a4-120">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="920a4-121">要添加更多邮箱，请使用搜索框查找用户邮箱和通讯组。</span><span class="sxs-lookup"><span data-stu-id="920a4-121">To add more mailboxes, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="920a4-122">您还可以添加用于存储 Office 365 组或 Microsoft 团队信息的邮箱。</span><span class="sxs-lookup"><span data-stu-id="920a4-122">You can also add mailboxes used to store an Office 365 Group or a Microsoft Team information.</span></span> <span data-ttu-id="920a4-123">选择用户、组、团队复选框，**单击"选择"，** 然后单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="920a4-123">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="920a4-124">单击"选择用户、组或团队以指定邮箱"时，显示的邮箱选取器为空。</span><span class="sxs-lookup"><span data-stu-id="920a4-124">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="920a4-125">這項設計的目的是提升效能。</span><span class="sxs-lookup"><span data-stu-id="920a4-125">This is by design to enhance performance.</span></span> <span data-ttu-id="920a4-126">要将人员添加到此列表，在搜索框中键入名称（至少 3 个字符）。</span><span class="sxs-lookup"><span data-stu-id="920a4-126">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="920a4-127">**SharePoint 网站**-**单击"选择网站"，** 然后再次**单击"选择网站"** 以指定要添加到人员的其他 SharePoint 和 OneDrive 业务网站。</span><span class="sxs-lookup"><span data-stu-id="920a4-127">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you wwant to add to a person.</span></span> <span data-ttu-id="920a4-128">您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="920a4-128">You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="920a4-129">键入要分配的每个网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="920a4-129">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="920a4-130">**单击"选择"，** 然后单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="920a4-130">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="920a4-131">**微软团队**–**单击"选择团队"，** 然后再次单击"**选择团队"** 以查看此人是今天成员的 Microsoft 团队组的列表。</span><span class="sxs-lookup"><span data-stu-id="920a4-131">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the person is a member of today.</span></span> <span data-ttu-id="920a4-132">选择要添加到人员中的团队。</span><span class="sxs-lookup"><span data-stu-id="920a4-132">Select the Teams that you want to add to the person.</span></span> <span data-ttu-id="920a4-133">选择后，系统将自动标识&选择与 Microsoft 团队关联的共享点和组邮箱。</span><span class="sxs-lookup"><span data-stu-id="920a4-133">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="920a4-134">**单击"选择"，** 然后单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="920a4-134">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="920a4-135">要添加其他 Microsoft 团队，您需要单独添加邮箱和 SharePoint 网站，如上所示。</span><span class="sxs-lookup"><span data-stu-id="920a4-135">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="920a4-136">将数据源映射到感兴趣的人员后，可以看到刚刚添加的总邮箱、站点和团队的摘要。</span><span class="sxs-lookup"><span data-stu-id="920a4-136">After you have finished mapping data sources to people of interest, you can see the summary of total mailboxes, sites, and Teams that you just added.</span></span> <span data-ttu-id="920a4-137">如果将任何其他数据源映射到感兴趣的人，并且将感兴趣的人搜索的范围，则在整个调查过程中，文档与感兴趣的人进行映射将保持不变，从而更容易组织证据或生成感兴趣的人的报告.</span><span class="sxs-lookup"><span data-stu-id="920a4-137">If you map any additional data sources to people of interest and scope your search by people of interest, the mapping of document to people of interest persist throughout the investigation, making it easier to organize evidence or generate report by people of interest.</span></span> 

## <a name="view-additional-people-of-interest-information"></a><span data-ttu-id="920a4-138">查看其他感兴趣的人员信息</span><span class="sxs-lookup"><span data-stu-id="920a4-138">View additional people of interest information</span></span>

<span data-ttu-id="920a4-139">**在"感兴趣的人"** 选项卡中，单击您已处理的人。</span><span class="sxs-lookup"><span data-stu-id="920a4-139">In **People of interest** tab, click on a person that you adeed.</span></span> <span data-ttu-id="920a4-140">在弹出窗口中，您将看到：</span><span class="sxs-lookup"><span data-stu-id="920a4-140">In a flyout, you'll see:</span></span>

- <span data-ttu-id="920a4-141">联系信息</span><span class="sxs-lookup"><span data-stu-id="920a4-141">Contact information</span></span>

  - <span data-ttu-id="920a4-142">**显示名称**： 通讯簿中显示的 peron 名称。</span><span class="sxs-lookup"><span data-stu-id="920a4-142">**Display Name**: The peron's name displayed in the address book.</span></span> <span data-ttu-id="920a4-143">这通常是名字、中间首字母和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="920a4-143">This is usually the combination of first name, middle initial and last name.</span></span>
  - <span data-ttu-id="920a4-144">**邮件/SMTP**： 人员的 SMTP 地址，例如，jeff@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="920a4-144">**Mail/SMTP**: The SMTP address of the person, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="920a4-145">**标题**： 职务。</span><span class="sxs-lookup"><span data-stu-id="920a4-145">**Title**: Job title.</span></span>
  - <span data-ttu-id="920a4-146">**部门：** 该人工作的部门的名称。</span><span class="sxs-lookup"><span data-stu-id="920a4-146">**Department**: The name of the department in which the person works.</span></span>
  - <span data-ttu-id="920a4-147">**经理：** 该人的经理。</span><span class="sxs-lookup"><span data-stu-id="920a4-147">**Manager**: The person's manager.</span></span> <span data-ttu-id="920a4-148">经理接收此人的任何上报通信。</span><span class="sxs-lookup"><span data-stu-id="920a4-148">Manager receives any escalation communications for this person.</span></span>
  
- <span data-ttu-id="920a4-149">位置信息</span><span class="sxs-lookup"><span data-stu-id="920a4-149">Location information</span></span>

  - <span data-ttu-id="920a4-150">**城市：** 人所在的城市。</span><span class="sxs-lookup"><span data-stu-id="920a4-150">**City**: The city in which the person is located.</span></span>
  - <span data-ttu-id="920a4-151">**州：** 该人所在的州或省。</span><span class="sxs-lookup"><span data-stu-id="920a4-151">**State**: The state or province in which the person is located.</span></span>
  - <span data-ttu-id="920a4-152">**国家/地区：** 人员所在的国家/地区;例如，"美国"或"英国"。</span><span class="sxs-lookup"><span data-stu-id="920a4-152">**Country/Region**: The country/region in which the person is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="920a4-153">**办公室：** 人员的办公室位置。</span><span class="sxs-lookup"><span data-stu-id="920a4-153">**Office**: The office location of the person.</span></span>

- <span data-ttu-id="920a4-154">处理状态</span><span class="sxs-lookup"><span data-stu-id="920a4-154">Processing status</span></span>

  - <span data-ttu-id="920a4-155">**索引状态**： 数据源深度索引的状态</span><span class="sxs-lookup"><span data-stu-id="920a4-155">**Indexing status**: Status of deep indexing the data sources</span></span>
  - <span data-ttu-id="920a4-156">**索引上次更新时间：** 上次触发深度索引作业的时间戳。</span><span class="sxs-lookup"><span data-stu-id="920a4-156">**Indexing Last Updated Time**: Timestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="920a4-157">**数据源**：显示映射到此人的邮箱、站点和团队的计数</span><span class="sxs-lookup"><span data-stu-id="920a4-157">**Data sources**: Shows the count of mailboxes, sites, and Teams mapped to the person</span></span>

- <span data-ttu-id="920a4-158">更新索引</span><span class="sxs-lookup"><span data-stu-id="920a4-158">Update index</span></span>
    - <span data-ttu-id="920a4-159">您可以重新索引此人的数据源。</span><span class="sxs-lookup"><span data-stu-id="920a4-159">You can re-index this person's data sources.</span></span> 

- <span data-ttu-id="920a4-160">查看活动</span><span class="sxs-lookup"><span data-stu-id="920a4-160">View activity</span></span> 

    - <span data-ttu-id="920a4-161">您可以查看和搜索用户的活动日志。</span><span class="sxs-lookup"><span data-stu-id="920a4-161">You can view and search user's activity logs.</span></span> <span data-ttu-id="920a4-162">有关详细信息，请参阅[查看感兴趣的人员活动](view-people-of-interest-activity.md)</span><span class="sxs-lookup"><span data-stu-id="920a4-162">For more information, see [View people of interest activity](view-people-of-interest-activity.md)</span></span> 
