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
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 了解如何建立像搜尋及透過 Office 365 中的安全性 & 合規性中心中的 PowerShell 指令碼執行報告的內容搜尋工作自動化。
ms.openlocfilehash: 915ea910eebba8f6f39ceb41d9475769a6403729
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077181"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="4b09b-103">建立、報告及刪除多個內容搜尋</span><span class="sxs-lookup"><span data-stu-id="4b09b-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="4b09b-104">快速建立和報告探索搜尋是通常重要步驟 eDiscovery 與調查時您想要了解基礎的資料，以及豐富性和搜尋的品質。</span><span class="sxs-lookup"><span data-stu-id="4b09b-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="4b09b-105">若要協助您這麼做，安全性 & 合規性中心 PowerShell 會提供一組 cmdlet 來自動化耗時的內容搜尋工作。</span><span class="sxs-lookup"><span data-stu-id="4b09b-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="4b09b-106">這些指令碼提供快速又簡單的方式，來建立搜尋，數目，然後再執行報告可協助您判斷有問題的資料數量的預估的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="4b09b-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="4b09b-107">您也可以使用指令碼以建立不同版本的搜尋來比較每個產生的結果。</span><span class="sxs-lookup"><span data-stu-id="4b09b-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="4b09b-108">這些指令碼可協助您快速且更有效地識別及 cull 您的資料。</span><span class="sxs-lookup"><span data-stu-id="4b09b-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="4b09b-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="4b09b-109">Before you begin</span></span>

- <span data-ttu-id="4b09b-110">您必須是 eDiscovery 管理員角色群組的成員安全 & 與規範中心執行本主題中所述的指令碼。</span><span class="sxs-lookup"><span data-stu-id="4b09b-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="4b09b-111">Onedrive for Business 網站組織可讓您加入至步驟 1 中的 CSV 檔案中收集的 Url 清單，請參閱[建立您組織中的所有 OneDrive 位置清單](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="4b09b-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> 
    
