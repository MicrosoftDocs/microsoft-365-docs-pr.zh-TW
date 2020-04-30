---
title: 對目標集合使用內容搜尋
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: 在安全性 & 規範中心使用內容搜尋，以執行目標集合。 目標集合表示您確信已回應案例或特權專案的專案位於特定信箱或網站資料夾中。 使用本文中的腳本，取得您要搜尋之特定信箱或網站資料夾的資料夾識別碼或路徑。
ms.openlocfilehash: 4808dad8faed99ac15c4f9828ad1759e2f1179fc
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942976"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="c0632-105">對目標集合使用內容搜尋</span><span class="sxs-lookup"><span data-stu-id="c0632-105">Use Content Search for targeted collections</span></span>

<span data-ttu-id="c0632-106">安全性&amp;與合規性中心的內容搜尋功能不會在 UI 中提供直接的方式，以搜尋 Exchange 信箱中的特定資料夾，或 SharePoint 和 OneDrive 商務網站。</span><span class="sxs-lookup"><span data-stu-id="c0632-106">The Content Search feature in the Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="c0632-107">不過，您可以在實際搜尋查詢語法中指定網站的電子郵件或路徑（DocumentLink）屬性的資料夾識別碼屬性，搜尋特定的資料夾（稱為*目標集合*）。</span><span class="sxs-lookup"><span data-stu-id="c0632-107">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="c0632-108">當您確信回應案例或特權專案的專案位於特定信箱或網站資料夾時，使用內容搜尋來執行目標集合很有用。</span><span class="sxs-lookup"><span data-stu-id="c0632-108">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="c0632-109">您可以使用本文中的腳本，取得 SharePoint 和商務用 OneDrive 的資料夾的信箱資料夾或路徑（DocumentLink）的資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="c0632-109">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="c0632-110">然後您可以使用搜尋查詢中的資料夾識別碼或路徑，傳回位於資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="c0632-110">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="c0632-111">若要傳回位於 SharePoint 或 OneDrive for Business 網站的資料夾中的內容，本主題中的腳本會使用 DocumentLink managed 屬性，而不是 Path 屬性。</span><span class="sxs-lookup"><span data-stu-id="c0632-111">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="c0632-112">DocumentLink 屬性比 Path 屬性更強健，因為它會傳回資料夾中的所有內容，而 Path 屬性則不會傳回某些媒體檔案。</span><span class="sxs-lookup"><span data-stu-id="c0632-112">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c0632-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="c0632-113">Before you begin</span></span>

