---
title: 使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 使用內容搜尋和本文中的腳本，針對使用者群組搜尋商務網站的信箱和 OneDrive。
ms.openlocfilehash: 31dfa2057eff27ed1d2579cc541361858a11c7ce
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943272"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單

安全性 & 合規性中心提供許多 Windows PowerShell Cmdlet，可讓您自動執行耗時的 eDiscovery 相關工作。 目前，在安全性 & 合規性中心內建立內容搜尋，以搜尋大量的保管人內容位置，需要一些時間與準備工作。 在您建立搜尋之前，您必須收集 OneDrive 每個商務用網站的 URL，然後將每個信箱和 OneDrive 的商務網站新增至搜尋。 在未來的版本中，這會在安全性 & 合規性中心較容易進行。 在此之前，您可以使用本文中的腳本來自動化此程式。 此腳本會提示您組織的 MySite 網域的名稱（例如， **contoso** in URL https://contoso-my.sharepoint.com)、使用者電子郵件地址的清單、新內容搜尋的名稱，以及要使用的搜尋查詢）。 腳本會針對清單中的每個使用者，取得商務 URL 的 OneDrive，然後使用您提供的搜尋查詢，來建立及啟動搜尋內容，以針對清單中的每一位使用者，搜尋信箱及 OneDrive for Business site。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須是 Security & 合規性中心內的 eDiscovery Manager 角色群組成員，以及 SharePoint Online 全域系統管理員，才能執行步驟3中的腳本。
    
- 請務必將您在步驟2中建立的使用者清單和步驟3中的腳本儲存在相同的資料夾中。 這樣會使執行腳本變得更容易。
    
- 腳本包含最低的錯誤處理。 其主要用途是快速且輕鬆地搜尋每個使用者之商務網站的信箱和 OneDrive。
    
- 任何 Microsoft standard support program 或 service 都不支援本主題中提供的範例腳本。 範例腳本是以不含任何類型擔保的方式提供。 Microsoft 進一步否認所有我[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)的 mplied 擔保，包括但不限於任何適售性或特定用途適用性的暗示擔保。 因使用或效能範例腳本及檔的整體風險，仍然保留給您。 在任何事件中，Microsoft、其作者、（包括但不限於使用或無法使用範例腳本或檔的任何損害（包括（但不限於）因使用或無法使用範例腳本或檔而造成的任何損害（包括但不限於公司中斷、商務中斷、商務資訊遺失或其他 pecuniary 遺失）以外的任何損害（包括但不限於）使用或無法使用範例腳本或檔時所產生的任何其他
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步驟 1：安裝 SharePoint Online 管理命令介面

第一步是安裝 SharePoint 線上管理命令介面。 您不需要在此程式中使用命令介面，但必須安裝它，因為它包含您在步驟3中執行之腳本所需的必要條件。 這些必要條件允許腳本與 SharePoint Online 進行通訊，以取得商務網站 OneDrive 的 URLs。
  
移至[設定 SharePoint 線上管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)，並執行步驟1和步驟2安裝 SharePoint 線上管理命令介面。
  
## <a name="step-2-generate-a-list-of-users"></a>步驟2：產生使用者清單

步驟3中的腳本會建立內容搜尋，以搜尋信箱及 OneDrive 帳戶清單中的使用者。 您可以只輸入文字檔中的電子郵件地址，也可以在 Windows PowerShell 中執行命令，以取得電子郵件地址清單，並將其儲存至檔案（位於您將在步驟3中儲存腳本的相同資料夾中）。
  
以下是[Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令，您可以 runt 以取得組織中所有使用者的電子郵件地址清單，並將其儲存至名為`Users.txt`的文字檔。 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

在您執行此命令之後，請務必開啟檔案，並移除包含屬性名稱的標頭`PrimarySmtpAddress`。 文字檔應該只包含電子郵件地址的清單，而不包含其他任何內容。 請確定電子郵件地址清單前面或後面沒有任何空白列。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>步驟3：執行腳本以建立及啟動搜尋

當您在此步驟中執行腳本時，它會提示您輸入下列資訊。 在執行腳本之前，請務必準備好此資訊。
  
- **您的使用者認證**-腳本會使用您的認證來存取 SharePoint 線上，以取得商務 OneDrive URLs，以及透過遠端 PowerShell 連接至安全性 & 規範中心。 
    
- **MySite 網域的名稱**-MySite 網域是包含組織中商務網站所有 OneDrive 的網域。 例如，如果 MySite 網域的 URL 是**https://contoso-my.sharepoint.com**，當腳本提示您輸入 MySite 網域`contoso`的名稱時，就會輸入。 
    
- **步驟2中的文字檔路徑名**-您在步驟2中建立的文字檔路徑名。 如果文字檔和腳本位於相同的資料夾中，請輸入文字檔的名稱。 否則，請輸入文字檔的完整路徑名。 
    
- **內容搜尋的名稱**-將由腳本建立的內容搜尋的名稱。 
    
- **搜尋查詢**-建立及執行將用於內容搜尋的搜尋查詢。 如需搜尋查詢的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。


**若要執行腳本：**
    
1. 使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `SearchEXOOD4B.ps1`。 將檔案儲存到您在步驟2中儲存的使用者清單所在的相同資料夾。
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. 開啟 Windows PowerShell，然後移至您用來儲存腳本的資料夾，以及步驟2中的使用者清單。
    
3. 啟動腳本;例如：
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. 當系統提示您輸入認證時，請輸入您的電子郵件地址和密碼，然後按一下 **[確定]**。 
    
5. 當腳本提示時，請輸入下列資訊。 輸入每一條資訊，然後按**enter**鍵。
    
    - MySite 網域的名稱。 
    
    - 包含使用者清單的文字檔路徑名。
    
    - 內容搜尋的名稱。
    
    - 搜尋查詢（將此專案保留空白以傳回內容位置中的所有專案）。
    
    腳本會為商務網站的每個 OneDrive 取得 URLs，然後建立並啟動搜尋。 您可以在安全性 & 規範中心」中執行**Get-ComplianceSearch** Cmdlet PowerShell 以顯示搜尋統計資料和結果，也可以前往安全性 & 規範中心的「**內容搜尋**」頁面，以查看搜尋的相關資訊。 
