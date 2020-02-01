---
title: 在 Office 365 中使用內容搜尋，對目標集合
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
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: 使用安全性 & 合規性中心的內容搜尋來執行目標的集合。 目標的集合表示您確信回應大小寫的項目或特殊權限項目都位於信箱或網站的特定資料夾。 使用本文中的指令碼，以取得資料夾識別碼或您想要搜尋的特定信箱或網站資料夾的路徑。
ms.openlocfilehash: 66929911cdb1692ea1ee2a8920dad349d50ec156
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597300"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>在 Office 365 中使用內容搜尋，對目標集合

Office 365 安全性中的內容搜尋功能&amp;合規性中心不提供在 UI 中搜尋特定資料夾中部署 Exchange 信箱或 SharePoint 和 OneDrive for Business 網站直接的方法。 不過，很可能在實際的搜尋查詢語法中指定的電子郵件] 資料夾識別碼屬性或網站的路徑 (DocumentLink) 屬性來搜尋特定資料夾 （稱為 「*目標集合*）。 當您確信回應大小寫的項目或特殊權限項目會位於特定的信箱或網站資料夾中，使用內容搜尋來執行目標的集合特別有用。 您可以使用本文中的指令碼，以取得信箱資料夾的資料夾識別碼或資料夾上的 SharePoint 和 OneDrive for Business 網站的路徑 (DocumentLink)。 然後您可以使用的資料夾識別碼或路徑在搜尋查詢中要傳回的項目位於資料夾中。

> [!NOTE]
> 若要傳回位於資料夾中的 SharePoint 或 OneDrive for Business 網站的內容，本主題中的指令碼會使用 DocumentLink managed 屬性，而不是在 Path 屬性。 DocumentLink 屬性是比 Path 屬性更強固的因為它會傳回所有內容在資料夾中，而路徑屬性不會都傳回某些媒體檔案。

## <a name="before-you-begin"></a>開始之前

