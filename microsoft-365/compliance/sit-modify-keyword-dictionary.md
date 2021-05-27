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
# <a name="modify-a-keyword-dictionary"></a>修改關鍵字字典

您可能需要修改您其中一個關鍵字字典中的關鍵字，或修改其中一個內建字典。 您可以透過 PowerShell 或「規範中心」來執行這項作業。

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>在規範中心修改關鍵字字典

關鍵字字典可以像或是 `Primary elements` `Supporting elements` 機密資訊類型 (SIT) 模式中使用。 您可以在建立 SIT 或現有的 SIT 時編輯關鍵字字典。 例如，編輯現有的關鍵字字典：

1. 開啟具有您要更新之關鍵字字典的模式。
2. 找到您要更新的關鍵字字典，然後選擇 [編輯]。 
3.  進行編輯，每行使用一個關鍵字。

![螢幕擷取畫面編輯關鍵字](../media/edit-keyword-dictionary.png)

4. 選擇 `Done` 。

## <a name="modify-a-keyword-dictionary-using-powershell"></a>使用 PowerShell 修改關鍵字字典 

在此範例中，我們會在 PowerShell 中修改一些字詞，將字詞儲存在本機，使得您可以在編輯器中加以修改，然後就地更新之前的字詞。 

首先，擷取字典物件：
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

列印 `$dict` 會顯示各種不同的變數。 關鍵字本身會儲存在後端的物件中，但 `$dict.KeywordDictionary` 包含它們的字串表示，您將用來修改字典。 

在修改字典之前，您必須使用 `.split(',')` 方法，將字詞字串重新轉換成陣列。 然後您會使用 `.trim()` 方法清除關鍵字之間不想要的空格，只留下要使用的關鍵字。 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

現在您將從字典中移除一些字詞。因為範例字典只有幾個關鍵字，所以您可以輕鬆地略過，直接匯出字典，並在 [記事本] 中編輯該字典，但字典通常包含大量文字，因此您必須先學習此方法才能在 PowerShell 中輕鬆地編輯。
  
在最後一個步驟中，您已將關鍵字儲存到陣列。有幾種方法可[從陣列中移除字詞](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))，但直接方法為建立您要從字典中移除之字詞的陣列，然後只將不在要移除之字詞清單中的字典字詞複製到其中。
  
執行命令 `$terms` 來顯示目前的字詞清單。命令的輸出看起來像這樣： 
  
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

執行下列命令來指定您想要移除的字詞：
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

執行下列命令來實際移除清單中的字詞：
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

執行命令 `$updatedTerms` 來顯示已更新的字詞清單。命令的輸出看起來像這樣 (已移除指定的字詞)： 
  
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

現在只需開啟檔案、新增其他字詞，並以 Unicode 編碼 (UTF-16) 儲存。現在，您將上傳更新的字詞並在原處更新字典。
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

現在字典已在原處更新。 `Identity` 欄位會採用字典的名稱。 如果您也想要使用 `set-` Cmdlet 來變更字典的名稱，只需將 `-Name` 參數與新的字典名稱新增至其上即可。 

另請參閱
- [建立關鍵字字典](create-a-keyword-dictionary.md)
- [建立自訂的敏感性資訊類型](create-a-custom-sensitive-information-type.md)
