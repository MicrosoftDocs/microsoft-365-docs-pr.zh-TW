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
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="44404-105">使用 PowerShell 指令碼來搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="44404-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="44404-106">安全性、合規性和稽核已經成為今日 IT 系統管理員的首要要務。</span><span class="sxs-lookup"><span data-stu-id="44404-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="44404-107">Microsoft 365 有數種內建功能，可協助組織管理安全性、合規性及稽核。</span><span class="sxs-lookup"><span data-stu-id="44404-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="44404-108">特別是，整合式稽核記錄可協助您調查安全性事件和合規性問題。</span><span class="sxs-lookup"><span data-stu-id="44404-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="44404-109">您可以使用下列方法來擷取稽核記錄：</span><span class="sxs-lookup"><span data-stu-id="44404-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="44404-110">Office 365 管理活動 API</span><span class="sxs-lookup"><span data-stu-id="44404-110">The Office 365 Management Activity API</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="44404-111">Microsoft 365 合規性中心中的[稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="44404-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="44404-112">Exchange Online PowerShell 中的 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) Cmdlet</span><span class="sxs-lookup"><span data-stu-id="44404-112">The [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="44404-113">如果您需要定期擷取稽核記錄，您應考慮使用 Office 365 管理活動 API 的解決方案，因為它為大型組織提供擴充性和效能，以持續擷取上百萬筆稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="44404-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="44404-114">使用 Microsoft 365 合規性中心中的稽核記錄搜尋工具，可以快速尋找在較短時間範圍內發生的特定作業相關稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="44404-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="44404-115">在稽核記錄搜尋工具中使用較長的時間範圍，特別是針對大型組織，可能會傳回太多記錄，而無法輕鬆管理或匯出。</span><span class="sxs-lookup"><span data-stu-id="44404-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="44404-116">當您需要手動為特定調查或事件擷取稽核資料時　(特別是大型組織中的較長日期範圍) 時，使用 **Search-UnifiedAuditLog** Cmdlet 可能是最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="44404-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="44404-117">本文包含的 PowerShell 指令碼可使用 Cmdlet 來擷取最多 50,000 筆稽核記錄，然後將它們匯出至 CSV 檔案，您可以在 Excel 中使用 Power Query 來設定格式，以協助您進行檢閱。</span><span class="sxs-lookup"><span data-stu-id="44404-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="44404-118">使用本文中的指令碼也能將大型稽核記錄搜尋在服務中逾時的可能性降到最低。</span><span class="sxs-lookup"><span data-stu-id="44404-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="44404-119">執行指令碼前</span><span class="sxs-lookup"><span data-stu-id="44404-119">Before you run the script</span></span>

- <span data-ttu-id="44404-120">您的組織必須啟用 [稽核記錄] 才能成功使用指令碼傳回稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="44404-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="44404-121">使用 Microsoft 365 和 Office 365 企業版的組織，預設會開啟 [稽核記錄]。</span><span class="sxs-lookup"><span data-stu-id="44404-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="44404-122">若要驗證貴組織已開啟 [稽核記錄搜尋]，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="44404-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  <span data-ttu-id="44404-123">**UnifiedAuditLogIngestionEnabled** 屬性值為 `True` 表示已開啟 [稽核記錄搜尋]。</span><span class="sxs-lookup"><span data-stu-id="44404-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="44404-124">您必須在 Exchange Online 中獲派為 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，才能成功執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="44404-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="44404-125">根據預設，這些角色會在 Exchange 系統管理員中心的 [權限] 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="44404-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="44404-126">如需詳細資訊，請參閱[在合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log)中的「搜尋稽核記錄的需求」章節。</span><span class="sxs-lookup"><span data-stu-id="44404-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="44404-127">指令碼完成可能需要很長時間。</span><span class="sxs-lookup"><span data-stu-id="44404-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="44404-128">執行所需的時間取決於您設定指令碼以擷取稽核記錄的日期範圍和間隔大小。</span><span class="sxs-lookup"><span data-stu-id="44404-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="44404-129">較大的日期範圍和較小的間隔會導致長時間執行。</span><span class="sxs-lookup"><span data-stu-id="44404-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="44404-130">如需日期範圍和間隔的詳細資訊，請參閱步驟 2 中的表格。</span><span class="sxs-lookup"><span data-stu-id="44404-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="44404-p108">在任何 Microsoft 標準支援程式或服務下，不支援本文章提供的樣本指令碼。樣本指令碼係依「現狀」提供，不附帶任何形式的擔保。Microsoft 另外不承擔任何默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作樣本指令碼和文件之外發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付指令碼相關的任何人在任何情況下均不負任何損害責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用樣本指令碼或文件所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="44404-p108">The sample script provided in this article isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="44404-136">步驟 1：連線至 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="44404-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="44404-137">第一個步驟是連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="44404-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="44404-138">您可以使用新式驗證或多重要素驗證 (MFA) 來連線。</span><span class="sxs-lookup"><span data-stu-id="44404-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="44404-139">如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="44404-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="44404-140">步驟 2：修改並執行指令碼以擷取稽核記錄</span><span class="sxs-lookup"><span data-stu-id="44404-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="44404-141">當您連線到 Exchange Online PowerShell 後，下一個步驟就是建立、修改然後執行指令碼以擷取稽核資料。</span><span class="sxs-lookup"><span data-stu-id="44404-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="44404-142">稽核記錄搜尋指令碼中的前七行包含下列可供您修改以設定搜尋的變數。</span><span class="sxs-lookup"><span data-stu-id="44404-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="44404-143">請參閱步驟 2 中的表格以取得這些變數的描述。</span><span class="sxs-lookup"><span data-stu-id="44404-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="44404-p111">使用 .ps1 檔名尾碼將下列文字儲存至 Windows PowerShell 指令碼。例如，SearchAuditLog.ps1。</span><span class="sxs-lookup"><span data-stu-id="44404-p111">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1. For example, SearchAuditLog.ps1.</span></span>

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

2. <span data-ttu-id="44404-146">修改下表中所列的變數以設定搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="44404-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="44404-147">指令碼包含這些變數的範例值，但您應該變更這些值 (除非另有說明)，以符合您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="44404-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   <br>

   ****

   |<span data-ttu-id="44404-148">變數</span><span class="sxs-lookup"><span data-stu-id="44404-148">Variable</span></span>|<span data-ttu-id="44404-149">範例值</span><span class="sxs-lookup"><span data-stu-id="44404-149">Sample value</span></span>|<span data-ttu-id="44404-150">描述</span><span class="sxs-lookup"><span data-stu-id="44404-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="44404-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="44404-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="44404-p113">指定記錄檔的名稱和位置，其中包含指令碼執行的稽核記錄搜尋進度相關資訊。此指令碼會將 UTC 時間戳記寫入記錄檔。</span><span class="sxs-lookup"><span data-stu-id="44404-p113">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script. The script writes UTC timestamps to the log file.</span></span>|
   |`$outputFile`|<span data-ttu-id="44404-154">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="44404-154">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="44404-155">指定 CSV 檔案的名稱和位置，該檔案包含指令碼所傳回的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="44404-155">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="44404-156">`[DateTime]$start` 和 `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="44404-156">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="44404-159">指定稽核記錄搜尋的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="44404-159">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="44404-160">指令碼會傳回在指定日期範圍內發生的稽核活動的記錄。</span><span class="sxs-lookup"><span data-stu-id="44404-160">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="44404-161">例如，若要傳回在 2021 年 1 月執行的活動，您可以使用 `"2021-01-01"` 作為開始日期，以及 `"2021-01-31"` 作為結束日期 (請務必用雙引號括住值)。指令碼中的範例值會傳回之前 24 小時內執行之活動的記錄。</span><span class="sxs-lookup"><span data-stu-id="44404-161">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="44404-162">如果您未在值中包含時間戳記，則預設時間戳記為指定日期的上午 12:00 (凌晨)。</span><span class="sxs-lookup"><span data-stu-id="44404-162">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="44404-163">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="44404-163">"AzureActiveDirectory"</span></span>|<span data-ttu-id="44404-164">指定要搜尋之稽核活動的記錄類型 (又稱為 *作業*)。</span><span class="sxs-lookup"><span data-stu-id="44404-164">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="44404-165">此屬性表示在其中觸發活動的服務或功能。</span><span class="sxs-lookup"><span data-stu-id="44404-165">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="44404-166">如需可用於此變數的記錄類型清單，請參閱[稽核記錄類型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。</span><span class="sxs-lookup"><span data-stu-id="44404-166">For a list of record types that you can use for this variable, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="44404-167">您可以使用記錄類型名稱或 ENUM 值。</span><span class="sxs-lookup"><span data-stu-id="44404-167">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="44404-168">**提示：** 若要傳回所有記錄類型的稽核記錄，請使用值 `$null` (不含雙引號)。</span><span class="sxs-lookup"><span data-stu-id="44404-168">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="44404-169">5000</span><span class="sxs-lookup"><span data-stu-id="44404-169">5000</span></span>|<span data-ttu-id="44404-170">指定指令碼每次呼叫 **Search-UnifiedAuditLog** Cmdlet 所傳回的結果數 (稱為 *結果集*)。</span><span class="sxs-lookup"><span data-stu-id="44404-170">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="44404-171">Cmdlet 支援的最大值為 5,000。</span><span class="sxs-lookup"><span data-stu-id="44404-171">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="44404-172">將此值保持原樣。</span><span class="sxs-lookup"><span data-stu-id="44404-172">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="44404-173">60</span><span class="sxs-lookup"><span data-stu-id="44404-173">60</span></span>|<span data-ttu-id="44404-174">為了克服傳回 5000 筆記錄的限制，此變數會採用您指定的日期範圍，並將它分成較小的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="44404-174">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="44404-175">現在，每個間隔 (而不是整個日期範圍) 都受限於 5000 筆的命令記錄輸出限制。</span><span class="sxs-lookup"><span data-stu-id="44404-175">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="44404-176">在日期範圍內每 60 分鐘 5000 筆記錄的預設值應足夠大部分的組織使用。</span><span class="sxs-lookup"><span data-stu-id="44404-176">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="44404-177">但是，如果指令碼傳回錯誤`maximum results limitation reached`，請縮短時間間隔 (例如，減少為 30 分鐘甚至 15 分鐘)，然後重新執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="44404-177">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="44404-178">上表中所列的大部分變數對應 **Search-UnifiedAuditLog** Cmdlet 的參數。</span><span class="sxs-lookup"><span data-stu-id="44404-178">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="44404-179">如需這些參數的詳細資訊，請參閱 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="44404-179">For more information about these parameters, see [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="44404-180">在您的本機電腦上，開啟 Windows PowerShell，然後移至您儲存修改後的指令碼所在的資料夾。</span><span class="sxs-lookup"><span data-stu-id="44404-180">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="44404-181">在 Exchange Online PowerShell 中執行指令碼；例如：</span><span class="sxs-lookup"><span data-stu-id="44404-181">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="44404-182">指令碼會在執行時顯示進度訊息。</span><span class="sxs-lookup"><span data-stu-id="44404-182">The script displays progress messages while it's running.</span></span> <span data-ttu-id="44404-183">指令碼執行完成之後，會建立記錄檔和包含稽核記錄的 CSV 檔案，請將它們儲存到 `$logFile` 和 `$outputFile` 變數所定義的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="44404-183">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44404-184">每次執行此指令碼時，傳回的稽核記錄數目上限為 50,000。</span><span class="sxs-lookup"><span data-stu-id="44404-184">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="44404-185">如果您執行此指令碼，而其傳回 50,000 筆結果，則表示日期範圍內發生之活動的稽核記錄可能未包含在內。</span><span class="sxs-lookup"><span data-stu-id="44404-185">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="44404-186">如果發生這種情況，建議您將日期範圍分割成較小的期間，然後重新執行每個日期範圍的指令碼。</span><span class="sxs-lookup"><span data-stu-id="44404-186">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="44404-187">例如，如果日期範圍 90 天傳回 50,000 筆結果，您可以重新執行指令碼兩次，一次針對該日期範圍內的前 45 天，另一次針對接下來的 45 天。</span><span class="sxs-lookup"><span data-stu-id="44404-187">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="44404-188">步驟 3：設定格式並檢視稽核記錄</span><span class="sxs-lookup"><span data-stu-id="44404-188">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="44404-189">當您執行指令碼並將稽核記錄匯出至 CSV 檔案之後，您可能會想要設定 CSV 的格式，以便更容易地檢閱和分析稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="44404-189">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="44404-190">其中一種方法是，使用 Excel 中的 Power Query JSON 轉換功能將 **AuditData** 欄位中，JSON 物件的每個屬性分割為各自的欄位。</span><span class="sxs-lookup"><span data-stu-id="44404-190">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="44404-191">如需逐步指示，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的「步驟 2：使用 Power Query 編輯器設定匯出之稽核記錄的格式」(部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="44404-191">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
