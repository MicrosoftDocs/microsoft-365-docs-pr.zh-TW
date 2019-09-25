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
# <a name="use-content-search-in-your-ediscovery-workflow"></a>在您的電子文件探索工作流程中使用內容搜尋

安全&合规性中心的内容搜索功能允许您搜索组织中的所有邮箱。 与 Exchange 在线中的就地电子数据展示（其中最多可搜索 10，000 个邮箱）不同，单个搜索中的目标邮箱数没有限制。 對於要求您執行整個組織搜尋的案例，您可以使用「內容搜尋」來搜尋所有信箱。 然后，您可以使用就地电子数据展示的工作流功能执行其他与电子数据展示相关的任务，例如将邮箱置于保留状态和导出搜索结果。 例如，假設您必須搜尋所有信箱以識別回應法律案件的特定監管人。 您可以使用安全&合规性中心中的内容搜索来搜索组织中的所有邮箱，以识别响应案例的邮箱。 然后，您可以将托管邮箱列表用作 Exchange 在线中就地电子数据展示搜索的源邮箱。 使用就地电子数据展示还允许您对这些源邮箱进行保留，将搜索结果复制到发现邮箱，并导出搜索结果。
  
本主题包括一个脚本，您可以使用在安全&合规性中心创建的搜索中的源邮箱列表和搜索查询，运行该脚本，在 Exchange 联机中创建就地电子数据展示搜索。 以下是程序的概觀：
  
