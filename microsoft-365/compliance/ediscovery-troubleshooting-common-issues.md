---
title: 疑難排解常見的 eDiscovery 問題
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解您可以採取的基本疑難排解步驟，以解決 Office 365 eDiscovery 中的常見問題。
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a867ed2e55c73fe4bbd890273d78cf57f4bfbd2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926543"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="fc4d0-103">調查、疑難排解及解決常見的 eDiscovery 問題</span><span class="sxs-lookup"><span data-stu-id="fc4d0-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="fc4d0-104">本主題涵蓋您可以採取的基本疑難排解步驟，用來識別及解決 ediscovery 搜尋期間或 eDiscovery 程式中其他位置可能會遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="fc4d0-105">解決這些案例中的部分需要 Microsoft 支援人員的協助。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="fc4d0-106">解決步驟中包含有關何時聯繫 Microsoft 支援的資訊。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="fc4d0-107">錯誤/問題：不明確的位置</span><span class="sxs-lookup"><span data-stu-id="fc4d0-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="fc4d0-108">如果您嘗試將使用者的信箱位置新增至搜尋中，且在 Exchange Online Protection (EOP) 目錄中有相同 userID 的重複或衝突物件，您會收到此錯誤： `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` 。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="fc4d0-109">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-109">Resolution</span></span>

<span data-ttu-id="fc4d0-110">檢查是否有相同使用者識別碼的重複使用者或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="fc4d0-111">連線至 [安全性 & 規範中心] PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="fc4d0-112">執行下列命令，以取回使用者名稱的所有實例：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="fc4d0-113">' Useralias@contoso.com ' 的輸出類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="fc4d0-114">姓名</span><span class="sxs-lookup"><span data-stu-id="fc4d0-114">Name</span></span>|<span data-ttu-id="fc4d0-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="fc4d0-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="fc4d0-116">Alias、User</span><span class="sxs-lookup"><span data-stu-id="fc4d0-116">Alias, User</span></span>|<span data-ttu-id="fc4d0-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="fc4d0-117">MailUser</span></span>|
   > |<span data-ttu-id="fc4d0-118">Alias、User</span><span class="sxs-lookup"><span data-stu-id="fc4d0-118">Alias, User</span></span>|<span data-ttu-id="fc4d0-119">使用者</span><span class="sxs-lookup"><span data-stu-id="fc4d0-119">User</span></span>|

