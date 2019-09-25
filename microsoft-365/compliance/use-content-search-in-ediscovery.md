---
title: 在您的 eDiscovery 工作流程中使用內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 脚本基于在安全&合规性中心创建的搜索，在 Exchange 在线中创建就地电子数据展示搜索。 '
ms.openlocfilehash: f3d5eb76dfa91334bccae42e0ddb66a71f739a6f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077459"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="ec35b-103">在您的電子文件探索工作流程中使用內容搜尋</span><span class="sxs-lookup"><span data-stu-id="ec35b-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="ec35b-104">安全&合规性中心的内容搜索功能允许您搜索组织中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-104">The Content Search feature in the Security & Compliance Center allows you to search all mailboxes in your organization.</span></span> <span data-ttu-id="ec35b-105">与 Exchange 在线中的就地电子数据展示（其中最多可搜索 10，000 个邮箱）不同，单个搜索中的目标邮箱数没有限制。</span><span class="sxs-lookup"><span data-stu-id="ec35b-105">Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search.</span></span> <span data-ttu-id="ec35b-106">對於要求您執行整個組織搜尋的案例，您可以使用「內容搜尋」來搜尋所有信箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-106">For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes.</span></span> <span data-ttu-id="ec35b-107">然后，您可以使用就地电子数据展示的工作流功能执行其他与电子数据展示相关的任务，例如将邮箱置于保留状态和导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ec35b-107">Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results.</span></span> <span data-ttu-id="ec35b-108">例如，假設您必須搜尋所有信箱以識別回應法律案件的特定監管人。</span><span class="sxs-lookup"><span data-stu-id="ec35b-108">For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case.</span></span> <span data-ttu-id="ec35b-109">您可以使用安全&合规性中心中的内容搜索来搜索组织中的所有邮箱，以识别响应案例的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-109">You can use Content Search in the Security & Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case.</span></span> <span data-ttu-id="ec35b-110">然后，您可以将托管邮箱列表用作 Exchange 在线中就地电子数据展示搜索的源邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-110">Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online.</span></span> <span data-ttu-id="ec35b-111">使用就地电子数据展示还允许您对这些源邮箱进行保留，将搜索结果复制到发现邮箱，并导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ec35b-111">Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="ec35b-112">本主题包括一个脚本，您可以使用在安全&合规性中心创建的搜索中的源邮箱列表和搜索查询，运行该脚本，在 Exchange 联机中创建就地电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="ec35b-112">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security & Compliance Center.</span></span> <span data-ttu-id="ec35b-113">以下是程序的概觀：</span><span class="sxs-lookup"><span data-stu-id="ec35b-113">Here's an overview of the process:</span></span>
  