[步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[第 2 步：在\&单个远程 PowerShell 会话中连接到安全合规性中心和在线交换](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Step 4: Start the In-Place eDiscovery search](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱

第一步是使用安全&合规性中心（或安全&合规性中心 PowerShell）创建内容搜索，以搜索组织中的所有邮箱。 單一內容搜尋的信箱數目沒有限制。 指定適當的關鍵字查詢 (或敏感資訊類型的查詢)，讓搜尋僅傳回與調查有關的來源信箱。 如有必要，縮小搜尋查詢以縮小搜尋結果的範圍和傳回的來源信箱。
  
> [!NOTE]
> 如果來源內容搜尋沒有傳回任何結果，當您在步驟 3 中執行指令碼時不會建立就地 eDiscovery。您可能必須修改搜尋查詢然後重新執行內容搜尋以傳回搜尋結果。 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>使用安全規範中心來搜尋所有信箱

1. [转到安全&合规中心。](go-to-the-securitycompliance-center.md) 
    
2. **单击"搜索** > **内容搜索"，****然后单击"新建搜索**![添加"图标。](media/O365-MDM-CreatePolicy-AddIcon.gif)
    
3. 在 **[新增搜尋]** 頁面上，輸入內容搜尋的名稱。 
    
4. 在 [您希望我們在哪裡搜尋?]**** 底下按一下 [搜尋所有信箱]****，然後按 [下一步]****。
    
5. 在 [您希望我們尋找什麼?]**** 下方的方塊，在方塊中輸入搜尋查詢。 您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。 您可以使用使用布尔运算符的更复杂的查询，例如 AND、OR、NOT 或 NEAR，也可以在消息中搜索敏感信息（如社会保险号）。 如需建立搜尋查詢的相關資訊，請參閱[Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。
    
6. 按一下 [搜尋]**** 以儲存搜尋設定並開始搜尋。 
    
    一段时间后，详细信息窗格中显示的搜索结果估计值。 預估包括搜尋結果的項目大小總計和總數。 在搜尋完成之後，您可以預覽搜尋結果。 如有必要，**单击"刷新**![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新详细信息窗格中的信息。 
    
7.  如有必要，縮小搜尋查詢以縮小搜尋結果的範圍然後重新啟動搜尋。 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>使用安全&合规性中心 PowerShell 搜索所有邮箱

您也可以使用 **New-ComplianceSearch** Cmdlet 來搜尋組織中的所有信箱。 第一步是[连接到安全&合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。
  
下面是使用 PowerShell 搜索组织中的所有邮箱的示例。 搜尋查詢會傳回 2015 年 1 月 1 日和 2015 年 6 月 30 日之間傳送的所有郵件，以及主旨行中包含片語 "financial report" 的郵件。 第一個命令會建立搜尋，第二個命令會執行搜尋。 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

有关详细信息，请参阅[新合规性搜索](https://go.microsoft.com/fwlink/p/?LinkId=517935)。
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>確認內容搜尋中的來源信箱數目

内容搜索最多返回 1，000 个包含搜索结果的源邮箱。 如果包含与搜索查询匹配的内容的邮箱超过 1，000 个，则上一步中创建的内容搜索中仅包含搜索结果最多的前 1，000 个邮箱。 因此，如果超过 1，000 个邮箱包含搜索结果，则其中一些邮箱将不会包含在复制到步骤 3 中创建的新就地电子数据展示搜索的源邮箱列表中。 
  
为了帮助您创建源邮箱不超过 1，000 个的内容搜索，请按照以下步骤运行一个脚本，该脚本显示您在步骤 1 中创建的内容搜索返回的源邮箱数（包含搜索结果）。 
  
1. 使用文件名后缀 .ps1 将以下文本保存到 PowerShell 脚本文件中。 例如，您可以将其保存到名为`SourceMailboxes.ps1`的文件。
    
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

2. 在"安全&合规性中心 PowerShell 中，转到您在上一步中创建的脚本所在的文件夹，然后运行该脚本;然后，转到在上一步中创建的脚本所在的文件夹，然后运行该脚本。例如：
    
    ```
    .\SourceMailboxes.ps1
    ```

3. 當指令碼提示時，輸入您在步驟 1 中建立的內容搜尋的名稱。
    
    指令碼會顯示包含搜尋結果的來源信箱數目。
    
如果源邮箱超过 1，000 个，请尝试创建两个（或更多）内容搜索。 例如，在一個內容搜尋中搜尋您組織的一半信箱，在另一個內容搜尋中搜尋另外一半。 您也可以變更搜尋準則來減少包含搜尋結果的信箱數目。 例如，可以包括日期范围或优化关键字查询。
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>第 2 步：在\&单个远程 PowerShell 会话中连接到安全合规性中心和在线交换

下一步是将 Windows PowerShell 连接到安全&合规性中心和 Exchange 在线组织。 这是必需的，因为您在步骤 3 中运行的脚本需要访问安全&合规性中心的内容搜索 cmdlet 和 Exchange 在线中的就地电子数据展示 cmdlet。
  
1. 使用文件名后缀 .ps1 将以下文本保存到 Windows PowerShell 脚本文件中。 例如，您可以将其保存到名为`ConnectEXO-CC.ps1`的文件。
    
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

如何知道這是否正常運作？ 运行脚本后，来自安全&合规性中心和 Exchange Online 的 cmdlet 将导入到您的本地 PowerShell 会话中。 如果您未收到任何錯誤，便已順利連線。 快速测试是运行安全&合规性中心 cmdlet（例如，**安装统一合规性先决条件）** 和 Exchange 联机 cmdlet，如**获取邮箱**。 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋

在步骤 2 中创建双 PowerShell 会话后，下一步是运行一个脚本，该脚本将现有内容搜索转换为就地电子数据展示搜索。 以下是指令碼執行的動作：
  
- 提示您輸入要轉換的內容搜尋的名稱。
    
- 確認內容搜尋已完成執行。如果內容搜尋未傳回任何結果，就不會建立就地 eDiscovery。
    
- 從包含搜尋結果的內容搜尋將來源信箱的清單儲存至變數。
    
- 建立新的就地 eDiscovery 搜尋，具有下列屬性。請注意，並未啟動新的搜尋。您將在步驟 4 中加以啟動。
    
  - **名称**- 新搜索的名称使用此格式：\<内容名称搜索\>@MBSearch1。 如果再次运行脚本并使用相同的源内容搜索，则搜索将命名为\<内容名称搜索\>@MBSearch2。
    
  - **源邮箱**- 包含搜索结果的内容搜索中的所有邮箱。 
    
  - **搜索查询**- 新搜索使用内容搜索中的搜索查询。 如果內容搜尋包括所有內容 (其中搜尋查詢為空白)，新的搜尋也會有空白的搜尋查詢並將包含在來源信箱中找到的所有內容。 
    
  - **仅估计搜索**- 新搜索标记为仅估计搜索。 在啟動之後，它不會將搜尋結果複製到探索信箱。 
    
1. 使用 ps1 的文件名后缀将以下文本保存到 Windows PowerShell 脚本文件中。 例如，您可以将其保存到名为`CreateMBSearchFromComplianceSearch.ps1`的文件。
    
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

2. 在步骤 2 中创建的 Windows PowerShell 会话中，转到您在上一步中创建的脚本所在的文件夹，然后运行该脚本;然后，转到在步骤 2 中创建的脚本所在的文件夹。例如：
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. 当脚本提示时，键入要隐藏到就地电子数据展示搜索的内容搜索的名称（例如，您在步骤 1 中创建的搜索），然后按**Enter。**
    
    如果指令碼狀態為成功，會建立新的就地 eDiscovery 搜尋，狀態為 **NotStarted**。 运行该命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`以显示新搜索的属性。 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>步驟 4：啟動就地 eDiscovery 搜尋

您在步驟 3 中執行的指令碼會建立新的就地 eDiscovery 搜尋，但不會啟動。下一個步驟是啟動搜尋，讓您取得搜尋結果的預估。
  
1. 在 Exchange 管理中心 （EAC） 中，转到**合规管理**\>**就地&amp;电子数据展示保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。
    
3. **单击"搜索**![搜索"](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)\>**图标"估计搜索结果"** 以开始搜索并返回搜索返回的总大小和项目数的估计值。 
    
    估計結果會顯示在詳細資料窗格中。 **单击"刷新**![刷新"图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新详细信息窗格中显示的信息。 
    
4. 若要在搜尋完成之後預覽結果，按一下詳細資料窗格中的 [預覽搜尋結果]****。
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>建立和執行就地 eDiscovery 搜尋之後接下來的步驟

建立並啟動步驟 3 中的指令碼建立的就地 eDiscovery 搜尋之後，您可以使用一般的就地 eDiscovery 工作流程在搜尋結果上執行不同的 eDiscovery 動作。
  
### <a name="create-an-in-place-hold"></a>建立就地保留

1. 在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。
    
2. 在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索，然后单击"**编辑"**![图标](media/O365-MDM-CreatePolicy-EditIcon.gif)。
    
3. 在 [就地保留設定]**** 頁面上，勾選 [將符合搜尋查詢的內容放入保留的所選信箱]**** 核取方塊，然後選擇下列其中一個選項： 
    
  - **无限期保留**- 选择此选项可将搜索返回的项目置于无限期保留状态。 除非您從搜尋中移除信箱或移除搜尋，否則保留的項目會一直保存下來。 
    
  - **指定相对于其接收日期持有物料的天数**- 选择此选项可保存特定期间的物料。 持續時間自接收或建立信箱項目的日期開始計算。 
    
4. 按一下 [儲存]**** 以建立就地保留並重新啟動搜尋。 
    
[回到頁首](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>複製搜尋結果

1. 在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。
    
3. **单击"搜索**![搜索"图标，](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)然后单击"从下拉列表中**复制搜索结果"。** 
    
4. 在 [複製搜尋結果]**** 中，從下列選項選取：
    
    - **包括不可搜索的项目**- 选中此复选框以包括无法搜索的邮箱项目（例如，具有文件类型附件的邮件，无法通过 Exchange 搜索编制索引）。 
    
    - **启用重复数据消除**- 选中此复选框可排除重复邮件。 只有一个邮件实例将复制到发现邮箱。 
    
    - **启用完全日志记录**- 选中此复选框以包含完整的登录搜索结果。 
    
    - **复制完成后向我发送邮件**- 选中此复选框在搜索完成后收到电子邮件通知。 
    
    - **将结果复制到此发现邮箱**- 单击"**浏览"** 以选择要将搜索结果复制到的发现邮箱。 
    
5. 按一下 [複製]**** 以開始程序來將搜尋結果複製到指定的探索信箱。 
    
6. **单击"刷新**![刷新"图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新详细信息窗格中显示的复制状态信息。 
    
7. 複製完成時，按一下 [開啟]**** 以開啟要檢視搜尋結果的探索信箱。 
  
### <a name="export-the-search-results"></a>匯出搜尋結果

1. 在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋，然後按一下 [匯出為 PST 檔案]****。
    
3. In the **eDiscovery PST Export Tool** window, do the following: 
    
    - Click **Browse** to specify the location where you want to download the PST file. 
    
    - Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file. 
    
    - Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file. 
    
4. Click **Start** to export the search results to a PST file. 
    
    包含匯出程序狀態資訊的視窗便會隨即顯示。
