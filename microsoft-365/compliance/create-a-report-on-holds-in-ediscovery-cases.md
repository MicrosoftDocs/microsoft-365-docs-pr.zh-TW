---
title: 在電子文件探索案例中的保留建立報表
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何產生包含與 eDiscovery 案例相關聯之所有保留資訊的報告。
ms.openlocfilehash: 35e432104e7c1358887eb89ae96b9bb0d1d12a0f
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546975"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>在電子文件探索案例中的保留建立報表

本文中的腳本可讓 eDiscovery 管理員和 eDiscovery 管理員產生報告，其中包含與 Office 365 或 Microsoft 365 中的「規範中心」有關 eDiscovery 案例相關聯之所有保留的相關資訊。 報告包含與保留相關聯之案例的名稱、置於保留狀態的內容位置，以及該保留是否是以查詢為基礎的資訊。 如果有些案例沒有任何保留，腳本將會建立其他不含保留案例清單的報表。

請參閱 [詳細資訊](#more-information) 一節，以取得報告中所含資訊的詳細描述。

## <a name="admin-requirements-and-script-information"></a>管理員需求和腳本資訊

- 若要在您的組織中產生所有 eDiscovery 案例的報告，您必須是組織中的 eDiscovery 系統管理員。 如果您是 eDiscovery 管理員，該報告將只會包含您可以存取之案例的相關資訊。 如需有關 eDiscovery 許可權的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。

- 本文中的腳本具有最低的錯誤處理方式。 主要用途是快速建立與您組織中的 eDiscovery 案例相關聯之保留的報告。

- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>步驟1：連線至安全性 & 規範中心 PowerShell

第一步是連接至組織的安全性 & 規範中心 PowerShell。 如需逐步指示，請參閱[連線至安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>步驟2：執行腳本以報告與 eDiscovery 案例相關聯的封存

在您連接至安全性 & 規範中心 PowerShell 之後，下一步是建立並執行腳本，以收集組織中 eDiscovery 案例的相關資訊。

1. 使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如，CaseHoldsReport.ps1。

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. 在步驟1中開啟的 [Windows PowerShell] 會話中，移至您用來儲存腳本的資料夾。

3. 執行腳本;例如：

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   腳本會提示目的檔案夾儲存報告。

4. 輸入要儲存報告之資料夾的完整路徑名稱，然後按 **enter**。

   > [!TIP]
   > 若要將報告儲存在腳本所在的相同資料夾中，請輸入句點 ( "。提示目的檔案夾時 ) 。 若要將報告儲存至腳本所在之資料夾的子資料夾，只要輸入子資料夾的名稱即可。

   腳本開始收集組織中所有 eDiscovery 案例的相關資訊。 在腳本執行時，請勿存取報告檔案。 腳本完成後，會在 Windows PowerShell 會話中顯示確認訊息。 顯示此訊息之後，您可以在步驟4中所指定的資料夾中存取報告。 報表的檔案名是 `CaseHoldsReport<DateTimeStamp>.csv` 。

   Addtionally，腳本也會建立報表，其中包含沒有任何保留的案例清單。 此報告的檔案名為 `CaseswithNoHolds<DateTimeStamp>.csv` 。

   以下是執行 CaseHoldsReport.ps1 腳本的範例。

   ![執行 CaseHoldsReport.ps1 腳本後的輸出](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>詳細資訊

當您執行本文中的腳本時所建立的案例保留報告中，包含每個保留的下列相關資訊。 如先前所述，您必須是 eDiscovery 系統管理員，才能傳回組織中所有保留的資訊。 如需案例保留的詳細資訊，請參閱 [eDiscovery 案例](ediscovery-cases.md)。

- 保留的名稱和保留相關之 eDiscovery 案例的名稱。

- EDiscovery 案例是否為使用中或已關閉狀態。

- 是否啟用或停用保留。

- 與保留相關的 eDiscovery 案例成員。 Case 成員可以查看或管理案例，視其所指派的 eDiscovery 許可權而定。

- 案例的建立時間和日期。

- 若案例是關閉的，關閉它和時間及日期的人員會關閉。

- 處於保留狀態的 Exchange 信箱和 SharePoint 網站位置。

- 如果保留是以查詢為基礎，則為查詢語法。

- 建立保留的時間和日期，以及建立該保留的人員。

- 上次變更保留的時間和日期，以及變更的人員。
