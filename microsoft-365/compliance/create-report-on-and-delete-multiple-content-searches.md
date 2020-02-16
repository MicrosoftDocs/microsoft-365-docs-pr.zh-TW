---
title: 建立、報告及刪除多個內容搜尋
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 了解如何建立像搜尋及透過 Office 365 中的安全性 & 合規性中心中的 PowerShell 指令碼執行報告的內容搜尋工作自動化。
ms.openlocfilehash: 915ea910eebba8f6f39ceb41d9475769a6403729
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077181"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>建立、報告及刪除多個內容搜尋

 快速建立和報告探索搜尋是通常重要步驟 eDiscovery 與調查時您想要了解基礎的資料，以及豐富性和搜尋的品質。 若要協助您這麼做，安全性 & 合規性中心 PowerShell 會提供一組 cmdlet 來自動化耗時的內容搜尋工作。 這些指令碼提供快速又簡單的方式，來建立搜尋，數目，然後再執行報告可協助您判斷有問題的資料數量的預估的搜尋結果。 您也可以使用指令碼以建立不同版本的搜尋來比較每個產生的結果。 這些指令碼可協助您快速且更有效地識別及 cull 您的資料。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須是 eDiscovery 管理員角色群組的成員安全 & 與規範中心執行本主題中所述的指令碼。 
    
