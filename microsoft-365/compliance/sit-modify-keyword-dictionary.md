---
title: 修改關鍵字字典
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
description: 瞭解如何在「Microsoft 365 規範中心」中修改關鍵字字典。
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685202"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="a6f7d-103">修改關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="a6f7d-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="a6f7d-104">您可能需要修改您其中一個關鍵字字典中的關鍵字，或修改其中一個內建字典。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="a6f7d-105">您可以透過 PowerShell 或「規範中心」來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="a6f7d-106">在規範中心修改關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="a6f7d-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="a6f7d-107">關鍵字字典可以像或是 `Primary elements` `Supporting elements` 機密資訊類型 (SIT) 模式中使用。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="a6f7d-108">您可以在建立 SIT 或現有的 SIT 時編輯關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="a6f7d-109">例如，編輯現有的關鍵字字典：</span><span class="sxs-lookup"><span data-stu-id="a6f7d-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="a6f7d-110">開啟具有您要更新之關鍵字字典的模式。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="a6f7d-111">找到您要更新的關鍵字字典，然後選擇 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="a6f7d-112">進行編輯，每行使用一個關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-112">Make your edits, using one keyword per line.</span></span>

![螢幕擷取畫面編輯關鍵字](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="a6f7d-114">選擇 `Done` 。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="a6f7d-115">使用 PowerShell 修改關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="a6f7d-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="a6f7d-116">在此範例中，我們會在 PowerShell 中修改一些字詞，將字詞儲存在本機，使得您可以在編輯器中加以修改，然後就地更新之前的字詞。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="a6f7d-117">首先，擷取字典物件：</span><span class="sxs-lookup"><span data-stu-id="a6f7d-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="a6f7d-118">列印 `$dict` 會顯示各種不同的變數。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="a6f7d-119">關鍵字本身會儲存在後端的物件中，但 `$dict.KeywordDictionary` 包含它們的字串表示，您將用來修改字典。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="a6f7d-120">在修改字典之前，您必須使用 `.split(',')` 方法，將字詞字串重新轉換成陣列。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="a6f7d-121">然後您會使用 `.trim()` 方法清除關鍵字之間不想要的空格，只留下要使用的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="a6f7d-p105">現在您將從字典中移除一些字詞。因為範例字典只有幾個關鍵字，所以您可以輕鬆地略過，直接匯出字典，並在 [記事本] 中編輯該字典，但字典通常包含大量文字，因此您必須先學習此方法才能在 PowerShell 中輕鬆地編輯。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="a6f7d-p106">在最後一個步驟中，您已將關鍵字儲存到陣列。有幾種方法可[從陣列中移除字詞](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))，但直接方法為建立您要從字典中移除之字詞的陣列，然後只將不在要移除之字詞清單中的字典字詞複製到其中。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="a6f7d-p107">執行命令 `$terms` 來顯示目前的字詞清單。命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="a6f7d-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="a6f7d-128">執行下列命令來指定您想要移除的字詞：</span><span class="sxs-lookup"><span data-stu-id="a6f7d-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="a6f7d-129">執行下列命令來實際移除清單中的字詞：</span><span class="sxs-lookup"><span data-stu-id="a6f7d-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="a6f7d-p108">執行命令 `$updatedTerms` 來顯示已更新的字詞清單。命令的輸出看起來像這樣 (已移除指定的字詞)：</span><span class="sxs-lookup"><span data-stu-id="a6f7d-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="a6f7d-p109">現在只需開啟檔案、新增其他字詞，並以 Unicode 編碼 (UTF-16) 儲存。現在，您將上傳更新的字詞並在原處更新字典。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="a6f7d-134">現在字典已在原處更新。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="a6f7d-135">`Identity` 欄位會採用字典的名稱。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="a6f7d-136">如果您也想要使用 `set-` Cmdlet 來變更字典的名稱，只需將 `-Name` 參數與新的字典名稱新增至其上即可。</span><span class="sxs-lookup"><span data-stu-id="a6f7d-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="a6f7d-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a6f7d-137">See Also</span></span>
- [<span data-ttu-id="a6f7d-138">建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="a6f7d-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="a6f7d-139">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="a6f7d-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
