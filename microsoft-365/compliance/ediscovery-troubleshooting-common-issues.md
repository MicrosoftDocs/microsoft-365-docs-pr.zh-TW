---
title: 疑難排解常見問題的 eDiscovery
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
description: 調查、 進行疑難排解及解決在 Office 365 電子文件探索中常見的問題。
siblings_only: true
ms.openlocfilehash: 0d411976ecf6adba9df1f75eb8a45409647b3e1a
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378635"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="9de71-103">調查、 進行疑難排解及解決常見問題 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9de71-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="9de71-104">本主題涵蓋基本疑難排解步驟，您可以用來識別並解決期間的 eDiscovery 搜尋或其他位置中的 eDiscovery 程序可能會遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="9de71-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="9de71-105">解決某些這些案例需要 Microsoft 支援服務說明。</span><span class="sxs-lookup"><span data-stu-id="9de71-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="9de71-106">資訊，請連絡 Microsoft 支援服務隨附於解決步驟。</span><span class="sxs-lookup"><span data-stu-id="9de71-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="9de71-107">錯誤/問題： 模稜兩可的位置</span><span class="sxs-lookup"><span data-stu-id="9de71-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="9de71-108">如果您嘗試新增至搜尋使用者的信箱位置，且沒有重複或衝突物件具有相同的使用者識別碼，Exchange Online Protection (EOP) 目錄中，您會收到此錯誤： `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`。</span><span class="sxs-lookup"><span data-stu-id="9de71-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you will receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span> 

### <a name="resolution"></a><span data-ttu-id="9de71-109">解決方案</span><span class="sxs-lookup"><span data-stu-id="9de71-109">Resolution</span></span>

<span data-ttu-id="9de71-110">檢查有重複的使用者或通訊群組清單使用相同的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="9de71-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="9de71-111">連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9de71-111">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="9de71-112">擷取所有的使用者名稱、 類型執行個體：</span><span class="sxs-lookup"><span data-stu-id="9de71-112">Retrieve all instances of the username, type:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

<span data-ttu-id="9de71-113">'Useralias@contoso.com' 的輸出可能類似下列：</span><span class="sxs-lookup"><span data-stu-id="9de71-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

> 
> |<span data-ttu-id="9de71-114">名稱</span><span class="sxs-lookup"><span data-stu-id="9de71-114">Name</span></span>  |<span data-ttu-id="9de71-115">收件者類型</span><span class="sxs-lookup"><span data-stu-id="9de71-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="9de71-116">別名，使用者</span><span class="sxs-lookup"><span data-stu-id="9de71-116">Alias, User</span></span>     |<span data-ttu-id="9de71-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="9de71-117">MailUser</span></span>         |
> |<span data-ttu-id="9de71-118">別名，使用者</span><span class="sxs-lookup"><span data-stu-id="9de71-118">Alias, User</span></span>     |<span data-ttu-id="9de71-119">使用者</span><span class="sxs-lookup"><span data-stu-id="9de71-119">User</span></span>         |

3. <span data-ttu-id="9de71-120">如果傳回多個使用者，找出並修正衝突的物件。</span><span class="sxs-lookup"><span data-stu-id="9de71-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="9de71-121">在特定位置上的錯誤/問題： 搜尋失敗</span><span class="sxs-lookup"><span data-stu-id="9de71-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="9de71-122">電子文件探索] 或 [內容搜尋，可能會產生下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="9de71-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="9de71-123">此搜尋完成 （#） 發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="9de71-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="9de71-124">您要重試失敗的位置上的搜尋嗎？</span><span class="sxs-lookup"><span data-stu-id="9de71-124">Would you like to retry the search on the failed locations?</span></span>

![搜尋特定位置失敗錯誤的螢幕擷取畫面]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="9de71-126">解決方案</span><span class="sxs-lookup"><span data-stu-id="9de71-126">Resolution</span></span>

<span data-ttu-id="9de71-127">如果您收到此錯誤，我們建議您驗證失敗，在搜尋] 的位置然後重新執行搜尋] 只有在失敗的位置上。</span><span class="sxs-lookup"><span data-stu-id="9de71-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="9de71-128">連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9de71-128">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. <span data-ttu-id="9de71-129">從 PowerShell 輸出，檢視失敗的位置，[錯誤] 欄位中，或是從中從搜尋輸出錯誤的狀態詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9de71-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="9de71-130">重試失敗的位置，以只 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="9de71-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="9de71-131">如果您繼續收到這些錯誤，請參閱[重試失敗位置](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search)的更多疑難排解的步驟。</span><span class="sxs-lookup"><span data-stu-id="9de71-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="9de71-132">錯誤/問題： 找不到檔案</span><span class="sxs-lookup"><span data-stu-id="9de71-132">Error/issue: File not found</span></span>

