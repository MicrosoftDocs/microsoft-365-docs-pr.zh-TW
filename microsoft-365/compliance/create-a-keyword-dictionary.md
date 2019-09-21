---
title: 建立關鍵字字典
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/11/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 識別敏感資訊有時會需要尋找關鍵字，尤其在識別泛用內容 (例如醫療保健相關的通訊) 或不適當或明確的語言時更是需要。儘管您可以建立敏感資訊類型的關鍵字清單，但關鍵字清單的大小會受到限制，而且需要修改 XML 才能建立或編輯它們。關鍵字字典可提供更簡單的關鍵字管理以及更為龐大的關鍵字規模，每部字典最多可支援 100,000 個字詞。
ms.openlocfilehash: 5e99cad328115ad6b49982ea4c5749cdea6e43ed
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076527"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="52fd2-105">建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="52fd2-105">Create a keyword dictionary</span></span>

<span data-ttu-id="52fd2-106">在 Office 365 中的資料遺失防護 (DLP) 可以識別、 監視和保護機密資訊。</span><span class="sxs-lookup"><span data-stu-id="52fd2-106">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information.</span></span> <span data-ttu-id="52fd2-107">識別敏感資訊有時需要尋找關鍵字，特別是當識別一般內容 （例如醫療保健相關的通訊） 或不當或明確的語言。</span><span class="sxs-lookup"><span data-stu-id="52fd2-107">Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="52fd2-108">雖然您可以建立關鍵字清單中的敏感資訊類型，關鍵字清單大小限制，且需要修改 XML，才能建立或編輯它們。</span><span class="sxs-lookup"><span data-stu-id="52fd2-108">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="52fd2-109">關鍵字字典提供更簡單管理的關鍵字，並在大規模地，支援最多 100000 的字詞，每個字典。</span><span class="sxs-lookup"><span data-stu-id="52fd2-109">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="52fd2-110">建立關鍵字字典的基本步驟</span><span class="sxs-lookup"><span data-stu-id="52fd2-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="52fd2-p103">字典的關鍵字可以來自各種來源，最常來自在服務中或是透過 PowerShell Cmdlet 匯入的檔案 (例如 .csv 或 .txt 清單)、來自您直接在 PowerShell Cmdlet 中輸入的清單，或來自現有的字典。當建立關鍵字字典時，您會依照相同的核心步驟：</span><span class="sxs-lookup"><span data-stu-id="52fd2-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="52fd2-113">使用**安全性 & 合規性中心**([https://protection.office.com](https://protection.office.com)) 或連線至**Office 365 安全性&amp;合規性中心 PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="52fd2-113">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Office 365 Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="52fd2-114">**定義，或從您預定的來源載入關鍵字**。</span><span class="sxs-lookup"><span data-stu-id="52fd2-114">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="52fd2-115">精靈及指令程式同時會接受逗點分隔的清單來建立自訂的關鍵字字典，因此這個步驟將而異稍微關鍵字來自何處的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="52fd2-115">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="52fd2-116">一旦載入，就會將它們編碼並轉換為位元組陣列，然後再匯入它們。</span><span class="sxs-lookup"><span data-stu-id="52fd2-116">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="52fd2-117">**建立字典**。</span><span class="sxs-lookup"><span data-stu-id="52fd2-117">**Create your dictionary**.</span></span> <span data-ttu-id="52fd2-118">選擇的名稱和描述，並建立您的字典。</span><span class="sxs-lookup"><span data-stu-id="52fd2-118">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="52fd2-119">建立關鍵字字典使用安全性 & 合規性中心</span><span class="sxs-lookup"><span data-stu-id="52fd2-119">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="52fd2-120">請使用下列步驟來建立和匯入自訂字典的關鍵字：</span><span class="sxs-lookup"><span data-stu-id="52fd2-120">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="52fd2-121">連線到安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="52fd2-121">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="52fd2-122">瀏覽至 [分類] > [敏感性資訊類型]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-122">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="52fd2-123">選取 [建立]\*\*\*\*，然後輸入您的敏感性資訊類型的 [名稱]\*\*\*\* 和 [描述]\*\*\*\*，然後選取 [下一步]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="52fd2-123">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="52fd2-124">選取 [新增項目]\*\*\*\*，然後在 [偵測內容包含]\*\*\*\* 下拉式清單中選取 [字典 (大型關鍵字)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-124">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="52fd2-125">選取 [新增字典]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="52fd2-125">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="52fd2-126">在 [搜尋] 控制項中，選取 [您可以在這裡建立新的關鍵字字典]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-126">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="52fd2-127">輸入自訂字典的 [名稱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-127">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="52fd2-128">選取 [匯入]\*\*\*\*，然後根據您的關鍵字檔案類型選取 [從文字]\*\*\*\* 或 [從 csv]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-128">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="52fd2-129">在 [檔案] 對話方塊中，選取來自您的本機電腦或網路檔案共用的關鍵字檔案，然後選取 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-129">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="52fd2-130">選取 [儲存]\*\*\*\*，然後從 [關鍵字字典]\*\*\*\* 清單選取您的自訂字典。</span><span class="sxs-lookup"><span data-stu-id="52fd2-130">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="52fd2-131">選取 [新增]\*\*\*\*，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-131">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="52fd2-132">檢閱並完成敏感性資訊類型選取項目，然後選取 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52fd2-132">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="52fd2-133">使用 PowerShell 從檔案建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="52fd2-133">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="52fd2-134">通常當您需要建立大型字典，它是使用關鍵字從檔案或從其他來源匯出清單。</span><span class="sxs-lookup"><span data-stu-id="52fd2-134">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="52fd2-135">在此情況下，您將建立關鍵字字典包含清單的不當螢幕上的外部電子郵件的語言。</span><span class="sxs-lookup"><span data-stu-id="52fd2-135">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="52fd2-136">您必須先[連線至 Office 365 安全性&amp;合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="52fd2-136">You must first [connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="52fd2-137">將關鍵字複製到文字檔案，並確定每個關鍵字位於個別行。</span><span class="sxs-lookup"><span data-stu-id="52fd2-137">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="52fd2-p107">使用 Unicode 編碼來儲存檔案。在 [記事本] \> [另存新檔]\*\*\*\* \> [編碼]\*\*\*\* \> [Unicode]\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="52fd2-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="52fd2-140">執行下列 Cmdlet 將檔案讀成變數：</span><span class="sxs-lookup"><span data-stu-id="52fd2-140">Read the file into a variable by running this cmdlet:</span></span>
    
    ```
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="52fd2-141">執行下列 Cmdlet 來建立字典：</span><span class="sxs-lookup"><span data-stu-id="52fd2-141">Create the dictionary by running this cmdlet:</span></span>
    
    ```
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="52fd2-142">修改現有的關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="52fd2-142">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="52fd2-143">您可能需要修改您其中一個關鍵字字典中的關鍵字，或修改其中一個內建字典。</span><span class="sxs-lookup"><span data-stu-id="52fd2-143">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="52fd2-144">目前，您只可以使用 PowerShell 來更新自訂關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="52fd2-144">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="52fd2-145">例如，我們將修改在 PowerShell 中，某些字詞儲存條款在本機上時您可以在其中修改它們在編輯器中，並再就地更新前一個字詞。</span><span class="sxs-lookup"><span data-stu-id="52fd2-145">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="52fd2-146">首先，擷取字典物件：</span><span class="sxs-lookup"><span data-stu-id="52fd2-146">First, retrieve the dictionary object:</span></span>
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="52fd2-147">列印`$dict`會顯示各種不同的變數。</span><span class="sxs-lookup"><span data-stu-id="52fd2-147">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="52fd2-148">關鍵字本身會儲存在物件上後端]，但`$dict.KeywordDictionary`包含它們，讓您將用來修改的字典的字串表示法。</span><span class="sxs-lookup"><span data-stu-id="52fd2-148">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="52fd2-149">您修改的字典之前，您需要開啟回陣列使用的字詞字串`.split(',')`方法。</span><span class="sxs-lookup"><span data-stu-id="52fd2-149">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="52fd2-150">然後會清除之間的關鍵字不想要的空格`.trim()`方法，保留的關鍵字來使用。</span><span class="sxs-lookup"><span data-stu-id="52fd2-150">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="52fd2-p111">現在您將從字典中移除一些字詞。因為範例字典只有幾個關鍵字，所以您可以輕鬆地略過移除，直接匯出字典，並在 [記事本] 中編輯該字典，但字典通常包含大量文字，因此您首先將學習此方法，以在 PowerShell 中輕鬆地編輯它們。</span><span class="sxs-lookup"><span data-stu-id="52fd2-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="52fd2-p112">在最後一個步驟中，您已將關鍵字儲存到陣列。有幾種方法可[從陣列中移除字詞](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)) (英文)，但直接方法為建立您要從字典中移除之字詞的陣列，然後只將不在要移除之字詞清單中的字典字詞複製到其中。</span><span class="sxs-lookup"><span data-stu-id="52fd2-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="52fd2-p113">執行命令 `$terms` 來顯示目前的字詞清單。命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="52fd2-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="52fd2-157">執行下列命令來指定您想要移除的字詞：</span><span class="sxs-lookup"><span data-stu-id="52fd2-157">Run this command to specify the terms that you want to remove:</span></span>
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="52fd2-158">執行下列命令來實際移除清單中的字詞：</span><span class="sxs-lookup"><span data-stu-id="52fd2-158">Run this command to actually remove the terms from the list:</span></span>
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="52fd2-p114">執行命令 `$updatedTerms` 來顯示已更新的字詞清單。命令的輸出看起來像這樣 (已移除指定的字詞)：</span><span class="sxs-lookup"><span data-stu-id="52fd2-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="52fd2-p115">現在將字典儲存在本機，並再新增一些字詞。在 PowerShell 中，您可以直接在這裡新增字詞，但您仍需要在本機匯出檔案，以確保它是以 Unicode 編碼儲存，且包含 BOM。</span><span class="sxs-lookup"><span data-stu-id="52fd2-p115">Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.</span></span>
  
<span data-ttu-id="52fd2-163">執行下列命令，將字典儲存在本機：</span><span class="sxs-lookup"><span data-stu-id="52fd2-163">Save the dictionary locally by running the following:</span></span>
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="52fd2-p116">現在只需開啟檔案、新增其他字詞，並以 Unicode 編碼 (UTF-16) 儲存。現在，您將上傳更新的字詞並適當地更新字典。</span><span class="sxs-lookup"><span data-stu-id="52fd2-p116">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="52fd2-p117">現在您已適當地更新字典。請注意，`Identity` 欄位會採用字典的名稱。如果您也想要使用 `set-` Cmdlet 來變更字典的名稱，只需將 `-Name` 參數與新的字典名稱新增至上述的命令即可。</span><span class="sxs-lookup"><span data-stu-id="52fd2-p117">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="52fd2-169">使用自訂敏感資訊類型和 DLP 原則中的關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="52fd2-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="52fd2-170">關鍵字字典可當作自訂機密資訊類型，比對需求的一部分，或為敏感資訊輸入本身。</span><span class="sxs-lookup"><span data-stu-id="52fd2-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="52fd2-171">兩者都需要您建立[自訂機密資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="52fd2-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="52fd2-172">遵循連結文件中的指示，建立敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="52fd2-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="52fd2-173">一旦您有 XML，您必須使用它的字典的 GUID 識別碼。</span><span class="sxs-lookup"><span data-stu-id="52fd2-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="52fd2-174">若要取得字典的身分識別，請執行下列命令，然後複製 **Identity** 屬性值：</span><span class="sxs-lookup"><span data-stu-id="52fd2-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="52fd2-175">此命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="52fd2-175">The output of the command looks like this:</span></span>
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

<span data-ttu-id="52fd2-p119">將身分識別貼入您的自訂敏感資訊類型的 XML 並上傳它。現在字典將出現在敏感資訊類型的清單中，而且您可以在原則中直接使用它，同時指定需要比對多少個關鍵字。</span><span class="sxs-lookup"><span data-stu-id="52fd2-p119">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```
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


