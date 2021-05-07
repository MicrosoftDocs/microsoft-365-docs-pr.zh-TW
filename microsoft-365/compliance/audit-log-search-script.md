---
title: 使用 PowerShell 指令碼來搜尋稽核記錄
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 使用 PowerShell 指令碼，在 Exchange Online 中執行 Search-UnifiedAuditLog Cmdlet，以搜尋稽核記錄檔。 此指令碼經過最佳化，可傳回大量 (最多50,000 筆) 稽核記錄。 指令碼會將這些記錄匯出為 CSV 檔案，您可以使用 Excel 中的 Power Query 來檢視或轉換。
ms.openlocfilehash: df5e675e5e36603a73078bd5ecf5e64bc7a76f95
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939563"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>使用 PowerShell 指令碼來搜尋稽核記錄

安全性、合規性和稽核已經成為今日 IT 系統管理員的首要要務。 Microsoft 365 有數種內建功能，可協助組織管理安全性、合規性及稽核。 特別是，整合式稽核記錄可協助您調查安全性事件和合規性問題。 您可以使用下列方法來擷取稽核記錄：

- [Office 365 管理活動 API](/office/office-365-management-api/office-365-management-activity-api-reference)

- Microsoft 365 合規性中心中的[稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)

- Exchange Online PowerShell 中的 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) Cmdlet

如果您需要定期擷取稽核記錄，您應考慮使用 Office 365 管理活動 API 的解決方案，因為它為大型組織提供擴充性和效能，以持續擷取上百萬筆稽核記錄。 使用 Microsoft 365 合規性中心中的稽核記錄搜尋工具，可以快速尋找在較短時間範圍內發生的特定作業相關稽核記錄。 在稽核記錄搜尋工具中使用較長的時間範圍，特別是針對大型組織，可能會傳回太多記錄，而無法輕鬆管理或匯出。

當您需要手動為特定調查或事件擷取稽核資料時　(特別是大型組織中的較長日期範圍) 時，使用 **Search-UnifiedAuditLog** Cmdlet 可能是最佳選擇。 本文包含的 PowerShell 指令碼可使用 Cmdlet 來擷取最多 50,000 筆稽核記錄，然後將它們匯出至 CSV 檔案，您可以在 Excel 中使用 Power Query 來設定格式，以協助您進行檢閱。 使用本文中的指令碼也能將大型稽核記錄搜尋在服務中逾時的可能性降到最低。

## <a name="before-you-run-the-script"></a>執行指令碼前

- 您的組織必須啟用 [稽核記錄] 才能成功使用指令碼傳回稽核記錄。 使用 Microsoft 365 和 Office 365 企業版的組織，預設會開啟 [稽核記錄]。 若要驗證貴組織已開啟 [稽核記錄搜尋]，您可以在 Exchange Online PowerShell 中執行下列命令：

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  **UnifiedAuditLogIngestionEnabled** 屬性值為 `True` 表示已開啟 [稽核記錄搜尋]。

- 您必須在 Exchange Online 中獲派為 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，才能成功執行指令碼。 根據預設，這些角色會在 Exchange 系統管理員中心的 [權限] 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。 如需詳細資訊，請參閱[在合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log)中的「搜尋稽核記錄的需求」章節。

- 指令碼完成可能需要很長時間。 執行所需的時間取決於您設定指令碼以擷取稽核記錄的日期範圍和間隔大小。 較大的日期範圍和較小的間隔會導致長時間執行。 如需日期範圍和間隔的詳細資訊，請參閱步驟 2 中的表格。

- 在任何 Microsoft 標準支援程式或服務下，不支援本文章提供的樣本指令碼。樣本指令碼係依「現狀」提供，不附帶任何形式的擔保。Microsoft 另外不承擔任何默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作樣本指令碼和文件之外發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付指令碼相關的任何人在任何情況下均不負任何損害責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用樣本指令碼或文件所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。

## <a name="step-1-connect-to-exchange-online-powershell"></a>步驟 1：連線至 Exchange Online PowerShell

第一個步驟是連線至 Exchange Online PowerShell。 您可以使用新式驗證或多重要素驗證 (MFA) 來連線。 如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>步驟 2：修改並執行指令碼以擷取稽核記錄

當您連線到 Exchange Online PowerShell 後，下一個步驟就是建立、修改然後執行指令碼以擷取稽核資料。 稽核記錄搜尋指令碼中的前七行包含下列可供您修改以設定搜尋的變數。 請參閱步驟 2 中的表格以取得這些變數的描述。