<span data-ttu-id="9de71-133">當執行 eDiscovery 搜尋，其中包含 SharePoint Online 和 One Drive For Business 位置，您可能會收到錯誤`File Not Found`雖然該檔案位於網站上。</span><span class="sxs-lookup"><span data-stu-id="9de71-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="9de71-134">此錯誤會處於 errors.csv 與匯出警告或略過 items.csv。</span><span class="sxs-lookup"><span data-stu-id="9de71-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="9de71-135">如果在網站上找不到檔案或索引已過期，這可能會發生。</span><span class="sxs-lookup"><span data-stu-id="9de71-135">This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="9de71-136">以下是錯誤的實際，新增的強調文字。</span><span class="sxs-lookup"><span data-stu-id="9de71-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="9de71-137">28.06.2019 10:02:19_FailedToExportItem_Failed 下載內容。</span><span class="sxs-lookup"><span data-stu-id="9de71-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="9de71-138">其他診斷資訊： Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure： 無法從內容類型的文件的 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 下載。</span><span class="sxs-lookup"><span data-stu-id="9de71-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="9de71-139">相互關聯識別碼： 3bd84722-937b-4 c 23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="9de71-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="9de71-140">ServerErrorCode:-2147024894---: > Microsoft.SharePoint.Client.ServerException：***找不到檔案***。</span><span class="sxs-lookup"><span data-stu-id="9de71-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="9de71-141">在 Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream (資料流 responseStream) 在 Microsoft.SharePoint.Client.ClientRequest.ProcessResponse()---: 內部例外堆疊追蹤的結尾-為-</span><span class="sxs-lookup"><span data-stu-id="9de71-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="9de71-142">解決方案</span><span class="sxs-lookup"><span data-stu-id="9de71-142">Resolution</span></span>

1. <span data-ttu-id="9de71-143">請在搜尋]，以確保的位置識別位置該檔案位於正確，以及新增搜尋位置。</span><span class="sxs-lookup"><span data-stu-id="9de71-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="9de71-144">用於程序在[手動要求編目和重新編製索引的網站、 文件庫或清單](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content)重新編製索引的網站。</span><span class="sxs-lookup"><span data-stu-id="9de71-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="9de71-145">錯誤/問題： 搜尋失敗，因為找不到收件者</span><span class="sxs-lookup"><span data-stu-id="9de71-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="9de71-146">EDiscovery 搜尋失敗，錯誤`recipient not found`。</span><span class="sxs-lookup"><span data-stu-id="9de71-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="9de71-147">如果使用者物件找不到 Exchange Online Protection (EOP) 因為物件已不會同步處理，可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="9de71-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="9de71-148">解決方案</span><span class="sxs-lookup"><span data-stu-id="9de71-148">Resolution</span></span>

