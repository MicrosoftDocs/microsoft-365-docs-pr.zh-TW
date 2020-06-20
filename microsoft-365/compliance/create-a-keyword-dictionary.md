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
# <a name="create-a-keyword-dictionary"></a>建立關鍵字字典

資料遺失防護（DLP）可以識別、監視和保護您的敏感資訊。 識別敏感資訊有時需要尋找關鍵字，尤其是在識別一般內容時（例如醫療保健相關的通訊）或不適當或明確的語言。 雖然您可以在機密資訊類型中建立關鍵字清單，但關鍵字清單大小有限，需要修改 XML 以建立或編輯。 關鍵字字典可提供更簡單的關鍵字管理，並以更大的比例來支援每個字典的100000字詞。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>建立關鍵字字典的基本步驟

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. 使用 [**安全性 & 規範中心** [https://protection.office.com](https://protection.office.com) ] （）或 [連線至**安全性與 &amp; 合規性中心] PowerShell**。
    
2. **定義或載入預定來源中的關鍵字**。 嚮導和指令程式都接受以逗號分隔的關鍵字清單，以建立自訂的關鍵字字典，所以此步驟會稍有不同，具體取決於關鍵字的來源位置。 一旦載入，就會將它們編碼並轉換為位元組陣列，然後再匯入它們。
    
3. **建立字典**。 選擇名稱和描述，然後建立字典。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>使用安全性 & 規範中心建立關鍵字字典

請使用下列步驟來建立和匯入自訂字典的關鍵字：

1. 連接至安全性 & 規範中心（ [https://protection.office.com](https://protection.office.com) ）。

2. 瀏覽至 [分類] > [敏感性資訊類型]****。

3. 選取 [建立]****，然後輸入您的敏感性資訊類型的 [名稱]**** 和 [描述]****，然後選取 [下一步]****

4. 選取 [新增項目]****，然後在 [偵測內容包含]**** 下拉式清單中選取 [字典 (大型關鍵字)]****。

5. 選取 [新增字典]****

6. 在 [搜尋] 控制項中，選取 [您可以在這裡建立新的關鍵字字典]****。

7. 輸入自訂字典的 [名稱]****。

8. 選取 [匯入]****，然後根據您的關鍵字檔案類型選取 [從文字]**** 或 [從 csv]****。

9. 在 [檔案] 對話方塊中，選取來自您的本機電腦或網路檔案共用的關鍵字檔案，然後選取 [開啟]****。

10. 選取 [儲存]****，然後從 [關鍵字字典]**** 清單選取您的自訂字典。

11. 選取 [新增]****，然後選取 [下一步]****。

12. 檢閱並完成敏感性資訊類型選取項目，然後選取 [完成]****。
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>使用 PowerShell 從檔案建立關鍵字字典

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. 將關鍵字複製到文字檔案，並確定每個關鍵字位於個別行。
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
3. 執行下列 Cmdlet 將檔案讀成變數：
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. 執行下列 Cmdlet 來建立字典：
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>修改現有的關鍵字字典

您可能需要修改您其中一個關鍵字字典中的關鍵字，或修改其中一個內建字典。 目前，您只可以使用 PowerShell 來更新自訂關鍵字字典。 

例如，我們將在 PowerShell 中修改一些字詞，並在本機儲存字詞，以在編輯器中修改，然後就地更新上述字詞。 

首先，擷取字典物件：
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

列印 `$dict` 會顯示不同的變數。 關鍵字本身會儲存在後端的物件中，但 `$dict.KeywordDictionary` 會包含它們的字串標記法，以供您用來修改字典。 

修改字典之前，您必須使用方法，將字詞的字串轉換回陣列 `.split(',')` 。 然後，您會使用方法清除關鍵字之間不想要的空格 `.trim()` ，只保留要使用的關鍵字。 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
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

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
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

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>使用自訂敏感資訊類型和 DLP 原則中的關鍵字字典

關鍵字字典可以做為自訂敏感資訊類型的符合性需求的一部分，或是自身的敏感資訊類型。 這兩者都需要您建立[自訂的機密資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。 依照連結的文章中的指示，建立敏感資訊類型。 當您有 XML 之後，您將需要字典的 GUID 識別碼才能使用它。
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

若要取得字典的身分識別，請執行下列命令，然後複製 **Identity** 屬性值： 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

此命令的輸出看起來像這樣：
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
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
