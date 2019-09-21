---
title: 使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 本文中使用內容搜尋和指令碼來搜尋信箱與 OneDrive for Business 網站的使用者群組。
ms.openlocfilehash: 9c8de90f8d2faee73ba269466f90478bc72b708e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077544"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="9ed4b-103">使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單</span><span class="sxs-lookup"><span data-stu-id="9ed4b-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="9ed4b-104">安全性 & 合規性中心提供數個 Windows PowerShell cmdlet，可讓您自動化耗時的 eDiscovery 相關工作。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="9ed4b-105">目前，安全性 & 規範中心來搜尋大量 custodian 內容位置中建立內容搜尋需要花費時間和準備。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="9ed4b-106">建立搜尋，您必須先收集每個 onedrive for Business 網站的 URL，然後新增每個信箱和 OneDrive for Business 網站搜尋。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="9ed4b-107">在未來版本中，這會比較容易安全 & 與規範中心執行動作。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="9ed4b-108">在那之前，您可以使用指令碼本文中，自動執行此程序。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="9ed4b-109">此指令碼會提示您輸入您的組織我的網站網域的名稱 (例如， **contoso**在 URL 中https://contoso-my.sharepoint.com)，清單中的使用者電子郵件地址，新的內容搜尋，以及搜尋查詢使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="9ed4b-110">指令碼取得 OneDrive for Business URL 在清單中，每位使用者，然後它會建立並啟動 「 內容搜尋 」 來搜尋信箱和 OneDrive for Business 網站的清單中，每位使用者使用您提供搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="9ed4b-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="9ed4b-111">Before you begin</span></span>

- <span data-ttu-id="9ed4b-112">您必須是安全 & 與規範中心和 SharePoint Online 的全域系統管理員在步驟 3 中執行指令碼中 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="9ed4b-113">請務必儲存您在步驟 2 和步驟 3 中指令碼的相同資料夾中建立的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="9ed4b-114">會將執行指令碼比較方便。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-114">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="9ed4b-115">指令碼包含最少的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-115">The script includes minimal error handling.</span></span> <span data-ttu-id="9ed4b-116">它的主要目的是要快速且輕鬆地搜尋的信箱和 OneDrive for Business 網站的每位使用者。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-116">It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="9ed4b-117">本主題所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-117">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="9ed4b-118">IS 提供的範例指令碼沒有任何形式之擔保。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-118">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="9ed4b-119">Microsoft 進一步不作任何所有我[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied 擔保包括，但不限於任何默示擔保售或適合特定用途。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-119">Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="9ed4b-120">與您保持承擔使用或效能的範例指令碼和文件的風險。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-120">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="9ed4b-121">事件無法在 Microsoft、 其作者，或任何其他參與建立、 實際執行環境或傳遞的指令碼的人對於而概之任何損害皆不 （包括，但不限於遺失的商務利益、 業務中斷、 遺失的損害嗎商業資訊或其他金錢遺失） 即使 Microsoft 已被告知賠償的可能性，承擔使用或無法使用的範例指令碼或文件。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-121">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="9ed4b-122">步驟 1：安裝 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="9ed4b-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="9ed4b-123">第一個步驟是安裝在 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="9ed4b-124">您不需要使用命令介面，在此程序，但是您必須安裝，因為它包含您在步驟 3 中執行的指令碼所需的必要條件。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="9ed4b-125">這些必要條件允許指令碼，以與 SharePoint Online 取得 onedrive for Business 網站的 Url 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="9ed4b-126">移至[設定 SharePoint Online 管理命令介面的 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)並執行步驟 1 和步驟 2，以安裝 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="9ed4b-127">步驟 2： 產生使用者的清單</span><span class="sxs-lookup"><span data-stu-id="9ed4b-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="9ed4b-128">步驟 3 中的指令碼會建立內容搜尋來搜尋信箱和 OneDrive 帳戶的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="9ed4b-129">您只可以在文字檔案中，輸入電子郵件地址，或您可以取得電子郵件地址的清單，並將其儲存至檔案 （位於相同的資料夾，您將在步驟 3 中儲存指令碼，以） 的 Windows PowerShell 中執行命令。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="9ed4b-130">以下是[Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令，您可以取得組織中的所有使用者的電子郵件地址清單，並將它儲存到文字檔，命名為 runt `Users.txt`。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-130">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="9ed4b-131">您執行此命令後，請務必要開啟的檔案，並移除標頭包含屬性名稱， `PrimarySmtpAddress`。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="9ed4b-132">電子郵件地址的清單，並無其他內容，應該只包含文字檔案。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="9ed4b-133">請確定有任何空白資料列之前或之後的電子郵件地址清單。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="9ed4b-134">步驟 3： 執行指令碼，以建立並啟動搜尋</span><span class="sxs-lookup"><span data-stu-id="9ed4b-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="9ed4b-135">當您在此步驟中執行指令碼時，它會提示您輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="9ed4b-136">請務必執行指令碼之前已準備好此資訊。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="9ed4b-137">**您的使用者認證**-指令碼會使用您的認證來存取 SharePoint Online 取得 OneDrive for Business Url，並連線至遠端 PowerShell 安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="9ed4b-138">**我的網站網域的名稱**-我的網站網域是包含所有商務用 OneDrive 網站組織中的網域。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="9ed4b-139">例如，如果我的網站網域 URL **https://contoso-my.sharepoint.com**，然後輸入`contoso`當指令碼會提示您輸入我的網站網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="9ed4b-140">**步驟 2 的文字檔案的路徑名稱**-您在步驟 2 中建立文字檔案的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="9ed4b-141">如果文字檔案和指令碼位於相同的資料夾，然後輸入的文字檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="9ed4b-142">否則，輸入的文字檔案的完整路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="9ed4b-143">**內容搜尋的名稱**-將指令碼所建立的內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="9ed4b-144">建立並執行**搜尋查詢**將用於使用內容搜尋的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="9ed4b-145">如需搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="9ed4b-146">**若要執行指令碼：**</span><span class="sxs-lookup"><span data-stu-id="9ed4b-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="9ed4b-147">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `SearchEXOOD4B.ps1`。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="9ed4b-148">將檔案儲存在步驟 2 中儲存的使用者清單所在的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```
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
  # To install, go to http://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
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

2. <span data-ttu-id="9ed4b-149">開啟 Windows PowerShell，並移至您儲存指令碼和使用者清單，從步驟 2 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="9ed4b-150">啟動指令碼。例如：</span><span class="sxs-lookup"><span data-stu-id="9ed4b-150">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="9ed4b-151">當系統提示提供認證，請輸入您的電子郵件地址和密碼，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="9ed4b-152">輸入下列資訊時提示指令碼。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="9ed4b-153">輸入每一項資訊，然後按**Enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="9ed4b-154">我的網站網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="9ed4b-155">包含使用者清單的文字檔案路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="9ed4b-156">內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="9ed4b-157">搜尋查詢 （離開此空白若要傳回的內容位置中的所有項目）。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="9ed4b-158">指令碼取得每個 onedrive for Business 網站的 Url，然後建立並啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="9ed4b-159">您可以執行**Get-compliancesearch** cmdlet 中的安全性 & 合規性中心 PowerShell 來顯示搜尋統計資料和結果，或您可以移至安全性 & 合規性中心，以檢視資訊中的 [**內容搜尋**] 頁面上關於搜尋。</span><span class="sxs-lookup"><span data-stu-id="9ed4b-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span> 