- 您必須是安全性中的 eDiscovery 管理員角色群組的成員&amp;合規性中心，以在步驟 1 中執行指令碼。 如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。
    
    此外，您必須獲指派 Exchange Online 組織中的 「 郵件收件者角色。 這樣才能執行**Get-mailboxfolderstatistics**指令程式，在 [步驟 1 中的指令碼包含這個功能。 根據預設，「 郵件收件者 」 角色被指派給組織管理和收件者管理角色群組在 Exchange Online。 如需指派 Exchange Online 中的權限的詳細資訊，請參閱[管理角色群組成員](https://go.microsoft.com/fwlink/p/?linkid=692102)。 您可能也建立自訂角色群組、 指派 「 郵件收件者 」 角色給它，然後再新增需要執行指令碼在步驟 1 中的成員。 如需詳細資訊，請參閱[管理角色群組](https://go.microsoft.com/fwlink/p/?linkid=730688)。
    
- 每次您在步驟 1 中，執行指令碼會建立新的遠端 PowerShell 工作階段。 因此您可能會用完所有遠端 PowerShell 工作階段提供給您。 若要避免這種情況，您可以執行下列命令，以中斷連線的作用中的遠端 PowerShell 工作階段。
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)＞。
    
- 指令碼包含最少的錯誤處理。 指令碼的主要用途是快速顯示信箱資料夾識別碼的清單或網站可以在內容搜尋的搜尋查詢語法中用來執行目標的集合的路徑。
    
- 本主題所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務。 以提供範例指令碼不擔保。 Microsoft 進一步不作任何默示的擔保，包括，但不限於任何默示擔保售或適合特定用途。 與您保持承擔使用或效能的範例指令碼和文件的風險。 事件無法在 Microsoft、 其作者，或任何其他參與建立、 實際執行環境或傳遞的指令碼的人對於而概之任何損害皆不 （包括，但不限於遺失的商務利益、 業務中斷、 遺失的損害嗎商業資訊或其他金錢遺失） 即使 Microsoft 已被告知賠償的可能性，承擔使用或無法使用的範例指令碼或文件。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>步驟 1： 執行指令碼，以取得之信箱或網站的資料夾清單

您在此第一個步驟中執行的指令碼會傳回信箱資料夾的清單或 SharePoint 和 OneDrive for Business 資料夾和對應的資料夾識別碼或每個資料夾的路徑。 當您執行此指令碼時，它會提示您輸入下列資訊。
  
- **電子郵件地址或網站的 URL**輸入到 Exchange 信箱資料夾和資料夾識別碼的清單傳回 custodian 電子郵件地址。 或輸入 SharePoint 網站的 URL 或商務用 OneDrive 網站，可傳回指定網站的路徑清單。 以下為一些範例： 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **商務用 OneDrive** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **您的使用者認證**-指令碼會使用您的認證來連線到 Exchange Online 與遠端 PowerShell 安全性 & 合規性中心。 如先前所述，您必須指派適當的權限，才能成功執行此指令碼。
    
若要顯示的信箱資料夾清單或網站 documentlink （路徑） 名稱：
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `GetFolderSearchParameters.ps1`。
    
  ```powershell
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security & Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                  #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)  #
  #      appended to the folder ID or documentlink to use in a Content Search.              #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
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

2. 在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。
    
3. 執行指令碼。例如：
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. 輸入指令碼會提示您輸入的資訊。
    
    指令碼會顯示信箱資料夾或指定之使用者的網站資料夾清單。 讓此視窗開啟，讓您可以複製的資料夾識別碼或 documentlink 名稱，並將它在貼到步驟 2 中的搜尋查詢。
    
    > [!TIP]
    > 而不是在 [電腦] 畫面上顯示的資料夾清單，您可以重新導向至文字檔的指令碼的輸出。 此檔案會儲存至指令碼的所在位置的資料夾。 例如，要重新導向的輸出傳送至文字檔的指令碼，在步驟 3 中執行下列命令：`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`然後您可以複製的資料夾識別碼或 documentlink 要在搜尋查詢中使用的檔案。
  
### <a name="script-output-for-mailbox-folders"></a>信箱資料夾的指令碼輸出

如果您收到信箱資料夾識別碼，指令碼會使用遠端 PowerShell 連線到 Exchange Online、 執行**Get MailboxFolderStatisics**指令程式，然後顯示 [從指定的信箱資料夾的清單。 信箱中每個資料夾，指令碼會顯示在**FolderPath**行中，[ **FolderQuery** ] 欄中的資料夾識別碼的資料夾名稱。 此外，指令碼會將**folderId** （這是信箱屬性的名稱） 的前置詞新增至資料夾識別碼。 由於**folderid**屬性是可搜尋的屬性，您要使用`folderid:<folderid>`搜尋查詢中搜尋該資料夾的步驟 2 中。 指令碼會顯示最大值為 100 個信箱資料夾。

> [!IMPORTANT]
> 本文中的指令碼包含編碼方式將轉換都會由**Get-mailboxfolderstatistics**會編入搜尋索引的相同 48 個字元格式的 64 個字元的資料夾識別碼值的邏輯。 如果您只要在 PowerShell 中的資料夾識別碼取得 （而不是在本文中執行指令碼） 執行**Get-mailboxfolderstatistics**指令程式，將會失敗的搜尋查詢，會使用該資料夾用戶端識別碼值。 您必須執行指令碼，以在內容搜尋中取得正確格式化資料夾可用的識別碼。
  
以下是範例傳回信箱資料夾的指令碼的輸出。
  
![信箱資料夾和傳回的 id 指令碼的資料夾清單的範例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
步驟 2 中的範例會顯示用來搜尋使用者的 [可復原的項目] 資料夾中的清除] 子資料夾的查詢。
  
### <a name="script-output-for-site-folders"></a>網站資料夾的指令碼輸出

如果您收到**documentlink**屬性的路徑從 SharePoint 或 OneDrive for Business 網站，指令碼安全性 & 合規性中心使用遠端 PowerShell 連線時，會建立新的內容搜尋的搜尋資料夾的網站，然後顯示位於指定的站台的資料夾清單。 指令碼會顯示每個資料夾的名稱，並將**documentlink**的前置詞新增至資料夾的 URL。 由於**documentlink**屬性是可搜尋的屬性，您要使用`documentlink:<path>`搜尋查詢中搜尋該資料夾的步驟 2 中的屬性： 值組。 指令碼會顯示最大值為 200 個站台資料夾。 如果有 200 個以上的網站資料夾，會顯示為最新的。
  
以下是範例的指令碼的站台資料夾所傳回的輸出。
  
![指令碼所傳回的站台資料夾 documentlink 名稱的清單的範例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>步驟 2： 使用資料夾識別碼或 documentlink 來執行目標的集合

之後您已執行指令碼，以收集資料夾識別碼或 documentlinks 特定使用者，接著移至安全性 & 規範中心，並建立新的內容搜尋來搜尋特定的資料夾清單。 您要使用`folderid:<folderid>`或`documentlink:<path>`屬性： 值配對的搜尋查詢中，您設定內容搜尋關鍵字] 方塊中 （或如果您使用**New-compliancesearch** cmdlet *ContentMatchQuery*參數的值為）。 您可以合併`folderid`或`documentlink`屬性與其他搜尋參數，或搜尋條件。 如果您只會包括`folderid`或`documentlink`屬性在查詢中的，搜尋會傳回位於指定的資料夾內的所有項目。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 中，使用的帳戶與您用來執行指令碼在步驟 1 中的認證。
    
3. 在安全性 & 合規性中心的左窗格中，按一下 [**搜尋** \> **內容搜尋**]，然後按一下 [**新增**![加入圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
4. 在 [新增搜尋]**** 頁面上，輸入內容搜尋的名稱。 此名稱在您的組織中必須是唯一的。 
    
5. 在 [**您希望在哪裡我們在哪裡**，執行下列其中一項根據您要搜尋的信箱資料夾或站台資料夾：
    
    - 按一下 [**選擇来搜尋的特定信箱**，然後新增您指定當您在步驟 1 中執行指令碼的同一個信箱。 
    
      或
    
    - 按一下 [**選擇要搜尋的特定網站**新增至搜尋，然後新增您指定當您在步驟 1 中執行指令碼的相同網站 URL。 
    
6. 按 [下一步]****。
    
7. 在**什麼您希望我們要尋找的**頁面上的 [關鍵字] 方塊中，貼上`folderid:<folderid>`或`documentlink:<path>`指令碼在步驟 1 中所傳回的值。 
    
    例如，下列螢幕擷取畫面中的查詢會搜尋使用者的 [可復原的項目] 資料夾中的 [清除] 子資料夾中的任何項目 (值`folderid`在步驟 1 中的螢幕擷取畫面所示的清除] 子資料夾的屬性):
    
    ![貼上 folderid 或至搜尋查詢的 [關鍵字] 方塊中 documentlink](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. 按一下 [**搜尋**] 以啟動目標的集合的搜尋。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>對目標集合的搜尋查詢的範例

以下是使用的一些範例`folderid`和`documentlink`搜尋查詢來執行目標的集合中的屬性。 請注意，用於預留位置`folderid:<folderid>`和`documentlink:<path>`儲存空間。 
  
- 本範例會搜尋三個不同的信箱資料夾。 您可以使用類似的查詢語法來搜尋使用者的 [可復原的項目] 資料夾中的隱藏的資料夾。
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 本範例會搜尋信箱資料夾包含精準字詞的項目。
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 本範例會搜尋包含標題中的字母 「 NDA 」 的文件的網站資料夾 （和任何子資料夾）。
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- 本範例會搜尋網站資料夾 （和任何子資料夾） 的文件那里已變更的日期範圍內。
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>詳細資訊

在本文中使用指令碼來執行目標的集合時，請記住下列事項。
  
- 指令碼不會從結果中移除任何資料夾。 讓某些資料夾中所列的結果可能無法 （或傳回零的項目） 因為它們包含系統所產生的內容。
    
- 此指令碼只會傳回使用者的主要信箱資料夾的資訊。 它不會在使用者的封存信箱中傳回資料夾的相關資訊。
    
- 搜尋信箱資料夾時，只有指定的資料夾時 (識別由其`folderid`屬性) 將搜尋;無法搜尋的子資料夾。 若要搜尋的子資料夾，您需要使用的資料夾識別碼，針對您想要搜尋的子資料夾。 
    
- 搜尋網站資料夾，該資料夾時 (由識別其`documentlink`屬性)，以及將會搜尋所有的子資料夾。 
    
- 匯出在其中您只指定搜尋結果時`folderid`在搜尋查詢的屬性，您可以選擇先匯出選項，「 不含已無法辨識的格式，如果出版物的所有項目已加密，或因為其他原因而未建立索引 」。 一律會將資料夾中的所有項目匯出不論其索引狀態，因為資料夾識別碼一律編製索引。
