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
ms.openlocfilehash: 7b24313c54fdf49876c58d1809cbb29159f4508f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114257"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="509d1-103">自訂內建機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="509d1-103">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="509d1-p101">在內容中尋找機密資訊時，您需要以所謂的規則來說明資訊。資料外洩防護 (DLP) 包含您可以立即使用之最常用機密資訊類型的規則。若要使用這些規則，您必須將其包含在原則中。您也許想要調整這些內建規則以符合貴組織的特定需求，您可以藉由建立自訂機密資訊類型來完成。本主題說明如何自訂其中包含現有規則集合的 XML 檔案，以偵測更大範圍的潛在信用卡資訊。</span><span class="sxs-lookup"><span data-stu-id="509d1-p101">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="509d1-p102">您可以採用此範例並且將其套用至其他內建機密資訊類型。如需預設機密資訊類型清單及 XML 定義，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="509d1-p102">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="509d1-111">匯出目前規則的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="509d1-111">Export the XML file of the current rules</span></span>

<span data-ttu-id="509d1-112">若要匯出 XML，您必須[透過遠端 PowerShell 連線到安全性與合規性中心。](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="509d1-112">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="509d1-p103">在 PowerShell 中，輸入下列項目以在畫面上顯示貴組織的規則。如果您尚未建立自己的規則，則只會看到標示為「Microsoft 規則套件」的預設、內建規則。</span><span class="sxs-lookup"><span data-stu-id="509d1-p103">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. <span data-ttu-id="509d1-p104">藉由輸入下列項目，在變數中儲存貴組織的規則。儲存在變數中可讓項目方便稍後以適用遠端 PowerShell 命令的格式提供。</span><span class="sxs-lookup"><span data-stu-id="509d1-p104">Store your organization's rules in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

   ```powershell    
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```
    
3. <span data-ttu-id="509d1-p105">藉由輸入下列項目來製作格式化的 XML 檔案及其所有資料。(`Set-content` 是會將 XML 寫入檔案之 Cmdlet 的一部分。)</span><span class="sxs-lookup"><span data-stu-id="509d1-p105">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="509d1-p106">請確定您使用規則套件儲存所在的確切檔案路徑。`C:\custompath\` 是預留位置。</span><span class="sxs-lookup"><span data-stu-id="509d1-p106">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="509d1-121">尋找您要在 XML 中修改的規則</span><span class="sxs-lookup"><span data-stu-id="509d1-121">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="509d1-p107">上述 Cmdlet 會匯出整個 *規則集合*，該集合包含我們提供的預設規則。接下來您必須特別尋找您想要修改的「信用卡號碼」規則。</span><span class="sxs-lookup"><span data-stu-id="509d1-p107">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="509d1-124">使用文字編輯器開啟您在上一節中匯出的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="509d1-124">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="509d1-p108">向下捲動到 `<Rules>` 標記，該標記是包含 DLP 規則的區段開頭。因為此 XML 檔案包含整個規則集合的資訊，它在頂端包含其他資訊，您必須捲動過去以前往規則。</span><span class="sxs-lookup"><span data-stu-id="509d1-p108">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>
    
3. <span data-ttu-id="509d1-p109">尋找 *Func_credit_card* 以尋找「信用卡號碼」規則定義。在 XML 中，規則名稱不能包含空格，因此空格通常會以底線取代，且規則名稱有時候會是縮寫。範例是美國社會安全號碼規則，它縮寫為 _SSN_。「信用卡號碼」規則 XML 看起來應該會像下列程式碼範例。</span><span class="sxs-lookup"><span data-stu-id="509d1-p109">Look for *Func_credit_card* to find the Credit Card Number rule definition. In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated _SSN_. The Credit Card Number rule XML should look like the following code sample.</span></span>
    
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

<span data-ttu-id="509d1-p110">既然您已在 XML 中找到「信用卡號碼」規則定義，可以自訂規則的 XML 以符合您的需求。如需複習 XML 定義，請參閱本主題頂端的[術語詞彙](#term-glossary)。</span><span class="sxs-lookup"><span data-stu-id="509d1-p110">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="509d1-133">修改 XML 及建立新的機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="509d1-133">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="509d1-p111">首先，您必須建立新的敏感性資訊類型，因為您無法直接修改預設規則。您可以對自訂敏感性資訊類型執行各種不同動作，而[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)會概述這些動作。針對此範例，我們保持簡單，只移除補強證據並且將關鍵字新增至「信用卡號碼」規則。</span><span class="sxs-lookup"><span data-stu-id="509d1-p111">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="509d1-p112">所有 XML 規則定義都是根據下列一般範本所建置。您需要複製及貼上範本中的「信用卡號碼」定義 XML、修改某些值 (請注意下列範例中的 ". . ." 預留位置)，然後將修改後的 XML 上傳為可在原則中使用的新規則。</span><span class="sxs-lookup"><span data-stu-id="509d1-p112">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
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

<span data-ttu-id="509d1-p113">現在，您有一些項目看起來與下列 XML 類似。因為規則套件和規則是根據其唯一的 GUID 進行識別，所以您必須產生兩個 GUID：一個適用於規則套件、一個用來取代「信用卡號碼」規則的 GUID。下列程式碼範例中實體識別碼的 GUID，適用於我們的內建規則定義，您需要以新的加以取代。有許多方法可以產生 GUID，但是您可以藉由在 PowerShell 中輸入 **[guid]::NewGuid()**，輕鬆地完成。</span><span class="sxs-lookup"><span data-stu-id="509d1-p113">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
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

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="509d1-146">從機密資訊類型移除確切辨識項需求</span><span class="sxs-lookup"><span data-stu-id="509d1-146">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="509d1-147">現在您有新的敏感性資訊類型可以上傳到安全性與合規性中心，下一步是讓規則更精確。</span><span class="sxs-lookup"><span data-stu-id="509d1-147">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="509d1-148">修改規則，讓它只會尋找通過總和檢查碼但不需要額外 (確切) 辨識項 (例如關鍵字) 的 16 位數數字。</span><span class="sxs-lookup"><span data-stu-id="509d1-148">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="509d1-149">若要這麼做，您需要移除會尋找確切辨識項的 XML 部分。</span><span class="sxs-lookup"><span data-stu-id="509d1-149">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="509d1-150">確切辨識項在減少誤判方面很有幫助。</span><span class="sxs-lookup"><span data-stu-id="509d1-150">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="509d1-151">在此情況下，信用卡號碼附近通常會有特定關鍵字或到期日。</span><span class="sxs-lookup"><span data-stu-id="509d1-151">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="509d1-152">如果您移除該辨識項，也應該藉由降低 `confidenceLevel` (在此範例中是 85) 來調整對於找到信用卡號碼的信心。</span><span class="sxs-lookup"><span data-stu-id="509d1-152">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="509d1-153">尋找貴組織的特定關鍵字</span><span class="sxs-lookup"><span data-stu-id="509d1-153">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="509d1-p115">您可能想要要求確切辨識項，但是想要不同或額外的關鍵字，而且或許想要變更尋找該辨識項的位置。您可以調整 `patternsProximity` 以將確切辨識項的視窗展開或縮小為大約 16 位數數字。若要新增您自己的關鍵字，您必須定義關鍵字清單並且在規則內參考。下列 XML 會新增關鍵字 "company card" 和 "Contoso card"，這樣在 150 個字元內包含這些片語的任何訊息，都會識別為信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="509d1-p115">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>
  
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

## <a name="upload-your-rule"></a><span data-ttu-id="509d1-158">上傳您的規則</span><span class="sxs-lookup"><span data-stu-id="509d1-158">Upload your rule</span></span>

<span data-ttu-id="509d1-159">若要上傳您的規則，您必須執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="509d1-159">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="509d1-p116">以 Unicode 編碼方式將它儲存為 .xml 檔案。這非常重要，因為如果檔案是以其他編碼方式儲存，則規則不會運作。</span><span class="sxs-lookup"><span data-stu-id="509d1-p116">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="509d1-162">透過遠端 PowerShell 連線到安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="509d1-162">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](/powershell/exchange/connect-to-scc-powershell)
    
3. <span data-ttu-id="509d1-163">在 PowerShell 中，輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="509d1-163">In the PowerShell, type the following.</span></span>

   ```powershell    
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```
   
   > [!IMPORTANT]
   > <span data-ttu-id="509d1-p117">請確定您使用規則套件儲存所在的確切檔案路徑。`C:\custompath\` 是預留位置。</span><span class="sxs-lookup"><span data-stu-id="509d1-p117">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="509d1-166">若要確認，輸入 Y，並按下 **ENTER** 鍵。</span><span class="sxs-lookup"><span data-stu-id="509d1-166">To confirm, type Y, and then press **Enter**.</span></span>

5. <span data-ttu-id="509d1-167">輸入下列命令，確認您的新規則已上傳，並確認顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="509d1-167">Verify that your new rule was uploaded and its display name by typing:</span></span>

   ```powershell
   Get-DlpSensitiveInformationType
   ```

<span data-ttu-id="509d1-p118">若要開始使用新規則來偵測機密資訊，您需要將規則新增至 DLP 原則。若要深入了解如何將規則新增至原則，請參閱[從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)。</span><span class="sxs-lookup"><span data-stu-id="509d1-p118">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="509d1-170">術語詞彙</span><span class="sxs-lookup"><span data-stu-id="509d1-170">Term glossary</span></span>

<span data-ttu-id="509d1-171">以下是您在此程序期間遇到之術語的定義。</span><span class="sxs-lookup"><span data-stu-id="509d1-171">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="509d1-172">**詞彙**</span><span class="sxs-lookup"><span data-stu-id="509d1-172">**Term**</span></span>|<span data-ttu-id="509d1-173">**定義**</span><span class="sxs-lookup"><span data-stu-id="509d1-173">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="509d1-174">實體</span><span class="sxs-lookup"><span data-stu-id="509d1-174">Entity</span></span>|<span data-ttu-id="509d1-p119">實體是我們所謂的機密資訊類型，例如信用卡號碼。每個實體都有唯一的 GUID 作為其識別碼。如果您複製 GUID 並且在 XML 中搜尋，您會找到 XML 規則定義及該 XML 規則的所有當地語系化轉譯。您也可以藉由尋找轉譯的 GUID 並且搜尋該 GUID，來尋找此定義。</span><span class="sxs-lookup"><span data-stu-id="509d1-p119">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="509d1-179">函式</span><span class="sxs-lookup"><span data-stu-id="509d1-179">Functions</span></span>|<span data-ttu-id="509d1-p120">XML 檔案參考 `Func_credit_card`，這是已編譯程式碼中的函式。函式是用來執行複雜 regexes 並確認總和檢查碼符合我們的內建規則。因為這是在程式碼中發生，所以部分變數不會在 XML 檔案中顯示。</span><span class="sxs-lookup"><span data-stu-id="509d1-p120">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="509d1-182">IdMatch</span><span class="sxs-lookup"><span data-stu-id="509d1-182">IdMatch</span></span>|<span data-ttu-id="509d1-183">這是模式要嘗試符合的識別碼，例如信用卡號。</span><span class="sxs-lookup"><span data-stu-id="509d1-183">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="509d1-184">關鍵字清單</span><span class="sxs-lookup"><span data-stu-id="509d1-184">Keyword lists</span></span>|<span data-ttu-id="509d1-p121">XML 檔案也會參考 `keyword_cc_verification` 和 `keyword_cc_name`，這是關鍵字清單，我們會從中尋找與實體 `patternsProximity` 的相符項目。目前不會在 XML 中顯示。</span><span class="sxs-lookup"><span data-stu-id="509d1-p121">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="509d1-187">模式</span><span class="sxs-lookup"><span data-stu-id="509d1-187">Pattern</span></span>|<span data-ttu-id="509d1-p122">模式包含敏感性類型尋找的清單。包括關鍵字、regexes 及內部函式 (執行驗證總和檢查碼之類的工作)。敏感性資訊類型可以有多個具有唯一信賴度的模式。這在建立敏感性資訊類型時很有用，其會在找到確切證據時傳回高信賴度，在找到很少確切證據或完全找不到時傳回較低信賴度。</span><span class="sxs-lookup"><span data-stu-id="509d1-p122">The pattern contains the list of what the sensitive type is looking for. This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums. Sensitive information types can have multiple patterns with unique confidences. This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="509d1-192">模式 confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="509d1-192">Pattern confidenceLevel</span></span>|<span data-ttu-id="509d1-p123">這是 DLP 引擎找到相符項目的信賴等級。此信賴等級與符合模式需求時，模式的相符項目相關聯。這是當使用 Exchange 郵件流程規則 (也稱為傳輸規則) 時，您應該考慮的信賴度量值。</span><span class="sxs-lookup"><span data-stu-id="509d1-p123">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="509d1-196">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="509d1-196">patternsProximity</span></span>|<span data-ttu-id="509d1-197">當我們尋找看起來像是信用卡號碼模式的項目時，`patternsProximity` 是與我們尋找確切辨識項的位置接近的數字。</span><span class="sxs-lookup"><span data-stu-id="509d1-197">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="509d1-198">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="509d1-198">recommendedConfidence</span></span>|<span data-ttu-id="509d1-p124">這是我們針對此規則建議的信賴等級。建議的信賴度會套用至實體和親和性。對於實體，永遠不會針對模式的 `confidenceLevel` 評估此數字。這只是一個建議，協助您在想要套用時選擇一個信賴等級。對於親和性，模式的 `confidenceLevel` 必須高於要叫用之郵件流程規則動作的 `recommendedConfidence` 數字。`recommendedConfidence` 是在會叫用動作之郵件流程規則中使用的預設信賴等級。如果您想要的話，可以改為根據模式的信賴等級，手動變更要叫用的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="509d1-p124">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="509d1-206">相關資訊</span><span class="sxs-lookup"><span data-stu-id="509d1-206">For more information</span></span>

- [<span data-ttu-id="509d1-207">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="509d1-207">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="509d1-208">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="509d1-208">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="509d1-209">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="509d1-209">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)