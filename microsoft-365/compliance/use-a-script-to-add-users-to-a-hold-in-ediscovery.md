---
title: 使用指令碼將使用者新增至 eDiscovery 案例中安全性 & 合規性中心中的保留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: 執行指令碼，以快速新增信箱和 OneDrive for Business 網站至新的保留與安全性 & 規範中心的 eDiscovery 案例相關聯。
ms.openlocfilehash: 7a7ea582391e2fbfcef8b63d331d64f52db4460c
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685636"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-security--compliance-center"></a>使用指令碼將使用者新增至 eDiscovery 案例中安全性 & 合規性中心中的保留

安全性 & 合規性中心提供的 Windows PowerShell cmdlet，可讓您大量自動化耗時建立及管理 eDiscovery 案例相關的工作。 目前，放置大量上的位置保存 custodian 內容安全性 & 合規性中心使用 eDiscovery 案例工具需要花費時間和準備。 例如，建立保留，您必須先收集 URL 的每個商務用 OneDrive 網站，您想要就地保留。 然後您想要就地保留每位使用者，您必須將他們的信箱和其 OneDrive for Business 網站新增至保留。 在未來版本的安全性 & 合規性中心，這會取得執行的工作變得更容易。 在那之前，您可以使用指令碼本文中，自動執行此程序。
  