[<span data-ttu-id="ec35b-114">步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱</span><span class="sxs-lookup"><span data-stu-id="ec35b-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="ec35b-115">第 2 步：在\&单个远程 PowerShell 会话中连接到安全合规性中心和在线交换</span><span class="sxs-lookup"><span data-stu-id="ec35b-115">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="ec35b-116">步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋</span><span class="sxs-lookup"><span data-stu-id="ec35b-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="ec35b-117">Step 4: Start the In-Place eDiscovery search</span><span class="sxs-lookup"><span data-stu-id="ec35b-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="ec35b-118">步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱</span><span class="sxs-lookup"><span data-stu-id="ec35b-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="ec35b-119">第一步是使用安全&合规性中心（或安全&合规性中心 PowerShell）创建内容搜索，以搜索组织中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-119">The first step is to use the Security & Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization.</span></span> <span data-ttu-id="ec35b-120">單一內容搜尋的信箱數目沒有限制。</span><span class="sxs-lookup"><span data-stu-id="ec35b-120">There's no limit for the number of mailboxes for a single Content Search.</span></span> <span data-ttu-id="ec35b-121">指定適當的關鍵字查詢 (或敏感資訊類型的查詢)，讓搜尋僅傳回與調查有關的來源信箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-121">Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation.</span></span> <span data-ttu-id="ec35b-122">如有必要，縮小搜尋查詢以縮小搜尋結果的範圍和傳回的來源信箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-122">If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec35b-p104">如果來源內容搜尋沒有傳回任何結果，當您在步驟 3 中執行指令碼時不會建立就地 eDiscovery。您可能必須修改搜尋查詢然後重新執行內容搜尋以傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="ec35b-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="ec35b-125">使用安全規範中心來搜尋所有信箱</span><span class="sxs-lookup"><span data-stu-id="ec35b-125">Use the Security & Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="ec35b-126">[转到安全&合规中心。](go-to-the-securitycompliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="ec35b-126">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="ec35b-127">**单击"搜索** > **内容搜索"，\*\*\*\*然后单击"新建搜索**![添加"图标。](media/O365-MDM-CreatePolicy-AddIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="ec35b-127">Click **Search** > **Content search**, and then click **New search** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="ec35b-128">在 **[新增搜尋]** 頁面上，輸入內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="ec35b-129">在 [您希望我們在哪裡搜尋?]\*\*\*\* 底下按一下 [搜尋所有信箱]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec35b-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="ec35b-130">在 [您希望我們尋找什麼?]\*\*\*\* 下方的方塊，在方塊中輸入搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="ec35b-130">In the box under **What do you want us to look for?**, type a search query in the box.</span></span> <span data-ttu-id="ec35b-131">您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。</span><span class="sxs-lookup"><span data-stu-id="ec35b-131">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="ec35b-132">您可以使用使用布尔运算符的更复杂的查询，例如 AND、OR、NOT 或 NEAR，也可以在消息中搜索敏感信息（如社会保险号）。</span><span class="sxs-lookup"><span data-stu-id="ec35b-132">You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages.</span></span> <span data-ttu-id="ec35b-133">如需建立搜尋查詢的相關資訊，請參閱[Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="ec35b-133">For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="ec35b-134">按一下 [搜尋]\*\*\*\* 以儲存搜尋設定並開始搜尋。</span><span class="sxs-lookup"><span data-stu-id="ec35b-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="ec35b-135">一段时间后，详细信息窗格中显示的搜索结果估计值。</span><span class="sxs-lookup"><span data-stu-id="ec35b-135">After a while, an estimate of the search results displayed in the details pane.</span></span> <span data-ttu-id="ec35b-136">預估包括搜尋結果的項目大小總計和總數。</span><span class="sxs-lookup"><span data-stu-id="ec35b-136">The estimate includes the total size and number of items for the search results.</span></span> <span data-ttu-id="ec35b-137">在搜尋完成之後，您可以預覽搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="ec35b-137">After the search is completed, you can preview the search results.</span></span> <span data-ttu-id="ec35b-138">如有必要，**单击"刷新**![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="ec35b-138">If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="ec35b-139">如有必要，縮小搜尋查詢以縮小搜尋結果的範圍然後重新啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="ec35b-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="ec35b-140">使用安全&合规性中心 PowerShell 搜索所有邮箱</span><span class="sxs-lookup"><span data-stu-id="ec35b-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="ec35b-141">您也可以使用 **New-ComplianceSearch** Cmdlet 來搜尋組織中的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-141">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization.</span></span> <span data-ttu-id="ec35b-142">第一步是[连接到安全&合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。</span><span class="sxs-lookup"><span data-stu-id="ec35b-142">The first step is to [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="ec35b-143">下面是使用 PowerShell 搜索组织中的所有邮箱的示例。</span><span class="sxs-lookup"><span data-stu-id="ec35b-143">Here's an example of using PowerShell to search all mailboxes in your organization.</span></span> <span data-ttu-id="ec35b-144">搜尋查詢會傳回 2015 年 1 月 1 日和 2015 年 6 月 30 日之間傳送的所有郵件，以及主旨行中包含片語 "financial report" 的郵件。</span><span class="sxs-lookup"><span data-stu-id="ec35b-144">The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line.</span></span> <span data-ttu-id="ec35b-145">第一個命令會建立搜尋，第二個命令會執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="ec35b-145">The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="ec35b-146">有关详细信息，请参阅[新合规性搜索](https://go.microsoft.com/fwlink/p/?LinkId=517935)。</span><span class="sxs-lookup"><span data-stu-id="ec35b-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="ec35b-147">確認內容搜尋中的來源信箱數目</span><span class="sxs-lookup"><span data-stu-id="ec35b-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="ec35b-148">内容搜索最多返回 1，000 个包含搜索结果的源邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-148">A Content Search returns a maximum of 1,000 source mailboxes that contain search results.</span></span> <span data-ttu-id="ec35b-149">如果包含与搜索查询匹配的内容的邮箱超过 1，000 个，则上一步中创建的内容搜索中仅包含搜索结果最多的前 1，000 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-149">If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step.</span></span> <span data-ttu-id="ec35b-150">因此，如果超过 1，000 个邮箱包含搜索结果，则其中一些邮箱将不会包含在复制到步骤 3 中创建的新就地电子数据展示搜索的源邮箱列表中。</span><span class="sxs-lookup"><span data-stu-id="ec35b-150">So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="ec35b-151">为了帮助您创建源邮箱不超过 1，000 个的内容搜索，请按照以下步骤运行一个脚本，该脚本显示您在步骤 1 中创建的内容搜索返回的源邮箱数（包含搜索结果）。</span><span class="sxs-lookup"><span data-stu-id="ec35b-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="ec35b-152">使用文件名后缀 .ps1 将以下文本保存到 PowerShell 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="ec35b-152">Save the following text to a PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="ec35b-153">例如，您可以将其保存到名为`SourceMailboxes.ps1`的文件。</span><span class="sxs-lookup"><span data-stu-id="ec35b-153">For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. <span data-ttu-id="ec35b-154">在"安全&合规性中心 PowerShell 中，转到您在上一步中创建的脚本所在的文件夹，然后运行该脚本;然后，转到在上一步中创建的脚本所在的文件夹，然后运行该脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="ec35b-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="ec35b-155">當指令碼提示時，輸入您在步驟 1 中建立的內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="ec35b-156">指令碼會顯示包含搜尋結果的來源信箱數目。</span><span class="sxs-lookup"><span data-stu-id="ec35b-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="ec35b-157">如果源邮箱超过 1，000 个，请尝试创建两个（或更多）内容搜索。</span><span class="sxs-lookup"><span data-stu-id="ec35b-157">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches.</span></span> <span data-ttu-id="ec35b-158">例如，在一個內容搜尋中搜尋您組織的一半信箱，在另一個內容搜尋中搜尋另外一半。</span><span class="sxs-lookup"><span data-stu-id="ec35b-158">For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search.</span></span> <span data-ttu-id="ec35b-159">您也可以變更搜尋準則來減少包含搜尋結果的信箱數目。</span><span class="sxs-lookup"><span data-stu-id="ec35b-159">You could also change the search criteria to reduce the number of mailboxes that contain search results.</span></span> <span data-ttu-id="ec35b-160">例如，可以包括日期范围或优化关键字查询。</span><span class="sxs-lookup"><span data-stu-id="ec35b-160">For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="ec35b-161">第 2 步：在\&单个远程 PowerShell 会话中连接到安全合规性中心和在线交换</span><span class="sxs-lookup"><span data-stu-id="ec35b-161">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="ec35b-162">下一步是将 Windows PowerShell 连接到安全&合规性中心和 Exchange 在线组织。</span><span class="sxs-lookup"><span data-stu-id="ec35b-162">The next step is to connect Windows PowerShell to both the Security & Compliance Center and to your Exchange Online organization.</span></span> <span data-ttu-id="ec35b-163">这是必需的，因为您在步骤 3 中运行的脚本需要访问安全&合规性中心的内容搜索 cmdlet 和 Exchange 在线中的就地电子数据展示 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ec35b-163">This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security & Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="ec35b-164">使用文件名后缀 .ps1 将以下文本保存到 Windows PowerShell 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="ec35b-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="ec35b-165">例如，您可以将其保存到名为`ConnectEXO-CC.ps1`的文件。</span><span class="sxs-lookup"><span data-stu-id="ec35b-165">For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="ec35b-166">在本地计算机上，打开 Windows PowerShell，转到您在上一步中创建的脚本所在的文件夹，然后运行该脚本;然后，打开 Windows PowerShell。"例如：</span><span class="sxs-lookup"><span data-stu-id="ec35b-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="ec35b-167">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="ec35b-167">How do you know if this worked?</span></span> <span data-ttu-id="ec35b-168">运行脚本后，来自安全&合规性中心和 Exchange Online 的 cmdlet 将导入到您的本地 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="ec35b-168">After you run the script, cmdlets from the Security & Compliance Center and Exchange Online are imported into your local PowerShell session.</span></span> <span data-ttu-id="ec35b-169">如果您未收到任何錯誤，便已順利連線。</span><span class="sxs-lookup"><span data-stu-id="ec35b-169">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="ec35b-170">快速测试是运行安全&合规性中心 cmdlet（例如，**安装统一合规性先决条件）** 和 Exchange 联机 cmdlet，如**获取邮箱**。</span><span class="sxs-lookup"><span data-stu-id="ec35b-170">A quick test is to run a Security & Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="ec35b-171">步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋</span><span class="sxs-lookup"><span data-stu-id="ec35b-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="ec35b-172">在步骤 2 中创建双 PowerShell 会话后，下一步是运行一个脚本，该脚本将现有内容搜索转换为就地电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="ec35b-172">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search.</span></span> <span data-ttu-id="ec35b-173">以下是指令碼執行的動作：</span><span class="sxs-lookup"><span data-stu-id="ec35b-173">Here's what the script does:</span></span>
  
- <span data-ttu-id="ec35b-174">提示您輸入要轉換的內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="ec35b-p116">確認內容搜尋已完成執行。如果內容搜尋未傳回任何結果，就不會建立就地 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="ec35b-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="ec35b-177">從包含搜尋結果的內容搜尋將來源信箱的清單儲存至變數。</span><span class="sxs-lookup"><span data-stu-id="ec35b-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="ec35b-p117">建立新的就地 eDiscovery 搜尋，具有下列屬性。請注意，並未啟動新的搜尋。您將在步驟 4 中加以啟動。</span><span class="sxs-lookup"><span data-stu-id="ec35b-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="ec35b-181">**名称**- 新搜索的名称使用此格式：\<内容名称搜索\>@MBSearch1。</span><span class="sxs-lookup"><span data-stu-id="ec35b-181">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1.</span></span> <span data-ttu-id="ec35b-182">如果再次运行脚本并使用相同的源内容搜索，则搜索将命名为\<内容名称搜索\>@MBSearch2。</span><span class="sxs-lookup"><span data-stu-id="ec35b-182">If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="ec35b-183">**源邮箱**- 包含搜索结果的内容搜索中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="ec35b-184">**搜索查询**- 新搜索使用内容搜索中的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="ec35b-184">**Search query** - The new search uses the search query from the Content Search.</span></span> <span data-ttu-id="ec35b-185">如果內容搜尋包括所有內容 (其中搜尋查詢為空白)，新的搜尋也會有空白的搜尋查詢並將包含在來源信箱中找到的所有內容。</span><span class="sxs-lookup"><span data-stu-id="ec35b-185">If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="ec35b-186">**仅估计搜索**- 新搜索标记为仅估计搜索。</span><span class="sxs-lookup"><span data-stu-id="ec35b-186">**Estimate only search** - The new search is marked as an estimate-only search.</span></span> <span data-ttu-id="ec35b-187">在啟動之後，它不會將搜尋結果複製到探索信箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-187">It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="ec35b-188">使用 ps1 的文件名后缀将以下文本保存到 Windows PowerShell 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="ec35b-188">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1.</span></span> <span data-ttu-id="ec35b-189">例如，您可以将其保存到名为`CreateMBSearchFromComplianceSearch.ps1`的文件。</span><span class="sxs-lookup"><span data-stu-id="ec35b-189">For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. <span data-ttu-id="ec35b-190">在步骤 2 中创建的 Windows PowerShell 会话中，转到您在上一步中创建的脚本所在的文件夹，然后运行该脚本;然后，转到在步骤 2 中创建的脚本所在的文件夹。例如：</span><span class="sxs-lookup"><span data-stu-id="ec35b-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="ec35b-191">当脚本提示时，键入要隐藏到就地电子数据展示搜索的内容搜索的名称（例如，您在步骤 1 中创建的搜索），然后按**Enter。**</span><span class="sxs-lookup"><span data-stu-id="ec35b-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="ec35b-192">如果指令碼狀態為成功，會建立新的就地 eDiscovery 搜尋，狀態為 **NotStarted**。</span><span class="sxs-lookup"><span data-stu-id="ec35b-192">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**.</span></span> <span data-ttu-id="ec35b-193">运行该命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`以显示新搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="ec35b-193">Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="ec35b-194">步驟 4：啟動就地 eDiscovery 搜尋</span><span class="sxs-lookup"><span data-stu-id="ec35b-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="ec35b-p123">您在步驟 3 中執行的指令碼會建立新的就地 eDiscovery 搜尋，但不會啟動。下一個步驟是啟動搜尋，讓您取得搜尋結果的預估。</span><span class="sxs-lookup"><span data-stu-id="ec35b-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="ec35b-197">在 Exchange 管理中心 （EAC） 中，转到**合规管理**\>**就地&amp;电子数据展示保留**。</span><span class="sxs-lookup"><span data-stu-id="ec35b-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="ec35b-198">在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="ec35b-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="ec35b-199">**单击"搜索**![搜索"](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)\>**图标"估计搜索结果"** 以开始搜索并返回搜索返回的总大小和项目数的估计值。</span><span class="sxs-lookup"><span data-stu-id="ec35b-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="ec35b-200">估計結果會顯示在詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="ec35b-200">The estimates are displayed in the details pane.</span></span> <span data-ttu-id="ec35b-201">**单击"刷新**![刷新"图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新详细信息窗格中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="ec35b-201">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="ec35b-202">若要在搜尋完成之後預覽結果，按一下詳細資料窗格中的 [預覽搜尋結果]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec35b-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="ec35b-203">建立和執行就地 eDiscovery 搜尋之後接下來的步驟</span><span class="sxs-lookup"><span data-stu-id="ec35b-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="ec35b-204">建立並啟動步驟 3 中的指令碼建立的就地 eDiscovery 搜尋之後，您可以使用一般的就地 eDiscovery 工作流程在搜尋結果上執行不同的 eDiscovery 動作。</span><span class="sxs-lookup"><span data-stu-id="ec35b-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="ec35b-205">建立就地保留</span><span class="sxs-lookup"><span data-stu-id="ec35b-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="ec35b-206">在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。</span><span class="sxs-lookup"><span data-stu-id="ec35b-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="ec35b-207">在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索，然后单击"**编辑"**![图标](media/O365-MDM-CreatePolicy-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="ec35b-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="ec35b-208">在 [就地保留設定]\*\*\*\* 頁面上，勾選 [將符合搜尋查詢的內容放入保留的所選信箱]\*\*\*\* 核取方塊，然後選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="ec35b-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="ec35b-209">**无限期保留**- 选择此选项可将搜索返回的项目置于无限期保留状态。</span><span class="sxs-lookup"><span data-stu-id="ec35b-209">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold.</span></span> <span data-ttu-id="ec35b-210">除非您從搜尋中移除信箱或移除搜尋，否則保留的項目會一直保存下來。</span><span class="sxs-lookup"><span data-stu-id="ec35b-210">Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="ec35b-211">**指定相对于其接收日期持有物料的天数**- 选择此选项可保存特定期间的物料。</span><span class="sxs-lookup"><span data-stu-id="ec35b-211">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period.</span></span> <span data-ttu-id="ec35b-212">持續時間自接收或建立信箱項目的日期開始計算。</span><span class="sxs-lookup"><span data-stu-id="ec35b-212">The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="ec35b-213">按一下 [儲存]\*\*\*\* 以建立就地保留並重新啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="ec35b-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="ec35b-214">回到頁首</span><span class="sxs-lookup"><span data-stu-id="ec35b-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="ec35b-215">複製搜尋結果</span><span class="sxs-lookup"><span data-stu-id="ec35b-215">Copy the search results</span></span>

1. <span data-ttu-id="ec35b-216">在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。</span><span class="sxs-lookup"><span data-stu-id="ec35b-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="ec35b-217">在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="ec35b-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="ec35b-218">**单击"搜索**![搜索"图标，](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)然后单击"从下拉列表中**复制搜索结果"。**</span><span class="sxs-lookup"><span data-stu-id="ec35b-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="ec35b-219">在 [複製搜尋結果]\*\*\*\* 中，從下列選項選取：</span><span class="sxs-lookup"><span data-stu-id="ec35b-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="ec35b-220">**包括不可搜索的项目**- 选中此复选框以包括无法搜索的邮箱项目（例如，具有文件类型附件的邮件，无法通过 Exchange 搜索编制索引）。</span><span class="sxs-lookup"><span data-stu-id="ec35b-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="ec35b-221">**启用重复数据消除**- 选中此复选框可排除重复邮件。</span><span class="sxs-lookup"><span data-stu-id="ec35b-221">**Enable de-duplication** - Select this check box to exclude duplicate messages.</span></span> <span data-ttu-id="ec35b-222">只有一个邮件实例将复制到发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-222">Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="ec35b-223">**启用完全日志记录**- 选中此复选框以包含完整的登录搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ec35b-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="ec35b-224">**复制完成后向我发送邮件**- 选中此复选框在搜索完成后收到电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="ec35b-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="ec35b-225">**将结果复制到此发现邮箱**- 单击"**浏览"** 以选择要将搜索结果复制到的发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="ec35b-226">按一下 [複製]\*\*\*\* 以開始程序來將搜尋結果複製到指定的探索信箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="ec35b-227">**单击"刷新**![刷新"图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新详细信息窗格中显示的复制状态信息。</span><span class="sxs-lookup"><span data-stu-id="ec35b-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="ec35b-228">複製完成時，按一下 [開啟]\*\*\*\* 以開啟要檢視搜尋結果的探索信箱。</span><span class="sxs-lookup"><span data-stu-id="ec35b-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="ec35b-229">匯出搜尋結果</span><span class="sxs-lookup"><span data-stu-id="ec35b-229">Export the search results</span></span>

1. <span data-ttu-id="ec35b-230">在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。</span><span class="sxs-lookup"><span data-stu-id="ec35b-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="ec35b-231">在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋，然後按一下 [匯出為 PST 檔案]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec35b-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="ec35b-232">In the **eDiscovery PST Export Tool** window, do the following:</span><span class="sxs-lookup"><span data-stu-id="ec35b-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="ec35b-233">Click **Browse** to specify the location where you want to download the PST file.</span><span class="sxs-lookup"><span data-stu-id="ec35b-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="ec35b-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span><span class="sxs-lookup"><span data-stu-id="ec35b-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="ec35b-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span><span class="sxs-lookup"><span data-stu-id="ec35b-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="ec35b-238">Click **Start** to export the search results to a PST file.</span><span class="sxs-lookup"><span data-stu-id="ec35b-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="ec35b-239">包含匯出程序狀態資訊的視窗便會隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="ec35b-239">A window is displayed that contains status information about the export process.</span></span>