3. <span data-ttu-id="fc4d0-120">若傳回多個使用者，請找出並修正衝突的物件。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="fc4d0-121">錯誤/問題：搜尋在特定位置失敗</span><span class="sxs-lookup"><span data-stu-id="fc4d0-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="fc4d0-122">EDiscovery 或內容搜尋可能會產生下列錯誤： `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="fc4d0-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![搜尋特定位置未通過錯誤螢幕擷取畫面](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="fc4d0-124">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-124">Resolution</span></span>

<span data-ttu-id="fc4d0-125">如果您收到此錯誤，建議您確認在搜尋中失敗的位置，然後在失敗的位置上只重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="fc4d0-126">連線至 [安全性 & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="fc4d0-127">從 PowerShell 輸出的錯誤欄位中，或從搜尋輸出錯誤中的狀態詳細資料中，查看失敗的位置。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="fc4d0-128">只重試失敗位置上的 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="fc4d0-129">如果您繼續收到這些錯誤，請參閱 [重試失敗位置](/Office365/SecurityCompliance/retry-failed-content-search) ，以取得更多疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="fc4d0-130">錯誤/問題：找不到檔案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-130">Error/issue: File not found</span></span>

<span data-ttu-id="fc4d0-131">當執行的 eDiscovery 搜尋包含 SharePoint 線上及一個用於商務位置的硬碟磁碟機時，您可能會收到錯誤， `File Not Found` 但檔案位於網站上。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="fc4d0-132">此錯誤會出現在 [匯出警告] 和 [errors.csv 或略過 items.csv 中。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="fc4d0-133">如果無法在網站上找到檔案，或索引已過期，就可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="fc4d0-134">以下是具有強調新增) 之實際錯誤 (的文字。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="fc4d0-135">28.06.2019 10：02：19_FailedToExportItem_Failed 下載內容。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="fc4d0-136">其他診斷資訊： ContentDownloadTemporaryFailure：無法從 content 6ea52149 ExportWorker-91cd-4965-b5bb-82ca6a3ec9be-類型的檔。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="fc4d0-137">相關識別碼：3bd84722-937b-4c23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="fc4d0-138">ServerErrorCode：-2147024894---Microsoft.SharePoint > ***未找到*** ServerException： File。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="fc4d0-139">在 responseStream Microsoft.SharePoint ProcessResponseStream (Stream) at Microsoft.SharePoint ClientRequest ProcessResponse () ---內部例外狀況堆疊追蹤的結尾---</span><span class="sxs-lookup"><span data-stu-id="fc4d0-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="fc4d0-140">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-140">Resolution</span></span>

1. <span data-ttu-id="fc4d0-141">檢查搜尋中識別的位置，以確保檔案的位置正確，並新增至搜尋位置。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="fc4d0-142">您可以使用程式 [，以手動方式要求編目及重新建立網站、文件庫或清單的索引，以重新索引](/sharepoint/crawl-site-content) 網站。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="fc4d0-143">錯誤/問題：搜尋失敗，因為找不到收件者</span><span class="sxs-lookup"><span data-stu-id="fc4d0-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="fc4d0-144">EDiscovery 搜尋失敗，錯誤為 `recipient not found` 。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="fc4d0-145">如果無法在 Exchange Online Protection (EOP) 中找到使用者物件，因為物件尚未同步處理，可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="fc4d0-146">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-146">Resolution</span></span>

1. <span data-ttu-id="fc4d0-147">連接至 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-147">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="fc4d0-148">執行下列命令，檢查使用者是否已同步處理至 Exchange Online Protection：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="fc4d0-149">使用者提出問題時，應該會有郵件使用者物件。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="fc4d0-150">若未傳回任何專案，請調查 user 物件。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="fc4d0-151">如果物件無法同步處理，請與 Microsoft 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="fc4d0-152">錯誤/問題：匯出搜尋結果的速度緩慢</span><span class="sxs-lookup"><span data-stu-id="fc4d0-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="fc4d0-153">在安全性與合規性中心匯出搜尋結果從 eDiscovery 或內容搜尋時，下載時間會比預期更長。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="fc4d0-154">您可以查看要下載的資料量，並可能增加匯出速度。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="fc4d0-155">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-155">Resolution</span></span>

1. <span data-ttu-id="fc4d0-156">連線至 [安全性 & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-156">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="fc4d0-157">在 SearchResults 和 SearchStatistics 參數中尋找要下載的資料量。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="fc4d0-158">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="fc4d0-159">在 [結果] 欄位中，尋找已匯出的資料，並查看任何發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="fc4d0-160">檢查您將內容匯出到的目錄中的追蹤 .log 檔案，以查看是否有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="fc4d0-161">如果仍有問題，請考慮將傳回一組大型結果的搜尋分割成較小的搜尋。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="fc4d0-162">例如，您可以在搜尋查詢中使用日期範圍，以傳回較小的結果集，可更快速地下載。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="fc4d0-163">錯誤/問題：「發生內部伺服器錯誤 (500) </span><span class="sxs-lookup"><span data-stu-id="fc4d0-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="fc4d0-164">執行 eDiscovery 搜尋時，如果搜尋持續失敗，且發生錯誤類似「發生內部伺服器錯誤 (500) 」，您可能需要在特定信箱位置上只重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![內部伺服器錯誤500螢幕擷取畫面](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="fc4d0-166">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-166">Resolution</span></span>

1. <span data-ttu-id="fc4d0-167">將搜尋分割成較小的搜尋，然後再次執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="fc4d0-168">請嘗試使用較小的日期範圍或限制要搜尋的位置數目。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="fc4d0-169">連線至 [安全性 & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="fc4d0-170">檢查結果和錯誤的輸出。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="fc4d0-171">檢查追蹤 .log 檔。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-171">Examine the trace.log file.</span></span> <span data-ttu-id="fc4d0-172">它位於您匯出搜尋結果所在的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="fc4d0-173">連絡 Microsoft 支援人員。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="fc4d0-174">錯誤/問題：保留未同步處理</span><span class="sxs-lookup"><span data-stu-id="fc4d0-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="fc4d0-175">電子檔探索案例保留原則同步發佈錯誤。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="fc4d0-176">錯誤讀取：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-176">The error reads:</span></span>

> <span data-ttu-id="fc4d0-177">「資源：部署原則所花費的時間超過預期。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="fc4d0-178">更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。」</span><span class="sxs-lookup"><span data-stu-id="fc4d0-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="fc4d0-179">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-179">Resolution</span></span>

1. <span data-ttu-id="fc4d0-180">連線至 [安全性 & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 然後針對 eDiscovery 案例保留執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-180">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="fc4d0-181">若為保留原則，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="fc4d0-182">檢查 DistributionDetail 參數中的值，以查看類似下列的錯誤：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="fc4d0-183">錯誤：資源：部署原則所花費的時間超過預期。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="fc4d0-184">更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。」</span><span class="sxs-lookup"><span data-stu-id="fc4d0-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="fc4d0-185">嘗試在有問題的原則上執行 RetryDistribution 參數：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="fc4d0-186">針對 eDiscovery 案例保留：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="fc4d0-187">對於保留原則：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="fc4d0-188">連絡 Microsoft 支援人員。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="fc4d0-189">錯誤：「使用 HTTP 條件標頭 (指定的條件不符合) </span><span class="sxs-lookup"><span data-stu-id="fc4d0-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="fc4d0-190">使用 eDiscovery 匯出工具下載搜尋結果時，可能會收到下列錯誤： `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 這是暫時性的錯誤，通常會發生于 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="fc4d0-191">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-191">Resolution</span></span>

<span data-ttu-id="fc4d0-192">若要解決此問題，請重試 [下載搜尋結果](export-search-results.md#step-2-download-the-search-results)，這將會重新開機 EDiscovery 匯出工具。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="fc4d0-193">錯誤/問題：已下載的匯出未顯示任何結果</span><span class="sxs-lookup"><span data-stu-id="fc4d0-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="fc4d0-194">匯出成功後，透過匯出工具完成的下載會在結果中顯示零個檔案。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="fc4d0-195">解決方案</span><span class="sxs-lookup"><span data-stu-id="fc4d0-195">Resolution</span></span>

<span data-ttu-id="fc4d0-196">這是用戶端問題，為了進行修正，請嘗試下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fc4d0-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="fc4d0-197">嘗試使用另一部用戶端/電腦來下載。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="fc4d0-198">請務必下載到本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="fc4d0-199">請確定病毒掃描程式未執行。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="fc4d0-200">請確定沒有任何其他匯出正在下載至相同的資料夾或任何上層資料夾。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="fc4d0-201">如果上述步驟無法運作，請停用 [壓縮] 和 [重復資料刪除]。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="fc4d0-202">如果這樣做正常，則問題是由於本機病毒掃描程式或磁片問題所造成。</span><span class="sxs-lookup"><span data-stu-id="fc4d0-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>