---
title: 自訂內建機密資訊類型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何建立自訂機密資訊類型，讓您能夠使用符合貴組織需求的規則。
ms.openlocfilehash: 40584b430af6e822b115e014c20481c027222aae
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423402"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>自訂內建機密資訊類型

在內容中尋找機密資訊時，您需要以所謂的規則來說明資訊。資料外洩防護 (DLP) 包含您可以立即使用之最常用機密資訊類型的規則。若要使用這些規則，您必須將其包含在原則中。您也許想要調整這些內建規則以符合貴組織的特定需求，您可以藉由建立自訂機密資訊類型來完成。本主題說明如何自訂其中包含現有規則集合的 XML 檔案，以偵測更大範圍的潛在信用卡資訊。 
  
您可以採用此範例並且將其套用至其他內建機密資訊類型。如需預設機密資訊類型清單及 XML 定義，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)。 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>匯出目前規則的 XML 檔案

若要匯出 XML，您必須[透過遠端 PowerShell 連線到安全性與合規性中心。](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。
  
1. 在 PowerShell 中，輸入下列項目以在畫面上顯示貴組織的規則。如果您尚未建立自己的規則，則只會看到標示為「Microsoft 規則套件」的預設、內建規則。

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. 藉由輸入下列項目，在變數中儲存貴組織的規則。儲存在變數中可讓項目方便稍後以適用遠端 PowerShell 命令的格式提供。

   ```powershell    
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```
    
3. 藉由輸入下列項目來製作格式化的 XML 檔案及其所有資料。(`Set-content` 是會將 XML 寫入檔案之 Cmdlet 的一部分。) 

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > 請確定您使用規則套件儲存所在的確切檔案路徑。`C:\custompath\` 是預留位置。 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>尋找您要在 XML 中修改的規則

上述 Cmdlet 會匯出整個 *規則集合*，該集合包含我們提供的預設規則。接下來您必須特別尋找您想要修改的「信用卡號碼」規則。 
  
1. 使用文字編輯器開啟您在上一節中匯出的 XML 檔案。
    
2. 向下捲動到 `<Rules>` 標記，該標記是包含 DLP 規則的區段開頭。因為此 XML 檔案包含整個規則集合的資訊，它在頂端包含其他資訊，您必須捲動過去以前往規則。
    
3. 尋找 *Func_credit_card* 以尋找「信用卡號碼」規則定義。在 XML 中，規則名稱不能包含空格，因此空格通常會以底線取代，且規則名稱有時候會是縮寫。範例是美國社會安全號碼規則，它縮寫為 _SSN_。「信用卡號碼」規則 XML 看起來應該會像下列程式碼範例。
    
   ```xml
   <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
          patternsProximity="300" recommendedConfidence="85">
         <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_credit_card" />
           <Any minMatches="1">
             <Match idRef="Keyword_cc_verification" />
             <Match idRef="Keyword_cc_name" />
             <Match idRef="Func_expiration_date" />
           </Any>
         </Pattern>
       </Entity>
   ```

既然您已在 XML 中找到「信用卡號碼」規則定義，可以自訂規則的 XML 以符合您的需求。如需複習 XML 定義，請參閱本主題頂端的[術語詞彙](#term-glossary)。
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>修改 XML 及建立新的機密資訊類型

首先，您必須建立新的敏感性資訊類型，因為您無法直接修改預設規則。您可以對自訂敏感性資訊類型執行各種不同動作，而[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)會概述這些動作。針對此範例，我們保持簡單，只移除補強證據並且將關鍵字新增至「信用卡號碼」規則。
  
所有 XML 規則定義都是根據下列一般範本所建置。您需要複製及貼上範本中的「信用卡號碼」定義 XML、修改某些值 (請注意下列範例中的 ". . ." 預留位置)，然後將修改後的 XML 上傳為可在原則中使用的新規則。
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

現在，您有一些項目看起來與下列 XML 類似。因為規則套件和規則是根據其唯一的 GUID 進行識別，所以您必須產生兩個 GUID：一個適用於規則套件、一個用來取代「信用卡號碼」規則的 GUID。下列程式碼範例中實體識別碼的 GUID，適用於我們的內建規則定義，您需要以新的加以取代。有許多方法可以產生 GUID，但是您可以藉由在 PowerShell 中輸入 **[guid]::NewGuid()**，輕鬆地完成。 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>從機密資訊類型移除確切辨識項需求

現在您有新的敏感性資訊類型可以上傳到安全性與合規性中心，下一步是讓規則更精確。 修改規則，讓它只會尋找通過總和檢查碼但不需要額外 (確切) 辨識項 (例如關鍵字) 的 16 位數數字。 若要這麼做，您需要移除會尋找確切辨識項的 XML 部分。 確切辨識項在減少誤判方面很有幫助。 在此情況下，信用卡號碼附近通常會有特定關鍵字或到期日。 如果您移除該辨識項，也應該藉由降低 `confidenceLevel` (在此範例中是 85) 來調整對於找到信用卡號碼的信心。
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>尋找貴組織的特定關鍵字

您可能想要要求確切辨識項，但是想要不同或額外的關鍵字，而且或許想要變更尋找該辨識項的位置。您可以調整 `patternsProximity` 以將確切辨識項的視窗展開或縮小為大約 16 位數數字。若要新增您自己的關鍵字，您必須定義關鍵字清單並且在規則內參考。下列 XML 會新增關鍵字 "company card" 和 "Contoso card"，這樣在 150 個字元內包含這些片語的任何訊息，都會識別為信用卡號碼。
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>上傳您的規則

若要上傳您的規則，您必須執行下列動作。
  
1. 以 Unicode 編碼方式將它儲存為 .xml 檔案。這非常重要，因為如果檔案是以其他編碼方式儲存，則規則不會運作。
    
2. [透過遠端 PowerShell 連線到安全性與合規性中心。](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    
3. 在 PowerShell 中，輸入下列命令。

   ```powershell    
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```
   
   > [!IMPORTANT]
   > 請確定您使用規則套件儲存所在的確切檔案路徑。`C:\custompath\` 是預留位置。 
  
4. 若要確認，輸入 Y，並按下 **ENTER** 鍵。

5. 輸入下列命令，確認您的新規則已上傳，並確認顯示名稱：

   ```powershell
   Get-DlpSensitiveInformationType
   ```

若要開始使用新規則來偵測機密資訊，您需要將規則新增至 DLP 原則。若要深入了解如何將規則新增至原則，請參閱[從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)。
  
## <a name="term-glossary"></a>術語詞彙

以下是您在此程序期間遇到之術語的定義。
  
|**詞彙**|**定義**|
|:-----|:-----|
|實體|實體是我們所謂的機密資訊類型，例如信用卡號碼。每個實體都有唯一的 GUID 作為其識別碼。如果您複製 GUID 並且在 XML 中搜尋，您會找到 XML 規則定義及該 XML 規則的所有當地語系化轉譯。您也可以藉由尋找轉譯的 GUID 並且搜尋該 GUID，來尋找此定義。|
|函式|XML 檔案參考 `Func_credit_card`，這是已編譯程式碼中的函式。函式是用來執行複雜 regexes 並確認總和檢查碼符合我們的內建規則。因為這是在程式碼中發生，所以部分變數不會在 XML 檔案中顯示。|
|IdMatch|這是模式要嘗試符合的識別碼，例如信用卡號。|
|關鍵字清單|XML 檔案也會參考 `keyword_cc_verification` 和 `keyword_cc_name`，這是關鍵字清單，我們會從中尋找與實體 `patternsProximity` 的相符項目。目前不會在 XML 中顯示。|
|模式|模式包含敏感性類型要尋找的項目清單。 這包括關鍵字、Regex 及內部函數 (會執行驗證總和檢查碼之類的工作)。 敏感性資訊類型可能會有多個模式，而每個模式的可信度都不同。 建立會在找到確切辨識項時傳回高信賴度、找到一些確切辨識項或完全找不到時傳回較低信賴度的敏感性資訊類型時，這很有幫助。|
|模式 confidenceLevel|這是 DLP 引擎找到相符項目的信賴等級。此信賴等級與符合模式需求時，模式的相符項目相關聯。這是當使用 Exchange 郵件流程規則 (也稱為傳輸規則) 時，您應該考慮的信賴度量值。|
|patternsProximity|當我們尋找看起來像是信用卡號碼模式的項目時，`patternsProximity` 是與我們尋找確切辨識項的位置接近的數字。|
|recommendedConfidence|這是我們針對此規則建議的信賴等級。建議的信賴度會套用至實體和親和性。對於實體，永遠不會針對模式的 `confidenceLevel` 評估此數字。這只是一個建議，協助您在想要套用時選擇一個信賴等級。對於親和性，模式的 `confidenceLevel` 必須高於要叫用之郵件流程規則動作的 `recommendedConfidence` 數字。`recommendedConfidence` 是在會叫用動作之郵件流程規則中使用的預設信賴等級。如果您想要的話，可以改為根據模式的信賴等級，手動變更要叫用的郵件流程規則。|
   
## <a name="for-more-information"></a>相關資訊

- [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)
    
- [建立自訂的敏感性資訊類型](create-a-custom-sensitive-information-type.md)
    
- [資料外洩防護原則概觀](data-loss-prevention-policies.md)
