---
title: 對目標集合使用內容搜尋
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 在 Microsoft 365 規範中心使用內容搜尋，以執行目標集合，以搜尋特定信箱或網站資料夾中的專案。
ms.openlocfilehash: cf0364d39a78e1bbbc062d85ce750d190fbbda5a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311892"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="d7f54-103">對目標集合使用內容搜尋</span><span class="sxs-lookup"><span data-stu-id="d7f54-103">Use Content search for targeted collections</span></span>

<span data-ttu-id="d7f54-104">Microsoft 365 規範中心的內容搜尋工具不會在 UI 中提供直接的方式，以搜尋 Exchange 信箱或 SharePoint 和商務用 OneDrive 網站中的特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-104">The Content search tool in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="d7f54-105">不過，您可以在實際搜尋查詢語法中指定網站的 [電子郵件] 或 [)  (路徑] 的資料夾識別碼內容， (稱為 *目標集合*) ，以搜尋特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="d7f54-106">當您確信回應案例或特權專案的專案位於特定信箱或網站資料夾時，使用內容搜尋來執行目標集合很有用。</span><span class="sxs-lookup"><span data-stu-id="d7f54-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="d7f54-107">您可以使用本文中的腳本，取得信箱資料夾的資料夾識別碼，或 SharePoint 和商務用 OneDrive 網站上資料夾的 (DocumentLink) 路徑。</span><span class="sxs-lookup"><span data-stu-id="d7f54-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="d7f54-108">然後您可以使用搜尋查詢中的資料夾識別碼或路徑，傳回位於資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="d7f54-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="d7f54-109">若要傳回位於 SharePoint 或商務用 OneDrive 網站的資料夾中的內容，本主題中的腳本會使用 DocumentLink managed 屬性，而不是 Path 屬性。</span><span class="sxs-lookup"><span data-stu-id="d7f54-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="d7f54-110">DocumentLink 屬性比 Path 屬性更強健，因為它會傳回資料夾中的所有內容，而 Path 屬性則不會傳回某些媒體檔案。</span><span class="sxs-lookup"><span data-stu-id="d7f54-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="d7f54-111">在執行目標集合之前</span><span class="sxs-lookup"><span data-stu-id="d7f54-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="d7f54-112">您必須是 [安全性 & 規範中心] 中的 eDiscovery 管理員角色群組成員，才可執行步驟1中的腳本。</span><span class="sxs-lookup"><span data-stu-id="d7f54-112">You have to be a member of the eDiscovery Manager role group in Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="d7f54-113">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f54-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="d7f54-114">您也必須為您的 Exchange Online 組織指派「郵件收件者」角色。</span><span class="sxs-lookup"><span data-stu-id="d7f54-114">You also have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="d7f54-115">這是執行 **Get-MailboxFolderStatistics** Cmdlet 的必要指令，該指令包含在腳本中。</span><span class="sxs-lookup"><span data-stu-id="d7f54-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="d7f54-116">根據預設，會將「郵件收件者」角色指派給 Exchange Online 中的組織管理和收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="d7f54-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="d7f54-117">如需在 Exchange Online 指派許可權的相關資訊，請參閱[Manage role group members](/exchange/manage-role-group-members-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="d7f54-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](/exchange/manage-role-group-members-exchange-2013-help).</span></span> <span data-ttu-id="d7f54-118">您也可以建立自訂角色群組、指派「郵件收件者」角色給它，然後新增需要在步驟1中執行腳本的成員。</span><span class="sxs-lookup"><span data-stu-id="d7f54-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="d7f54-119">如需詳細資訊，請參閱 [管理角色群組](/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="d7f54-119">For more information, see [Manage role groups](/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="d7f54-120">本文中的腳本支援新式驗證。</span><span class="sxs-lookup"><span data-stu-id="d7f54-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="d7f54-121">如果您是 Microsoft 365 或 Microsoft 365 GCC 組織，您可以使用腳本。</span><span class="sxs-lookup"><span data-stu-id="d7f54-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="d7f54-122">如果您是 Office 365 德國組織、Microsoft 365 GCC 高組織或 Microsoft 365 DoD 組織，您必須編輯腳本以順利執行它。</span><span class="sxs-lookup"><span data-stu-id="d7f54-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="d7f54-123">具體說來，您必須編輯該行 `Connect-ExchangeOnline` 並使用 *ExchangeEnvironmentName* 參數 (，並使用適當的值為您的組織輸入) 以連接至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d7f54-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="d7f54-124">此外，您必須編輯該行 `Connect-IPPSSession` 並使用 *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 參數 (以及組織類型的適當值，) 才能連線至安全性 & 規範中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d7f54-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d7f54-125">如需詳細資訊，請參閱[連線中 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa)及[連線安全性 & 規範中心 PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)的範例。</span><span class="sxs-lookup"><span data-stu-id="d7f54-125">For more information, see the examples in [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="d7f54-126">每當您執行腳本時，就會建立新的遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="d7f54-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="d7f54-127">這表示您可以使用所有可用的遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="d7f54-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="d7f54-128">若要避免發生這種情況，請執行下列命令，以中斷使用中遠端 PowerShell 會話的連線。</span><span class="sxs-lookup"><span data-stu-id="d7f54-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="d7f54-129">如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)＞。</span><span class="sxs-lookup"><span data-stu-id="d7f54-129">For more information, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d7f54-130">腳本包含最低的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="d7f54-130">The script includes minimal error handling.</span></span> <span data-ttu-id="d7f54-131">腳本的主要用途是快速顯示可在內容搜尋的搜尋查詢語法中使用的信箱資料夾 IDs 或網站路徑清單，以執行目標集合。</span><span class="sxs-lookup"><span data-stu-id="d7f54-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="d7f54-132">在任何 Microsoft standard support 方案或服務下，都不支援本主題中提供的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="d7f54-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="d7f54-133">範例指令碼係依「現狀」提供，不含任何種類的擔保方式。</span><span class="sxs-lookup"><span data-stu-id="d7f54-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="d7f54-134">Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。</span><span class="sxs-lookup"><span data-stu-id="d7f54-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="d7f54-135">使用或操作範例指令碼和文件發生的所有風險，皆屬於您的責任。</span><span class="sxs-lookup"><span data-stu-id="d7f54-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="d7f54-136">Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼或文件所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="d7f54-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="d7f54-137">步驟1：執行腳本以取得信箱或網站的資料夾清單</span><span class="sxs-lookup"><span data-stu-id="d7f54-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="d7f54-138">您在此第一個步驟中執行的腳本會傳回信箱資料夾或 SharePoint 和商務用 OneDrive 資料夾的清單，以及每個資料夾對應的資料夾識別碼或路徑。</span><span class="sxs-lookup"><span data-stu-id="d7f54-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="d7f54-139">當您執行此腳本時，它會提示您輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="d7f54-139">When you run this script, it will prompt you for the following information.</span></span>