1. <span data-ttu-id="9de71-149">連線至[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9de71-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="9de71-150">請檢查的 user 物件，是否同步處理到 Exchange Online Protection 類型：</span><span class="sxs-lookup"><span data-stu-id="9de71-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. <span data-ttu-id="9de71-151">應該要有使用者問題的郵件使用者物件。</span><span class="sxs-lookup"><span data-stu-id="9de71-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="9de71-152">如果會傳回 nothing，調查的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="9de71-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="9de71-153">如果無法同步處理物件，請連絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="9de71-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="9de71-154">錯誤/問題： 匯出搜尋結果緩慢</span><span class="sxs-lookup"><span data-stu-id="9de71-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="9de71-155">當從 eDiscovery] 或 [內容搜尋中的安全性與合規性中心匯出搜尋結果，下載花費的時間比預期。</span><span class="sxs-lookup"><span data-stu-id="9de71-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="9de71-156">您可以檢查的資料量来下載，並可能增加匯出速度。</span><span class="sxs-lookup"><span data-stu-id="9de71-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="9de71-157">解決方案</span><span class="sxs-lookup"><span data-stu-id="9de71-157">Resolution</span></span>

1.  <span data-ttu-id="9de71-158">請嘗試使用識別[增加下載速度](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)」 文件中的步驟。</span><span class="sxs-lookup"><span data-stu-id="9de71-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2.  <span data-ttu-id="9de71-159">如果仍有問題，連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9de71-159">If you still have issues, connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. <span data-ttu-id="9de71-160">尋找下載 SearchResults 及 SearchStatistics 參數中的資料量。</span><span class="sxs-lookup"><span data-stu-id="9de71-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

5. <span data-ttu-id="9de71-161">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9de71-161">Enter the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. <span data-ttu-id="9de71-162">在 [結果] 欄位中，尋找已匯出的資料，並檢視任何發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="9de71-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

7. <span data-ttu-id="9de71-163">請檢查 trace.log 檔案位在您匯出的內容有任何錯誤的目錄。</span><span class="sxs-lookup"><span data-stu-id="9de71-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="9de71-164">錯誤/問題: 「 發生內部伺服器錯誤 (500) 」</span><span class="sxs-lookup"><span data-stu-id="9de71-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="9de71-165">當執行 eDiscovery 搜尋，如果搜尋持續失敗，類似於 「 時發生內部伺服器錯誤 (500) 」 的錯誤，可能需要重新執行只能在特定信箱的位置上的搜尋。</span><span class="sxs-lookup"><span data-stu-id="9de71-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![內部伺服器錯誤 500 螢幕擷取畫面](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="9de71-167">解決方案</span><span class="sxs-lookup"><span data-stu-id="9de71-167">Resolution</span></span>

1. <span data-ttu-id="9de71-168">搜尋分成較小的搜尋，並再次執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="9de71-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="9de71-169">請嘗試使用較小的日期範圍，或限制搜尋的位置數目。</span><span class="sxs-lookup"><span data-stu-id="9de71-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="9de71-170">連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9de71-170">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

3. <span data-ttu-id="9de71-171">檢查結果和錯誤的輸出。</span><span class="sxs-lookup"><span data-stu-id="9de71-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="9de71-172">檢查 trace.log 檔案。</span><span class="sxs-lookup"><span data-stu-id="9de71-172">Examine the trace.log file.</span></span> <span data-ttu-id="9de71-173">它會傳送匯出至的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="9de71-173">It will be in the same folder that you sent the export to.</span></span>

5. <span data-ttu-id="9de71-174">連絡 Microsoft 支援人員。</span><span class="sxs-lookup"><span data-stu-id="9de71-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="9de71-175">保留不同步處理錯誤/問題：</span><span class="sxs-lookup"><span data-stu-id="9de71-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="9de71-176">eDiscovery 案例保留原則同步處理通訊時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="9de71-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="9de71-177">錯誤會顯示如下：</span><span class="sxs-lookup"><span data-stu-id="9de71-177">The error reads:</span></span>

> <span data-ttu-id="9de71-178">「 資源： 花費的時間超過部署原則預期時間。</span><span class="sxs-lookup"><span data-stu-id="9de71-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="9de71-179">它可能需要其他兩個小時更新的最終的部署狀態，因此請回到 [幾個小時。 」</span><span class="sxs-lookup"><span data-stu-id="9de71-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="9de71-180">解決方案</span><span class="sxs-lookup"><span data-stu-id="9de71-180">Resolution</span></span>

1.  <span data-ttu-id="9de71-181">連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9de71-181">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then enter the following command:</span></span>

    ```powershell
    Get-RetentionCompliancePolicy  <policyname> - DistributionDetail | FL
    ```

2. <span data-ttu-id="9de71-182">檢查錯誤如下所示的 DistributionDetail 參數的值：</span><span class="sxs-lookup"><span data-stu-id="9de71-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="9de71-183">如果存在錯誤，請建立升級為 PG 強制手動重新同步處理的原則。</span><span class="sxs-lookup"><span data-stu-id="9de71-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="9de71-184">連絡 Microsoft 支援人員。</span><span class="sxs-lookup"><span data-stu-id="9de71-184">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="9de71-185">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9de71-185">See Also</span></span>

- [<span data-ttu-id="9de71-186">若要避免內容位置錯誤的祕訣</span><span class="sxs-lookup"><span data-stu-id="9de71-186">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)