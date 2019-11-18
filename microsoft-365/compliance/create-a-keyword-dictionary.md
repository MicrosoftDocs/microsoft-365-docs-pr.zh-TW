---
title: 建立關鍵字字典
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
ms.openlocfilehash: 73ca1e83f716af076f99b1bcb8fba4fbb6e69d9d
ms.sourcegitcommit: 547bfc5f1fec7545cbe71b1919454425556c9227
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2019
ms.locfileid: "38685500"
---
# <a name="create-a-keyword-dictionary"></a>建立關鍵字字典

在 Office 365 中的資料遺失防護 (DLP) 可以識別、 監視和保護機密資訊。識別敏感資訊有時需要尋找關鍵字，特別是當識別一般內容 （例如醫療保健相關的通訊） 或不當或明確的語言。雖然您可以建立關鍵字清單中的敏感資訊類型，關鍵字清單大小限制，且需要修改 XML，才能建立或編輯它們。關鍵字字典提供更簡單管理的關鍵字，並在大規模地，支援最多 100000 的字詞，每個字典。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>建立關鍵字字典的基本步驟

字典的關鍵字可以來自各種來源，最常來自在服務中或是透過 PowerShell Cmdlet 匯入的檔案 (例如 .csv 或 .txt 清單)、來自您直接在 PowerShell Cmdlet 中輸入的清單，或來自現有的字典。當建立關鍵字字典時，您會依照相同的核心步驟：
  
1. 使用**安全性 & 合規性中心**([https://protection.office.com](https://protection.office.com)) 或連線至**Office 365 安全性&amp;合規性中心 PowerShell**。
    
2. **定義，或從您預定的來源載入關鍵字**。 精靈及指令程式同時會接受逗點分隔的清單來建立自訂的關鍵字字典，因此這個步驟將而異稍微關鍵字來自何處的關鍵字。 一旦載入，就會將它們編碼並轉換為位元組陣列，然後再匯入它們。
    
3. **建立字典**。 選擇的名稱和描述，並建立您的字典。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>建立關鍵字字典使用安全性 & 合規性中心

請使用下列步驟來建立和匯入自訂字典的關鍵字：

1. 連線到安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))。

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

通常當您需要建立大型字典，它是使用關鍵字從檔案或從其他來源匯出清單。 在此情況下，您將建立關鍵字字典包含清單的不當螢幕上的外部電子郵件的語言。 您必須先[連線至 Office 365 安全性&amp;合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
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

例如，我們將修改在 PowerShell 中，某些字詞儲存條款在本機上時您可以在其中修改它們在編輯器中，並再就地更新前一個字詞。 

首先，擷取字典物件：
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

列印`$dict`會顯示各種不同的變數。 關鍵字本身會儲存在物件上後端]，但`$dict.KeywordDictionary`包含它們，讓您將用來修改的字典的字串表示法。 

您修改的字典之前，您需要開啟回陣列使用的字詞字串`.split(',')`方法。 然後會清除之間的關鍵字不想要的空格`.trim()`方法，保留的關鍵字來使用。 
  
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

關鍵字字典可當作自訂機密資訊類型，比對需求的一部分，或為敏感資訊輸入本身。 兩者都需要您建立[自訂機密資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。 遵循連結文件中的指示，建立敏感資訊類型。 一旦您有 XML，您必須使用它的字典的 GUID 識別碼。
  
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
