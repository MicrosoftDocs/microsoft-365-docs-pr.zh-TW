---
title: 使用腳本將使用者新增至核心 eDiscovery 案例中的保留
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
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: 瞭解如何執行腳本，將商務網站的信箱 & OneDrive 新增至與 Microsoft 365 規範中心內的 eDiscovery 案例相關聯的新保留。
ms.openlocfilehash: 278e8e051165eca906e9b454268068cbbe6aef05
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175572"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>使用腳本將使用者新增至核心 eDiscovery 案例中的保留

安全性 & 合規性中心 PowerShell 提供 Cmdlet，可讓您自動化與建立及管理 eDiscovery 案例相關的耗時工作。 目前，使用安全性 & 合規性中心內的核心 eDiscovery 案例，將大量的保管人內容位置保留在暫止狀態，並準備好。 例如，在您建立保留之前，您必須為想要保留的商務網站收集每個 OneDrive 的 URL。 然後，針對您想要保留的每位使用者，您必須將其信箱和其 OneDrive 的商務網站新增至保留狀態。 您可以使用本文中的腳本來自動化此程式。
  
腳本會提示您組織之「我的網站」網域的名稱 (例如， `contoso` 在 URL 中 https://contoso-my.sharepoint.com) ，現有 eDiscovery 案例的名稱、與案例關聯的新保留名稱、您想要保留之使用者的電子郵件地址清單，以及您想要建立查詢式保留的搜尋查詢。 然後，腳本會為清單中的每位使用者取得商務用網站 OneDrive 的 URL，並建立新的保留，然後針對清單中的每一位使用者，新增信箱及 OneDrive 的商務用網站。 腳本也會產生包含新保留相關資訊的記錄檔。
  
以下是進行這種動作的步驟：
  
[步驟 1：安裝 SharePoint Online 管理命令介面](#step-1-install-the-sharepoint-online-management-shell)
  
[步驟2：產生使用者清單](#step-2-generate-a-list-of-users)
  
[步驟3：執行腳本以建立保留並新增使用者](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>將使用者新增至保留之前

- 您必須是 Security & 合規性中心內的 eDiscovery Manager 角色群組成員，以及 SharePoint Online 系統管理員執行步驟3中的腳本。 如需詳細資訊，請參閱 [在 Office 365 安全性 & 規範中心指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。

- 最多可將1000個信箱和100網站新增至與安全性 & 合規性中心內的 eDiscovery 案例相關聯的保留。 假設您要置於保留狀態的每一位使用者都有商務網站的 OneDrive，您可以使用本文中的腳本，將最多100個使用者新增至保留。

- 請務必將您在步驟2中建立的使用者清單和步驟3中的腳本儲存在相同的資料夾中。 這樣會使執行腳本變得更容易。

- 腳本會將使用者清單新增至與現有案例關聯的新保留。 在執行腳本之前，請確定您要建立保留的大小寫與所建立的專案。

- 本文中的腳本可在連線至安全性 & 合規性中心 PowerShell 及 SharePoint 線上管理命令介面時，支援新式驗證。 如果您是 Microsoft 365 或 Microsoft 365 GCC 組織，您可以將腳本當做-。 如果您是 Office 365 德國組織、Microsoft 365 GCC 高組織或 Microsoft 365 DoD 組織，您必須編輯腳本，以順利執行它。 具體而言，您必須編輯該行 `Connect-IPPSSession` 並使用 *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 參數 (以及組織類型的適當值) 才能連線至安全性 & 規範中心 PowerShell。 如需詳細資訊，請參閱 [Connect To Security & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)中的範例。

- 腳本會自動中斷與安全性 & 合規性中心的連線 PowerShell 和 SharePoint 線上管理命令介面。

- 腳本包含最低的錯誤處理。 其主要用途是快速而輕鬆地將每位使用者的信箱和 OneDrive 用於保留的商務網站。

- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步驟 1：安裝 SharePoint Online 管理命令介面

第一步是安裝本機電腦上的 SharePoint Online 管理命令介面（如果尚未安裝）。 您不需要在此程式中使用命令介面，但必須安裝它，因為它包含您在步驟3中執行之腳本所需的必要條件。 這些必要條件允許腳本與 SharePoint Online 進行通訊，以取得商務網站 OneDrive 的 URLs。
  
移至 [設定 SharePoint 線上管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318) ，並執行步驟1和步驟2，在您的本機電腦上安裝 SharePoint 的線上管理命令介面。

## <a name="step-2-generate-a-list-of-users"></a>步驟2：產生使用者清單

步驟3中的腳本會建立與 eDiscovery 案例相關聯的保留，並新增要保留之使用者清單的信箱和 OneDrive。 您可以只輸入文字檔中的電子郵件地址，也可以在 Windows PowerShell 中執行命令，以取得電子郵件地址的清單，並將其儲存至相同資料夾中的檔案 (，您將在步驟 3) 中儲存腳本。
  
以下是您使用連線至 Exchange Online 組織的遠端 PowerShell 所執行的 PowerShell 命令 () 以取得組織中所有使用者的電子郵件地址清單，並將其儲存至名為 HoldUsers.txt 的文字檔。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

在您執行此命令之後，請開啟文字檔，並移除包含屬性名稱的標頭  `PrimarySmtpAddress` 。 然後針對您想要新增至您在步驟3中建立之保留的使用者，移除所有的電子郵件地址。 請確定電子郵件地址清單前面或後面沒有任何空白列。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>步驟3：執行腳本以建立保留並新增使用者

當您在此步驟中執行腳本時，它會提示您輸入下列資訊。 在執行腳本之前，請務必準備好此資訊。
  
- **您的使用者認證：** 腳本會使用您的認證，以使用 PowerShell 與安全性 & 合規性中心相連。 它也會使用這些認證來存取 SharePoint 線上，以取得使用者清單的商務用 OneDrive URLs。

- **SharePoint 網域的名稱：** 腳本會提示您輸入此名稱，以便連接至 SharePoint 系統管理中心。 它也會在您的組織中使用 OneDrive URLs 的功能變數名稱。 例如，如果系統管理中心的 URL 是 `https://contoso-admin.sharepoint.com` 和 OneDrive 的 url `https://contoso-my.sharepoint.com` ，則 `contoso` 當腳本提示您輸入功能變數名稱時，就會輸入該 url。

- **案例名稱：** 現有案例的名稱。 此腳本會建立與此案例相關聯的新保留。

- **保留的名稱：** 腳本將要建立並與指定之案例產生關聯的保留名稱。

- **查詢型保留的搜尋查詢：** 您可以建立以查詢為基礎的保留，使只保留符合指定之搜尋準則的內容。 若要將所有內容保留，只要在提示搜尋查詢時按下 **enter** 鍵。

- **開啟暫止狀態：** 您可以讓腳本在建立保留後將其開啟，也可以讓腳本建立保留，但不加以啟用。 如果您未啟用 [保留] 的腳本，您可以稍後在安全性 & 合規性中心或執行下列 PowerShell 命令進行開啟：

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **具有使用者清單之文字檔的名稱** -步驟2中包含要新增至保留之使用者清單的文字檔名稱。 如果此檔案與腳本位於相同的資料夾中，只要輸入檔案名 (例如，HoldUsers.txt) 。 如果文字檔位於另一個資料夾中，請輸入完整的檔案名。

在您收集腳本將會提示您的資訊後，最後一步是執行腳本以建立新的保留，並新增使用者。
  
1. 使用檔案名尾碼，將下列文字儲存至 Windows PowerShell 腳本檔案 `.ps1` 。 例如，`AddUsersToHold.ps1`。

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. 在您的本機電腦上，開啟 [Windows PowerShell]，然後移至您用來儲存腳本的資料夾。

3. 執行腳本;例如：

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. 輸入腳本提示您的資訊。

   腳本會連線至安全性 & 合規性中心 PowerShell，然後在 eDiscovery 案例中建立新的保留，然後在清單中為使用者新增信箱和 OneDrive。 您可以移至安全性 & 合規性中心的 [ **eDiscovery** ] 頁面上的案例，以查看新的保留。

在腳本執行完畢後，它會建立下列記錄檔，並將其儲存至腳本所在的資料夾。
  
- **LocationsOnHold.txt：** 包含腳本成功放置之商務網站的信箱和 OneDrive 清單。

- **LocationsNotOnHold.txt：** 包含未保留腳本之商務網站的信箱和 OneDrive 清單。 如果使用者有信箱，但不是商務網站的 OneDrive，該使用者將會包含在未保留之商務網站的 OneDrive 清單中。

- **GetCaseHoldPolicy.txt：** 包含新保留的 **Get-CaseHoldPolicy** Cmdlet 的輸出，腳本會在建立新的保留後執行。 此指令程式傳回的資訊包含使用者清單，以及其信箱和 OneDrive 商務網站保留，以及是否已啟用或停用保留。 

- **GetCaseHoldRule.txt：** 包含新保留的 **Get-CaseHoldRule** Cmdlet 的輸出，腳本會在建立新的保留後執行。 如果您使用腳本來建立查詢型保留，則此 Cmdlet 傳回的資訊會包含搜尋查詢。