- Onedrive for Business 網站組織可讓您加入至步驟 1 中的 CSV 檔案中收集的 Url 清單，請參閱[建立您組織中的所有 OneDrive 位置清單](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。 
    
- 請務必儲存您在本主題的相同資料夾中建立的所有檔案。 會將執行指令碼比較方便。
    
- 指令碼包含最少的錯誤處理。 其主要目的是要快速地建立、 回報及刪除多個內容搜尋。
    
- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>步驟 1： 建立 CSV 檔案，其中包含您想要執行搜尋的相關資訊

您在此步驟中建立的逗點分隔的值 (CSV) 檔案包含每個使用者想要搜尋資料列。 您可以搜尋使用者的 Exchange Online 信箱 （其中包含封存信箱，如果已啟用），其 OneDrive for Business 網站。 或者，您可以搜尋只是信箱或商務用 OneDrive 網站。 您也可以在 SharePoint Online 組織中搜尋任何網站。 您在步驟 3 中執行的指令碼會建立 CSV 檔案中的每一列的個別搜尋。 
  
1. 複製並貼入.txt 檔案，使用 [記事本] 中的下列文字。 此檔案儲存至資料夾，在本機電腦上。 您將此資料夾以及儲存其他指令碼。
    
    ```text
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    在第一列或標題列，該檔案列出**New-compliancesearch** cmdlet （在步驟 3 中的指令碼） 時用來建立新的內容搜尋的參數。 每個參數名稱都是以逗號分隔。 請確定標題列中沒有任何空格。 標題列底下的每個資料列代表每個搜尋的參數值。 請務必將 CSV 檔案中的版面配置區資料取代實際資料。 
    
2. 在 Excel 中，開啟.txt 檔案，並再使用下表中的資訊來編輯每個搜尋資訊的檔案。 
    
    |**參數**|**描述**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |使用者信箱的 SMTP 地址。  <br/> |
    | `SharePointLocation` <br/> |使用者的 OneDrive for Business 網站或組織中任何網站的 URL 的 URL。 Onedrive for Business 網站的 url，請使用此格式： ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。 例如，  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。  <br/> |
    | `ContentMatchQuery` <br/> |搜尋的搜尋查詢。 如需建立搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。  <br/> |
    | `StartDate` <br/> |電子郵件，日期當時或之後的訊息已接收到收件者或寄件者所傳送。 文件在 SharePoint 或 OneDrive for Business 網站的上次修改日期當時或之後的文件。  <br/> |
    | `EndDate` <br/> |電子郵件所傳送的日期當天或之前的訊息已傳送的使用者。 文件在 SharePoint 或 OneDrive for Business 網站的上次修改日期當天或之前的文件。  <br/> |
   
3. Excel 檔案儲存為 CSV 檔案的資料夾在本機電腦上。 您在步驟 3 中建立的指令碼會建立搜尋，以使用 CSV 檔案中的資訊。 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步驟 2︰連線至安全性與合規性中心 PowerShell

下一步是連線至安全性 & 貴組織的合規性中心 PowerShell。
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `ConnectSCC.ps1`。 將檔案儲存至您儲存 CSV 檔案，以在步驟 1 中的相同資料夾。
    
    ```powershell
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. 在您的本機電腦上開啟 Windows PowerShell 移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼。例如：
    
    ```powershell
    .\ConnectSCC.ps1
    ```

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>步驟 3： 執行指令碼，以建立並啟動搜尋

在此步驟中的指令碼會建立每個資料列的個別內容搜尋您在步驟 1 建立的 CSV 檔案中。 當您執行此指令碼時，將會提示您輸入兩個值：
  
- **搜尋群組識別碼**此名稱會提供簡單的方法來組織建立 CSV 檔中搜尋。 會建立每個搜尋名為具有搜尋群組識別碼，並接著一個數字會附加至搜尋名稱。 例如，如果您輸入**ContosoCase**搜尋群組識別碼，然後搜尋名為**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**，等等。 請注意，您輸入的名稱是區分大小寫。 當您使用步驟 4 和步驟 5 中搜尋群組識別碼時，您必須使用相同的情況下，如同您在建立時。 
    
- **CSV 檔案**-您在步驟 1 中建立 CSV 檔案的名稱。 請務必包含使用完整的檔案名稱，包含.csv 檔案的副檔名;例如， `ContosoCase.csv`。
    
若要執行指令碼，請執行下列步驟：

1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `CreateSearches.ps1`。 將檔案儲存到您用來儲存其他檔案的相同資料夾。
    
  ```Powershell
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. 在 Windows PowerShell 中，移至在前一個步驟中，您儲存指令碼的所在資料夾，然後執行指令碼;例如：
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. 在**搜尋群組識別碼**提示字元處，輸入搜尋群組名稱，然後按下**Enter**。例如， `ContosoCase`。 請記住此名稱會區分大小寫，所以您必須先在後續步驟中輸入相同的方式。
    
4. 在**來源 CSV 檔案**提示字元處，輸入 CSV 檔案中，包含.csv 檔案的副檔名; 名稱例如， `ContosoCase.csv`。
    
5. 按**Enter**以繼續執行指令碼。 
    
    指令碼會顯示進度的建立和執行搜尋。 指令碼完成時，它會傳回的提示。 
    
    ![執行指令碼以建立多個規範搜尋的範例輸出](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>步驟 4： 執行指令碼，以報告搜尋估計

建立搜尋之後下, 一步是執行指令碼來顯示簡單的步驟 3 中建立每個搜尋的搜尋點擊數報告。 報告也會包含每個搜尋和點擊的總數與總大小的所有搜尋結果的大小。 當您執行報告的指令碼時，系統會提示您針對搜尋群組 ID]，然後將 CSV 檔案名稱如果您想要將報告儲存至 CSV 檔案。
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `SearchReport.ps1`。 將檔案儲存到您用來儲存其他檔案的相同資料夾。
    
  ```Powershell
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. 在 Windows PowerShell 中，移至在前一個步驟中，您儲存指令碼的所在資料夾，然後執行指令碼;例如：
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. 在**搜尋群組識別碼**提示字元處，輸入搜尋群組名稱，然後按下**Enter**。例如`ContosoCase`。 請記住，這個名稱會區分大小寫，所以您必須先輸入相同的方式一樣當您在步驟 3 中執行指令碼時。
    
4. **檔案路徑，以儲存到一個 CSV 檔案 （只顯示 [報表保留空白） 報告**系統提示時，請輸入完整的檔名的路徑 （包括.csv 檔案的副檔名） 的檔案名稱，如果您想要將報告儲存至 CSV 檔案。 CSV 檔案，包括副檔名為.csv 檔案的名稱。 例如，您可以輸入`ContosoCaseReport.csv`若要將它儲存到目前的目錄或您可以輸入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`將它儲存到不同的資料夾。 您也可以將提示顯示報表，但不將它儲存到檔案留白。 
    
5. 按 **Enter**。
    
    指令碼會顯示進度的建立和執行搜尋。 指令碼完成時，會顯示報表。 
    
    ![執行搜尋報告，以顯示搜尋群組的估計](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> 如果相同的信箱或網站指定為 [搜尋] 群組中的多個搜尋的內容位置，（適用於項目數目與大小總計） 報告中的總結果估計可能包含相同的項目結果。 這是因為在相同的電子郵件或文件會被計算一次以上如果它會比對 [搜尋] 群組中的不同搜尋查詢。 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>步驟 5： 執行指令碼，以刪除搜尋

您可能建立的搜尋很多，因為此最後一個指令碼只是容易快速刪除您在步驟 3 中建立搜尋。 像其他的指令碼，這樣也會提示您輸入搜尋群組識別碼。 當您執行此指令碼時，將會刪除所有的搜尋，在 [搜尋名稱搜尋群組識別碼。 
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `DeleteSearches.ps1`。 將檔案儲存到您用來儲存其他檔案的相同資料夾。
    
  ```Powershell
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. 在 Windows PowerShell 中，移至在前一個步驟中，您儲存指令碼的所在資料夾，然後執行指令碼;例如：
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. 在**搜尋群組識別碼**提示字元處，輸入您要刪除搜尋的搜尋群組名稱，然後按 [ **Enter**;例如， `ContosoCase`。 請記住，這個名稱會區分大小寫，所以您必須先輸入相同的方式一樣當您在步驟 3 中執行指令碼時。
    
    指令碼會顯示在刪除每個搜尋的名稱。
    
    ![執行指令碼，以刪除搜尋群組中的搜尋](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