指令碼會提示您輸入您的組織我的網站網域的名稱 (例如， **contoso**在 URL 中https://contoso-my.sharepoint.com)、 現有的 eDiscovery 案例，與案例相關聯的新保留名稱的名稱您想要放入使用者的電子郵件地址清單暫留，以及搜尋查詢，以使用如果您想要建立查詢式保留。 指令碼再取得的 OneDrive for Business 網站的清單中的每個使用者的 [URL、 會建立新的保留，並將信箱和 OneDrive for Business 網站的清單中的每個使用者至保留。 指令碼也會產生包含新的保留狀態的相關資訊的記錄檔。 
  
若要完成這項工作的步驟如下：
  
[步驟 1：安裝 SharePoint Online 管理命令介面](#step-1-install-the-sharepoint-online-management-shell)
  
[步驟 2： 產生使用者的清單](#step-2-generate-a-list-of-users)
  
[步驟 3： 執行指令碼，以建立保留並新增使用者](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-begin"></a>開始之前

- 您必須是安全 & 與規範中心和 SharePoint Online 的全域系統管理員在步驟 3 中執行指令碼中 eDiscovery 管理員角色群組的成員。 如需詳細資訊，請參閱[指派 Office 365 安全性 & 合規性中心的 eDiscovery 權限](assign-ediscovery-permissions.md)。
    
- 最大值為 1000 個信箱和 100 個網站可以新增至保留與安全性 & 規範中心的 eDiscovery 案例相關聯。 假設您想要就地保留每個使用者擁有商務用 OneDrive 網站，您可以新增至本文中使用指令碼保留的最大值為 100 個使用者。 
    
- 請務必儲存您在步驟 2 和步驟 3 中指令碼的相同資料夾中建立的使用者清單。 會將執行指令碼比較方便。
    
- 指令碼會將使用者清單新增至現有的案例相關聯的新保留。 請務必執行指令碼之前，會建立您想要關聯與保留的案例。
    
- 指令碼包含最少的錯誤處理。 其主要用途是可快速且輕鬆地讓信箱和商務用 OneDrive 網站上每個使用者的保留。
    
- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步驟 1：安裝 SharePoint Online 管理命令介面

第一個步驟是安裝在 SharePoint Online 管理命令介面，如果尚未安裝在本機電腦上。 您不需要使用命令介面，在此程序，但是您必須安裝，因為它包含您在步驟 3 中執行的指令碼所需的必要條件。 這些必要條件允許指令碼，以與 SharePoint Online 取得 onedrive for Business 網站的 Url 進行通訊。
  
移至[設定 SharePoint Online 管理命令介面的 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)並執行步驟 1 和步驟 2 到您本機電腦上安裝 SharePoint Online 管理命令介面。 

## <a name="step-2-generate-a-list-of-users"></a>步驟 2： 產生使用者的清單

步驟 3 中的指令碼會建立有相關聯的 eDiscovery 案例，與新增信箱和 OneDrive for Business 網站至保留的使用者清單中的保留。 您只可以在文字檔案中，輸入電子郵件地址，或您可以取得電子郵件地址的清單，並將其儲存至檔案 （位於相同的資料夾，您將在步驟 3 中儲存指令碼，以） 的 Windows PowerShell 中執行命令。
  
以下是 PowerShell 命令 （，您使用遠端 PowerShell 連線至 Exchange Online 組織執行） 來取得您組織中的所有使用者之電子郵件地址清單，並將它儲存到文字檔名為 HoldUsers.txt。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

您執行此命令，開啟文字檔案，然後移除包含屬性名稱，標頭之後`PrimarySmtpAddress`。 然後移除您想要新增至保留您在步驟 3 中建立的使用者除外的所有電子郵件地址。 請確定有任何空白資料列之前或之後的電子郵件地址清單。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>步驟 3： 執行指令碼，以建立保留並新增使用者

當您在此步驟中執行指令碼時，它會提示您輸入下列資訊。 請務必執行指令碼之前已準備好此資訊。
  
- **您的使用者認證**-指令碼會使用您的認證來連線至遠端 PowerShell 安全性 & 合規性中心。 它也會使用這些認證來存取 SharePoint Online 取得 OneDrive for Business Url 的使用者清單。
    
- **我的網站網域的名稱**-我的網站網域是包含所有商務用 OneDrive 網站組織中的網域。 例如，如果我的網站網域 URL **https://contoso-my.sharepoint.com**，然後輸入`contoso`當指令碼會提示您輸入我的網站網域的名稱。 
    
- **這種情況的名稱**-現有案例的名稱。 指令碼會建立新的保留與此案例相關聯。
    
- **的保留名稱**-保留會建立指令碼，並將其關聯的指定的大小寫名稱。
    
- **搜尋查詢的查詢式保留**-您可以建立查詢式保留，以便符合指定的搜尋條件的內容會置於保留。 要就地保留所有內容，只要按**Enter**鍵時提示您進行搜尋查詢。 
    
- **是否要開啟保留**-您可以開啟保留之後建立，或您可以建立保留，而不加以啟用指令碼指令碼。 如果您不需要開啟保留的指令碼，您可以將它稍後安全 & 合規性中心內，或藉由執行下列 PowerShell 命令： 
    
  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **使用之使用者的清單的文字檔案名稱**-步驟 2，其中包含要新增至保留的使用者清單的文字檔案的名稱。 如果此檔案位於指令碼的相同資料夾中，只要輸入檔案 (例如，HoldUsers.txt) 的名稱。 如果文字檔案是另一個資料夾中，輸入檔案的完整路徑名稱。
    
您收集了指令碼會提示您輸入的資訊之後，最後一個步驟是執行指令碼，以建立新的保留，並將使用者新增至它。
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `AddUsersToHold.ps1`。
    
  ```powershell
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
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
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. 在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。
    
3. 執行指令碼。例如：
    
      ```powershell
    .\AddUsersToHold.ps1
      ```

4. 輸入指令碼會提示您輸入的資訊。
    
    指令碼連線到安全性 & 合規性中心 PowerShell 中，然後在 eDiscovery 案例中建立新的保留並新增清單中的使用者信箱和商務用 OneDrive。 安全性 & 合規性中心，以檢視新的保留 [ **eDiscovery** ] 頁面上，您可以移至的案例。 
    
指令碼完成之後執行，它會建立下列記錄檔，並將它們儲存到指令碼的所在位置的資料夾。
  
- **LocationsOnHold.txt** -包含信箱和 OneDrive for Business 網站指令碼成功置於保留的的清單。
    
- **LocationsNotOnHold.txt** -包含信箱和 OneDrive for Business 網站的指令碼不就地保留] 的清單。 如果使用者擁有信箱，但不是 OneDrive for Business 網站，使用者會包含清單中的 OneDrive for Business 網站，也未處於保留狀態。
    
- **GetCaseHoldPolicy.txt** -包含新的保留，請建立新的保留之後執行指令碼**Get-caseholdpolicy** cmdlet 的輸出。 此 cmdlet 所傳回的資訊包括的使用者其信箱和商務用 OneDrive 網站已暫留保留和是否啟用或停用保留的清單。 
    
- **GetCaseHoldRule.txt** -包含新的保留，請建立新的保留之後執行指令碼**Get-caseholdrule** cmdlet 的輸出。 此 cmdlet 所傳回的資訊包括搜尋查詢，如果您使用指令碼來建立查詢式保留。 
