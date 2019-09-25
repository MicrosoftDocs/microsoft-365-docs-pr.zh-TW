---
title: 搜尋並刪除郵件 - 管理中心說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 管理员可以使用搜索邮箱 cmdlet 搜索用户邮箱，然后从邮箱中删除邮件。
ms.openlocfilehash: bb375bc7a3273e78acb44807e51a1cee0261e7af
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077566"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="e98b4-103">搜尋並刪除郵件 - 管理中心說明</span><span class="sxs-lookup"><span data-stu-id="e98b4-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="e98b4-104">管理员可以使用**搜索邮箱**cmdlet 搜索用户邮箱，然后从邮箱中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="e98b4-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="e98b4-105">要在一个步骤中搜索和删除邮件，请_使用"删除内容"_ 开关运行**搜索邮箱**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e98b4-105">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="e98b4-106">但是，执行此操作时，无法预览搜索结果或生成搜索将返回的邮件日志，并且可能会无意中删除您不打算删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="e98b4-106">However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to.</span></span> <span data-ttu-id="e98b4-107">要在删除邮件之前预览搜索中的邮件的日志，请_使用"仅 LogOnly"_ 开关运行**搜索邮箱**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e98b4-107">To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="e98b4-108">作为附加保护，您可以首先使用_目标邮箱_和目标_文件夹_参数将邮件复制到另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="e98b4-108">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters.</span></span> <span data-ttu-id="e98b4-109">通过执行此操作，您可以保留已删除邮件的副本，以防需要再次访问它们。</span><span class="sxs-lookup"><span data-stu-id="e98b4-109">By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="e98b4-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="e98b4-110">Before you begin</span></span>

- <span data-ttu-id="e98b4-111">預估完成時間：10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="e98b4-111">Estimated time to complete: 10 minutes.</span></span> <span data-ttu-id="e98b4-112">实际时间可能因邮箱大小和搜索查询而异。</span><span class="sxs-lookup"><span data-stu-id="e98b4-112">The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="e98b4-113">不能使用 Exchange 管理中心 （EAC） 执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="e98b4-113">You can't use the Exchange admin center (EAC) to perform these procedures.</span></span> <span data-ttu-id="e98b4-114">您必須使用命令介面。</span><span class="sxs-lookup"><span data-stu-id="e98b4-114">You must use the Shell.</span></span>
    
- <span data-ttu-id="e98b4-115">您需要分配以下两个管理角色来搜索和删除用户邮箱中的邮件：</span><span class="sxs-lookup"><span data-stu-id="e98b4-115">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="e98b4-116">**邮箱搜索**- 此角色允许您跨组织中的多个邮箱搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="e98b4-116">**Mailbox Search**- This role allows you to search for messages across multiple mailboxes in your organization.</span></span> <span data-ttu-id="e98b4-117">根據預設，系統管理員不會被指派這個角色。</span><span class="sxs-lookup"><span data-stu-id="e98b4-117">Administrators aren't assigned this role by default.</span></span> <span data-ttu-id="e98b4-118">要为自己分配此角色以便可以搜索邮箱，请将自己添加为"发现管理"角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="e98b4-118">To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group.</span></span> <span data-ttu-id="e98b4-119">请参阅[将用户添加到发现管理角色组](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e98b4-119">See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="e98b4-120">**邮箱导入导出**- 此角色允许您从用户的邮箱中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="e98b4-120">**Mailbox Import Export** - This role allows you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="e98b4-121">默认情况下，此角色不会分配给任何角色组。</span><span class="sxs-lookup"><span data-stu-id="e98b4-121">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="e98b4-122">要从用户的邮箱中删除邮件，可以将邮箱导入导出角色添加到组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="e98b4-122">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="e98b4-123">有关详细信息，请参阅[管理角色组中](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)的"将角色添加到角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="e98b4-123">For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="e98b4-124">如果要从中删除邮件的邮箱启用了单个项目恢复，则必须首先禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="e98b4-124">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature.</span></span> <span data-ttu-id="e98b4-125">如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e98b4-125">For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="e98b4-126">如果要删除邮件的邮箱处于保留状态，我们建议您在删除保留和删除邮箱内容之前咨询记录管理或法律部门。</span><span class="sxs-lookup"><span data-stu-id="e98b4-126">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content.</span></span> <span data-ttu-id="e98b4-127">获得批准后，请按照"[清理可恢复项目文件夹"](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)主题中列出的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="e98b4-127">After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="e98b4-128">您可以使用**搜索邮箱**cmdlet 搜索最多 10，000 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="e98b4-128">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="e98b4-129">如果您是 Exchange 在线组织，并且邮箱超过 10，000 个，则可以使用合规性搜索功能（或相应的**New 合规性搜索**cmdlet）搜索无限数量的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e98b4-129">If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes.</span></span> <span data-ttu-id="e98b4-130">然后，**您可以使用"新合规性搜索**操作"cmdlet 删除合规性搜索返回的邮件。</span><span class="sxs-lookup"><span data-stu-id="e98b4-130">Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search.</span></span> <span data-ttu-id="e98b4-131">有关详细信息，请参阅[搜索和删除来自 Office 365 组织的电子邮件。](https://go.microsoft.com/fwlink/p/?LinkId=786856)</span><span class="sxs-lookup"><span data-stu-id="e98b4-131">For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="e98b4-132">如果包含搜索查询（通过使用*搜索查询*参数），**搜索邮箱**cmdlet 将在搜索结果中返回最多 10，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="e98b4-132">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results.</span></span> <span data-ttu-id="e98b4-133">因此，如果包含搜索查询，则可能需要多次运行**搜索邮箱**命令才能删除 10，000 多个项目。</span><span class="sxs-lookup"><span data-stu-id="e98b4-133">Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="e98b4-134">运行**搜索邮箱**cmdlet 时，还将搜索用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="e98b4-134">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="e98b4-135">同样，当您使用"_删除内容"_ 开关的**搜索邮箱**cmdlet 时，主存档邮箱中的项目将被删除。</span><span class="sxs-lookup"><span data-stu-id="e98b4-135">Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="e98b4-136">为了防止这种情况，您可以*包括"不包含存档"* 开关。</span><span class="sxs-lookup"><span data-stu-id="e98b4-136">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span>
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="e98b4-137">搜索消息并记录搜索结果</span><span class="sxs-lookup"><span data-stu-id="e98b4-137">Search messages and log the search results</span></span>

