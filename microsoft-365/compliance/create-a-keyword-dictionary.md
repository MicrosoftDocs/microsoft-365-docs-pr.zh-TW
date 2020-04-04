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
description: 識別敏感資訊有時會需要尋找關鍵字，尤其在識別泛用內容 (例如醫療保健相關的通訊) 或不適當或明確的語言時更是需要。儘管您可以建立敏感資訊類型的關鍵字清單，但關鍵字清單的大小會受到限制，而且需要修改 XML 才能建立或編輯它們。關鍵字字典可提供更簡單的關鍵字管理以及更為龐大的關鍵字規模，每部字典最多可支援 100,000 個字詞。
ms.openlocfilehash: 2ae63a9bf10ee43b3f761d8c60652c7c2a5e8b5f
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141508"
---
# <a name="create-a-keyword-dictionary"></a>建立關鍵字字典

Office 365 中的資料遺失防護（DLP）可以識別、監視和保護您的敏感資訊。識別敏感資訊有時需要尋找關鍵字，尤其是在識別一般內容時（例如醫療保健相關的通訊）或不適當或明確的語言。雖然您可以在機密資訊類型中建立關鍵字清單，但關鍵字清單大小有限，需要修改 XML 以建立或編輯。關鍵字字典提供更簡單的關鍵字管理，並以更大的比例來支援每個字典中的字詞的100KB。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>建立關鍵字字典的基本步驟

字典的關鍵字可以來自各種來源，最常來自在服務中或是透過 PowerShell Cmdlet 匯入的檔案 (例如 .csv 或 .txt 清單)、來自您直接在 PowerShell Cmdlet 中輸入的清單，或來自現有的字典。當建立關鍵字字典時，您會依照相同的核心步驟：
  
1. 使用**安全性 & 規範中心**（[https://protection.office.com](https://protection.office.com)）或連線到**Office 365 安全性&amp;與合規性中心 PowerShell**。
    
2. **定義或載入預定來源中的關鍵字**。 嚮導和指令程式都接受以逗號分隔的關鍵字清單，以建立自訂的關鍵字字典，所以此步驟會稍有不同，具體取決於關鍵字的來源位置。 一旦載入，就會將它們編碼並轉換為位元組陣列，然後再匯入它們。
    
3. **建立字典**。 選擇名稱和描述，然後建立字典。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>使用安全性 & 規範中心建立關鍵字字典

請使用下列步驟來建立和匯入自訂字典的關鍵字：

1. 連接至安全性 & 規範中心（[https://protection.office.com](https://protection.office.com)）。

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

通常當您需要建立大型詞典時，會使用來自檔案或從其他來源匯出的清單中的關鍵字。 在此情況下，您會在外部電子郵件中建立包含不適當語言的關鍵字字典。 您必須先連線[到 Office 365 安全性&amp;與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
1. 將關鍵字複製到文字檔案，並確定每個關鍵字位於個別行。
    
2. 使用 Unicode 編碼來儲存檔案。在 [記事本] \> [另存新檔]**** \> [編碼]**** \> [Unicode]**** 中。
    
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

列印`$dict`會顯示不同的變數。 關鍵字本身會儲存在後端的物件中，但`$dict.KeywordDictionary`會包含它們的字串標記法，以供您用來修改字典。 

修改字典之前，您必須使用`.split(',')`方法，將字詞的字串轉換回陣列。 然後，您會使用`.trim()`方法清除關鍵字之間不想要的空格，只保留要使用的關鍵字。 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

現在您將從字典中移除一些字詞。因為範例字典只有幾個關鍵字，所以您可以輕鬆地略過移除，直接匯出字典，並在 [記事本] 中編輯該字典，但字典通常包含大量文字，因此您首先將學習此方法，以在 PowerShell 中輕鬆地編輯它們。
  
在最後一個步驟中，您已將關鍵字儲存到陣列。有幾種方法可[從陣列中移除字詞](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)) (英文)，但直接方法為建立您要從字典中移除之字詞的陣列，然後只將不在要移除之字詞清單中的字典字詞複製到其中。
  
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

現在只需開啟檔案、新增其他字詞，並以 Unicode 編碼 (UTF-16) 儲存。現在，您將上傳更新的字詞並適當地更新字典。
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

現在您已適當地更新字典。請注意，`Identity` 欄位會採用字典的名稱。如果您也想要使用 `set-` Cmdlet 來變更字典的名稱，只需將 `-Name` 參數與新的字典名稱新增至上述的命令即可。 
  
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


將身分識別貼入您的自訂敏感資訊類型的 XML 並上傳它。現在字典將出現在敏感資訊類型的清單中，而且您可以在原則中直接使用它，同時指定需要比對多少個關鍵字。
  
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