- <span data-ttu-id="c0632-114">您必須是安全性&amp;與合規性中心內 eDiscovery 管理員角色群組的成員，才可執行步驟1中的腳本。</span><span class="sxs-lookup"><span data-stu-id="c0632-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="c0632-115">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c0632-115">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="c0632-116">此外，您必須在 Exchange Online 組織中指派「郵件收件者」角色。</span><span class="sxs-lookup"><span data-stu-id="c0632-116">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="c0632-117">這是執行**Get-MailboxFolderStatistics** Cmdlet 所需的，該指令會包含在步驟1的腳本中。</span><span class="sxs-lookup"><span data-stu-id="c0632-117">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="c0632-118">根據預設，會將「郵件收件者」角色指派給 Exchange Online 中的組織管理和收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="c0632-118">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="c0632-119">如需在 Exchange Online 中指派許可權的相關資訊，請參閱[Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102)。</span><span class="sxs-lookup"><span data-stu-id="c0632-119">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="c0632-120">您也可以建立自訂角色群組、指派「郵件收件者」角色給它，然後新增需要在步驟1中執行腳本的成員。</span><span class="sxs-lookup"><span data-stu-id="c0632-120">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="c0632-121">如需詳細資訊，請參閱[管理角色群組](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="c0632-121">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="c0632-122">每當您在步驟1中執行腳本時，就會建立新的遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c0632-122">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="c0632-123">您可以使用所有可用的遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c0632-123">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="c0632-124">若要避免發生這種情況，您可以執行下列命令，以中斷使用中遠端 PowerShell 會話的連線。</span><span class="sxs-lookup"><span data-stu-id="c0632-124">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="c0632-125">如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)＞。</span><span class="sxs-lookup"><span data-stu-id="c0632-125">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="c0632-126">腳本包含最低的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="c0632-126">The script includes minimal error handling.</span></span> <span data-ttu-id="c0632-127">腳本的主要用途是快速顯示可在內容搜尋的搜尋查詢語法中使用的信箱資料夾 IDs 或網站路徑清單，以執行目標集合。</span><span class="sxs-lookup"><span data-stu-id="c0632-127">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="c0632-128">在任何 Microsoft standard support 方案或服務下，都不支援本主題中提供的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="c0632-128">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="c0632-129">範例腳本是以不含任何類型擔保的方式提供。</span><span class="sxs-lookup"><span data-stu-id="c0632-129">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="c0632-130">Microsoft 進一步否認所有暗示擔保，包括但不限於任何適售性或特定用途適用性的暗示擔保。</span><span class="sxs-lookup"><span data-stu-id="c0632-130">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="c0632-131">因使用或效能範例腳本及檔的整體風險，仍然保留給您。</span><span class="sxs-lookup"><span data-stu-id="c0632-131">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="c0632-132">在任何事件中，Microsoft、其作者、（包括但不限於使用或無法使用範例腳本或檔的任何損害（包括（但不限於）因使用或無法使用範例腳本或檔而造成的任何損害（包括但不限於公司中斷、商務中斷、商務資訊遺失或其他 pecuniary 遺失）以外的任何損害（包括但不限於）使用或無法使用範例腳本或檔時所產生的任何其他</span><span class="sxs-lookup"><span data-stu-id="c0632-132">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="c0632-133">步驟1：執行腳本以取得信箱或網站的資料夾清單</span><span class="sxs-lookup"><span data-stu-id="c0632-133">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="c0632-134">您在此第一個步驟中執行的腳本會傳回商務資料夾的信箱資料夾或 SharePoint 和 OneDrive 清單，以及每個資料夾對應的資料夾識別碼或路徑。</span><span class="sxs-lookup"><span data-stu-id="c0632-134">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="c0632-135">當您執行此腳本時，它會提示您輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="c0632-135">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="c0632-136">**電子郵件地址或網站 URL**輸入保管人的電子郵件地址，以傳回 Exchange 信箱資料夾和資料夾 IDs 的清單。</span><span class="sxs-lookup"><span data-stu-id="c0632-136">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="c0632-137">或輸入 SharePoint 網站的 URL，或輸入商務用 OneDrive 的網站，以傳回指定網站的路徑清單。</span><span class="sxs-lookup"><span data-stu-id="c0632-137">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="c0632-138">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="c0632-138">Here are some examples:</span></span> 
    
  - <span data-ttu-id="c0632-139">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c0632-139">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="c0632-140">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="c0632-140">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="c0632-141">**商務 OneDrive** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="c0632-141">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="c0632-142">**您的使用者認證**-腳本會使用您的認證，透過遠端 PowerShell 連線到 Exchange Online 和安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="c0632-142">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="c0632-143">如先前所述，您必須獲指派適當的許可權，才可成功執行這個腳本。</span><span class="sxs-lookup"><span data-stu-id="c0632-143">As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="c0632-144">若要顯示信箱資料夾或網站 documentlink （路徑）名稱的清單，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c0632-144">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="c0632-145">使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `GetFolderSearchParameters.ps1`。</span><span class="sxs-lookup"><span data-stu-id="c0632-145">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
  ```powershell
  #########################################################################################################
  # This PowerShell script will prompt you for:                                #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
  # The script will then:                                            #
  #    * If an email address is supplied: list the folders for the target mailbox.            #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                    #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
  #      appended to the folder ID or documentlink to use in a Content Search.                #
  # Notes:                                                #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
  #      the current folder and all sub-folders are searched.                        #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                                #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
  #########################################################################################################
  # Collect the target email address or SharePoint Url
  $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
  # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
  }
  elseif ($addressOrSite.IndexOf("http") -ige 0)
  {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
  }
  else
  {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
  }
  ```

