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
ms.openlocfilehash: 1e1aa45c3bf4d31e4c969b0bc0949109fa716467
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841159"
---
# <a name="create-a-keyword-dictionary"></a>建立關鍵字字典

資料外洩防護 (DLP) 可識別、監視及保護您的敏感性項目。 識別敏感性項目有時需要尋找關鍵字，特別是在識別一般內容 (例如醫療保健相關通訊)，或是不適當或偏激的言語。 雖然您可以在敏感性資訊類型中建立關鍵字清單，但關鍵字清單的大小有限，且需要修改 XML 來建立或編輯。 關鍵字字典提供更簡單的關鍵字管理並具有更大的規模，在字典中最多可支援 1 ＭB 的字詞 (壓縮後) 及任何語言。 壓縮後的租用戶限制也是 1 MB。 1MB 的壓縮後限制表示整個租用戶的所有字典加起來可以接近 1 百萬個字元。

## <a name="keyword-dictionary-limits"></a>關鍵字字典限制

每個租用最多可以建立 50 個基於關鍵字字典的敏感性資訊類型。 若要了解租用戶中有多少關鍵字字典，請利用 [連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的程序，連線到您的租用戶並執行此 PowerShell 指令碼。

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>建立關鍵字字典的基本步驟

字典的關鍵字可以來自各種來源，最常來自在服務中或是透過 PowerShell Cmdlet 匯入的檔案 (例如 .csv 或 .txt 清單)、來自您直接在 PowerShell Cmdlet 中輸入的清單，或來自現有的字典。當建立關鍵字字典時，您會依照相同的核心步驟：
  
1. 使用 **安全性與合規性中心** ([https://protection.office.com](https://protection.office.com)) 或連線到 **安全性與合規性中心 PowerShell**。
    
2. **從預期的來源定義或載入關鍵字**。 精靈和 Cmdlet 都會接受以逗點分隔的關鍵字清單，用來建立自訂關鍵字字典，因此這個步驟會根據您的關鍵字來自何處而略有不同。 一旦載入，就會將它們編碼並轉換為位元組陣列，然後再匯入它們。
    
3. **建立字典**。 選擇名稱和描述，然後建立字典。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>使用安全性與合規性中心建立關鍵字字典

請使用下列步驟來建立和匯入自訂字典的關鍵字：

1. 連線到安全性與合規性中心 ([https://protection.office.com](https://protection.office.com))。

2. 瀏覽至 [分類] > [敏感性資訊類型]。

3. 選取 [建立]，然後輸入您的敏感性資訊類型的 [名稱] 和 [描述]，然後選取 [下一步]

4. 選取 [新增項目]，然後在 [偵測內容包含] 下拉式清單中選取 [字典 (大型關鍵字)]。

5. 選取 [新增字典]

6. 在 [搜尋] 控制項中，選取 [您可以在這裡建立新的關鍵字字典]。

7. 輸入自訂字典的 [名稱]。

8. 選取 [匯入]，然後根據您的關鍵字檔案類型選取 [從文字] 或 [從 csv]。

9. 在 [檔案] 對話方塊中，選取來自您的本機電腦或網路檔案共用的關鍵字檔案，然後選取 [開啟]。

10. 選取 [儲存]，然後從 [關鍵字字典] 清單選取您的自訂字典。

11. 選取 [新增]，然後選取 [下一步]。

12. 檢閱並完成敏感性資訊類型選取項目，然後選取 [完成]。
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>使用 PowerShell 從檔案建立關鍵字字典

當您需要建立大型字典時，通常會使用來自檔案或從其他來源匯出清單中的關鍵字。 在此情況下，您會建立一個關鍵字字典，其中包含要在外部電子郵件中過濾的不適當言語清單。 必須先 [連線到安全性 &amp; 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。
  
1. 將關鍵字複製到文字檔案，並確定每個關鍵字位於個別行。
    
2. 使用 Unicode 編碼來儲存檔案。在 [記事本] \> [另存新檔] \> [編碼] \> [Unicode] 中。
    
3. 執行下列 Cmdlet 將檔案讀成變數：
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. 執行下列 Cmdlet 來建立字典：
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>使用自訂敏感資訊類型和 DLP 原則中的關鍵字字典

關鍵字字典可做為自訂敏感性資訊類型的符合需求一部分，或做為敏感性資訊類型本身。 兩者都需要您建立[自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。 按照連結文章中的指示建立敏感性資訊類型。 當您有 XML 之後，就需要字典的 GUID 識別碼來使用它。
  
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

> [!NOTE]
> Microsoft 365 資訊保護在預覽版中支援下列雙位元組字元集語言：
> - 中文 (簡體)
> - 中文 (繁體)
> - 韓文
> - 日文
>
>這項支援適用於敏感性資訊類型。 如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。
