---
title: 複製內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 指令碼，以快速地複製現有的 Office 365 或 Microsoft 365 的合規性中心中 「 內容搜尋。 當您複製搜尋時、 （以新名稱） 的新搜尋會建立包含原始的搜尋相同的屬性。 然後您可以編輯新的搜尋 （藉由變更的關鍵字查詢或日期範圍），然後再執行它。
ms.openlocfilehash: 25aa5d6a1ba19f697a6ccf474e055faf6a19d6bd
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685586"
---
# <a name="clone-a-content-search"></a>複製內容搜尋

在 Office 365 或 Microsoft 365 的合規性中心中建立 「 內容搜尋 」 搜尋大量信箱或 SharePoint 和 OneDrive for Business 網站可能需要一段時間。 指定要搜尋的網站也可以是出錯的機會如果打錯的 URL。 若要避免這些問題，您可以使用 Windows PowerShell 指令碼本文中，快速地複製現有的內容搜尋。 當您複製搜尋時，會建立包含屬性 （例如內容的位置和搜尋查詢） 與相同的原始的搜尋 （使用不同的名稱） 的新搜尋。 然後您可以編輯新的搜尋 （藉由變更的關鍵字查詢或日期範圍），並加以執行。
  
為什麼要複製的內容搜尋？
  
- 若要比較的結果不同的關鍵字搜尋查詢的相同的內容位置上執行。
    
- 若要儲存您不必重新輸入大量內容的位置，當您建立新的搜尋。
    
- 若要縮小搜尋結果中。例如，如果您有傳回結果太多要匯出的搜尋，您可以複製搜尋，然後再新增搜尋條件，根據日期範圍，以減少搜尋結果數目。
  
## <a name="before-you-begin"></a>開始之前

- 您必須是 eDiscovery 管理員角色群組的成員安全 & 與規範中心執行本主題所述的指令碼。
    
- 指令碼包含最少的錯誤處理。 指令碼的主要用途是快速地複製內容搜尋。
    
- 指令碼會建立新的內容搜尋，但不會啟動它。
    
- 此指令碼會考慮是否要複製內容搜尋相關聯的 eDiscovery 案例。 如果搜尋與案例相關聯，也會與相同的案例相關聯的新搜尋。 如果現有的搜尋不與案例相關聯，新的搜尋將會列在規範中心中的 [**內容搜尋**] 頁面上。 
    
- 本主題所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務。 以提供範例指令碼不擔保。 Microsoft 進一步不作任何默示的擔保，包括，但不限於任何默示擔保售或適合特定用途。 與您保持承擔使用或效能的範例指令碼和文件的風險。 事件無法在 Microsoft、 其作者，或任何其他參與建立、 實際執行環境或傳遞的指令碼的人對於而概之任何損害皆不 （包括，但不限於遺失的商務利益、 業務中斷、 遺失的損害嗎商業資訊或其他金錢遺失） 即使 Microsoft 已被告知賠償的可能性，承擔使用或無法使用的範例指令碼或文件。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>步驟 1： 執行指令碼以複製搜尋

在此步驟中的指令碼會建立新的內容搜尋由複製現有的方式。 當您執行此指令碼時，將會提示您輸入下列資訊：
  
- **您的使用者認證**-指令碼會使用您的認證來連線到安全性 & 合規性中心的 Office 365 組織使用 Windows PowerShell。 如先前所述，您必須是 eDiscovery 管理員角色群組的成員安全性 & compCompliance 管理中心中執行指令碼。 
    
- **現有的搜尋的名稱**-這是您想要複製內容搜尋。 
    
- **，將會建立新搜尋的名稱**-如果您將此值保留空白，指令碼會建立新的搜尋，根據您要複製的搜尋名稱的名稱。 
    
複製搜尋：
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `CloneSearch.ps1`。
    
  ```powershell
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
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

2. 開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。
    
3. 執行指令碼。例如：
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. 當系統提示提供認證，請輸入您的電子郵件地址和密碼，，然後按一下 [**確定]**。
    
5. 輸入下列資訊時提示指令碼。 輸入每一項資訊，然後按**Enter**鍵。
    
    - 現有的搜尋的名稱。
    
    - 新的搜尋的名稱。
    
    指令碼會建立新的內容搜尋，但不會啟動它。 這可以讓您有機會編輯，並在下一個步驟中執行搜尋。 藉由執行**Get-compliancesearch** cmdlet 或移至 [規範中心，根據新的搜尋是與案例相關聯的 [**內容搜尋**] 或 [ **eDiscovery** ] 頁面上，您可以檢視新的搜尋的屬性。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>步驟 2： 編輯，並在 「 規範中心執行複製的搜尋

您已執行指令碼以複製現有的內容搜尋之後下, 一步是以移至 「 合規性中心 」，編輯與執行新的搜尋。 如先前所述，您可以編輯搜尋的關鍵字搜尋查詢以及新增或移除搜尋條件。 如需詳細資訊，請參閱：
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
    
- [電子文件探索案例](ediscovery-cases.md)
