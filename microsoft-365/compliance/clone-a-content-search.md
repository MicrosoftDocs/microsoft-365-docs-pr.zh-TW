---
title: 複製內容搜尋
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: 使用本文中的 PowerShell 腳本，可在 Office 365 或 Microsoft 365 的規範中心內快速複製現有的內容搜尋。
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918059"
---
# <a name="clone-a-content-search"></a>複製內容搜尋

在搜尋許多信箱或 SharePoint 和商務用 OneDrive 網站的 Office 365 或 Microsoft 365 中建立內容搜尋，可能需要一段時間。 如果您錯誤鍵入 URL，也可以指定要搜尋的網站。 為了避免發生這些問題，您可以使用本文中的 Windows PowerShell 腳本，快速複製現有的內容搜尋。 當您複製搜尋時，會建立新的搜尋)  (，其中包含相同的 (屬性，如內容位置和搜尋查詢) 的原始搜尋。 然後，您可以變更關鍵字查詢或日期範圍，並執行它，以編輯新的搜尋。
  
為何要複製內容搜尋？
  
- 若要比較不同關鍵字搜尋查詢的結果，請在相同的內容位置上執行。
    
- 若要讓您在建立新的搜尋時，不必重新輸入大量的內容位置。
    
- 可減少搜尋結果的大小。 例如，如果您有一個搜尋會傳回太多結果以進行匯出，您可以複製搜尋，然後根據日期範圍新增搜尋條件，以減少搜尋結果的數目。
  
## <a name="script-information"></a>腳本資訊

- 您必須是 Security & 合規性中心內 eDiscovery 管理員角色群組的成員，才可執行本主題中所述的腳本。
    
- 腳本包含最低的錯誤處理。 腳本的主要用途是快速複製內容搜尋。
    
- 腳本會建立新的內容搜尋，但不會將其啟動。
    
- 此腳本會考慮您要製作的內容搜尋是否與 eDiscovery 案例相關聯。 如果搜尋與案例相關聯，則新的搜尋也會與同一個案例產生關聯。 如果現有的搜尋未與案例相關聯，則新的搜尋會列在「規範中心」的 [ **內容搜尋** ] 頁面上。 
    
- 在任何 Microsoft standard support 方案或服務下，都不支援本主題中提供的範例腳本。 範例指令碼係依「現狀」提供，不含任何種類的擔保方式。 Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。 使用或操作範例指令碼和文件發生的所有風險，皆屬於您的責任。 Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼或文件所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>步驟1：執行腳本以複製搜尋

此步驟中的腳本會複製現有的內容，以建立新的內容搜尋。 當您執行此腳本時，系統會提示您輸入下列資訊：
  
- **您的使用者認證**-腳本會使用您的認證，以使用 Windows PowerShell 連接組織的安全性 & 規範中心。 如先前所述，您必須是 Security & compCompliance Center 中 eDiscovery Manager 角色群組的成員，才能執行該腳本。 
    
- **現有搜尋的名稱** -這是您要複製的內容搜尋。 
    
- **將要建立之新搜尋的名稱** （如果您將此值保留空白），腳本會根據您要複製的搜尋名稱，為新的搜尋建立名稱。 
    
若要複製搜尋：
  
1. 使用 .ps1 的檔案名尾碼，將下列文字儲存至 Windows PowerShell 腳本檔案;例如， `CloneSearch.ps1` 。
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. 開啟 Windows PowerShell，然後移至您用來儲存腳本的資料夾。
    
3. 執行腳本;例如：
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. 當系統提示您輸入認證時，請輸入您的電子郵件地址和密碼，然後按一下 **[確定]**。
    
5. 當腳本提示時，請輸入下列資訊。 輸入每一條資訊，然後按 **enter** 鍵。
    
    - 現有搜尋的名稱。
    
    - 新搜尋的名稱。
    
    腳本會建立新的內容搜尋，但不會將其啟動。 這可讓您有機會在下一個步驟中編輯及執行搜尋。 您可以執行 **Get-ComplianceSearch** 指令程式，或前往規範中心中的 [ **內容搜尋** ] 或 [ **eDiscovery** ] 頁面，以查看新搜尋的屬性，視新的搜尋是否與案例相關聯而定。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>步驟2：在規範中心編輯和執行複製的搜尋

在您執行腳本以複製現有的內容搜尋之後，下一步是移至規範中心以編輯及執行新的搜尋。 如先前所述，您可以變更關鍵字搜尋查詢，並新增或移除搜尋條件，以編輯搜尋。 如需詳細資訊，請參閱：
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
    
- [電子文件探索案例](./get-started-core-ediscovery.md)