---
title: 建立關鍵字字典
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解在 Office 365 安全性與合規性中心建立關鍵字字典的基本步驟。
ms.openlocfilehash: 24f6bb636c702438be8ca9520c6523031f297410
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683760"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="b46a5-103">建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="b46a5-103">Create a keyword dictionary</span></span>

<span data-ttu-id="b46a5-104">資料外洩防護 (DLP) 可識別、監視及保護您的敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="b46a5-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="b46a5-105">識別敏感性項目有時需要尋找關鍵字，特別是在識別一般內容 (例如醫療保健相關通訊)，或是不適當或偏激的言語。</span><span class="sxs-lookup"><span data-stu-id="b46a5-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="b46a5-106">雖然您可以在敏感性資訊類型中建立關鍵字清單，但關鍵字清單的大小有限，且需要修改 XML 來建立或編輯。</span><span class="sxs-lookup"><span data-stu-id="b46a5-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="b46a5-107">關鍵字字典提供更簡單的關鍵字管理並具有更大的規模，在字典中最多可支援 1 ＭB 的字詞 (壓縮後) 及任何語言。</span><span class="sxs-lookup"><span data-stu-id="b46a5-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="b46a5-108">壓縮後的租用戶限制也是 1 MB。</span><span class="sxs-lookup"><span data-stu-id="b46a5-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="b46a5-109">1MB 的壓縮後限制表示整個租用戶的所有字典加起來可以接近 1 百萬個字元。</span><span class="sxs-lookup"><span data-stu-id="b46a5-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="b46a5-110">關鍵字字典限制</span><span class="sxs-lookup"><span data-stu-id="b46a5-110">Keyword dictionary limits</span></span>