2. <span data-ttu-id="c0632-146">在您的本機電腦上，開啟 [Windows PowerShell]，然後移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-146">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="c0632-147">執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="c0632-147">Run the script; for example:</span></span>
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="c0632-148">輸入腳本提示您的資訊。</span><span class="sxs-lookup"><span data-stu-id="c0632-148">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="c0632-149">腳本會顯示指定使用者的信箱資料夾或網站資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="c0632-149">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="c0632-150">讓此視窗開啟，讓您可以複製資料夾識別碼或 documentlink 名稱，並將其貼到步驟2中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="c0632-150">Let this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c0632-151">您可以將腳本的輸出重新導向至文字檔，而不是顯示電腦畫面上的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="c0632-151">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="c0632-152">此檔案會儲存至腳本所在的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-152">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="c0632-153">例如，若要將腳本輸出重新導向至文字檔，請在步驟3中執行下列命令： `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`然後，您就可以從檔案中複製資料夾識別碼或 documentlink，以在搜尋查詢中使用。</span><span class="sxs-lookup"><span data-stu-id="c0632-153">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="c0632-154">信箱資料夾的腳本輸出</span><span class="sxs-lookup"><span data-stu-id="c0632-154">Script output for mailbox folders</span></span>

<span data-ttu-id="c0632-155">如果您正在取得信箱資料夾 IDs，腳本會透過遠端 PowerShell 連線到 Exchange Online，執行 MailboxFolderStatisics 指令**程式**，然後顯示指定信箱中的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="c0632-155">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="c0632-156">針對信箱中的每個資料夾，腳本會在 [ **FolderPath** ] 欄中顯示資料夾的名稱，並在 [ **FolderQuery** ] 欄中顯示資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="c0632-156">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="c0632-157">此外，腳本會將**folderId**的首碼（即信箱屬性的名稱）新增至資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="c0632-157">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="c0632-158">由於**folderid**屬性是可搜尋的屬性，因此您將`folderid:<folderid>`在步驟2的搜尋查詢中使用，來搜尋該資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-158">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="c0632-159">腳本會顯示最多100個信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-159">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0632-160">本文中的腳本包含編碼邏輯，可將**Get-MailboxFolderStatistics**所傳回的64字元資料夾識別碼值，轉換成為搜尋編制索引的相同48字元格式。</span><span class="sxs-lookup"><span data-stu-id="c0632-160">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="c0632-161">如果您只在 PowerShell 中執行**Get-MailboxFolderStatistics** Cmdlet 以取得資料夾識別碼（而不是在本文中執行腳本），則使用該資料夾識別碼值的搜尋查詢會失敗。</span><span class="sxs-lookup"><span data-stu-id="c0632-161">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="c0632-162">您必須執行腳本，才能取得可在內容搜尋中使用的正確格式資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="c0632-162">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="c0632-163">以下是信箱資料夾腳本所傳回的輸出範例。</span><span class="sxs-lookup"><span data-stu-id="c0632-163">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![腳本所傳回的信箱資料夾和資料夾 IDs 清單範例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="c0632-165">步驟2中的範例會顯示用來搜尋使用者的 [可復原的專案] 資料夾中的 [清除] 子資料夾的查詢。</span><span class="sxs-lookup"><span data-stu-id="c0632-165">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="c0632-166">網站資料夾的腳本輸出</span><span class="sxs-lookup"><span data-stu-id="c0632-166">Script output for site folders</span></span>

