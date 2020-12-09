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
ms.openlocfilehash: 4f1bad23705729c15976959a3902501f05da7600
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602034"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>調查、疑難排解及解決常見的 eDiscovery 問題

本主題涵蓋您可以採取的基本疑難排解步驟，用來識別及解決 ediscovery 搜尋期間或 eDiscovery 程式中其他位置可能會遇到的問題。 解決這些案例中的部分需要 Microsoft 支援人員的協助。 解決步驟中包含有關何時聯繫 Microsoft 支援的資訊。

## <a name="errorissue-ambiguous-location"></a>錯誤/問題：不明確的位置

如果您嘗試將使用者的信箱位置新增至搜尋中，且在 Exchange Online Protection (EOP) 目錄中有相同 userID 的重複或衝突物件，您會收到此錯誤： `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` 。

### <a name="resolution"></a>解決方案

檢查是否有相同使用者識別碼的重複使用者或通訊群組清單。

1. 連線至 [安全性 & 規範中心] PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 執行下列命令，以取回使用者名稱的所有實例：

    ```powershell
    Get-Recipient <username>
    ```

   ' Useralias@contoso.com ' 的輸出類似下列所示：

   > 
   > |姓名|RecipientType|
   > |---|---|
   > |Alias、User|MailUser|
   > |Alias、User|使用者|

3. 若傳回多個使用者，請找出並修正衝突的物件。

## <a name="errorissue-search-fails-on-specific-locations"></a>錯誤/問題：搜尋在特定位置失敗

EDiscovery 或內容搜尋可能會產生下列錯誤： `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![搜尋特定位置未通過錯誤螢幕擷取畫面](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>解決方案

如果您收到此錯誤，建議您確認在搜尋中失敗的位置，然後在失敗的位置上只重新執行搜尋。

1. 連線至 [安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 然後執行下列命令：

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. 從 PowerShell 輸出的錯誤欄位中，或從搜尋輸出錯誤中的狀態詳細資料中，查看失敗的位置。

3. 只重試失敗位置上的 eDiscovery 搜尋。

4. 如果您繼續收到這些錯誤，請參閱 [重試失敗位置](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) ，以取得更多疑難排解步驟。

## <a name="errorissue-file-not-found"></a>錯誤/問題：找不到檔案

當執行的 eDiscovery 搜尋包含 SharePoint 線上及一個用於商務位置的硬碟磁碟機時，您可能會收到錯誤， `File Not Found` 但檔案位於網站上。 此錯誤會出現在 [匯出警告] 和 [errors.csv 或略過 items.csv 中。 如果無法在網站上找到檔案，或索引已過期，就可能會發生這種情況。 以下是具有強調新增) 之實際錯誤 (的文字。

> 28.06.2019 10：02：19_FailedToExportItem_Failed 下載內容。 其他診斷資訊： ContentDownloadTemporaryFailure：無法從 content 6ea52149 ExportWorker-91cd-4965-b5bb-82ca6a3ec9be-類型的檔。 相關識別碼：3bd84722-937b-4c23-b61b-08d6fba9ec32。 ServerErrorCode：-2147024894---Microsoft.SharePoint > ***未找到*** ServerException： File。 在 responseStream Microsoft.SharePoint ProcessResponseStream (Stream) at Microsoft.SharePoint。 ( # A3---內部例外狀況堆疊追蹤的結尾---

### <a name="resolution"></a>解決方案

1. 檢查搜尋中識別的位置，以確保檔案的位置正確，並新增至搜尋位置。

2. 您可以使用程式 [，以手動方式要求編目及重新建立網站、文件庫或清單的索引，以重新索引](https://docs.microsoft.com/sharepoint/crawl-site-content) 網站。

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>錯誤/問題：搜尋失敗，因為找不到收件者

EDiscovery 搜尋失敗，錯誤為 `recipient not found` 。 如果無法在 Exchange Online Protection (EOP) 中找到使用者物件，因為物件尚未同步處理，可能會發生此錯誤。

### <a name="resolution"></a>解決方案

1. 連接至 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行下列命令，檢查使用者是否已同步處理至 Exchange Online Protection：

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. 使用者提出問題時，應該會有郵件使用者物件。 若未傳回任何專案，請調查 user 物件。 如果物件無法同步處理，請與 Microsoft 支援人員聯繫。

## <a name="errorissue-exporting-search-results-is-slow"></a>錯誤/問題：匯出搜尋結果的速度緩慢

在安全性與合規性中心匯出搜尋結果從 eDiscovery 或內容搜尋時，下載時間會比預期更長。  您可以查看要下載的資料量，並可能增加匯出速度。

### <a name="resolution"></a>解決方案

1. 連線至 [安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 然後執行下列命令：

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. 在 SearchResults 和 SearchStatistics 參數中尋找要下載的資料量。

3. 執行下列命令：

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. 在 [結果] 欄位中，尋找已匯出的資料，並查看任何發生的錯誤。

5. 檢查您將內容匯出到的目錄中的追蹤 .log 檔案，以查看是否有任何錯誤。

6. 如果仍有問題，請考慮將傳回一組大型結果的搜尋分割成較小的搜尋。 例如，您可以在搜尋查詢中使用日期範圍，以傳回較小的結果集，可更快速地下載。

## <a name="errorissue-internal-server-error-500-occurred"></a>錯誤/問題：「發生內部伺服器錯誤 (500) 

執行 eDiscovery 搜尋時，如果搜尋持續失敗，且發生錯誤類似「發生內部伺服器錯誤 (500) 」，您可能需要在特定信箱位置上只重新執行搜尋。

![內部伺服器錯誤500螢幕擷取畫面](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>解決方案

1. 將搜尋分割成較小的搜尋，然後再次執行搜尋。  請嘗試使用較小的日期範圍或限制要搜尋的位置數目。

2. 連線至 [安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 然後執行下列命令：

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. 檢查結果和錯誤的輸出。

4. 檢查追蹤 .log 檔。 它位於您匯出搜尋結果所在的相同資料夾中。

5. 連絡 Microsoft 支援人員。

## <a name="errorissue-holds-dont-sync"></a>錯誤/問題：保留未同步處理

電子檔探索案例保留原則同步發佈錯誤。 錯誤讀取：

> 「資源：部署原則所花費的時間超過預期。 更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。」

### <a name="resolution"></a>解決方案

1. 連線至 [安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 然後針對 eDiscovery 案例保留執行下列命令：

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    若為保留原則，請執行下列命令：

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. 檢查 DistributionDetail 參數中的值，以查看類似下列的錯誤：

   > 錯誤：資源：部署原則所花費的時間超過預期。 更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。」

3. 嘗試在有問題的原則上執行 RetryDistribution 參數：

   針對 eDiscovery 案例保留：

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   對於保留原則：

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. 連絡 Microsoft 支援人員。

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>錯誤：「使用 HTTP 條件標頭 (指定的條件不符合) 

使用 eDiscovery 匯出工具下載搜尋結果時，可能會收到下列錯誤： `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 這是暫時性的錯誤，通常會發生于 Azure 儲存位置。

### <a name="resolution"></a>解決方案

若要解決此問題，請重試 [下載搜尋結果](export-search-results.md#step-2-download-the-search-results)，這將會重新開機 EDiscovery 匯出工具。

## <a name="see-also"></a>另請參閱

- [避免內容位置錯誤的秘訣](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
