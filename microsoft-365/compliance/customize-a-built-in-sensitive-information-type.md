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
ms.openlocfilehash: 6e9fb0295f8958584878921c1fac362dc511be8f
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086610"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="e9556-103">自訂內建機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="e9556-103">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="e9556-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span><span class="sxs-lookup"><span data-stu-id="e9556-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span></span> <span data-ttu-id="e9556-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span><span class="sxs-lookup"><span data-stu-id="e9556-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span></span> <span data-ttu-id="e9556-106">To use these rules, you have to include them in a policy.</span><span class="sxs-lookup"><span data-stu-id="e9556-106">To use these rules, you have to include them in a policy.</span></span> <span data-ttu-id="e9556-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="e9556-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span></span> <span data-ttu-id="e9556-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span><span class="sxs-lookup"><span data-stu-id="e9556-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="e9556-109">You can take this example and apply it to other built-in sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="e9556-109">You can take this example and apply it to other built-in sensitive information types.</span></span> <span data-ttu-id="e9556-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="e9556-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="e9556-111">匯出目前規則的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="e9556-111">Export the XML file of the current rules</span></span>

<span data-ttu-id="e9556-112">若要匯出 XML，您必須[透過遠端 PowerShell 連線到安全性與合規性中心。](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="e9556-112">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="e9556-113">In the PowerShell, type the following to display your organization's rules on screen.</span><span class="sxs-lookup"><span data-stu-id="e9556-113">In the PowerShell, type the following to display your organization's rules on screen.</span></span> <span data-ttu-id="e9556-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span><span class="sxs-lookup"><span data-stu-id="e9556-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. <span data-ttu-id="e9556-115">Store your organization's rules in a variable by typing the following.</span><span class="sxs-lookup"><span data-stu-id="e9556-115">Store your organization's rules in a variable by typing the following.</span></span> <span data-ttu-id="e9556-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span><span class="sxs-lookup"><span data-stu-id="e9556-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

   ```powershell    
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```
    
3. <span data-ttu-id="e9556-117">Make a formatted XML file with all that data by typing the following.</span><span class="sxs-lookup"><span data-stu-id="e9556-117">Make a formatted XML file with all that data by typing the following.</span></span> <span data-ttu-id="e9556-118">( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span><span class="sxs-lookup"><span data-stu-id="e9556-118">( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="e9556-119">Make sure that you use the file location where your rule pack is actually stored.</span><span class="sxs-lookup"><span data-stu-id="e9556-119">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="e9556-120">`C:\custompath\` is a placeholder.</span><span class="sxs-lookup"><span data-stu-id="e9556-120">`C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="e9556-121">尋找您要在 XML 中修改的規則</span><span class="sxs-lookup"><span data-stu-id="e9556-121">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="e9556-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span><span class="sxs-lookup"><span data-stu-id="e9556-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span></span> <span data-ttu-id="e9556-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span><span class="sxs-lookup"><span data-stu-id="e9556-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="e9556-124">使用文字編輯器開啟您在上一節中匯出的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="e9556-124">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="e9556-125">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules.</span><span class="sxs-lookup"><span data-stu-id="e9556-125">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules.</span></span> <span data-ttu-id="e9556-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span><span class="sxs-lookup"><span data-stu-id="e9556-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>
    
3. <span data-ttu-id="e9556-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span><span class="sxs-lookup"><span data-stu-id="e9556-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span></span> <span data-ttu-id="e9556-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span><span class="sxs-lookup"><span data-stu-id="e9556-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span></span> <span data-ttu-id="e9556-129">An example of this is the U.S. Social Security number rule, which is abbreviated _SSN_.</span><span class="sxs-lookup"><span data-stu-id="e9556-129">An example of this is the U.S. Social Security number rule, which is abbreviated _SSN_.</span></span> <span data-ttu-id="e9556-130">The Credit Card Number rule XML should look like the following code sample.</span><span class="sxs-lookup"><span data-stu-id="e9556-130">The Credit Card Number rule XML should look like the following code sample.</span></span>
    
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

<span data-ttu-id="e9556-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span><span class="sxs-lookup"><span data-stu-id="e9556-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span></span> <span data-ttu-id="e9556-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span><span class="sxs-lookup"><span data-stu-id="e9556-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="e9556-133">修改 XML 及建立新的機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="e9556-133">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="e9556-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span><span class="sxs-lookup"><span data-stu-id="e9556-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span></span> <span data-ttu-id="e9556-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e9556-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="e9556-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span><span class="sxs-lookup"><span data-stu-id="e9556-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="e9556-137">All XML rule definitions are built on the following general template.</span><span class="sxs-lookup"><span data-stu-id="e9556-137">All XML rule definitions are built on the following general template.</span></span> <span data-ttu-id="e9556-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span><span class="sxs-lookup"><span data-stu-id="e9556-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span></span> <span data-ttu-id="e9556-139">.</span><span class="sxs-lookup"><span data-stu-id="e9556-139">.</span></span> <span data-ttu-id="e9556-140">."</span><span class="sxs-lookup"><span data-stu-id="e9556-140">."</span></span> <span data-ttu-id="e9556-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span><span class="sxs-lookup"><span data-stu-id="e9556-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
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

<span data-ttu-id="e9556-142">Now, you have something that looks similar to the following XML.</span><span class="sxs-lookup"><span data-stu-id="e9556-142">Now, you have something that looks similar to the following XML.</span></span> <span data-ttu-id="e9556-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span><span class="sxs-lookup"><span data-stu-id="e9556-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span></span> <span data-ttu-id="e9556-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span><span class="sxs-lookup"><span data-stu-id="e9556-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span></span> <span data-ttu-id="e9556-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span><span class="sxs-lookup"><span data-stu-id="e9556-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
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

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="e9556-146">從機密資訊類型移除確切辨識項需求</span><span class="sxs-lookup"><span data-stu-id="e9556-146">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="e9556-147">現在您有新的敏感性資訊類型可以上傳到安全性與合規性中心，下一步是讓規則更精確。</span><span class="sxs-lookup"><span data-stu-id="e9556-147">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="e9556-148">修改規則，讓它只會尋找通過總和檢查碼但不需要額外 (確切) 辨識項 (例如關鍵字) 的 16 位數數字。</span><span class="sxs-lookup"><span data-stu-id="e9556-148">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="e9556-149">若要這麼做，您需要移除會尋找確切辨識項的 XML 部分。</span><span class="sxs-lookup"><span data-stu-id="e9556-149">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="e9556-150">確切辨識項在減少誤判方面很有幫助。</span><span class="sxs-lookup"><span data-stu-id="e9556-150">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="e9556-151">在此情況下，信用卡號碼附近通常會有特定關鍵字或到期日。</span><span class="sxs-lookup"><span data-stu-id="e9556-151">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="e9556-152">如果您移除該辨識項，也應該藉由降低 `confidenceLevel` (在此範例中是 85) 來調整對於找到信用卡號碼的信心。</span><span class="sxs-lookup"><span data-stu-id="e9556-152">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="e9556-153">尋找貴組織的特定關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9556-153">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="e9556-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span><span class="sxs-lookup"><span data-stu-id="e9556-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span></span> <span data-ttu-id="e9556-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span><span class="sxs-lookup"><span data-stu-id="e9556-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span></span> <span data-ttu-id="e9556-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span><span class="sxs-lookup"><span data-stu-id="e9556-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span></span> <span data-ttu-id="e9556-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span><span class="sxs-lookup"><span data-stu-id="e9556-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>
  
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

## <a name="upload-your-rule"></a><span data-ttu-id="e9556-158">上傳您的規則</span><span class="sxs-lookup"><span data-stu-id="e9556-158">Upload your rule</span></span>

<span data-ttu-id="e9556-159">若要上傳您的規則，您必須執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="e9556-159">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="e9556-160">Save it as an .xml file with Unicode encoding.</span><span class="sxs-lookup"><span data-stu-id="e9556-160">Save it as an .xml file with Unicode encoding.</span></span> <span data-ttu-id="e9556-161">This is important because the rule won't work if the file is saved with a different encoding.</span><span class="sxs-lookup"><span data-stu-id="e9556-161">This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="e9556-162">透過遠端 PowerShell 連線到安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e9556-162">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="e9556-163">在 PowerShell 中，輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="e9556-163">In the PowerShell, type the following.</span></span>

   ```powershell    
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```
   
   > [!IMPORTANT]
   > <span data-ttu-id="e9556-164">Make sure that you use the file location where your rule pack is actually stored.</span><span class="sxs-lookup"><span data-stu-id="e9556-164">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="e9556-165">`C:\custompath\` is a placeholder.</span><span class="sxs-lookup"><span data-stu-id="e9556-165">`C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="e9556-166">若要確認，輸入 Y，並按下 **ENTER** 鍵。</span><span class="sxs-lookup"><span data-stu-id="e9556-166">To confirm, type Y, and then press **Enter**.</span></span>

5. <span data-ttu-id="e9556-167">輸入下列命令，確認您的新規則已上傳，並確認顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="e9556-167">Verify that your new rule was uploaded and its display name by typing:</span></span>

   ```powershell
   Get-DlpSensitiveInformationType
   ```

<span data-ttu-id="e9556-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span><span class="sxs-lookup"><span data-stu-id="e9556-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span></span> <span data-ttu-id="e9556-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="e9556-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="e9556-170">術語詞彙</span><span class="sxs-lookup"><span data-stu-id="e9556-170">Term glossary</span></span>

<span data-ttu-id="e9556-171">以下是您在此程序期間遇到之術語的定義。</span><span class="sxs-lookup"><span data-stu-id="e9556-171">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="e9556-172">**詞彙**</span><span class="sxs-lookup"><span data-stu-id="e9556-172">**Term**</span></span>|<span data-ttu-id="e9556-173">**定義**</span><span class="sxs-lookup"><span data-stu-id="e9556-173">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9556-174">實體</span><span class="sxs-lookup"><span data-stu-id="e9556-174">Entity</span></span>|<span data-ttu-id="e9556-175">Entities are what we call sensitive information types, such as credit card numbers.</span><span class="sxs-lookup"><span data-stu-id="e9556-175">Entities are what we call sensitive information types, such as credit card numbers.</span></span> <span data-ttu-id="e9556-176">Each entity has a unique GUID as its ID.</span><span class="sxs-lookup"><span data-stu-id="e9556-176">Each entity has a unique GUID as its ID.</span></span> <span data-ttu-id="e9556-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span><span class="sxs-lookup"><span data-stu-id="e9556-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span></span> <span data-ttu-id="e9556-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span><span class="sxs-lookup"><span data-stu-id="e9556-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="e9556-179">函式</span><span class="sxs-lookup"><span data-stu-id="e9556-179">Functions</span></span>|<span data-ttu-id="e9556-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span><span class="sxs-lookup"><span data-stu-id="e9556-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span></span> <span data-ttu-id="e9556-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span><span class="sxs-lookup"><span data-stu-id="e9556-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="e9556-182">IdMatch</span><span class="sxs-lookup"><span data-stu-id="e9556-182">IdMatch</span></span>|<span data-ttu-id="e9556-183">這是模式要嘗試符合的識別碼，例如信用卡號。</span><span class="sxs-lookup"><span data-stu-id="e9556-183">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="e9556-184">關鍵字清單</span><span class="sxs-lookup"><span data-stu-id="e9556-184">Keyword lists</span></span>|<span data-ttu-id="e9556-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span><span class="sxs-lookup"><span data-stu-id="e9556-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span></span> <span data-ttu-id="e9556-186">These aren't currently displayed in the XML.</span><span class="sxs-lookup"><span data-stu-id="e9556-186">These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="e9556-187">模式</span><span class="sxs-lookup"><span data-stu-id="e9556-187">Pattern</span></span>|<span data-ttu-id="e9556-188">模式包含敏感性類型要尋找的項目清單。</span><span class="sxs-lookup"><span data-stu-id="e9556-188">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="e9556-189">這包括關鍵字、Regex 及內部函數 (會執行驗證總和檢查碼之類的工作)。</span><span class="sxs-lookup"><span data-stu-id="e9556-189">This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums.</span></span> <span data-ttu-id="e9556-190">敏感性資訊類型可能會有多個模式，而每個模式的可信度都不同。</span><span class="sxs-lookup"><span data-stu-id="e9556-190">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="e9556-191">建立會在找到確切辨識項時傳回高信賴度、找到一些確切辨識項或完全找不到時傳回較低信賴度的敏感性資訊類型時，這很有幫助。</span><span class="sxs-lookup"><span data-stu-id="e9556-191">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="e9556-192">模式 confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="e9556-192">Pattern confidenceLevel</span></span>|<span data-ttu-id="e9556-193">This is the level of confidence that the DLP engine found a match.</span><span class="sxs-lookup"><span data-stu-id="e9556-193">This is the level of confidence that the DLP engine found a match.</span></span> <span data-ttu-id="e9556-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span><span class="sxs-lookup"><span data-stu-id="e9556-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span></span> <span data-ttu-id="e9556-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span><span class="sxs-lookup"><span data-stu-id="e9556-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="e9556-196">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="e9556-196">patternsProximity</span></span>|<span data-ttu-id="e9556-197">當我們尋找看起來像是信用卡號碼模式的項目時，`patternsProximity` 是與我們尋找確切辨識項的位置接近的數字。</span><span class="sxs-lookup"><span data-stu-id="e9556-197">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="e9556-198">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="e9556-198">recommendedConfidence</span></span>|<span data-ttu-id="e9556-199">This is the confidence level we recommend for this rule.</span><span class="sxs-lookup"><span data-stu-id="e9556-199">This is the confidence level we recommend for this rule.</span></span> <span data-ttu-id="e9556-200">The recommended confidence applies to entities and affinities.</span><span class="sxs-lookup"><span data-stu-id="e9556-200">The recommended confidence applies to entities and affinities.</span></span> <span data-ttu-id="e9556-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span><span class="sxs-lookup"><span data-stu-id="e9556-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span></span> <span data-ttu-id="e9556-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span><span class="sxs-lookup"><span data-stu-id="e9556-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span></span> <span data-ttu-id="e9556-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span><span class="sxs-lookup"><span data-stu-id="e9556-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span></span> <span data-ttu-id="e9556-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span><span class="sxs-lookup"><span data-stu-id="e9556-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span></span> <span data-ttu-id="e9556-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span><span class="sxs-lookup"><span data-stu-id="e9556-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="e9556-206">相關資訊</span><span class="sxs-lookup"><span data-stu-id="e9556-206">For more information</span></span>

- [<span data-ttu-id="e9556-207">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="e9556-207">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="e9556-208">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="e9556-208">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="e9556-209">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="e9556-209">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
