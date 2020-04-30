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
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 瞭解如何透過 Office 365 的安全性 & 規範中心內的 PowerShell 腳本，以自動化內容搜尋工作，例如建立搜尋及執行報告。
ms.openlocfilehash: 4e66013ba34c71fd7e2078691f892c2ae289538b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943494"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>建立、報告及刪除多個內容搜尋

 當您嘗試深入瞭解基礎資料時，以及搜尋的豐富程度和品質，在 eDiscovery 和調查中，快速建立及報告探索搜尋通常是很重要的步驟。 為了協助您執行這項作業，安全性 & 規範中心 PowerShell 提供一組 Cmdlet，以自動化耗時的內容搜尋任務。 這兩個腳本提供一種快速快捷的方式來建立許多搜尋，然後執行估計的搜尋結果報告，可協助您判斷問題的資料量。 您也可以使用腳本來建立不同的搜尋版本，以比較每個搜尋產生的結果。 這些腳本可協助您快速且有效地識別及挑選您的資料。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須是 Security & 合規性中心內 eDiscovery 管理員角色群組的成員，才可執行本主題中所述的腳本。 
    
- 若要收集組織中您可以在步驟1中新增至 CSV 檔案之商務網站的 OneDrive URLs 清單，請參閱[建立組織中所有 OneDrive 位置的清單](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。 
    
- 請務必將您在本主題中建立的所有檔案儲存至相同的資料夾。 這樣會使執行腳本變得更容易。
    
- 腳本包含最低的錯誤處理。 其主要用途是快速建立、報告和刪除多個內容搜尋。
    
- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>步驟1：建立包含您要執行之搜尋資訊的 CSV 檔案

在此步驟中建立的逗點分隔值（CSV）檔案，會為每一個要搜尋的使用者包含一列。 您可以搜尋使用者的 Exchange Online 信箱（包含封存信箱（如果已啟用），以及其 OneDrive 的商務網站。 或者，您可以只搜尋商務網站的信箱或 OneDrive。 您也可以搜尋 SharePoint Online 組織中的任何網站。 您在步驟3中執行的腳本會為 CSV 檔案中的每一列建立個別的搜尋。 
  
1. 使用 [記事本] 複製並貼上下列文字至 .txt 檔案。 將此檔案儲存到本機電腦上的資料夾。 您也可以將其他腳本儲存至此資料夾。
    
    ```text
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    檔案的第一列（或標題列）會列出**New-ComplianceSearch** Cmdlet （在步驟3的腳本中）建立新的內容搜尋時所使用的參數。 每個參數名稱都是以逗號分隔。 請確定標頭列中沒有任何空格。 標頭列底下的每一列都代表每個搜尋的參數值。 請務必以實際資料取代 CSV 檔案中的預留位置資料。 
    
2. 在 Excel 中開啟 .txt 檔，然後使用下表中的資訊，針對每個搜尋的資訊來編輯檔案。 
    
    |**參數**|**描述**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |使用者信箱的 SMTP 位址。  <br/> |
    | `SharePointLocation` <br/> |使用者的商務用網站 OneDrive URL，或組織中任何網站的 URL。 若為商務用網站的 OneDrive URL，請使用此格式` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `：。 例如，  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。  <br/> |
    | `ContentMatchQuery` <br/> |搜尋的搜尋查詢。 如需建立搜尋查詢的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。  <br/> |
    | `StartDate` <br/> |若為電子郵件，收件者或傳送者傳送郵件的日期或後的日期。 對於商務網站 SharePoint 或 OneDrive 的檔，上次修改檔的日期。  <br/> |
    | `EndDate` <br/> |電子郵件，由使用者傳送的郵件傳送日期或之前的日期。 對於商務網站 SharePoint 或 OneDrive 的檔，上次修改檔的日期。  <br/> |
   
3. 將 Excel 檔案當做 CSV 檔案儲存至本機電腦上的資料夾。 您在步驟3中建立的腳本會使用此 CSV 檔案中的資訊來建立搜尋。 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步驟 2︰連線至安全性與合規性中心 PowerShell

下一步是連接至組織的安全性 & 規範中心 PowerShell。
  
1. 使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `ConnectSCC.ps1`。 將檔案儲存到您在步驟1中儲存 CSV 檔案的相同資料夾。
    
    ```powershell
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. 在您的本機電腦上，開啟 [Windows PowerShell]，移至您在上一個步驟中建立的腳本所在的資料夾，然後執行腳本;例如：
    
    ```powershell
    .\ConnectSCC.ps1
    ```

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>步驟3：執行腳本以建立及啟動搜尋

此步驟中的腳本會針對您在步驟1中建立的 CSV 檔案中的每一列，建立個別的內容搜尋。 當您執行此腳本時，系統會提示您輸入兩個值：
  
- **搜尋群組識別碼**-此名稱提供一種簡單的方法，可組織從 CSV 檔案建立的搜尋。 所建立的每個搜尋都是以搜尋群組識別碼命名，然後在搜尋名稱中附加數位。 例如，如果您為搜尋群組識別碼輸入**ContosoCase** ，則搜尋會命名為**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**等。 請注意，您輸入的名稱會區分大小寫。 當您在步驟4和步驟5中使用搜尋群組識別碼時，您必須使用與建立它時相同的大小寫。 
    
- **Csv**檔案-您在步驟1中建立的 CSV 檔案名。 請務必包含使用完整檔案名，包含 .csv 副檔名;例如， `ContosoCase.csv`。
    
若要執行指令碼，請執行下列步驟：

1. 使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `CreateSearches.ps1`。 將檔案儲存到儲存其他檔案所在的相同資料夾。
    
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

2. 在 [Windows PowerShell] 中，移至上一個步驟中您用來儲存腳本的資料夾，然後執行腳本;例如：
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. 在 [**搜尋群組識別碼**] 提示中，輸入搜尋組名，然後按**enter**;例如， `ContosoCase`。 請記住，此名稱區分大小寫，所以您必須在後續步驟中以相同的方式輸入此名稱。
    
4. 在**來源 CSV**檔案提示字元處，輸入 csv 檔案名（包括 .csv 副檔名）的名稱;例如， `ContosoCase.csv`。
    
5. 按**enter**繼續執行腳本。 
    
    腳本會顯示建立及執行搜尋的進度。 當腳本完成時，會傳回提示。 
    
    ![執行指令碼以建立多個規範搜尋的範例輸出](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>步驟4：執行腳本以報告搜尋估計

在您建立搜尋之後，下一步是執行腳本，以顯示在步驟3中所建立之每個搜尋之搜尋命中數目的簡單報告。 報告也包含每個搜尋的結果大小，以及所有搜尋的命中總數及總大小。 當您執行報表腳本時，系統會提示您輸入搜尋群組識別碼，如果您想要將報告儲存至 CSV 檔案，則會提示您輸入 CSV 檔案名。
  
1. 使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `SearchReport.ps1`。 將檔案儲存到儲存其他檔案所在的相同資料夾。
    
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

2. 在 [Windows PowerShell] 中，移至上一個步驟中您用來儲存腳本的資料夾，然後執行腳本;例如：
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. 在 [**搜尋群組識別碼**] 提示中，輸入搜尋組名，然後按**enter**;例如`ContosoCase`。 請記住，這個名稱是區分大小寫的，所以您必須使用在步驟3中執行腳本時所用的相同方式來輸入。
    
4. 若要將報告儲存至**csv 檔案（保留空白以顯示報告）** 提示，請在您想要將報告儲存至 csv 檔案時，輸入完整檔案名路徑的檔案名（包括 .csv 副檔名）。 CSV 檔案名（包括 .csv 副檔名）的名稱。 例如，您可以輸入`ContosoCaseReport.csv`將其儲存至目前的目錄，或輸入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`將其儲存至不同的資料夾。 您也可以將提示保留空白，以顯示報表，但不會將其儲存至檔案。 
    
5. 按 **Enter**。
    
    腳本會顯示建立及執行搜尋的進度。 當腳本完成時，就會顯示報告。 
    
    ![執行搜尋報告，以顯示搜尋群組的估計](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> 如果相同的信箱或網站指定為搜尋群組中的多個搜尋中的內容位置，則報告中的總結果（專案數目及總大小）可能會包含相同專案的結果。 這是因為當電子郵件訊息或檔符合搜尋群組中不同搜尋的查詢時，將會算作超過一次的電子郵件或檔。 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>步驟5：執行腳本以刪除搜尋

因為您可能會建立許多搜尋，所以最後的腳本只是讓您輕鬆地快速刪除您在步驟3中建立的搜尋。 與其他腳本類似的是，這也會提示您輸入搜尋群組識別碼。 當您執行此腳本時，搜尋名稱中的所有搜尋群組識別碼都會被刪除。 
  
1. 使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `DeleteSearches.ps1`。 將檔案儲存到儲存其他檔案所在的相同資料夾。
    
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

2. 在 [Windows PowerShell] 中，移至上一個步驟中您用來儲存腳本的資料夾，然後執行腳本;例如：
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. 在 [**搜尋群組識別碼**] 提示中，輸入您要刪除之搜尋的搜尋組名，然後按**enter**;例如， `ContosoCase`。 請記住，這個名稱是區分大小寫的，所以您必須使用在步驟3中執行腳本時所用的相同方式來輸入。
    
    腳本會顯示每個已刪除之搜尋的名稱。
    
    ![執行指令碼，以刪除搜尋群組中的搜尋](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
