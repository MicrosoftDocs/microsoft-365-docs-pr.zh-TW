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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解在 Office 365 安全性 & 規範中心建立關鍵字字典的基本步驟。
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818052"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="cc038-103">建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="cc038-103">Create a keyword dictionary</span></span>

<span data-ttu-id="cc038-104">資料遺失防護（DLP）可以識別、監視和保護您的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="cc038-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive information.</span></span> <span data-ttu-id="cc038-105">識別敏感資訊有時需要尋找關鍵字，尤其是在識別一般內容時（例如醫療保健相關的通訊）或不適當或明確的語言。</span><span class="sxs-lookup"><span data-stu-id="cc038-105">Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="cc038-106">雖然您可以在機密資訊類型中建立關鍵字清單，但關鍵字清單大小有限，需要修改 XML 以建立或編輯。</span><span class="sxs-lookup"><span data-stu-id="cc038-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="cc038-107">關鍵字字典可提供更簡單的關鍵字管理，並以更大的比例來支援每個字典的100000字詞。</span><span class="sxs-lookup"><span data-stu-id="cc038-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="cc038-108">建立關鍵字字典的基本步驟</span><span class="sxs-lookup"><span data-stu-id="cc038-108">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="cc038-109">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span><span class="sxs-lookup"><span data-stu-id="cc038-109">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span></span> <span data-ttu-id="cc038-110">When you create a keyword dictionary, you follow the same core steps:</span><span class="sxs-lookup"><span data-stu-id="cc038-110">When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="cc038-111">使用 [**安全性 & 規範中心** [https://protection.office.com](https://protection.office.com) ] （）或 [連線至**安全性與 &amp; 合規性中心] PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="cc038-111">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="cc038-112">**定義或載入預定來源中的關鍵字**。</span><span class="sxs-lookup"><span data-stu-id="cc038-112">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="cc038-113">嚮導和指令程式都接受以逗號分隔的關鍵字清單，以建立自訂的關鍵字字典，所以此步驟會稍有不同，具體取決於關鍵字的來源位置。</span><span class="sxs-lookup"><span data-stu-id="cc038-113">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="cc038-114">一旦載入，就會將它們編碼並轉換為位元組陣列，然後再匯入它們。</span><span class="sxs-lookup"><span data-stu-id="cc038-114">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="cc038-115">**建立字典**。</span><span class="sxs-lookup"><span data-stu-id="cc038-115">**Create your dictionary**.</span></span> <span data-ttu-id="cc038-116">選擇名稱和描述，然後建立字典。</span><span class="sxs-lookup"><span data-stu-id="cc038-116">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="cc038-117">使用安全性 & 規範中心建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="cc038-117">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="cc038-118">請使用下列步驟來建立和匯入自訂字典的關鍵字：</span><span class="sxs-lookup"><span data-stu-id="cc038-118">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="cc038-119">連接至安全性 & 規範中心（ [https://protection.office.com](https://protection.office.com) ）。</span><span class="sxs-lookup"><span data-stu-id="cc038-119">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="cc038-120">瀏覽至 [分類] > [敏感性資訊類型]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-120">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="cc038-121">選取 [建立]\*\*\*\*，然後輸入您的敏感性資訊類型的 [名稱]\*\*\*\* 和 [描述]\*\*\*\*，然後選取 [下一步]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cc038-121">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="cc038-122">選取 [新增項目]\*\*\*\*，然後在 [偵測內容包含]\*\*\*\* 下拉式清單中選取 [字典 (大型關鍵字)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-122">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="cc038-123">選取 [新增字典]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cc038-123">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="cc038-124">在 [搜尋] 控制項中，選取 [您可以在這裡建立新的關鍵字字典]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-124">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="cc038-125">輸入自訂字典的 [名稱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-125">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="cc038-126">選取 [匯入]\*\*\*\*，然後根據您的關鍵字檔案類型選取 [從文字]\*\*\*\* 或 [從 csv]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-126">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="cc038-127">在 [檔案] 對話方塊中，選取來自您的本機電腦或網路檔案共用的關鍵字檔案，然後選取 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-127">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="cc038-128">選取 [儲存]\*\*\*\*，然後從 [關鍵字字典]\*\*\*\* 清單選取您的自訂字典。</span><span class="sxs-lookup"><span data-stu-id="cc038-128">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="cc038-129">選取 [新增]\*\*\*\*，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-129">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="cc038-130">檢閱並完成敏感性資訊類型選取項目，然後選取 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc038-130">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="cc038-131">使用 PowerShell 從檔案建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="cc038-131">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="cc038-132">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span><span class="sxs-lookup"><span data-stu-id="cc038-132">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="cc038-133">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span><span class="sxs-lookup"><span data-stu-id="cc038-133">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="cc038-134">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="cc038-134">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="cc038-135">將關鍵字複製到文字檔案，並確定每個關鍵字位於個別行。</span><span class="sxs-lookup"><span data-stu-id="cc038-135">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="cc038-136">Save the text file with Unicode encoding.</span><span class="sxs-lookup"><span data-stu-id="cc038-136">Save the text file with Unicode encoding.</span></span> <span data-ttu-id="cc038-137">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="cc038-137">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="cc038-138">執行下列 Cmdlet 將檔案讀成變數：</span><span class="sxs-lookup"><span data-stu-id="cc038-138">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="cc038-139">執行下列 Cmdlet 來建立字典：</span><span class="sxs-lookup"><span data-stu-id="cc038-139">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="cc038-140">修改現有的關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="cc038-140">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="cc038-141">您可能需要修改您其中一個關鍵字字典中的關鍵字，或修改其中一個內建字典。</span><span class="sxs-lookup"><span data-stu-id="cc038-141">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="cc038-142">目前，您只可以使用 PowerShell 來更新自訂關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="cc038-142">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="cc038-143">例如，我們將在 PowerShell 中修改一些字詞，並在本機儲存字詞，以在編輯器中修改，然後就地更新上述字詞。</span><span class="sxs-lookup"><span data-stu-id="cc038-143">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="cc038-144">首先，擷取字典物件：</span><span class="sxs-lookup"><span data-stu-id="cc038-144">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="cc038-145">列印 `$dict` 會顯示不同的變數。</span><span class="sxs-lookup"><span data-stu-id="cc038-145">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="cc038-146">關鍵字本身會儲存在後端的物件中，但 `$dict.KeywordDictionary` 會包含它們的字串標記法，以供您用來修改字典。</span><span class="sxs-lookup"><span data-stu-id="cc038-146">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="cc038-147">修改字典之前，您必須使用方法，將字詞的字串轉換回陣列 `.split(',')` 。</span><span class="sxs-lookup"><span data-stu-id="cc038-147">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="cc038-148">然後，您會使用方法清除關鍵字之間不想要的空格 `.trim()` ，只保留要使用的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="cc038-148">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="cc038-149">Now you'll remove some terms from the dictionary.</span><span class="sxs-lookup"><span data-stu-id="cc038-149">Now you'll remove some terms from the dictionary.</span></span> <span data-ttu-id="cc038-150">Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc038-150">Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="cc038-151">In the last step, you saved the keywords to an array.</span><span class="sxs-lookup"><span data-stu-id="cc038-151">In the last step, you saved the keywords to an array.</span></span> <span data-ttu-id="cc038-152">There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span><span class="sxs-lookup"><span data-stu-id="cc038-152">There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="cc038-153">Run the command  `$terms` to show the current list of terms.</span><span class="sxs-lookup"><span data-stu-id="cc038-153">Run the command  `$terms` to show the current list of terms.</span></span> <span data-ttu-id="cc038-154">The output of the command looks like this:</span><span class="sxs-lookup"><span data-stu-id="cc038-154">The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="cc038-155">執行下列命令來指定您想要移除的字詞：</span><span class="sxs-lookup"><span data-stu-id="cc038-155">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="cc038-156">執行下列命令來實際移除清單中的字詞：</span><span class="sxs-lookup"><span data-stu-id="cc038-156">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="cc038-157">Run the command  `$updatedTerms` to show the updated list of terms.</span><span class="sxs-lookup"><span data-stu-id="cc038-157">Run the command  `$updatedTerms` to show the updated list of terms.</span></span> <span data-ttu-id="cc038-158">The output of the command looks like this (the specified terms have been removed):</span><span class="sxs-lookup"><span data-stu-id="cc038-158">The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="cc038-159">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="cc038-159">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16).</span></span> <span data-ttu-id="cc038-160">Now you'll upload the updated terms and update the dictionary in place.</span><span class="sxs-lookup"><span data-stu-id="cc038-160">Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="cc038-161">Now the dictionary has been updated in place.</span><span class="sxs-lookup"><span data-stu-id="cc038-161">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="cc038-162">Note that the  `Identity` field takes the name of the dictionary.</span><span class="sxs-lookup"><span data-stu-id="cc038-162">Note that the  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="cc038-163">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span><span class="sxs-lookup"><span data-stu-id="cc038-163">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="cc038-164">使用自訂敏感資訊類型和 DLP 原則中的關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="cc038-164">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="cc038-165">關鍵字字典可以做為自訂敏感資訊類型的符合性需求的一部分，或是自身的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cc038-165">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="cc038-166">這兩者都需要您建立[自訂的機密資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="cc038-166">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="cc038-167">依照連結的文章中的指示，建立敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cc038-167">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="cc038-168">當您有 XML 之後，您將需要字典的 GUID 識別碼才能使用它。</span><span class="sxs-lookup"><span data-stu-id="cc038-168">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="cc038-169">若要取得字典的身分識別，請執行下列命令，然後複製 **Identity** 屬性值：</span><span class="sxs-lookup"><span data-stu-id="cc038-169">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="cc038-170">此命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="cc038-170">The output of the command looks like this:</span></span>
  
<span data-ttu-id="cc038-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="cc038-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="cc038-172">Paste the identity into your custom sensitive information type's XML and upload it.</span><span class="sxs-lookup"><span data-stu-id="cc038-172">Paste the identity into your custom sensitive information type's XML and upload it.</span></span> <span data-ttu-id="cc038-173">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span><span class="sxs-lookup"><span data-stu-id="cc038-173">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