- <span data-ttu-id="d7f54-140">**電子郵件地址或網站 URL**：輸入管理員的電子郵件地址，以傳回 Exchange 信箱資料夾和資料夾 IDs 清單。</span><span class="sxs-lookup"><span data-stu-id="d7f54-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="d7f54-141">或輸入 SharePoint 網站或商務用 OneDrive 網站的 URL，以傳回指定網站的路徑清單。</span><span class="sxs-lookup"><span data-stu-id="d7f54-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="d7f54-142">範例如下：</span><span class="sxs-lookup"><span data-stu-id="d7f54-142">Here are some examples:</span></span>

  - <span data-ttu-id="d7f54-143">**Exchange**： stacig@contoso .com name.onmicrosoft.com17 <spam> <spam></span><span class="sxs-lookup"><span data-stu-id="d7f54-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="d7f54-144">**SharePoint**： HTTPs <span>//</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="d7f54-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span>

  - <span data-ttu-id="d7f54-145">**商務用 OneDrive**： HTTPs <span>//</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="d7f54-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span>

- <span data-ttu-id="d7f54-146">**您的使用者認證**：腳本會使用您的認證，以連線至 Exchange Online PowerShell 或安全性 & 規範中心 PowerShell 使用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="d7f54-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="d7f54-147">如先前所述，您必須獲指派適當的許可權，才可成功執行這個腳本。</span><span class="sxs-lookup"><span data-stu-id="d7f54-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="d7f54-148">若要顯示信箱資料夾或網站 documentlink 的清單) 名稱 (路徑：</span><span class="sxs-lookup"><span data-stu-id="d7f54-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>

1. <span data-ttu-id="d7f54-149">使用 .ps1 的檔案名尾碼，將下列文字儲存至 Windows PowerShell 腳本檔案;例如， `GetFolderSearchParameters.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="d7f54-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
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
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
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

2. <span data-ttu-id="d7f54-150">在您的本機電腦上，開啟 [Windows PowerShell]，然後移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="d7f54-151">執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="d7f54-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="d7f54-152">輸入腳本提示您的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7f54-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="d7f54-153">腳本會顯示指定使用者的信箱資料夾或網站資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="d7f54-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="d7f54-154">讓此視窗保持開啟，以便您可以複製資料夾識別碼或 documentlink 名稱，並將其貼到步驟2中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="d7f54-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="d7f54-155">您可以將腳本的輸出重新導向至文字檔，而不是顯示電腦畫面上的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="d7f54-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="d7f54-156">此檔案會儲存至腳本所在的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="d7f54-157">例如，若要將腳本輸出重新導向至文字檔，請在步驟3中執行下列命令：  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 然後，您就可以從檔案中複製資料夾識別碼或 documentlink，以在搜尋查詢中使用。</span><span class="sxs-lookup"><span data-stu-id="d7f54-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>

### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="d7f54-158">信箱資料夾的腳本輸出</span><span class="sxs-lookup"><span data-stu-id="d7f54-158">Script output for mailbox folders</span></span>

<span data-ttu-id="d7f54-159">如果您正在取得信箱資料夾 IDs，腳本會連接至 Exchange Online PowerShell，執行 **MailboxFolderStatisics 指令程式**，然後顯示指定信箱中的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="d7f54-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="d7f54-160">針對信箱中的每個資料夾，腳本會在 [ **FolderPath** ] 欄中顯示資料夾的名稱，並在 [ **FolderQuery** ] 欄中顯示資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="d7f54-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="d7f54-161">此外，腳本會新增 **folderId** (的首碼，也就是信箱屬性) 至資料夾識別碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="d7f54-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="d7f54-162">由於 **folderid** 屬性是可搜尋的屬性，因此您將  `folderid:<folderid>` 在步驟2的搜尋查詢中使用，來搜尋該資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="d7f54-163">腳本會顯示最多100個信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7f54-164">本文中的腳本包含編碼邏輯，可將 **Get-MailboxFolderStatistics** 所傳回的64字元資料夾識別碼值，轉換成為搜尋編制索引的相同48字元格式。</span><span class="sxs-lookup"><span data-stu-id="d7f54-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="d7f54-165">如果您只在 PowerShell 中執行 **Get-MailboxFolderStatistics** Cmdlet 以取得資料夾識別碼 (但不是在本文中執行腳本) ，則使用該資料夾識別碼值的搜尋查詢會失敗。</span><span class="sxs-lookup"><span data-stu-id="d7f54-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="d7f54-166">您必須執行腳本，才能取得可在內容搜尋中使用的正確格式資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="d7f54-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>

<span data-ttu-id="d7f54-167">以下是信箱資料夾腳本所傳回的輸出範例。</span><span class="sxs-lookup"><span data-stu-id="d7f54-167">Here's an example of the output returned by the script for mailbox folders.</span></span>

![腳本所傳回的信箱資料夾和資料夾 IDs 清單範例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

<span data-ttu-id="d7f54-169">步驟2中的範例會顯示用來搜尋使用者的 [可復原的專案] 資料夾中的 [清除] 子資料夾的查詢。</span><span class="sxs-lookup"><span data-stu-id="d7f54-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>

### <a name="script-output-for-site-folders"></a><span data-ttu-id="d7f54-170">網站資料夾的腳本輸出</span><span class="sxs-lookup"><span data-stu-id="d7f54-170">Script output for site folders</span></span>

<span data-ttu-id="d7f54-171">如果您從 SharePoint 或商務用 OneDrive 網站取得 **documentlink** 屬性的路徑，腳本會連線至安全性 & 合規性 PowerShell，並建立新的內容搜尋來搜尋網站中的資料夾，然後顯示位於指定網站中的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="d7f54-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="d7f54-172">腳本會顯示每個資料夾的名稱，並將 **documentlink** 的首碼新增至資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="d7f54-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="d7f54-173">由於 **documentlink** 屬性是可搜尋的屬性，因此您將在 `documentlink:<path>` 步驟2的搜尋查詢中使用 property： value 對來搜尋該資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="d7f54-174">腳本會顯示最多200個網站資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="d7f54-175">如果有200以上的網站資料夾，則會顯示最新的網站資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>

<span data-ttu-id="d7f54-176">以下是網站資料夾腳本所傳回的輸出範例。</span><span class="sxs-lookup"><span data-stu-id="d7f54-176">Here's an example of the output returned by the script for site folders.</span></span>

![腳本傳回之網站資料夾的 documentlink 名稱清單範例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="d7f54-178">步驟2：使用資料夾識別碼或 documentlink 來執行目標集合</span><span class="sxs-lookup"><span data-stu-id="d7f54-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="d7f54-179">在您執行腳本來收集特定使用者的資料夾 IDs 或檔連結的清單後，下一步是移至「Microsoft 365 規範中心」，並建立新的內容搜尋來搜尋特定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="d7f54-180">`folderid:<folderid>` `documentlink:<path>` 如果您使用 **New-ComplianceSearch** Cmdlet) ，您會在 [內容搜尋關鍵字] 方塊中所設定的搜尋查詢中，使用 or property： value 組 (，也可以使用 *ContentMatchQuery* 參數的值。</span><span class="sxs-lookup"><span data-stu-id="d7f54-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="d7f54-181">您可以將  `folderid` or  `documentlink` 屬性與其他搜尋參數或搜尋條件結合使用。</span><span class="sxs-lookup"><span data-stu-id="d7f54-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="d7f54-182">如果您在查詢中只包含  `folderid` or  `documentlink` 屬性，則搜尋會傳回位於指定資料夾中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="d7f54-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>

1. <span data-ttu-id="d7f54-183"><https://compliance.microsoft.com>使用您在步驟1中用來執行腳本的帳戶和認證，移至並登入。</span><span class="sxs-lookup"><span data-stu-id="d7f54-183">Go to <https://compliance.microsoft.com> and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="d7f54-184">在 [規範中心] 的左窗格中，按一下 [**顯示所有**  >  **內容搜尋**]，然後按一下 [**新增搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="d7f54-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="d7f54-185">在 [ **關鍵字** ] 方塊中， `folderid:<folderid>` 將  `documentlink:<path>` 步驟1中的腳本所傳回的 or 值貼上。</span><span class="sxs-lookup"><span data-stu-id="d7f54-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="d7f54-186">例如，下列螢幕擷取畫面中的查詢會搜尋使用者的 [可復原的專案] 資料夾中的 [清除] 子資料夾中的任何專案 ([清除] 子資料夾的 `folderid` 屬性值會顯示在步驟 1) 中的螢幕擷取畫面中：</span><span class="sxs-lookup"><span data-stu-id="d7f54-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![將 folderid 或 documentlink 貼到搜尋查詢的關鍵字方塊中](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="d7f54-188">在 [ **位置**] 下，選取 [ **特定位置** ]，然後按一下 [ **修改**]。</span><span class="sxs-lookup"><span data-stu-id="d7f54-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="d7f54-189">請根據您搜尋的是信箱資料夾或網站資料夾，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d7f54-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="d7f54-190">在 [ **Exchange 電子郵件**] 旁，按一下 **[選擇使用者、群組或小組**]，然後新增您在步驟1中執行腳本時所指定的相同信箱。</span><span class="sxs-lookup"><span data-stu-id="d7f54-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="d7f54-191">或</span><span class="sxs-lookup"><span data-stu-id="d7f54-191">Or</span></span>

    - <span data-ttu-id="d7f54-192">在 [ **SharePoint 網站**] 旁，按一下 **[選擇網站**]，然後新增當您在步驟1中執行腳本時所指定的相同網站 URL。</span><span class="sxs-lookup"><span data-stu-id="d7f54-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="d7f54-193">在您儲存要搜尋的內容位置之後，請按一下 [ **儲存 & 執行**]，輸入內容搜尋的名稱，然後按一下 [ **儲存** ] 以開始目標集合搜尋。</span><span class="sxs-lookup"><span data-stu-id="d7f54-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span>

### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="d7f54-194">目標集合的搜尋查詢範例</span><span class="sxs-lookup"><span data-stu-id="d7f54-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="d7f54-195">以下是  `folderid`  `documentlink` 在搜尋查詢中使用和屬性來執行目標集合的一些範例。</span><span class="sxs-lookup"><span data-stu-id="d7f54-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="d7f54-196">使用預留位置做為  `folderid:<folderid>` 及  `documentlink:<path>` 節省空間。</span><span class="sxs-lookup"><span data-stu-id="d7f54-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span>

- <span data-ttu-id="d7f54-197">這個範例會搜尋三個不同的信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="d7f54-198">您可以使用類似的查詢語法，在使用者的 [可復原的專案] 資料夾中搜尋隱藏的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="d7f54-199">本範例會在信箱資料夾中搜尋包含確切片語的專案。</span><span class="sxs-lookup"><span data-stu-id="d7f54-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="d7f54-200">本範例會在標題中搜尋包含字母 "保密協定" 的檔的網站資料夾 (及任何子資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="d7f54-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="d7f54-201">此範例會在某個日期範圍內，搜尋 (和所有子資料夾) 中已變更的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="d7f54-202">其他資訊</span><span class="sxs-lookup"><span data-stu-id="d7f54-202">More information</span></span>

<span data-ttu-id="d7f54-203">使用本文中的腳本時，請記住下列事項，以執行目標集合。</span><span class="sxs-lookup"><span data-stu-id="d7f54-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>

- <span data-ttu-id="d7f54-204">腳本不會移除結果中的任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="d7f54-205">因此，結果中所列的某些資料夾可能會無法搜尋 (或傳回零個專案) 因為它們包含系統所產生的內容，或是因為它們只包含子資料夾而非信箱專案。</span><span class="sxs-lookup"><span data-stu-id="d7f54-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="d7f54-206">此腳本只會傳回使用者主要信箱的資料夾資訊。</span><span class="sxs-lookup"><span data-stu-id="d7f54-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="d7f54-207">它不會傳回使用者封存信箱中資料夾的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d7f54-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="d7f54-208">若要傳回使用者封存信箱中資料夾的相關資訊，您可以編輯腳本。</span><span class="sxs-lookup"><span data-stu-id="d7f54-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="d7f54-209">若要這麼做，請將該行變更 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` 為， `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` 然後儲存並執行編輯過的腳本。</span><span class="sxs-lookup"><span data-stu-id="d7f54-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="d7f54-210">這項變更會傳回使用者封存信箱中的資料夾及子資料夾的資料夾 IDs。</span><span class="sxs-lookup"><span data-stu-id="d7f54-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="d7f54-211">若要搜尋整個封存信箱，您可以 `OR` 在搜尋查詢中，以運算子連線所有的資料夾識別碼屬性：值配對。</span><span class="sxs-lookup"><span data-stu-id="d7f54-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="d7f54-212">搜尋信箱資料夾時，只會搜尋以其屬性) 所指定的指定資料夾 (`folderid` ; 也不會搜尋子資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f54-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="d7f54-213">若要搜尋子資料夾，您必須使用您要搜尋之子資料夾的資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="d7f54-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="d7f54-214">搜尋網站資料夾時，資料夾 (會以其 `documentlink` 屬性) 及所有子資料夾加以搜尋。</span><span class="sxs-lookup"><span data-stu-id="d7f54-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span>

- <span data-ttu-id="d7f54-215">當您在 [搜尋查詢] 中只指定屬性時，若要匯出的搜尋結果 `folderid` ，您可以選擇 [第一個匯出] 選項：「所有未辨識格式的專案（除外）」、「加密」或「尚未」為其他原因編制索引」。</span><span class="sxs-lookup"><span data-stu-id="d7f54-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="d7f54-216">不論索引狀態為何，資料夾識別碼永遠都會被匯出，因為資料夾識別碼永遠都是編制索引。</span><span class="sxs-lookup"><span data-stu-id="d7f54-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