<span data-ttu-id="e98b4-138">本示例在"主题"字段中搜索 4 月 Stewart 的邮箱，查找包含短语"您的银行对帐单"的邮件，并将搜索结果记录在管理员邮箱的"搜索和删除日志"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e98b4-138">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox.</span></span> <span data-ttu-id="e98b4-139">邮件不会复制到目标邮箱或从目标邮箱中删除。</span><span class="sxs-lookup"><span data-stu-id="e98b4-139">Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="e98b4-140">本示例搜索组织中的所有邮箱，以寻找文件名中包含单词"特洛伊木马"的任何类型的附加文件的邮件，并将日志邮件发送到管理员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e98b4-140">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="e98b4-141">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e98b4-141">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
 
## <a name="search-and-delete-messages"></a><span data-ttu-id="e98b4-142">搜索和删除邮件</span><span class="sxs-lookup"><span data-stu-id="e98b4-142">Search and delete messages</span></span>

<span data-ttu-id="e98b4-143">本示例在"主题"字段中搜索 April Stewart 的邮箱，查找包含短语"您的银行对帐单"的邮件，并从源邮箱中删除邮件，而无需将搜索结果复制到其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="e98b4-143">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder.</span></span> <span data-ttu-id="e98b4-144">如前所述，您需要分配邮箱导入导入管理角色，以便从用户的邮箱中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="e98b4-144">As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e98b4-145">当您将**搜索邮箱**cmdlet_与"删除内容"_ 开关一起使用时，邮件将从源邮箱中永久删除。</span><span class="sxs-lookup"><span data-stu-id="e98b4-145">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox.</span></span> <span data-ttu-id="e98b4-146">在永久删除邮件之前，我们建议您使用_LogOnly_开关在删除邮件之前生成搜索中的邮件的日志，或者在从源邮箱中删除邮件之前将邮件复制到其他邮箱。</span><span class="sxs-lookup"><span data-stu-id="e98b4-146">Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="e98b4-147">本示例在 4 月 Stewart 的邮箱中搜索包含"主题"字段中短语"您的银行对帐单"的邮件，将搜索结果复制到邮箱备份邮箱中的文件夹 AprilStewart-DeleteDMessages，并从中删除邮件。四月的邮箱</span><span class="sxs-lookup"><span data-stu-id="e98b4-147">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="e98b4-148">本示例搜索组织中的所有邮箱，查找主题行为"下载此文件"的邮件，然后永久删除它们。</span><span class="sxs-lookup"><span data-stu-id="e98b4-148">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="e98b4-149">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e98b4-149">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>

## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="e98b4-150">使用 -日志级别完整参数</span><span class="sxs-lookup"><span data-stu-id="e98b4-150">Using the -LogLevel Full parameter</span></span>

<span data-ttu-id="e98b4-151">在前面的一些示例中，LogLevel__ 参数（带 值）`Full`用于记录有关**搜索邮箱**cmdlet 返回的结果的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e98b4-151">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="e98b4-152">包含此参数后，将创建一封电子邮件并将其发送到_由 TargetMailbox_参数指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e98b4-152">When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter.</span></span> <span data-ttu-id="e98b4-153">日志文件（是名为搜索结果.csv 的 CSV 格式文件）附加到此电子邮件，并将位于_由 TargetFolder_参数指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e98b4-153">The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter.</span></span> <span data-ttu-id="e98b4-154">日志文件包含运行**搜索邮箱**cmdlet 时搜索结果中包含的每封邮件的行。</span><span class="sxs-lookup"><span data-stu-id="e98b4-154">The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
