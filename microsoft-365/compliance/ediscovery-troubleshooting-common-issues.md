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
ms.openlocfilehash: 37e92e480759601f9dfe61430bdd647b20df051d
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685611"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>調查、 進行疑難排解及解決常見問題 eDiscovery

本主題涵蓋基本疑難排解步驟，您可以用來識別並解決期間的 eDiscovery 搜尋或其他位置中的 eDiscovery 程序可能會遇到的問題。 解決某些這些案例需要 Microsoft 支援服務說明。 資訊，請連絡 Microsoft 支援服務隨附於解決步驟。

## <a name="errorissue-ambiguous-location"></a>錯誤/問題： 模稜兩可的位置

如果您嘗試新增至搜尋使用者的信箱位置，且沒有重複或衝突物件具有相同的使用者識別碼，Exchange Online Protection (EOP) 目錄中，您會收到此錯誤： `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`。 

### <a name="resolution"></a>解決方案

檢查有重複的使用者或通訊群組清單使用相同的使用者識別碼。

1. 連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

2. 執行下列命令，以擷取使用者名稱的所有執行個體：

    ```powershell
    Get-Recipient <username>
    ```

   'Useralias@contoso.com' 的輸出可能類似下列：

   > 
   > |名稱  |收件者類型  |
   > |---------|---------|
   > |別名，使用者     |MailUser         |
   > |別名，使用者     |使用者         |

3. 如果傳回多個使用者，找出並修正衝突的物件。

## <a name="errorissue-search-fails-on-specific-locations"></a>在特定位置上的錯誤/問題： 搜尋失敗

電子文件探索] 或 [內容搜尋，可能會產生下列錯誤：
>此搜尋完成 （#） 發生錯誤。  您要重試失敗的位置上的搜尋嗎？

![搜尋特定位置失敗錯誤的螢幕擷取畫面]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>解決方案

如果您收到此錯誤，我們建議您驗證失敗，在搜尋] 的位置然後重新執行搜尋] 只有在失敗的位置上。

1. 連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)並執行下列命令：

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. 從 PowerShell 輸出，檢視失敗的位置，[錯誤] 欄位中，或是從中從搜尋輸出錯誤的狀態詳細資料。

3. 重試失敗的位置，以只 eDiscovery 搜尋。

4. 如果您繼續收到這些錯誤，請參閱[重試失敗位置](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search)的更多疑難排解的步驟。

## <a name="errorissue-file-not-found"></a>錯誤/問題： 找不到檔案

當執行 eDiscovery 搜尋，其中包含 SharePoint Online 和 One Drive For Business 位置，您可能會收到錯誤`File Not Found`雖然該檔案位於網站上。 此錯誤會處於 errors.csv 與匯出警告或略過 items.csv。 如果在網站上找不到檔案或過期的索引時，這可能會發生。 以下是錯誤的實際 （使用新增的強調） 的文字。
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed 下載內容。 其他診斷資訊： Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure： 無法從內容類型的文件的 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 下載。 相互關聯識別碼： 3bd84722-937b-4 c 23-b61b-08d6fba9ec32。 ServerErrorCode:-2147024894---: > Microsoft.SharePoint.Client.ServerException：***找不到檔案***。 在 Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream (資料流 responseStream) 在 Microsoft.SharePoint.Client.ClientRequest.ProcessResponse()---: 內部例外堆疊追蹤的結尾-為-

### <a name="resolution"></a>解決方案

1. 請在搜尋]，以確保的位置識別位置該檔案位於正確，以及新增搜尋位置。

2. 用於程序在[手動要求編目和重新編製索引的網站、 文件庫或清單](https://docs.microsoft.com/sharepoint/crawl-site-content)重新編製索引的網站。

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>錯誤/問題： 搜尋失敗，因為找不到收件者

EDiscovery 搜尋失敗，錯誤`recipient not found`。 如果使用者物件找不到 Exchange Online Protection (EOP) 因為物件已不會同步處理，可能會發生此錯誤。

### <a name="resolution"></a>解決方案

1. 連線至[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 執行下列命令，以檢查是否使用者已同步處理至 Exchange Online Protection:

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. 應該要有使用者問題的郵件使用者物件。 如果會傳回 nothing，調查的使用者物件。 如果無法同步處理物件，請連絡 Microsoft 支援服務。

## <a name="errorissue-exporting-search-results-is-slow"></a>錯誤/問題： 匯出搜尋結果緩慢

當從 eDiscovery] 或 [內容搜尋中的安全性與合規性中心匯出搜尋結果，下載花費的時間比預期。  您可以檢查的資料量来下載，並可能增加匯出速度。

### <a name="resolution"></a>解決方案

1.  請嘗試使用識別[增加下載速度](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)」 文件中的步驟。

2.  如果您仍有問題，連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然後執行下列命令：

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. 尋找下載 SearchResults 及 SearchStatistics 參數中的資料量。

5. 執行下列命令：

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. 在 [結果] 欄位中，尋找已匯出的資料，並檢視任何發生的錯誤。

7. 請檢查 trace.log 檔案位在您匯出的內容有任何錯誤的目錄。

## <a name="errorissue-internal-server-error-500-occurred"></a>錯誤/問題: 「 發生內部伺服器錯誤 (500) 」

當執行 eDiscovery 搜尋，如果搜尋持續失敗，類似於 「 時發生內部伺服器錯誤 (500) 」 的錯誤，可能需要重新執行只能在特定信箱的位置上的搜尋。

![內部伺服器錯誤 500 螢幕擷取畫面](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>解決方案

1. 搜尋分成較小的搜尋，並再次執行搜尋。  請嘗試使用較小的日期範圍，或限制搜尋的位置數目。

2. 連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)並執行下列命令：

    ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
    Get-ComplianceSearch <searchname> | FL
    ```

3. 檢查結果和錯誤的輸出。

4. 檢查 trace.log 檔案。 它位於您匯出搜尋結果的相同資料夾中。

5. 連絡 Microsoft 支援人員。

## <a name="errorissue-holds-dont-sync"></a>保留不同步處理錯誤/問題：

eDiscovery 案例保留原則同步處理通訊時發生錯誤。 錯誤會顯示如下：

> 「 資源： 花費的時間超過部署原則預期時間。 它可能需要其他 2 小時更新的最終的部署狀態，因此請回到 [幾個小時。 」

### <a name="resolution"></a>解決方案

1.  連線至[Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)並執行下列命令，以電子文件探索案例保留：

    ```powershell
    Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
    ```

    保留原則，執行下列命令：

    ```powershell
    Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
    ```

2. 檢查錯誤如下所示的 DistributionDetail 參數的值：
 
   > 錯誤： 資源： 花費的時間超過部署原則預期時間。 它可能需要其他 2 小時更新的最終的部署狀態，因此請回到 [幾個小時。 」 
   
3. 請嘗試執行 RetryDistribution 參數有問題的原則：
   
    
    針對 eDiscovery 案件保留：

    ```powershell
    Set-CaseHoldPolicy <policyname> -RetryDistribution
    ```

    保留原則：

    ```powershell
    Set-RetentionCompliancePolicy <policyname> -RetryDistribution
    ``` 

4. 連絡 Microsoft 支援人員。

## <a name="see-also"></a>另請參閱

- [若要避免內容位置錯誤的祕訣](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
