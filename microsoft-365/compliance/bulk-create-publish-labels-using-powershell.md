---
title: 使用 PowerShell 建立及發佈保留標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何從命令列使用 PowerShell 建立及發佈保留標籤，而不受 Microsoft 365 合規性中心的影響。
ms.openlocfilehash: 416746bb849020d76bcf950d397768239d17baf1
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126364"
---
# <a name="create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="ef6b0-103">使用 PowerShell 建立及發佈保留標籤</span><span class="sxs-lookup"><span data-stu-id="ef6b0-103">Create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="ef6b0-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="ef6b0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ef6b0-105">在您決定使用 [保留標籤](retention.md) 來協助您保留或刪除 Microsoft 365 中的文件和電子郵件後，您可能會發現您可能有許多，甚至數百個保留標籤供您建立及發佈。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-105">After you've decided to use [retention labels](retention.md) to help you keep or delete documents and emails in Microsoft 365, you might have realized that you have many and possibly hundreds of retention labels to create and publish.</span></span> <span data-ttu-id="ef6b0-106">按縮放比例建立保留標籤的建議方法，是使用 Microsoft 365 合規性中心的 [檔案計畫](file-plan-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-106">The recommended method to create retention labels at scale is by using [file plan](file-plan-manager.md) from the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ef6b0-107">不過，您也可以使用 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-107">However, you can also use [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span></span>
  
