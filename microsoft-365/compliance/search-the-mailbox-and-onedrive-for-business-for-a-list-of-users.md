---
title: 使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單
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
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 本文中使用內容搜尋和指令碼來搜尋信箱與 OneDrive for Business 網站的使用者群組。
ms.openlocfilehash: 02b89646fdb4175d30dce8840ac069f62995cbbc
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685584"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單

安全性 & 合規性中心提供數個 Windows PowerShell cmdlet，可讓您自動化耗時的 eDiscovery 相關工作。 目前，安全性 & 規範中心來搜尋大量 custodian 內容位置中建立內容搜尋需要花費時間和準備。 建立搜尋，您必須先收集每個 onedrive for Business 網站的 URL，然後新增每個信箱和 OneDrive for Business 網站搜尋。 在未來版本中，這會比較容易安全 & 與規範中心執行動作。 在那之前，您可以使用指令碼本文中，自動執行此程序。 此指令碼會提示您輸入您的組織我的網站網域的名稱 (例如， **contoso**在 URL 中https://contoso-my.sharepoint.com)，清單中的使用者電子郵件地址，新的內容搜尋，以及搜尋查詢使用的名稱。 指令碼取得 OneDrive for Business URL 在清單中，每位使用者，然後它會建立並啟動 「 內容搜尋 」 來搜尋信箱和 OneDrive for Business 網站的清單中，每位使用者使用您提供搜尋查詢。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須是安全 & 與規範中心和 SharePoint Online 的全域系統管理員在步驟 3 中執行指令碼中 eDiscovery 管理員角色群組的成員。
    
- 請務必儲存您在步驟 2 和步驟 3 中指令碼的相同資料夾中建立的使用者清單。 會將執行指令碼比較方便。
    
- 指令碼包含最少的錯誤處理。 它的主要目的是要快速且輕鬆地搜尋的信箱和 OneDrive for Business 網站的每位使用者。
    
- 本主題所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務。 IS 提供的範例指令碼沒有任何形式之擔保。 Microsoft 進一步不作任何所有我[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied 擔保包括，但不限於任何默示擔保售或適合特定用途。 與您保持承擔使用或效能的範例指令碼和文件的風險。 事件無法在 Microsoft、 其作者，或任何其他參與建立、 實際執行環境或傳遞的指令碼的人對於而概之任何損害皆不 （包括，但不限於遺失的商務利益、 業務中斷、 遺失的損害嗎商業資訊或其他金錢遺失） 即使 Microsoft 已被告知賠償的可能性，承擔使用或無法使用的範例指令碼或文件。
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步驟 1：安裝 SharePoint Online 管理命令介面

第一個步驟是安裝在 SharePoint Online 管理命令介面。 您不需要使用命令介面，在此程序，但是您必須安裝，因為它包含您在步驟 3 中執行的指令碼所需的必要條件。 這些必要條件允許指令碼，以與 SharePoint Online 取得 onedrive for Business 網站的 Url 進行通訊。
  
移至[設定 SharePoint Online 管理命令介面的 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)並執行步驟 1 和步驟 2，以安裝 SharePoint Online 管理命令介面。
  
## <a name="step-2-generate-a-list-of-users"></a>步驟 2： 產生使用者的清單

步驟 3 中的指令碼會建立內容搜尋來搜尋信箱和 OneDrive 帳戶的使用者清單。 您只可以在文字檔案中，輸入電子郵件地址，或您可以取得電子郵件地址的清單，並將其儲存至檔案 （位於相同的資料夾，您將在步驟 3 中儲存指令碼，以） 的 Windows PowerShell 中執行命令。
  
以下是[Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令，您可以取得組織中的所有使用者的電子郵件地址清單，並將它儲存到文字檔，命名為 runt `Users.txt`。 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

您執行此命令後，請務必要開啟的檔案，並移除標頭包含屬性名稱， `PrimarySmtpAddress`。 電子郵件地址的清單，並無其他內容，應該只包含文字檔案。 請確定有任何空白資料列之前或之後的電子郵件地址清單。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>步驟 3： 執行指令碼，以建立並啟動搜尋

當您在此步驟中執行指令碼時，它會提示您輸入下列資訊。 請務必執行指令碼之前已準備好此資訊。
  
- **您的使用者認證**-指令碼會使用您的認證來存取 SharePoint Online 取得 OneDrive for Business Url，並連線至遠端 PowerShell 安全性 & 合規性中心。 
    
- **我的網站網域的名稱**-我的網站網域是包含所有商務用 OneDrive 網站組織中的網域。 例如，如果我的網站網域 URL **https://contoso-my.sharepoint.com**，然後輸入`contoso`當指令碼會提示您輸入我的網站網域的名稱。 
    
- **步驟 2 的文字檔案的路徑名稱**-您在步驟 2 中建立文字檔案的路徑名稱。 如果文字檔案和指令碼位於相同的資料夾，然後輸入的文字檔案的名稱。 否則，輸入的文字檔案的完整路徑名稱。 
    
- **內容搜尋的名稱**-將指令碼所建立的內容搜尋的名稱。 
    
- 建立並執行**搜尋查詢**將用於使用內容搜尋的搜尋查詢。 如需搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。


**若要執行指令碼：**
    
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `SearchEXOOD4B.ps1`。 將檔案儲存在步驟 2 中儲存的使用者清單所在的相同資料夾。
    
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

2. 開啟 Windows PowerShell，並移至您儲存指令碼和使用者清單，從步驟 2 的資料夾。
    
3. 啟動指令碼。例如：
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. 當系統提示提供認證，請輸入您的電子郵件地址和密碼，，然後按一下 [**確定]**。 
    
5. 輸入下列資訊時提示指令碼。 輸入每一項資訊，然後按**Enter**鍵。
    
    - 我的網站網域的名稱。 
    
    - 包含使用者清單的文字檔案路徑名稱。
    
    - 內容搜尋的名稱。
    
    - 搜尋查詢 （離開此空白若要傳回的內容位置中的所有項目）。
    
    指令碼取得每個 onedrive for Business 網站的 Url，然後建立並啟動搜尋。 您也可以執行**Get-compliancesearch** cmdlet 中安全性 & 合規性中心 PowerShell 來顯示搜尋統計資料和結果，或者您可以移至 [**內容搜尋**] 頁面上，安全性 & 合規性中心，若要檢視搜尋的相關資訊。 