1. 使用 .ps1 檔名尾碼將下列文字儲存至 Windows PowerShell 指令碼。例如，SearchAuditLog.ps1。

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. 修改下表中所列的變數以設定搜尋準則。 指令碼包含這些變數的範例值，但您應該變更這些值 (除非另有說明)，以符合您的特定需求。

   <br>

   ****

   |變數|範例值|描述|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|指定記錄檔的名稱和位置，其中包含指令碼執行的稽核記錄搜尋進度相關資訊。此指令碼會將 UTC 時間戳記寫入記錄檔。|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|指定 CSV 檔案的名稱和位置，該檔案包含指令碼所傳回的稽核記錄。|
   |`[DateTime]$start` 和 `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|指定稽核記錄搜尋的日期範圍。 指令碼會傳回在指定日期範圍內發生的稽核活動的記錄。 例如，若要傳回在 2021 年 1 月執行的活動，您可以使用 `"2021-01-01"` 作為開始日期，以及 `"2021-01-31"` 作為結束日期 (請務必用雙引號括住值)。指令碼中的範例值會傳回之前 24 小時內執行之活動的記錄。 如果您未在值中包含時間戳記，則預設時間戳記為指定日期的上午 12:00 (凌晨)。|
   |`$record`|"AzureActiveDirectory"|指定要搜尋之稽核活動的記錄類型 (又稱為 *作業*)。 此屬性表示在其中觸發活動的服務或功能。 如需可用於此變數的記錄類型清單，請參閱[稽核記錄類型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。 您可以使用記錄類型名稱或 ENUM 值。 <br/><br/>**提示：** 若要傳回所有記錄類型的稽核記錄，請使用值 `$null` (不含雙引號)。|
   |`$resultSize`|5000|指定指令碼每次呼叫 **Search-UnifiedAuditLog** Cmdlet 所傳回的結果數 (稱為 *結果集*)。 Cmdlet 支援的最大值為 5,000。 將此值保持原樣。|
   |`$intervalMinutes`|60|為了克服傳回 5000 筆記錄的限制，此變數會採用您指定的日期範圍，並將它分成較小的時間間隔。 現在，每個間隔 (而不是整個日期範圍) 都受限於 5000 筆的命令記錄輸出限制。 在日期範圍內每 60 分鐘 5000 筆記錄的預設值應足夠大部分的組織使用。 但是，如果指令碼傳回錯誤`maximum results limitation reached`，請縮短時間間隔 (例如，減少為 30 分鐘甚至 15 分鐘)，然後重新執行指令碼。|
   ||||

   上表中所列的大部分變數對應 **Search-UnifiedAuditLog** Cmdlet 的參數。 如需這些參數的詳細資訊，請參閱 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)。

3. 在您的本機電腦上，開啟 Windows PowerShell，然後移至您儲存修改後的指令碼所在的資料夾。

4. 在 Exchange Online PowerShell 中執行指令碼；例如：

   ```powershell
   .\SearchAuditLog.ps1
   ```

指令碼會在執行時顯示進度訊息。 指令碼執行完成之後，會建立記錄檔和包含稽核記錄的 CSV 檔案，請將它們儲存到 `$logFile` 和 `$outputFile` 變數所定義的資料夾中。

> [!IMPORTANT]
> 每次執行此指令碼時，傳回的稽核記錄數目上限為 50,000。 如果您執行此指令碼，而其傳回 50,000 筆結果，則表示日期範圍內發生之活動的稽核記錄可能未包含在內。 如果發生這種情況，建議您將日期範圍分割成較小的期間，然後重新執行每個日期範圍的指令碼。 例如，如果日期範圍 90 天傳回 50,000 筆結果，您可以重新執行指令碼兩次，一次針對該日期範圍內的前 45 天，另一次針對接下來的 45 天。

## <a name="step-3-format-and-view-the-audit-records"></a>步驟 3：設定格式並檢視稽核記錄

當您執行指令碼並將稽核記錄匯出至 CSV 檔案之後，您可能會想要設定 CSV 的格式，以便更容易地檢閱和分析稽核記錄。 其中一種方法是，使用 Excel 中的 Power Query JSON 轉換功能將 **AuditData** 欄位中，JSON 物件的每個屬性分割為各自的欄位。 如需逐步指示，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的「步驟 2：使用 Power Query 編輯器設定匯出之稽核記錄的格式」(部分機器翻譯)。