<span data-ttu-id="c0632-167">如果您從 SharePoint 或商務 PowerShell 用 OneDrive 取得**documentlink**屬性的路徑，& 腳本會建立新的內容搜尋，以搜尋網站中的資料夾，然後顯示位於指定之網站中的資料夾的清單。）。</span><span class="sxs-lookup"><span data-stu-id="c0632-167">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to the Security & Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="c0632-168">腳本會顯示每個資料夾的名稱，並將**documentlink**的首碼新增至資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="c0632-168">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="c0632-169">由於**documentlink**屬性是可搜尋的屬性，因此您將`documentlink:<path>`在步驟2的搜尋查詢中使用 property： value 對來搜尋該資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-169">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="c0632-170">腳本會顯示最多200個網站資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-170">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="c0632-171">如果有200以上的網站資料夾，則會顯示最新的網站資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-171">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="c0632-172">以下是網站資料夾腳本所傳回的輸出範例。</span><span class="sxs-lookup"><span data-stu-id="c0632-172">Here's an example of the output returned by the script for site folders.</span></span>
  
![腳本傳回之網站資料夾的 documentlink 名稱清單範例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="c0632-174">步驟2：使用資料夾識別碼或 documentlink 來執行目標集合</span><span class="sxs-lookup"><span data-stu-id="c0632-174">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="c0632-175">在您執行腳本來收集特定使用者的資料夾 IDs 或 documentlinks 之後，下一步是移至安全性 & 規範中心，並建立新的內容搜尋來搜尋特定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-175">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security & Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="c0632-176">您可以在 [ `folderid:<folderid>`內容`documentlink:<path>`搜尋關鍵字] 方塊中所設定的搜尋查詢中使用 or property： value 組（如果使用**New-ComplianceSearch** Cmdlet，則為*ContentMatchQuery*參數的值）。</span><span class="sxs-lookup"><span data-stu-id="c0632-176">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="c0632-177">您可以將`folderid` or `documentlink`屬性與其他搜尋參數或搜尋條件結合使用。</span><span class="sxs-lookup"><span data-stu-id="c0632-177">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="c0632-178">如果您在查詢中`folderid`只`documentlink`包含 or 屬性，則搜尋會傳回位於指定資料夾中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="c0632-178">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="c0632-179">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="c0632-179">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c0632-180">使用您在步驟1中用來執行腳本的帳戶和認證來登入。</span><span class="sxs-lookup"><span data-stu-id="c0632-180">Sign in using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="c0632-181">在安全性 & 合規性中心的左窗格中，按一下 [**搜尋** \> **內容搜尋**]，然後按一下 [新增](../media/O365-MDM-CreatePolicy-AddIcon.gif)] [**新增** ![] 圖示。</span><span class="sxs-lookup"><span data-stu-id="c0632-181">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**, and then click **New** ![Add icon](../media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="c0632-182">在 [新增搜尋]\*\*\*\* 頁面上，輸入內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0632-182">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="c0632-183">此名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c0632-183">This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="c0632-184">在 [**您希望我們在哪裡查看**] 之下，根據您搜尋的是信箱資料夾或網站資料夾，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c0632-184">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="c0632-185">按一下 **[選擇要搜尋的特定信箱**]，然後新增當您在步驟1中執行腳本時所指定的相同信箱。</span><span class="sxs-lookup"><span data-stu-id="c0632-185">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="c0632-186">或者</span><span class="sxs-lookup"><span data-stu-id="c0632-186">Or</span></span>
    
    - <span data-ttu-id="c0632-187">按一下 **[選擇要搜尋的特定網站**] 進行搜尋，然後新增當您在步驟1中執行腳本時所指定的相同網站 URL。</span><span class="sxs-lookup"><span data-stu-id="c0632-187">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="c0632-188">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0632-188">Click **Next**.</span></span>
    
7. <span data-ttu-id="c0632-189">在 [**您想要做什麼？** ] 頁面上的 [關鍵字] 方塊中， `folderid:<folderid>`將`documentlink:<path>`步驟1中的腳本所傳回的 or 值貼上。</span><span class="sxs-lookup"><span data-stu-id="c0632-189">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="c0632-190">例如，下列螢幕擷取畫面中的查詢將會搜尋使用者的 [可復原的專案] 資料夾中的 [清除] 子資料夾中的任何`folderid`專案（[清除] 子資料夾的屬性值會顯示在步驟1的螢幕擷取畫面中）：</span><span class="sxs-lookup"><span data-stu-id="c0632-190">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![將 folderid 或 documentlink 貼到搜尋查詢的關鍵字方塊中](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="c0632-192">按一下 [**搜尋**] 以啟動目標集合搜尋。</span><span class="sxs-lookup"><span data-stu-id="c0632-192">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="c0632-193">目標集合的搜尋查詢範例</span><span class="sxs-lookup"><span data-stu-id="c0632-193">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="c0632-194">以下是在搜尋查詢中使用`folderid`和`documentlink`屬性來執行目標集合的一些範例。</span><span class="sxs-lookup"><span data-stu-id="c0632-194">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="c0632-195">請注意，預留位置是用於`folderid:<folderid>`和`documentlink:<path>`儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c0632-195">Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="c0632-196">這個範例會搜尋三個不同的信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-196">This example searches three different mailbox folders.</span></span> <span data-ttu-id="c0632-197">您可以使用類似的查詢語法，在使用者的 [可復原的專案] 資料夾中搜尋隱藏的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-197">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="c0632-198">本範例會在信箱資料夾中搜尋包含確切片語的專案。</span><span class="sxs-lookup"><span data-stu-id="c0632-198">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="c0632-199">本範例會在標題中搜尋包含「NDA」字母的檔的網站資料夾（及任何子資料夾）。</span><span class="sxs-lookup"><span data-stu-id="c0632-199">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="c0632-200">這個範例會搜尋在日期範圍內已變更之檔的網站資料夾（及任何子資料夾）。</span><span class="sxs-lookup"><span data-stu-id="c0632-200">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="c0632-201">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c0632-201">More information</span></span>

<span data-ttu-id="c0632-202">使用本文中的腳本時，請記住下列事項，以執行目標集合。</span><span class="sxs-lookup"><span data-stu-id="c0632-202">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="c0632-203">腳本不會移除結果中的任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-203">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="c0632-204">因此，結果中所列的某些資料夾可能會無法搜尋（或傳回零個專案），因為這些資料夾包含系統所產生的內容。</span><span class="sxs-lookup"><span data-stu-id="c0632-204">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="c0632-205">此腳本只會傳回使用者主要信箱的資料夾資訊。</span><span class="sxs-lookup"><span data-stu-id="c0632-205">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="c0632-206">它不會傳回使用者封存信箱中資料夾的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c0632-206">It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="c0632-207">搜尋信箱資料夾時，只會搜尋指定的資料夾（以`folderid`其屬性識別）;不會搜尋子資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-207">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="c0632-208">若要搜尋子資料夾，您必須使用您要搜尋之子資料夾的資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="c0632-208">To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="c0632-209">搜尋網站資料夾時，會搜尋該資料夾（依`documentlink`其屬性識別）和所有子資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0632-209">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="c0632-210">當您在 [搜尋查詢] 中只指定`folderid`屬性時，若要匯出的搜尋結果，您可以選擇 [第一個匯出] 選項：「所有未辨識格式的專案（除外）」、「加密」或「尚未」為其他原因編制索引」。</span><span class="sxs-lookup"><span data-stu-id="c0632-210">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="c0632-211">不論索引狀態為何，資料夾識別碼永遠都會被匯出，因為資料夾識別碼永遠都是編制索引。</span><span class="sxs-lookup"><span data-stu-id="c0632-211">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
