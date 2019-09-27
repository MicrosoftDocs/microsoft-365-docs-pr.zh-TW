---
title: 以供疑難排解之 eDiscovery 的常見問題
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 調查、 進行疑難排解並解決 Office 365 電子文件探索中的一般問題。
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207288"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="0541d-103">調查問題、 疑難排解及解決常見問題 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0541d-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="0541d-104">本主題涵蓋基本疑難排解步驟，您可以用來識別並解決期間的 eDiscovery 搜尋或其他位置中的 eDiscovery 程序可能會遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="0541d-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="0541d-105">解決某些這些案例則需要從客戶支援服務 (CSS)。</span><span class="sxs-lookup"><span data-stu-id="0541d-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="0541d-106">資訊，請連絡 CSS 隨附於解決步驟。</span><span class="sxs-lookup"><span data-stu-id="0541d-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="0541d-107">錯誤/問題模稜兩可的位置</span><span class="sxs-lookup"><span data-stu-id="0541d-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="0541d-108">您會收到此錯誤 」 的符合性搜尋包含下列無效的位置`(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"`如果您嘗試要加入使用者的信箱位置來搜尋並沒有使用相同的使用者識別碼，Exchange Online Protection (EOP) 中的重複或衝突物件目錄。</span><span class="sxs-lookup"><span data-stu-id="0541d-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="0541d-109">解決方案</span><span class="sxs-lookup"><span data-stu-id="0541d-109">Resolution</span></span>

<span data-ttu-id="0541d-110">檢查有重複的使用者或通訊群組清單使用相同的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="0541d-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="0541d-111">連線至[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="0541d-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="0541d-112">擷取所有的使用者名稱、 類型執行個體：</span><span class="sxs-lookup"><span data-stu-id="0541d-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="0541d-113">可能是 'useralias@contoso.com' 的輸出</span><span class="sxs-lookup"><span data-stu-id="0541d-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="0541d-114">名稱</span><span class="sxs-lookup"><span data-stu-id="0541d-114">Name</span></span>  |<span data-ttu-id="0541d-115">收件者類型</span><span class="sxs-lookup"><span data-stu-id="0541d-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="0541d-116">別名，使用者</span><span class="sxs-lookup"><span data-stu-id="0541d-116">Alias, User</span></span>     |<span data-ttu-id="0541d-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="0541d-117">MailUser</span></span>         |
> |<span data-ttu-id="0541d-118">別名，使用者</span><span class="sxs-lookup"><span data-stu-id="0541d-118">Alias, User</span></span>     |<span data-ttu-id="0541d-119">使用者</span><span class="sxs-lookup"><span data-stu-id="0541d-119">User</span></span>         |

3. <span data-ttu-id="0541d-120">如果傳回多個使用者，找出並修正衝突的物件。</span><span class="sxs-lookup"><span data-stu-id="0541d-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="0541d-121">在特定位置上失敗，錯誤/此問題： 搜尋</span><span class="sxs-lookup"><span data-stu-id="0541d-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="0541d-122">電子文件探索] 或 [內容搜尋，可能會產生下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="0541d-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="0541d-123">此搜尋完成 （#） 發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="0541d-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="0541d-124">您要重試失敗的位置上的搜尋嗎？</span><span class="sxs-lookup"><span data-stu-id="0541d-124">Would you like to retry the search on the failed locations?</span></span>

![搜尋特定位置失敗錯誤的螢幕擷取畫面]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="0541d-126">解決方案</span><span class="sxs-lookup"><span data-stu-id="0541d-126">Resolution</span></span>

<span data-ttu-id="0541d-127">如果您收到此錯誤，我們建議您驗證失敗，在搜尋] 然後僅在失敗的位置上重新執行搜尋的位置。</span><span class="sxs-lookup"><span data-stu-id="0541d-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="0541d-128">連線至[Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="0541d-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="0541d-129">類型：</span><span class="sxs-lookup"><span data-stu-id="0541d-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="0541d-130">從 PowerShell 輸出，檢視失敗的位置，[錯誤] 欄位中，或是從中從搜尋輸出錯誤的狀態詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0541d-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="0541d-131">重試失敗的位置，以只 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="0541d-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="0541d-132">如果您繼續收到這些錯誤，請參閱[重試失敗位置](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search)的其他疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="0541d-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="0541d-133">找不到的錯誤/此問題： 檔案</span><span class="sxs-lookup"><span data-stu-id="0541d-133">Error/issue file not found</span></span>

<span data-ttu-id="0541d-134">當執行 eDiscovery 搜尋，其中包含 SharePoint Online 和 One Drive For Business 位置，您可能會收到錯誤`File Not Found`雖然該檔案位於網站上。</span><span class="sxs-lookup"><span data-stu-id="0541d-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="0541d-135">這項錯誤會處於 errors.csv 與匯出警告或略過的 items.csv 這可能是因為如果在網站上找不到檔案或索引已過期。</span><span class="sxs-lookup"><span data-stu-id="0541d-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="0541d-136">以下是錯誤的實際，新增的強調文字。</span><span class="sxs-lookup"><span data-stu-id="0541d-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="0541d-137">28.06.2019 10:02:19_FailedToExportItem_Failed 下載內容。</span><span class="sxs-lookup"><span data-stu-id="0541d-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="0541d-138">其他診斷資訊： Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure： 無法從內容類型的文件的 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 下載。</span><span class="sxs-lookup"><span data-stu-id="0541d-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="0541d-139">相互關聯識別碼： 3bd84722-937b-4 c 23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="0541d-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="0541d-140">ServerErrorCode:-2147024894---: > Microsoft.SharePoint.Client.ServerException：***找不到檔案***。</span><span class="sxs-lookup"><span data-stu-id="0541d-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="0541d-141">在 Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream (資料流 responseStream) 在 Microsoft.SharePoint.Client.ClientRequest.ProcessResponse()---: 內部例外堆疊追蹤的結尾-為-</span><span class="sxs-lookup"><span data-stu-id="0541d-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="0541d-142">解決方案</span><span class="sxs-lookup"><span data-stu-id="0541d-142">Resolution</span></span>

1. <span data-ttu-id="0541d-143">請在搜尋]，以確保的位置識別位置該檔案位於正確，以及新增搜尋位置。</span><span class="sxs-lookup"><span data-stu-id="0541d-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="0541d-144">用於程序在[手動要求編目和重新編製索引的網站、 文件庫或清單](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content)重新編製索引的網站。</span><span class="sxs-lookup"><span data-stu-id="0541d-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="0541d-145">錯誤/問題搜尋失敗找不到收件者</span><span class="sxs-lookup"><span data-stu-id="0541d-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="0541d-146">eDiscovery 搜尋失敗，錯誤`recipient not found`。</span><span class="sxs-lookup"><span data-stu-id="0541d-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="0541d-147">如果使用者物件找不到 Exchange Online Protection (EOP) 因為物件已不會同步處理，可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="0541d-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="0541d-148">解決方案</span><span class="sxs-lookup"><span data-stu-id="0541d-148">Resolution</span></span>

1. <span data-ttu-id="0541d-149">連線至[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="0541d-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="0541d-150">請檢查的 user 物件，是否同步處理到 Exchange Online Protection 類型：</span><span class="sxs-lookup"><span data-stu-id="0541d-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="0541d-151">應該要有使用者問題的 mailuser 物件。</span><span class="sxs-lookup"><span data-stu-id="0541d-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="0541d-152">如果會傳回 nothing，調查的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="0541d-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="0541d-153">如果無法同步處理之物件的連絡 CSS。</span><span class="sxs-lookup"><span data-stu-id="0541d-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="0541d-154">匯出搜尋結果的錯誤/問題是很慢</span><span class="sxs-lookup"><span data-stu-id="0541d-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="0541d-155">當從 eDiscovery] 或 [內容搜尋中的安全性與合規性中心匯出搜尋結果，下載花費的時間比預期。</span><span class="sxs-lookup"><span data-stu-id="0541d-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="0541d-156">您可以檢查的資料量来下載，並可能增加匯出速度。</span><span class="sxs-lookup"><span data-stu-id="0541d-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="0541d-157">解決方案</span><span class="sxs-lookup"><span data-stu-id="0541d-157">Resolution</span></span>

1.  <span data-ttu-id="0541d-158">請嘗試使用識別[增加下載速度](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)」 文件中的步驟。</span><span class="sxs-lookup"><span data-stu-id="0541d-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="0541d-159">如果仍有問題，請連接至[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)和類型：</span><span class="sxs-lookup"><span data-stu-id="0541d-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="0541d-160">尋找下載 SearchResults 及 SearchStatistics 參數中的資料量。</span><span class="sxs-lookup"><span data-stu-id="0541d-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="0541d-161">類型：</span><span class="sxs-lookup"><span data-stu-id="0541d-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="0541d-162">在結果] 欄位會尋找已匯出及檢視發生任何錯誤的資料。</span><span class="sxs-lookup"><span data-stu-id="0541d-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="0541d-163">請檢查 trace.log 檔案位在您匯出的內容有任何錯誤的目錄。</span><span class="sxs-lookup"><span data-stu-id="0541d-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="0541d-164">錯誤/此問題: 「 發生內部伺服器錯誤 (500) 」</span><span class="sxs-lookup"><span data-stu-id="0541d-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="0541d-165">當執行 eDiscovery 搜尋，如果搜尋持續失敗，類似於 「 時發生內部伺服器錯誤 (500) 」 的錯誤，您可能需要重新執行搜尋只在特定的信箱位置上。</span><span class="sxs-lookup"><span data-stu-id="0541d-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![內部伺服器錯誤 500 螢幕擷取畫面](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="0541d-167">解決方案</span><span class="sxs-lookup"><span data-stu-id="0541d-167">Resolution</span></span>

1. <span data-ttu-id="0541d-168">搜尋分成較小的搜尋，並再次執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="0541d-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="0541d-169">請嘗試使用較小的日期範圍，或限制搜尋的位置數目。</span><span class="sxs-lookup"><span data-stu-id="0541d-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="0541d-170">連線至[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)和類型：</span><span class="sxs-lookup"><span data-stu-id="0541d-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="0541d-171">檢查結果和錯誤的輸出。</span><span class="sxs-lookup"><span data-stu-id="0541d-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="0541d-172">檢查 trace.log 檔案。</span><span class="sxs-lookup"><span data-stu-id="0541d-172">Examine the trace.log file.</span></span> <span data-ttu-id="0541d-173">它會傳送匯出至的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0541d-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="0541d-174">連絡客戶支援 CSS。</span><span class="sxs-lookup"><span data-stu-id="0541d-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="0541d-175">錯誤/此問題： 保留不同步處理</span><span class="sxs-lookup"><span data-stu-id="0541d-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="0541d-176">eDiscovery 案例保留原則同步處理通訊時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="0541d-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="0541d-177">錯誤會顯示如下：</span><span class="sxs-lookup"><span data-stu-id="0541d-177">The error reads:</span></span>

> <span data-ttu-id="0541d-178">「 資源： 花費的時間超過部署原則預期時間。</span><span class="sxs-lookup"><span data-stu-id="0541d-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="0541d-179">它可能需要其他兩個小時更新的最終的部署狀態，因此請回到 [幾個小時。 」</span><span class="sxs-lookup"><span data-stu-id="0541d-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="0541d-180">解決方案</span><span class="sxs-lookup"><span data-stu-id="0541d-180">Resolution</span></span>

1.  <span data-ttu-id="0541d-181">連線至[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)和類型：</span><span class="sxs-lookup"><span data-stu-id="0541d-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="0541d-182">檢查錯誤如下所示的 Distributiondetail 參數的值：</span><span class="sxs-lookup"><span data-stu-id="0541d-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="0541d-183">如果存在錯誤，請建立升級為 PG 強制手動重新同步處理的原則。</span><span class="sxs-lookup"><span data-stu-id="0541d-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="0541d-184">連絡 CSS。</span><span class="sxs-lookup"><span data-stu-id="0541d-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="0541d-185">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0541d-185">See Also</span></span>
- [<span data-ttu-id="0541d-186">若要避免內容位置錯誤的祕訣</span><span class="sxs-lookup"><span data-stu-id="0541d-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)