---
title: 複製內容搜尋
f1.keywords:
- NOCSH
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
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 腳本，可在 Office 365 或 Microsoft 365 中的規範中心內快速複製現有的內容搜尋。 當您複製搜尋時，會建立新的搜尋（具有新的名稱），該搜尋包含與原始搜尋相同的屬性。 然後，您可以變更關鍵字查詢或日期範圍，以編輯新的搜尋，然後再執行。
ms.openlocfilehash: bba683e7ffbad6177a6214ebb36e3aaece7aada7
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942936"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="cbd40-105">複製內容搜尋</span><span class="sxs-lookup"><span data-stu-id="cbd40-105">Clone a Content Search</span></span>

<span data-ttu-id="cbd40-106">在 Office 365 或 Microsoft 365 中建立「規範中心」的內容搜尋，以搜尋許多信箱或 SharePoint，並 OneDrive 商務網站可能需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="cbd40-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="cbd40-107">如果您錯誤鍵入 URL，也可以指定要搜尋的網站。</span><span class="sxs-lookup"><span data-stu-id="cbd40-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="cbd40-108">為了避免發生這些問題，您可以使用本文中的 Windows PowerShell 腳本，快速複製現有的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="cbd40-109">當您複製搜尋時，會建立新的搜尋（名稱不同），該搜尋包含相同的屬性（例如內容位置和搜尋查詢）作為原始搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-109">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="cbd40-110">然後，您可以變更關鍵字查詢或日期範圍，並執行它，以編輯新的搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-110">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="cbd40-111">為何要複製內容搜尋？</span><span class="sxs-lookup"><span data-stu-id="cbd40-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="cbd40-112">若要比較不同關鍵字搜尋查詢的結果，請在相同的內容位置上執行。</span><span class="sxs-lookup"><span data-stu-id="cbd40-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="cbd40-113">若要讓您在建立新的搜尋時，不必重新輸入大量的內容位置。</span><span class="sxs-lookup"><span data-stu-id="cbd40-113">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="cbd40-114">可減少搜尋結果的大小。</span><span class="sxs-lookup"><span data-stu-id="cbd40-114">To decrease the size of the search results.</span></span> <span data-ttu-id="cbd40-115">例如，如果您有一個搜尋會傳回太多結果以進行匯出，您可以複製搜尋，然後根據日期範圍新增搜尋條件，以減少搜尋結果的數目。</span><span class="sxs-lookup"><span data-stu-id="cbd40-115">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="cbd40-116">開始之前</span><span class="sxs-lookup"><span data-stu-id="cbd40-116">Before you begin</span></span>