<span data-ttu-id="b46a5-111">每個租用最多可以建立 50 個基於關鍵字字典的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b46a5-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="b46a5-112">若要了解租用戶中有多少關鍵字字典，請利用 [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 中的程序，連線到您的租用戶並執行此 PowerShell 指令碼。</span><span class="sxs-lookup"><span data-stu-id="b46a5-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="b46a5-113">建立關鍵字字典的基本步驟</span><span class="sxs-lookup"><span data-stu-id="b46a5-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="b46a5-p103">字典的關鍵字可以來自各種來源，最常來自在服務中或是透過 PowerShell Cmdlet 匯入的檔案 (例如 .csv 或 .txt 清單)、來自您直接在 PowerShell Cmdlet 中輸入的清單，或來自現有的字典。當建立關鍵字字典時，您會依照相同的核心步驟：</span><span class="sxs-lookup"><span data-stu-id="b46a5-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="b46a5-116">使用 **安全性與合規性中心** ([https://protection.office.com](https://protection.office.com)) 或連線到 **安全性與合規性中心 PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="b46a5-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="b46a5-117">**從預期的來源定義或載入關鍵字**。</span><span class="sxs-lookup"><span data-stu-id="b46a5-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="b46a5-118">精靈和 Cmdlet 都會接受以逗點分隔的關鍵字清單，用來建立自訂關鍵字字典，因此這個步驟會根據您的關鍵字來自何處而略有不同。</span><span class="sxs-lookup"><span data-stu-id="b46a5-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="b46a5-119">一旦載入，就會將它們編碼並轉換為位元組陣列，然後再匯入它們。</span><span class="sxs-lookup"><span data-stu-id="b46a5-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="b46a5-120">**建立字典**。</span><span class="sxs-lookup"><span data-stu-id="b46a5-120">**Create your dictionary**.</span></span> <span data-ttu-id="b46a5-121">選擇名稱和描述，然後建立字典。</span><span class="sxs-lookup"><span data-stu-id="b46a5-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="b46a5-122">使用安全性與合規性中心建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="b46a5-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="b46a5-123">請使用下列步驟來建立和匯入自訂字典的關鍵字：</span><span class="sxs-lookup"><span data-stu-id="b46a5-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="b46a5-124">連線到安全性與合規性中心 ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="b46a5-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="b46a5-125">瀏覽至 [分類] > [敏感性資訊類型]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="b46a5-126">選取 [建立]，然後輸入您的敏感性資訊類型的 [名稱] 和 [描述]，然後選取 [下一步]</span><span class="sxs-lookup"><span data-stu-id="b46a5-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="b46a5-127">選取 [新增項目]，然後在 [偵測內容包含] 下拉式清單中選取 [字典 (大型關鍵字)]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="b46a5-128">選取 [新增字典]</span><span class="sxs-lookup"><span data-stu-id="b46a5-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="b46a5-129">在 [搜尋] 控制項中，選取 [您可以在這裡建立新的關鍵字字典]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="b46a5-130">輸入自訂字典的 [名稱]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="b46a5-131">選取 [匯入]，然後根據您的關鍵字檔案類型選取 [從文字] 或 [從 csv]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="b46a5-132">在 [檔案] 對話方塊中，選取來自您的本機電腦或網路檔案共用的關鍵字檔案，然後選取 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="b46a5-133">選取 [儲存]，然後從 [關鍵字字典] 清單選取您的自訂字典。</span><span class="sxs-lookup"><span data-stu-id="b46a5-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="b46a5-134">選取 [新增]，然後選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="b46a5-135">檢閱並完成敏感性資訊類型選取項目，然後選取 [完成]。</span><span class="sxs-lookup"><span data-stu-id="b46a5-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="b46a5-136">使用 PowerShell 從檔案建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="b46a5-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="b46a5-137">當您需要建立大型字典時，通常會使用來自檔案或從其他來源匯出清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="b46a5-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="b46a5-138">在此情況下，您會建立一個關鍵字字典，其中包含要在外部電子郵件中過濾的不適當言語清單。</span><span class="sxs-lookup"><span data-stu-id="b46a5-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="b46a5-139">必須先 [連線到安全性 &amp; 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b46a5-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="b46a5-140">將關鍵字複製到文字檔案，並確定每個關鍵字位於個別行。</span><span class="sxs-lookup"><span data-stu-id="b46a5-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="b46a5-p107">使用 Unicode 編碼來儲存檔案。在 [記事本] \> [另存新檔] \> [編碼] \> [Unicode] 中。</span><span class="sxs-lookup"><span data-stu-id="b46a5-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="b46a5-143">執行下列 Cmdlet 將檔案讀成變數：</span><span class="sxs-lookup"><span data-stu-id="b46a5-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="b46a5-144">執行下列 Cmdlet 來建立字典：</span><span class="sxs-lookup"><span data-stu-id="b46a5-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="b46a5-145">使用自訂敏感資訊類型和 DLP 原則中的關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="b46a5-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="b46a5-146">關鍵字字典可做為自訂敏感性資訊類型的符合需求一部分，或做為敏感性資訊類型本身。</span><span class="sxs-lookup"><span data-stu-id="b46a5-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="b46a5-147">兩者都需要您建立[自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b46a5-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="b46a5-148">按照連結文章中的指示建立敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b46a5-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="b46a5-149">當您有 XML 之後，就需要字典的 GUID 識別碼來使用它。</span><span class="sxs-lookup"><span data-stu-id="b46a5-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="b46a5-150">若要取得字典的身分識別，請執行下列命令，然後複製 **Identity** 屬性值：</span><span class="sxs-lookup"><span data-stu-id="b46a5-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="b46a5-151">此命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="b46a5-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="b46a5-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="b46a5-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="b46a5-p109">將身分識別貼入您的自訂敏感資訊類型的 XML 並上傳它。現在字典將出現在敏感資訊類型的清單中，而且您可以在原則中直接使用它，同時指定需要比對多少個關鍵字。</span><span class="sxs-lookup"><span data-stu-id="b46a5-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```

> [!NOTE]
> <span data-ttu-id="b46a5-155">Microsoft 365 資訊保護在預覽版中支援下列雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="b46a5-155">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="b46a5-156">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="b46a5-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="b46a5-157">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="b46a5-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="b46a5-158">韓文</span><span class="sxs-lookup"><span data-stu-id="b46a5-158">Korean</span></span>
> - <span data-ttu-id="b46a5-159">日文</span><span class="sxs-lookup"><span data-stu-id="b46a5-159">Japanese</span></span>
>
><span data-ttu-id="b46a5-160">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b46a5-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="b46a5-161">如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="b46a5-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
