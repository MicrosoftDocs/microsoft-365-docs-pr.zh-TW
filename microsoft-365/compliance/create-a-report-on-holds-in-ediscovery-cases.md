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
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: 您可以使用本文中的腳本，產生一個報告，其中包含與 Office 365 或 Microsoft 365 中的「規範中心」有關之所有保留的相關資訊。
ms.openlocfilehash: 263ac052f320a989b8843f2954a5df0933cdb2f4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632248"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="c389d-103">在電子文件探索案例中的保留建立報表</span><span class="sxs-lookup"><span data-stu-id="c389d-103">Create a report on holds in eDiscovery cases</span></span>
  
<span data-ttu-id="c389d-104">本文中的腳本可讓 eDiscovery 管理員和 eDiscovery 管理員產生報告，其中包含與 Office 365 或 Microsoft 365 中的「規範中心」有關 eDiscovery 案例相關聯之所有保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c389d-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="c389d-105">報告包含與保留相關聯之案例的名稱、置於保留狀態的內容位置，以及該保留是否是以查詢為基礎的資訊。</span><span class="sxs-lookup"><span data-stu-id="c389d-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="c389d-106">如果有些案例沒有任何保留，腳本將會建立其他不含保留案例清單的報表。</span><span class="sxs-lookup"><span data-stu-id="c389d-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="c389d-107">請參閱[詳細資訊](#more-information)一節，以取得報告中所含資訊的詳細描述。</span><span class="sxs-lookup"><span data-stu-id="c389d-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="c389d-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="c389d-108">Before you begin</span></span>

- <span data-ttu-id="c389d-109">若要在您的組織中產生所有 eDiscovery 案例的報告，您必須是組織中的 eDiscovery 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c389d-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="c389d-110">如果您是 eDiscovery 管理員，該報告將只會包含您可以存取之案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c389d-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="c389d-111">如需有關 eDiscovery 許可權的詳細資訊，請參閱[指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c389d-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="c389d-112">本文中的腳本具有最低的錯誤處理方式。</span><span class="sxs-lookup"><span data-stu-id="c389d-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="c389d-113">主要用途是快速建立與您組織中的 eDiscovery 案例相關聯之保留的報告。</span><span class="sxs-lookup"><span data-stu-id="c389d-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="c389d-p104">在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="c389d-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="c389d-119">步驟1：連線至安全性 & 規範中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c389d-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="c389d-120">第一步是連接至組織的安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="c389d-120">The first step is to connect to the Security & Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="c389d-121">使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="c389d-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```powershell
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="c389d-122">在您的本機電腦上，開啟 [Windows PowerShell]，然後移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c389d-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="c389d-123">執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="c389d-123">Run the script; for example:</span></span>

    ```powershell
    .\ConnectSCC.ps1
    ```

4. <span data-ttu-id="c389d-124">當系統提示您輸入認證時，請輸入您的電子郵件地址和密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c389d-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="c389d-125">步驟2：執行腳本以報告與 eDiscovery 案例相關聯的封存</span><span class="sxs-lookup"><span data-stu-id="c389d-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="c389d-126">在您連接至安全性 & 規範中心 PowerShell 之後，下一步是建立並執行腳本，以收集組織中 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c389d-126">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="c389d-127">使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如，CaseHoldsReport. ps1。</span><span class="sxs-lookup"><span data-stu-id="c389d-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="c389d-128">在步驟1中開啟的 [Windows PowerShell] 會話中，移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c389d-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="c389d-129">執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="c389d-129">Run the script; for example:</span></span>

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="c389d-130">腳本會提示目的檔案夾儲存報告。</span><span class="sxs-lookup"><span data-stu-id="c389d-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="c389d-131">輸入要儲存報告之資料夾的完整路徑名稱，然後按**enter**。</span><span class="sxs-lookup"><span data-stu-id="c389d-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c389d-132">若要將報告儲存在腳本所在的相同資料夾中，請在系統提示您輸入目的檔案夾時，輸入句點（"."）。</span><span class="sxs-lookup"><span data-stu-id="c389d-132">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="c389d-133">若要將報告儲存至腳本所在之資料夾的子資料夾，只要輸入子資料夾的名稱即可。</span><span class="sxs-lookup"><span data-stu-id="c389d-133">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="c389d-134">腳本開始收集組織中所有 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c389d-134">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="c389d-135">在腳本執行時，請勿存取報告檔案。</span><span class="sxs-lookup"><span data-stu-id="c389d-135">Don't access the report file while the script is running.</span></span> <span data-ttu-id="c389d-136">腳本完成後，會在 Windows PowerShell 會話中顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="c389d-136">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="c389d-137">顯示此訊息之後，您可以在步驟4中所指定的資料夾中存取報告。</span><span class="sxs-lookup"><span data-stu-id="c389d-137">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="c389d-138">報表的檔案名是`CaseHoldsReport<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="c389d-138">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="c389d-139">Addtionally，腳本也會建立報表，其中包含沒有任何保留的案例清單。</span><span class="sxs-lookup"><span data-stu-id="c389d-139">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="c389d-140">此報告的檔案名為`CaseswithNoHolds<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="c389d-140">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="c389d-141">以下是執行 CaseHoldsReport 腳本的範例。</span><span class="sxs-lookup"><span data-stu-id="c389d-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![執行 CaseHoldsReport 的腳本後的輸出](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="c389d-143">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c389d-143">More information</span></span>

<span data-ttu-id="c389d-144">當您執行本文中的腳本時所建立的案例保留報告中，包含每個保留的下列相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c389d-144">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="c389d-145">如先前所述，您必須是 eDiscovery 系統管理員，才能傳回組織中所有保留的資訊。</span><span class="sxs-lookup"><span data-stu-id="c389d-145">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="c389d-146">如需案例保留的詳細資訊，請參閱[eDiscovery 案例](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="c389d-146">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="c389d-147">保留的名稱和保留相關之 eDiscovery 案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="c389d-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="c389d-148">EDiscovery 案例是否為使用中或已關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="c389d-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="c389d-149">是否啟用或停用保留。</span><span class="sxs-lookup"><span data-stu-id="c389d-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="c389d-150">與保留相關的 eDiscovery 案例成員。</span><span class="sxs-lookup"><span data-stu-id="c389d-150">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="c389d-151">Case 成員可以查看或管理案例，視其所指派的 eDiscovery 許可權而定。</span><span class="sxs-lookup"><span data-stu-id="c389d-151">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="c389d-152">案例的建立時間和日期。</span><span class="sxs-lookup"><span data-stu-id="c389d-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="c389d-153">若案例是關閉的，關閉它和時間及日期的人員會關閉。</span><span class="sxs-lookup"><span data-stu-id="c389d-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="c389d-154">處於保留狀態的 Exchange 信箱和 SharePoint 網站位置。</span><span class="sxs-lookup"><span data-stu-id="c389d-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="c389d-155">如果保留是以查詢為基礎，則為查詢語法。</span><span class="sxs-lookup"><span data-stu-id="c389d-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="c389d-156">建立保留的時間和日期，以及建立該保留的人員。</span><span class="sxs-lookup"><span data-stu-id="c389d-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="c389d-157">上次變更保留的時間和日期，以及變更的人員。</span><span class="sxs-lookup"><span data-stu-id="c389d-157">The time and date the hold was last changed and the person who changed it.</span></span>
