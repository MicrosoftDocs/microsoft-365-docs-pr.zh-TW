---
title: 在 Office 365 中创建有关电子数据展示案例中的保留的报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: 使用本文中的脚本生成报告，其中包含有关 Office 365 或 Microsoft 365 中的合规性中心中与电子数据展示案例关联的所有保留的信息。
ms.openlocfilehash: 7118b62dcd42413309e33c45e80516c8822faeff
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076517"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>在 Office 365 中创建有关电子数据展示案例中的保留的报告
  
本文中的脚本允许电子数据展示管理员和电子数据展示经理生成一个报告，其中包含与 Office 365 或 Microsoft 365 中的合规性中心中的电子数据展示案例关联的所有保留的信息。 报表包含信息，如保留关联的案例的名称、置于保留中的内容位置以及保留是否基于查询。 如果存在没有任何保留的情况，脚本将创建一个附加报告，其中包含没有保留的案例列表。

有关报告中包含的信息的详细说明，[请参阅"详细信息"](#more-information)部分。 
  
## <a name="before-you-begin"></a>開始之前

- 要生成有关组织中的所有电子数据展示案例的报告，您必须是组织中电子数据展示管理员。 如果您是电子数据展示管理器，则报告将仅包含有关您可以访问的案例的信息。 有关电子数据展示权限的详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。
    
- 本文中的脚本具有最少的错误处理。 主要目的是快速创建有关与组织中电子数据展示案例关联的保留的报告。
    
- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>第 1 步：连接到安全&合规性中心 PowerShell

第一步是连接到组织的安全&合规性中心。
  
1. 使用文件名后缀 .ps1 将以下文本保存到 Windows PowerShell 脚本文件中;例如， `ConnectSCC.ps1`. 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. 在本地计算机上，打开 Windows PowerShell 并转到保存脚本的文件夹。 
    
3. 运行脚本;例如：

    ```
    .\ConnectSCC.ps1
    ```
   
4. 当系统提示输入凭据时，请输入您的电子邮件地址和密码，然后单击"**确定"。** 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>步骤 2：运行脚本以报告与电子数据展示案例关联的保留

连接到安全&合规中心 PowerShell 后，下一步是创建并运行脚本，以收集有关组织中电子数据展示案例的信息。 
  
1. 使用文件名后缀 .ps1 将以下文本保存到 Windows PowerShell 脚本文件中;例如，CaseHoldsReport.ps1。 
    
  ```
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

2. 在步骤 1 中打开的 Windows PowerShell 会话中，转到保存脚本的文件夹。 
    
3. 运行脚本;例如：

    ```
    .\CaseHoldsReport.ps1
    ```

    脚本将提示目标文件夹将报表保存到。 
    
4. 键入要将报表保存到的文件夹的完整路径名称，然后**按"输入"。**
    
    > [!TIP]
    > 要将报表保存在脚本所在的同一文件夹中，在提示输入目标文件夹时键入句点 （"."）。 要将报表保存在脚本所在的文件夹中的子文件夹中，只需键入子文件夹的名称。 
  
    该脚本开始收集有关组织中所有电子数据展示案例的信息。 脚本运行时不要访问报表文件。 脚本完成后，Windows PowerShell 会话中将显示一条确认消息。 显示此消息后，可以访问步骤 4 中指定的文件夹中的报表。 报表的文件名为`CaseHoldsReport<DateTimeStamp>.csv`。

    此外，脚本还会创建一个报表，其中包含没有任何保留的案例列表。 此报表的文件名为`CaseswithNoHolds<DateTimeStamp>.csv`。
    
    下面是运行 CaseHoldsReport.ps1 脚本的示例。 
    
    ![运行 CaseHoldsReport.ps1 脚本后的输出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>詳細資訊

在本文中运行脚本时创建的 case 保留报表，其中包含有关每个保留的以下信息。 如前所述，您必须是电子数据展示管理员才能返回组织中所有保留的信息。 有关案例保留的详细信息，请参阅[电子数据展示案例](ediscovery-cases.md)。
  
  - 保留的名称和与保留关联的电子数据展示案例的名称。
    
  - 电子数据展示案例是否处于活动状态或已关闭。
    
  - 是否启用或禁用保留。
    
  - 保留关联的电子数据展示案例的成员。 案例成员可以查看或管理案例，具体取决于他们分配了电子数据展示权限。
    
  - 创建案例的时间和日期。
    
  - 如果案件已结案，则结案人以及结案的时间和日期。
    
  - Exchange 邮箱和 SharePoint 站点处于保留状态的位置。
    
  - 如果保留基于查询，则查询语法。
    
  - 创建保留的时间和日期以及创建保留的人员。
    
  - 上次更改保留的时间和日期以及更改保留的时间和日期。