- <span data-ttu-id="cbd40-117">您必須是 Security & 合規性中心內 eDiscovery 管理員角色群組的成員，才可執行本主題中所述的腳本。</span><span class="sxs-lookup"><span data-stu-id="cbd40-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="cbd40-118">腳本包含最低的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="cbd40-118">The script includes minimal error handling.</span></span> <span data-ttu-id="cbd40-119">腳本的主要用途是快速複製內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-119">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="cbd40-120">腳本會建立新的內容搜尋，但不會將其啟動。</span><span class="sxs-lookup"><span data-stu-id="cbd40-120">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="cbd40-121">此腳本會考慮您要製作的內容搜尋是否與 eDiscovery 案例相關聯。</span><span class="sxs-lookup"><span data-stu-id="cbd40-121">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="cbd40-122">如果搜尋與案例相關聯，則新的搜尋也會與同一個案例產生關聯。</span><span class="sxs-lookup"><span data-stu-id="cbd40-122">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="cbd40-123">如果現有的搜尋未與案例相關聯，則新的搜尋會列在「規範中心」的 [**內容搜尋**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="cbd40-123">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="cbd40-124">在任何 Microsoft standard support 方案或服務下，都不支援本主題中提供的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="cbd40-124">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="cbd40-125">範例腳本是以不含任何類型擔保的方式提供。</span><span class="sxs-lookup"><span data-stu-id="cbd40-125">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="cbd40-126">Microsoft 進一步否認所有暗示擔保，包括但不限於任何適售性或特定用途適用性的暗示擔保。</span><span class="sxs-lookup"><span data-stu-id="cbd40-126">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="cbd40-127">因使用或效能範例腳本及檔的整體風險，仍然保留給您。</span><span class="sxs-lookup"><span data-stu-id="cbd40-127">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="cbd40-128">在任何事件中，Microsoft、其作者、（包括但不限於使用或無法使用範例腳本或檔的任何損害（包括（但不限於）因使用或無法使用範例腳本或檔而造成的任何損害（包括但不限於公司中斷、商務中斷、商務資訊遺失或其他 pecuniary 遺失）以外的任何損害（包括但不限於）使用或無法使用範例腳本或檔時所產生的任何其他</span><span class="sxs-lookup"><span data-stu-id="cbd40-128">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="cbd40-129">步驟1：執行腳本以複製搜尋</span><span class="sxs-lookup"><span data-stu-id="cbd40-129">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="cbd40-130">此步驟中的腳本會複製現有的內容，以建立新的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-130">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="cbd40-131">當您執行此腳本時，系統會提示您輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="cbd40-131">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="cbd40-132">**您的使用者認證**-腳本會使用您的認證，以 Windows PowerShell 連接至組織的安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="cbd40-132">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="cbd40-133">如先前所述，您必須是 Security & compCompliance Center 中 eDiscovery Manager 角色群組的成員，才能執行該腳本。</span><span class="sxs-lookup"><span data-stu-id="cbd40-133">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="cbd40-134">**現有搜尋的名稱**-這是您要複製的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-134">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="cbd40-135">**將要建立之新搜尋的名稱**（如果您將此值保留空白），腳本會根據您要複製的搜尋名稱，為新的搜尋建立名稱。</span><span class="sxs-lookup"><span data-stu-id="cbd40-135">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="cbd40-136">若要複製搜尋：</span><span class="sxs-lookup"><span data-stu-id="cbd40-136">To clone a search:</span></span>
  
1. <span data-ttu-id="cbd40-137">使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `CloneSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="cbd40-137">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="cbd40-138">開啟 Windows PowerShell，然後移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="cbd40-138">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="cbd40-139">執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="cbd40-139">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="cbd40-140">當系統提示您輸入認證時，請輸入您的電子郵件地址和密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cbd40-140">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="cbd40-141">當腳本提示時，請輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="cbd40-141">Enter following information when prompted by the script.</span></span> <span data-ttu-id="cbd40-142">輸入每一條資訊，然後按**enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="cbd40-142">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="cbd40-143">現有搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="cbd40-143">The name of the existing search.</span></span>
    
    - <span data-ttu-id="cbd40-144">新搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="cbd40-144">The name of the new search.</span></span>
    
    <span data-ttu-id="cbd40-145">腳本會建立新的內容搜尋，但不會將其啟動。</span><span class="sxs-lookup"><span data-stu-id="cbd40-145">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="cbd40-146">這可讓您有機會在下一個步驟中編輯及執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-146">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="cbd40-147">您可以執行**Get-ComplianceSearch**指令程式，或前往規範中心中的 [**內容搜尋**] 或 [ **eDiscovery** ] 頁面，以查看新搜尋的屬性，視新的搜尋是否與案例相關聯而定。</span><span class="sxs-lookup"><span data-stu-id="cbd40-147">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="cbd40-148">步驟2：在規範中心編輯和執行複製的搜尋</span><span class="sxs-lookup"><span data-stu-id="cbd40-148">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="cbd40-149">在您執行腳本以複製現有的內容搜尋之後，下一步是移至規範中心以編輯及執行新的搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-149">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="cbd40-150">如先前所述，您可以變更關鍵字搜尋查詢，並新增或移除搜尋條件，以編輯搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbd40-150">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="cbd40-151">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="cbd40-151">For more information, see:</span></span>
  
- [<span data-ttu-id="cbd40-152">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="cbd40-152">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="cbd40-153">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="cbd40-153">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="cbd40-154">電子文件探索案例</span><span class="sxs-lookup"><span data-stu-id="cbd40-154">eDiscovery cases</span></span>](ediscovery-cases.md)