- <span data-ttu-id="4b09b-112">請務必儲存您在本主題的相同資料夾中建立的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="4b09b-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="4b09b-113">會將執行指令碼比較方便。</span><span class="sxs-lookup"><span data-stu-id="4b09b-113">That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="4b09b-114">指令碼包含最少的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="4b09b-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="4b09b-115">其主要目的是要快速地建立、 回報及刪除多個內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="4b09b-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="4b09b-p104">在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="4b09b-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="4b09b-121">步驟 1： 建立 CSV 檔案，其中包含您想要執行搜尋的相關資訊</span><span class="sxs-lookup"><span data-stu-id="4b09b-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="4b09b-122">您在此步驟中建立的逗點分隔的值 (CSV) 檔案包含每個使用者想要搜尋資料列。</span><span class="sxs-lookup"><span data-stu-id="4b09b-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="4b09b-123">您可以搜尋使用者的 Exchange Online 信箱 （其中包含封存信箱，如果已啟用），其 OneDrive for Business 網站。</span><span class="sxs-lookup"><span data-stu-id="4b09b-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="4b09b-124">或者，您可以搜尋只是信箱或商務用 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="4b09b-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="4b09b-125">您也可以在 SharePoint Online 組織中搜尋任何網站。</span><span class="sxs-lookup"><span data-stu-id="4b09b-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="4b09b-126">您在步驟 3 中執行的指令碼會建立 CSV 檔案中的每一列的個別搜尋。</span><span class="sxs-lookup"><span data-stu-id="4b09b-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="4b09b-127">複製並貼入.txt 檔案，使用 [記事本] 中的下列文字。</span><span class="sxs-lookup"><span data-stu-id="4b09b-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="4b09b-128">此檔案儲存至資料夾，在本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="4b09b-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="4b09b-129">您將此資料夾以及儲存其他指令碼。</span><span class="sxs-lookup"><span data-stu-id="4b09b-129">You'll save the other scripts to this folder as well.</span></span>
    
    ```text
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="4b09b-130">在第一列或標題列，該檔案列出**New-compliancesearch** cmdlet （在步驟 3 中的指令碼） 時用來建立新的內容搜尋的參數。</span><span class="sxs-lookup"><span data-stu-id="4b09b-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="4b09b-131">每個參數名稱都是以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="4b09b-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="4b09b-132">請確定標題列中沒有任何空格。</span><span class="sxs-lookup"><span data-stu-id="4b09b-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="4b09b-133">標題列底下的每個資料列代表每個搜尋的參數值。</span><span class="sxs-lookup"><span data-stu-id="4b09b-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="4b09b-134">請務必將 CSV 檔案中的版面配置區資料取代實際資料。</span><span class="sxs-lookup"><span data-stu-id="4b09b-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="4b09b-135">在 Excel 中，開啟.txt 檔案，並再使用下表中的資訊來編輯每個搜尋資訊的檔案。</span><span class="sxs-lookup"><span data-stu-id="4b09b-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="4b09b-136">**參數**</span><span class="sxs-lookup"><span data-stu-id="4b09b-136">**Parameter**</span></span>|<span data-ttu-id="4b09b-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="4b09b-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="4b09b-138">使用者信箱的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="4b09b-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="4b09b-139">使用者的 OneDrive for Business 網站或組織中任何網站的 URL 的 URL。</span><span class="sxs-lookup"><span data-stu-id="4b09b-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="4b09b-140">Onedrive for Business 網站的 url，請使用此格式： ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。</span><span class="sxs-lookup"><span data-stu-id="4b09b-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="4b09b-141">例如，  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>  <br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="4b09b-142">搜尋的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="4b09b-142">The search query for the search.</span></span> <span data-ttu-id="4b09b-143">如需建立搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="4b09b-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>  <br/> |
    | `StartDate` <br/> |<span data-ttu-id="4b09b-144">電子郵件，日期當時或之後的訊息已接收到收件者或寄件者所傳送。</span><span class="sxs-lookup"><span data-stu-id="4b09b-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="4b09b-145">文件在 SharePoint 或 OneDrive for Business 網站的上次修改日期當時或之後的文件。</span><span class="sxs-lookup"><span data-stu-id="4b09b-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="4b09b-146">電子郵件所傳送的日期當天或之前的訊息已傳送的使用者。</span><span class="sxs-lookup"><span data-stu-id="4b09b-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="4b09b-147">文件在 SharePoint 或 OneDrive for Business 網站的上次修改日期當天或之前的文件。</span><span class="sxs-lookup"><span data-stu-id="4b09b-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="4b09b-148">Excel 檔案儲存為 CSV 檔案的資料夾在本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="4b09b-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="4b09b-149">您在步驟 3 中建立的指令碼會建立搜尋，以使用 CSV 檔案中的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b09b-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="4b09b-150">步驟 2︰連線至安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b09b-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="4b09b-151">下一步是連線至安全性 & 貴組織的合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4b09b-151">The next step is to connect to the Security & Compliance Center PowerShell for your organization.</span></span>
  
1. <span data-ttu-id="4b09b-152">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-152">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> <span data-ttu-id="4b09b-153">將檔案儲存至您儲存 CSV 檔案，以在步驟 1 中的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b09b-153">Save the file to the same folder that you saved the CSV file to in Step 1.</span></span>
    
    ```powershell
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="4b09b-154">在您的本機電腦上開啟 Windows PowerShell 移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼。例如：</span><span class="sxs-lookup"><span data-stu-id="4b09b-154">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```powershell
    .\ConnectSCC.ps1
    ```

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="4b09b-155">步驟 3： 執行指令碼，以建立並啟動搜尋</span><span class="sxs-lookup"><span data-stu-id="4b09b-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="4b09b-156">在此步驟中的指令碼會建立每個資料列的個別內容搜尋您在步驟 1 建立的 CSV 檔案中。</span><span class="sxs-lookup"><span data-stu-id="4b09b-156">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="4b09b-157">當您執行此指令碼時，將會提示您輸入兩個值：</span><span class="sxs-lookup"><span data-stu-id="4b09b-157">When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="4b09b-158">**搜尋群組識別碼**此名稱會提供簡單的方法來組織建立 CSV 檔中搜尋。</span><span class="sxs-lookup"><span data-stu-id="4b09b-158">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="4b09b-159">會建立每個搜尋名為具有搜尋群組識別碼，並接著一個數字會附加至搜尋名稱。</span><span class="sxs-lookup"><span data-stu-id="4b09b-159">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="4b09b-160">例如，如果您輸入**ContosoCase**搜尋群組識別碼，然後搜尋名為**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**，等等。</span><span class="sxs-lookup"><span data-stu-id="4b09b-160">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="4b09b-161">請注意，您輸入的名稱是區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="4b09b-161">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="4b09b-162">當您使用步驟 4 和步驟 5 中搜尋群組識別碼時，您必須使用相同的情況下，如同您在建立時。</span><span class="sxs-lookup"><span data-stu-id="4b09b-162">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="4b09b-163">**CSV 檔案**-您在步驟 1 中建立 CSV 檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b09b-163">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="4b09b-164">請務必包含使用完整的檔案名稱，包含.csv 檔案的副檔名;例如， `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-164">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="4b09b-165">若要執行指令碼，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4b09b-165">To run the script:</span></span>

1. <span data-ttu-id="4b09b-166">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `CreateSearches.ps1`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-166">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="4b09b-167">將檔案儲存到您用來儲存其他檔案的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b09b-167">Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="4b09b-168">在 Windows PowerShell 中，移至在前一個步驟中，您儲存指令碼的所在資料夾，然後執行指令碼;例如：</span><span class="sxs-lookup"><span data-stu-id="4b09b-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="4b09b-169">在**搜尋群組識別碼**提示字元處，輸入搜尋群組名稱，然後按下**Enter**。例如， `ContosoCase`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-169">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="4b09b-170">請記住此名稱會區分大小寫，所以您必須先在後續步驟中輸入相同的方式。</span><span class="sxs-lookup"><span data-stu-id="4b09b-170">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="4b09b-171">在**來源 CSV 檔案**提示字元處，輸入 CSV 檔案中，包含.csv 檔案的副檔名; 名稱例如， `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="4b09b-172">按**Enter**以繼續執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="4b09b-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="4b09b-173">指令碼會顯示進度的建立和執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="4b09b-173">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="4b09b-174">指令碼完成時，它會傳回的提示。</span><span class="sxs-lookup"><span data-stu-id="4b09b-174">When the script is complete, it returns to the prompt.</span></span> 
    
    ![執行指令碼以建立多個規範搜尋的範例輸出](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="4b09b-176">步驟 4： 執行指令碼，以報告搜尋估計</span><span class="sxs-lookup"><span data-stu-id="4b09b-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="4b09b-177">建立搜尋之後下, 一步是執行指令碼來顯示簡單的步驟 3 中建立每個搜尋的搜尋點擊數報告。</span><span class="sxs-lookup"><span data-stu-id="4b09b-177">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="4b09b-178">報告也會包含每個搜尋和點擊的總數與總大小的所有搜尋結果的大小。</span><span class="sxs-lookup"><span data-stu-id="4b09b-178">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="4b09b-179">當您執行報告的指令碼時，系統會提示您針對搜尋群組 ID]，然後將 CSV 檔案名稱如果您想要將報告儲存至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="4b09b-179">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="4b09b-180">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `SearchReport.ps1`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-180">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="4b09b-181">將檔案儲存到您用來儲存其他檔案的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b09b-181">Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="4b09b-182">在 Windows PowerShell 中，移至在前一個步驟中，您儲存指令碼的所在資料夾，然後執行指令碼;例如：</span><span class="sxs-lookup"><span data-stu-id="4b09b-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="4b09b-183">在**搜尋群組識別碼**提示字元處，輸入搜尋群組名稱，然後按下**Enter**。例如`ContosoCase`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-183">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="4b09b-184">請記住，這個名稱會區分大小寫，所以您必須先輸入相同的方式一樣當您在步驟 3 中執行指令碼時。</span><span class="sxs-lookup"><span data-stu-id="4b09b-184">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="4b09b-185">**檔案路徑，以儲存到一個 CSV 檔案 （只顯示 [報表保留空白） 報告**系統提示時，請輸入完整的檔名的路徑 （包括.csv 檔案的副檔名） 的檔案名稱，如果您想要將報告儲存至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="4b09b-185">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="4b09b-186">CSV 檔案，包括副檔名為.csv 檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b09b-186">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="4b09b-187">例如，您可以輸入`ContosoCaseReport.csv`若要將它儲存到目前的目錄或您可以輸入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`將它儲存到不同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b09b-187">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="4b09b-188">您也可以將提示顯示報表，但不將它儲存到檔案留白。</span><span class="sxs-lookup"><span data-stu-id="4b09b-188">You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="4b09b-189">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="4b09b-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="4b09b-190">指令碼會顯示進度的建立和執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="4b09b-190">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="4b09b-191">指令碼完成時，會顯示報表。</span><span class="sxs-lookup"><span data-stu-id="4b09b-191">When the script is complete, the report is displayed.</span></span> 
    
    ![執行搜尋報告，以顯示搜尋群組的估計](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="4b09b-193">如果相同的信箱或網站指定為 [搜尋] 群組中的多個搜尋的內容位置，（適用於項目數目與大小總計） 報告中的總結果估計可能包含相同的項目結果。</span><span class="sxs-lookup"><span data-stu-id="4b09b-193">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="4b09b-194">這是因為在相同的電子郵件或文件會被計算一次以上如果它會比對 [搜尋] 群組中的不同搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="4b09b-194">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="4b09b-195">步驟 5： 執行指令碼，以刪除搜尋</span><span class="sxs-lookup"><span data-stu-id="4b09b-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="4b09b-196">您可能建立的搜尋很多，因為此最後一個指令碼只是容易快速刪除您在步驟 3 中建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="4b09b-196">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="4b09b-197">像其他的指令碼，這樣也會提示您輸入搜尋群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="4b09b-197">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="4b09b-198">當您執行此指令碼時，將會刪除所有的搜尋，在 [搜尋名稱搜尋群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="4b09b-198">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="4b09b-199">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `DeleteSearches.ps1`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-199">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="4b09b-200">將檔案儲存到您用來儲存其他檔案的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b09b-200">Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="4b09b-201">在 Windows PowerShell 中，移至在前一個步驟中，您儲存指令碼的所在資料夾，然後執行指令碼;例如：</span><span class="sxs-lookup"><span data-stu-id="4b09b-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="4b09b-202">在**搜尋群組識別碼**提示字元處，輸入您要刪除搜尋的搜尋群組名稱，然後按 [ **Enter**;例如， `ContosoCase`。</span><span class="sxs-lookup"><span data-stu-id="4b09b-202">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="4b09b-203">請記住，這個名稱會區分大小寫，所以您必須先輸入相同的方式一樣當您在步驟 3 中執行指令碼時。</span><span class="sxs-lookup"><span data-stu-id="4b09b-203">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="4b09b-204">指令碼會顯示在刪除每個搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b09b-204">The script displays the name of each search that's deleted.</span></span>
    
    ![執行指令碼，以刪除搜尋群組中的搜尋](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