<span data-ttu-id="ef6b0-108">使用本文的資訊、範本檔和範例以及指令檔，來協助您以大量方式建立保留標籤，並以保留標籤原則發佈。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-108">Use the information, template files and examples, and script in this article to help you bulk-create retention labels and publish them in retention label policies.</span></span> <span data-ttu-id="ef6b0-109">然後，保留標籤可 [由系統管理員及使用者套用](create-apply-retention-labels.md#how-to-apply-published-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-109">Then, the retention labels can be [applied by administrators and users](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span></span>

<span data-ttu-id="ef6b0-110">提供的指示不支援自動套用的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-110">The supplied instructions don't support retention labels that are auto-applied.</span></span>

<span data-ttu-id="ef6b0-111">概觀：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-111">Overview:</span></span> 

1. <span data-ttu-id="ef6b0-112">在 Excel 中建立保留標籤清單，以及其保留標籤原則清單。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-112">In Excel, create a list of your retention labels and a list of their retention label policies.</span></span>

2. <span data-ttu-id="ef6b0-113">使用 PowerShell，在這些清單中建立保留標籤和保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-113">Use PowerShell to create the retention labels and retention label policies in those lists.</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="ef6b0-114">免責聲明</span><span class="sxs-lookup"><span data-stu-id="ef6b0-114">Disclaimer</span></span>

<span data-ttu-id="ef6b0-115">在任何 Microsoft 標準支援程式或服務下，不支援本文中提供的範例指令碼。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-115">The sample scripts provided in this article aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="ef6b0-116">範例指令碼係依「現狀」提供，不含任何種類的擔保方式。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-116">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="ef6b0-117">Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-117">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="ef6b0-118">使用或操作範例指令碼和文件發生的所有風險，皆屬於您的責任。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-118">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="ef6b0-119">Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼或文件所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-119">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-the-retention-labels"></a><span data-ttu-id="ef6b0-120">步驟 1：建立 .csv 檔案以建立保留標籤</span><span class="sxs-lookup"><span data-stu-id="ef6b0-120">Step 1: Create a .csv file for the retention labels</span></span>

1. <span data-ttu-id="ef6b0-121">複製下列用於範本的範例 .csv 檔案，以及用於四個不同保留標籤的範例專案，並將其貼到 Excel 中。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-121">Copy the following sample .csv file for a template and example entries for four different retention labels, and paste them into Excel.</span></span> 

2. <span data-ttu-id="ef6b0-122">資料剖析： **資料** 索引標籤 \> **資料行的文字** \> **分隔符號** \> **逗號** \> **一般**</span><span class="sxs-lookup"><span data-stu-id="ef6b0-122">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="ef6b0-123">將範例取代為您自行保留標籤和設定的專案。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-123">Replace the examples with entries for your own retention labels and settings.</span></span> <span data-ttu-id="ef6b0-124">如需參數值的詳細資訊，請參閱 [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511)。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-124">For more information about the parameter values, see [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span></span>

3. <span data-ttu-id="ef6b0-125">將工作表另存為 .csv 檔案，以便在後續步驟中輕鬆找到。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-125">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="ef6b0-126">例如：C: \>Scripts\Labels.csv</span><span class="sxs-lookup"><span data-stu-id="ef6b0-126">For example: C:\>Scripts\Labels.csv</span></span>

  
<span data-ttu-id="ef6b0-127">附註：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-127">Notes:</span></span>

- <span data-ttu-id="ef6b0-p106">如果 .csv 檔案包含的保留標籤與已存在的保留標籤同名，則指令碼會略過建立該保留標籤。不會建立重複的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-p106">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label. No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="ef6b0-130">請勿變更或重新命名所提供範例 .csv 檔案中的欄標題，否則指令碼將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-130">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-labels"></a><span data-ttu-id="ef6b0-131">保留標籤的範例 .csv 檔案</span><span class="sxs-lookup"><span data-stu-id="ef6b0-131">Sample .csv file for retention labels</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-the-retention-label-policies"></a><span data-ttu-id="ef6b0-132">步驟 2：建立 .csv 檔案以建立保留標籤原則</span><span class="sxs-lookup"><span data-stu-id="ef6b0-132">Step 2: Create a .csv file for the retention label policies</span></span>

1. <span data-ttu-id="ef6b0-133">複製下列用於範本的範例 .csv 檔案，以及用於三個不同保留標籤原則的範例專案，並將其貼到 Excel 中。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-133">Copy the following sample .csv file for a template and example entries for three different retention label policies, and paste them into Excel.</span></span> 

2. <span data-ttu-id="ef6b0-134">資料剖析： **資料** 索引標籤 \> **資料行的文字** \> **分隔符號** \> **逗號** \> **一般**</span><span class="sxs-lookup"><span data-stu-id="ef6b0-134">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="ef6b0-135">將範例取代為您自行保留標籤原則和其設定的專案。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-135">Replace the examples with entries for your own retention label policies and their settings.</span></span> <span data-ttu-id="ef6b0-136">如需此 Cmdlet 參數值的詳細資訊，請參閱 [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy).</span></span>

3. <span data-ttu-id="ef6b0-137">將工作表另存為 .csv 檔案，以便在後續步驟中輕鬆找到。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-137">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="ef6b0-138">例如：`<path>Policies.csv`</span><span class="sxs-lookup"><span data-stu-id="ef6b0-138">For example: `<path>Policies.csv`</span></span>


<span data-ttu-id="ef6b0-139">附註：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-139">Notes:</span></span>
  
- <span data-ttu-id="ef6b0-p109">如果 .csv 檔案包含的保留標籤原則與已存在的保留標籤原則同名，則指令碼會略過建立該保留標籤原則。不會建立重複的保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-p109">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy. No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="ef6b0-142">請勿變更或重新命名所提供範例 .csv 檔案中的欄標題，否則指令碼將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-142">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-policies"></a><span data-ttu-id="ef6b0-143">保留原則的範例 .csv 檔案</span><span class="sxs-lookup"><span data-stu-id="ef6b0-143">Sample .csv file for retention policies</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="ef6b0-144">步驟 3：建立 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="ef6b0-144">Step 3: Create the PowerShell script</span></span>

1. <span data-ttu-id="ef6b0-145">將以下 PowerShell 指令碼複製並貼到 [記事本] 中。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-145">Copy and paste the following PowerShell script into Notepad.</span></span>

2. <span data-ttu-id="ef6b0-146">將檔案使用 **.ps1** 的副檔名儲存在容易找到的位置。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-146">Save the file by using a file name extension of **.ps1** in a location that's easy to find.</span></span> <span data-ttu-id="ef6b0-147">例如：`<path>CreateRetentionSchedule.ps1`</span><span class="sxs-lookup"><span data-stu-id="ef6b0-147">For example: `<path>CreateRetentionSchedule.ps1`</span></span>

<span data-ttu-id="ef6b0-148">附註：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-148">Notes:</span></span>

- <span data-ttu-id="ef6b0-149">指令碼會提示您提供前兩個步驟建立的兩個來源檔案：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-149">The script prompts you to provide the two source files that you created in the previous two steps:</span></span>
    - <span data-ttu-id="ef6b0-150">如果您沒有指定要建立保留標籤的來源檔案，指令碼會繼續開啟，以建立保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-150">If you don't specify the source file to create the retention labels, the script moves on to create the retention label policies.</span></span> 
    - <span data-ttu-id="ef6b0-151">如果您沒有指定來源檔案來建立保留標籤原則，指令碼只會建立保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-151">If you don't specify the source file to create the retention label policies, the script creates the retention labels only.</span></span>

- <span data-ttu-id="ef6b0-152">指令碼會產生記錄檔，記錄執行的每個動作以及動作是否成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-152">The script generates a log file that records each action it took and whether the action succeeded or failed.</span></span> <span data-ttu-id="ef6b0-153">如需相關指示，請參閱最後一個步驟，瞭解如何找出此記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-153">See the final step for instructions how to locate this log file.</span></span>

### <a name="powershell-script"></a><span data-ttu-id="ef6b0-154">PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="ef6b0-154">PowerShell script</span></span>

```Powershell
<#
. Steps: Import and publish retention labels
    ○ Load retention labels csv file 
    ○ Validate csv file input
    ○ Create retention labels
    ○ Create retention policies
    ○ Publish retention labels for the policies
    ○ Generate the log for retention labels and policies creation
    ○ Generate the csv result for the labels and policies created
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is written to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is written to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-run-the-powershell-script"></a><span data-ttu-id="ef6b0-155">步驟 4：執行 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="ef6b0-155">Step 4: Run the PowerShell script</span></span>

<span data-ttu-id="ef6b0-156">首先，[連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-156">First, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="ef6b0-157">然後，執行建立並發佈保留標籤的指令碼：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-157">Then, run the script that creates and publishes the retention labels:</span></span>
  
1. <span data-ttu-id="ef6b0-158">在安全性與合規性中心 PowerShell 工作階段中，輸入路徑，後面跟著字元 `.\` 和指令碼的檔案名稱，然後按 ENTER 以執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-158">In your Security & Compliance Center PowerShell session, enter the path, followed by the characters `.\` and the file name of the script, and then press ENTER to run the script.</span></span> <span data-ttu-id="ef6b0-159">例如：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-159">For example:</span></span>
    
    ```powershell
    <path>.\CreateRetentionSchedule.ps1
    ```

2. <span data-ttu-id="ef6b0-160">指令碼會提示您輸入前面步驟建立的 .csv 檔案位置。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-160">The script prompts you for the locations of the .csv files that you created in the previous steps.</span></span> <span data-ttu-id="ef6b0-161">輸入路徑，後面跟著字元 `.\` 和 .csv 檔案的檔案名稱，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-161">Enter the path, followed by the characters `.\` and file name of the .csv file, and then press ENTER.</span></span> <span data-ttu-id="ef6b0-162">例如，針對第一個提示：</span><span class="sxs-lookup"><span data-stu-id="ef6b0-162">For example, for the first prompt:</span></span>
    
    ```powershell
    <path>.\Labels.csv
    ```

## <a name="step-5-view-the-log-file-with-the-results"></a><span data-ttu-id="ef6b0-163">步驟 5：檢視記錄檔與結果</span><span class="sxs-lookup"><span data-stu-id="ef6b0-163">Step 5: View the log file with the results</span></span>

<span data-ttu-id="ef6b0-164">使用指令碼建立的記錄檔來檢查結果，並找出任何需要解決的失敗。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-164">Use the log file that the script created to check the results and identify any failures that need resolving.</span></span>

<span data-ttu-id="ef6b0-165">您可以在下列位置找到記錄檔，但範例檔案名稱的位數可能會有所差異。</span><span class="sxs-lookup"><span data-stu-id="ef6b0-165">You can find the log file at the following location, although the digits in the example file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```


