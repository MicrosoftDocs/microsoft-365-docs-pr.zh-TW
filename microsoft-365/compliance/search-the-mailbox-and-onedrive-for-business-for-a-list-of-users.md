---
title: 在信箱 & 商務用 OneDrive 網站中搜尋使用內容搜尋的使用者清單
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 使用內容搜尋和本文中的腳本，搜尋使用者群組的信箱和商務用 OneDrive 網站。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922465"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單

安全性 & 規範中心提供許多 Windows PowerShell Cmdlet，可讓您自動執行耗時的 eDiscovery 相關工作。 目前，在安全性 & 合規性中心內建立內容搜尋，以搜尋大量的保管人內容位置，需要一些時間與準備工作。 在您建立搜尋之前，您必須收集每個商務用 OneDrive 網站的 URL，然後將每個信箱和商務用 OneDrive 網站新增至搜尋。 在未來的版本中，這會在安全性 & 合規性中心較容易進行。 在此之前，您可以使用本文中的腳本來自動化此程式。 此腳本會提示您組織的 MySite 網域的名稱 (例如，) URL 中的 **contoso** 、 `https://contoso-my.sharepoint.com` 使用者的電子郵件地址清單、新內容搜尋的名稱，以及要使用的搜尋查詢。 腳本會取得清單中每個使用者的商務用 OneDrive URL，然後使用您提供的搜尋查詢，建立及啟動搜尋該清單中每位使用者的信箱和商務用 OneDrive 網站的內容搜尋。
  
## <a name="permissions-and-script-information"></a>許可權及腳本資訊

- 您必須是 Security & 合規性中心內的 eDiscovery Manager 角色群組成員，以及 SharePoint Online 全域系統管理員，才能執行步驟3中的腳本。

- 請務必將您在步驟2中建立的使用者清單和步驟3中的腳本儲存在相同的資料夾中。 這樣會使執行腳本變得更容易。

- 腳本包含最低的錯誤處理。 其主要用途是快速且輕鬆地搜尋每位使用者的信箱和商務用 OneDrive 網站。

- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步驟 1：安裝 SharePoint Online 管理命令介面

第一步是安裝 SharePoint 線上管理命令介面。 您不需要在此程式中使用命令介面，但必須安裝它，因為它包含您在步驟3中執行之腳本所需的必要條件。 這些必要條件允許腳本與 SharePoint Online 進行通訊，以取得商務用 OneDrive 網站的 URLs。
  
移至[設定 SharePoint 線上管理命令介面 Windows PowerShell 環境](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)，並執行步驟1和步驟2安裝 SharePoint 線上管理命令介面。
  
## <a name="step-2-generate-a-list-of-users"></a>步驟2：產生使用者清單

步驟3中的腳本會建立內容搜尋，以搜尋信箱及 OneDrive 帳戶清單中的使用者。 您可以只輸入文字檔中的電子郵件地址，也可以在 Windows PowerShell 中執行命令，以取得電子郵件地址的清單，並將其儲存至相同資料夾中的檔案 (，您將在步驟 3) 中儲存腳本。
  
您可以 runt [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)命令，以取得組織中所有使用者的電子郵件地址清單，並將其儲存至名為的文字檔 `Users.txt` 。 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

在您執行此命令之後，請務必開啟檔案，並移除包含屬性名稱的標頭  `PrimarySmtpAddress` 。 文字檔應該只包含電子郵件地址的清單，而不包含其他任何內容。 請確定電子郵件地址清單前面或後面沒有任何空白列。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>步驟3：執行腳本以建立及啟動搜尋

當您在此步驟中執行腳本時，它會提示您輸入下列資訊。 在執行腳本之前，請務必準備好此資訊。
  
- **您的使用者認證**-腳本會使用您的認證來存取 SharePoint 線上，以取得商務用 OneDrive URLs 以及使用遠端 PowerShell 連線到安全性 & 規範中心。 
    
- **MySite 網域的名稱**-MySite 網域是包含組織中所有商務用 OneDrive 網站的網域。 例如，如果 MySite 網域的 URL 是 **https://contoso-my.sharepoint.com** ，  `contoso` 當腳本提示您輸入 MySite 網域的名稱時，就會輸入。 
    
- **步驟2中的文字檔路徑名** -您在步驟2中建立的文字檔路徑名。 如果文字檔和腳本位於相同的資料夾中，請輸入文字檔的名稱。 否則，請輸入文字檔的完整路徑名。 
    
- **內容搜尋的名稱** -將由腳本建立的內容搜尋的名稱。 
    
- **搜尋查詢** -建立及執行將用於內容搜尋的搜尋查詢。 如需搜尋查詢的詳細資訊，請參閱 [內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。


**若要執行腳本：**
    
1. 使用 .ps1 的檔案名尾碼，將下列文字儲存至 Windows PowerShell 腳本檔案;例如， `SearchEXOOD4B.ps1` 。 將檔案儲存到您在步驟2中儲存的使用者清單所在的相同資料夾。
    
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
    
5. 當腳本提示時，請輸入下列資訊。 輸入每一條資訊，然後按 **enter** 鍵。
    
    - MySite 網域的名稱。 
    
    - 包含使用者清單的文字檔路徑名。
    
    - 內容搜尋的名稱。
    
    - 搜尋查詢 (將此專案保持空白，以傳回內容位置) 中的所有專案。
    
    腳本會取得每個商務用 OneDrive 網站的 URLs，然後建立並啟動搜尋。 您可以在安全性 & 規範中心」中執行 **Get-ComplianceSearch** Cmdlet PowerShell 以顯示搜尋統計資料和結果，也可以前往安全性 & 規範中心的「 **內容搜尋** 」頁面，以查看搜尋的相關資訊。