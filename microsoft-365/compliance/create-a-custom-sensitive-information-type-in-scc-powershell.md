---
title: 在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全性與合規性中心建立及匯入 DLP 的自訂敏感性資訊類型。
ms.openlocfilehash: 536662737e2e3fc4fc2796b616adf59b544b2376
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327785"
---
# <a name="create-a-custom-sensitive-information-type-in-security--compliance-center-powershell"></a><span data-ttu-id="6b0ef-103">在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="6b0ef-103">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="6b0ef-p101">Microsoft 365 中的資料外洩防護 (DLP) 包含許多內建[敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)，可讓您在 DLP 原則中使用。這些內建類型可以協助識別及保護信用卡號碼、銀行帳號、護照號碼等等。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p101">Data loss prevention (DLP) in Microsoft 365 includes many built-in [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 
  
<span data-ttu-id="6b0ef-p102">但如果您需要識別及保護不同類型的機密資訊 (像是採用組織專用格式的員工 ID) 呢？若要這麼做，您可以建立自訂的機密資訊類型，機密資訊類型是在稱為*規則套件*的 XML 檔案中定義。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p102">But what if you need to identify and protect a different type of sensitive information (for example, an employee ID that uses a format specific to your organization)? To do this, you can create a custom sensitive information type that is defined in an XML file called a *rule package*.</span></span>
  
<span data-ttu-id="6b0ef-p103">本主題說明如何建立 XML 檔案，該檔案會定義您的自訂機密資訊類型。您必須知道如何建立規則運算式。例如，本主題會建立自訂機密資訊類型，該類型會識別員工識別碼。您可以使用這個範例 XML 作為專屬 XML 檔案的起點。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p103">This topic shows you how to create an XML file that defines your own custom sensitive information type. You need to know how to create a regular expression. As an example, this topic creates a custom sensitive information type that identifies an employee ID. You can use this example XML as a starting point for your own XML file.</span></span>
  
<span data-ttu-id="6b0ef-p104">建立格式正確的 XML 檔案之後，您可以藉由使用 Microsoft 365 PowerShell 將它上傳至 Microsoft 365。然後您就可以在 DLP 原則中使用自訂敏感性資訊類型，並且測試它是否會如您預期地偵測敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p104">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell. Then you're ready to use your custom sensitive information type in your DLP policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="6b0ef-p105">您也可以在在安全性與合規性中心建立較不複雜的自訂機密資訊類型。如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p105">You can also create less complex custom sensitive information types in the Security & Compliance Center UI. For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="6b0ef-116">重要免責聲明</span><span class="sxs-lookup"><span data-stu-id="6b0ef-116">Important disclaimer</span></span>
<!-- this is worded much better than the previous one is --><span data-ttu-id="6b0ef-p106">因為客戶環境及內容需求的差異，Microsoft 支援服務無法協助提供自訂內容比對定義。例如，定義自訂分類或規則運算式 (也稱為 RegEx)。針對自訂內容比對開發、測試及除錯，Microsoft 365 客戶將會需要依賴內部 IT 資源，或使用外部諮詢資源如 Microsoft 諮詢服務 (MCS)。支援的工程師能為該功能提供有限的支援，但無法保證任何自訂內容比對開發能夠滿足客戶需求或義務。可提供支援類型的範例，像是提供範例規則運算模式進行測試，或者支援服務能夠以單一特定內容範例，協助疑難排解現有未如預期觸發的 RegEx 模式。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p106"> Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns. For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS). Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.  As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes. Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

 <span data-ttu-id="6b0ef-122">如需用於處理文字之 Boost.RegEx (先前稱為 RegEx++) 引擎的詳細資訊，請參閱 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-122">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>
    
## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="6b0ef-123">規則套件的範例 XML</span><span class="sxs-lookup"><span data-stu-id="6b0ef-123">Sample XML of a rule package</span></span>

<span data-ttu-id="6b0ef-p107">以下是我們在本主題中建立的規則套件範例 XML。元素和屬性會在以下章節中說明。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p107">Here's the sample XML of the rule package that we'll create in this topic. Elements and attributes are explained in the sections below.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
    <Version build="0" major="1" minor="0" revision="0"/>
    <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
    <Details defaultLangCode="en-us">
        <LocalizedDetails langcode="en-us">
            <PublisherName>Contoso</PublisherName>
            <Name>Employee ID Custom Rule Pack</Name>
            <Description>
            This rule package contains the custom Employee ID entity.
            </Description>
        </LocalizedDetails>
    </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
    <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="70">
        <Pattern confidenceLevel="60">
            <IdMatch idRef="Regex_employee_id"/>
        </Pattern>
        <Pattern confidenceLevel="70">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
        </Pattern>
        <Pattern confidenceLevel="80">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
            <Any minMatches="1">
                <Match idRef="Keyword_badge" minCount="2"/>
                <Match idRef="Keyword_employee"/>
            </Any>
            <Any minMatches="0" maxMatches="0">
                <Match idRef="Keyword_false_positives_local"/>
                <Match idRef="Keyword_false_positives_intl"/>
            </Any>
        </Pattern>
    </Entity>
    <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
    <Keyword id="Keyword_employee">
        <Group matchStyle="word">
            <Term>Identification</Term>
            <Term>Contoso Employee</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_badge">
        <Group matchStyle="string">
            <Term>card</Term>
            <Term>badge</Term>
            <Term caseSensitive="true">ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_local">
        <Group matchStyle="word">
            <Term>credit card</Term>
            <Term>national ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_intl">
        <Group matchStyle="word">
            <Term>identity card</Term>
            <Term>national ID</Term>
            <Term>EU debit card</Term>
        </Group>
    </Keyword>
    <LocalizedStrings>
        <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
            <Name default="true" langcode="en-us">Employee ID</Name>
            <Description default="true" langcode="en-us">
            A custom classification for detecting Employee IDs.
            </Description>
            <Description default="false" langcode="de-de">
            Description for German locale.
            </Description>
        </Resource>
    </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="6b0ef-p108">您的關鍵需求是什麼？[Rule、Entity、Pattern 元素]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p108">What are your key requirements? [Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="6b0ef-128">在您開始之前，了解規則的 XML 結構描述基本結構，以及您可以如何使用這個結構來定義自訂機密資訊讓它識別正確內容，很有幫助。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-128">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="6b0ef-p109">規則會定義一或多個實體 (敏感性資訊類型)，每個實體會定義一或多個模式。模式是 DLP 在評估內容 (例如電子郵件和文件) 時尋找的項目。  </span><span class="sxs-lookup"><span data-stu-id="6b0ef-p109">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns. A pattern is what DLP looks for when it evaluates content such as email and documents.   </span></span><!-- ok then this is going to be really confusing since the terminology changes.... --><span data-ttu-id="6b0ef-p110"> (術語快速附註 - 如果您熟悉 DLP 原則，就會知道原則包含一或多個由條件和動作組成的規則。但是在本主題中，XML 標記使用規則來表示會定義實體的模式，也稱為機密資訊類型。因此在本主題中，當您看到規則時，請將它視為實體或機密資訊類型，而不是條件和動作。)</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p110"> (A quick note on terminology - if you're familiar with DLP policies, you know that a policy contains one or more rules comprised of conditions and actions. However, in this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type. So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.)</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="6b0ef-134">最簡單的案例：具有一種模式的實體</span><span class="sxs-lookup"><span data-stu-id="6b0ef-134">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="6b0ef-p111">以下是最簡單的案例。您想要您的 DLP 原則可以識別內容，其中包含貴組織的員工識別碼，該識別碼的格式為 9 位數數字。因此模式是指規則中所包含的規則運算式，可以識別 9 位數數字。任何包含 9 位數數字的內容都會滿足模式。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p111">Here's the simplest scenario. You want your DLP policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number. So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers. Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![具有一種模式的實體圖表](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="6b0ef-140">不過，這個模式雖然簡單，但是可以藉由將其中包含不一定是員工識別碼的任何 9 位數數字內容進行比對，識別許多誤判。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-140">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="6b0ef-141">更常見的案例：具有多種模式的實體</span><span class="sxs-lookup"><span data-stu-id="6b0ef-141">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="6b0ef-142">基於這個原因，使用一個以上的模式來定義實體更為常見，其中模式除了實體 (例如 9 位數數字) 之外，還會識別支援辨識項 (例如關鍵字或日期)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-142">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="6b0ef-143">例如，若要增加識別內容 (包含員工識別碼) 的可能性，除了 9 位數數字之外，您可以定義同時會識別雇用日期的另一個模式，並且再定義另一個模式，同時識別雇用日期和關鍵字 (例如「員工識別碼」)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-143">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![具有多種模式的實體圖表](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="6b0ef-145">請注意此結構的幾個重要層面：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-145">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="6b0ef-p112">需要更多辨識項的模式具有較高的信賴等級。這相當有用，因為當您稍後在 DLP 原則中使用這個機密資訊類型時，可以只對較高信賴相符項目使用更嚴格限制的動作 (例如封鎖內容)，以及對較低信賴相符項目使用較不具限制性的動作 (例如傳送通知)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p112">Patterns that require more evidence have a higher confidence level. This is useful because when you later use this sensitive information type in a DLP policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>
    
- <span data-ttu-id="6b0ef-p113">支援 IdMatch 和 Match 元素會參考 regexes 與關鍵字，它們實際上是 Rule 元素的子項目，而不是 Pattern 元素的子項目。這些支援元素是由 Pattern 參考，但是包含在 Rule 中。這表示支援元素 (例如規則運算式或關鍵字清單) 的單一定義可以由多個實體和模式參考。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p113">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern. These supporting elements are referenced by the Pattern but included in the Rule. This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>
    
## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="6b0ef-p114">您需要識別什麼實體？[Entity 元素、id 屬性]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p114">What entity do you need to identify? [Entity element, id attribute]</span></span>

<span data-ttu-id="6b0ef-p115">實體是機密資訊類型 (例如信用卡號碼)，具有定義良好的模式。每個實體都有唯一的 GUID 作為其識別碼。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p115">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern. Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="6b0ef-155">為實體命名並產生其 GUID</span><span class="sxs-lookup"><span data-stu-id="6b0ef-155">Name the entity and generate its GUID</span></span>
<!-- why isn't the following in procedure format? --><span data-ttu-id="6b0ef-p116"> 新增 Rules 和 Entity 元素。然後新增註解，其中包含自訂實體的名稱 (在此範例中是員工識別碼)。稍後您會將實體名稱新增至當地語系化字串區段，該名稱就是當您建立 DLP 原則時出現在 UI 中的名稱。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p116"> Add the Rules and Entity elements. Then add a comment that contains the name of your custom entity - in this example, Employee ID. Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a DLP policy.</span></span>
  
<span data-ttu-id="6b0ef-p117">接下來，為實體產生 GUID。有多種方法可以產生 GUID，但是您可以藉由在 PowerShell 中輸入 [guid]::NewGuid()，輕易地完成。稍後您也會將實體 GUID 新增至當地語系化字串區段。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p117">Next, generate a GUID for your entity. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid(). Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![XML 標記，顯示 Rules 和 Entity 元素](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="6b0ef-p118">您要比對什麼模式？[Pattern 元素、IdMatch 元素、Regex 元素]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p118">What pattern do you want to match? [Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="6b0ef-p119">模式包含機密資訊類型所尋找項目的清單。這些項目包含 regexes、關鍵字及內建函式 (執行像是執行 regexes 以尋找日期或地址的工作)。機密資訊類型可以有多個具有唯一信賴的模式。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p119">The pattern contains the list of what the sensitive information type is looking for. This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses). Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="6b0ef-p120">以下模式的共通點是都參考相同的規則運算式，該運算式會尋找 由空格 (\s) … (\s) 圍繞的 9 位數數字 (\d{9})。此規則運算式是由 IdMatch 元素參考，是所有模式 (尋找員工識別碼實體) 的通用需求。IdMatch 是模式嘗試比對的識別碼，例如員工識別碼或信用卡號碼或社會安全號碼。Pattern 元素必須確實只有一個 IdMatch 元素。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p120">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) … (\s). This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity. IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number. A Pattern element must have exactly one IdMatch element.</span></span>
  
![XML 標記，顯示會參考單一 Regex 元素的多個 Pattern 元素](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="6b0ef-p121">滿足條件時，模式會傳回計數和信賴等級，您可以在 DLP 原則的條件中使用。當您將會偵測機密資訊類型的條件新增至 DLP 原則時，可以編輯計數和信賴等級，如下所示。信賴等級 (也稱為比對正確性) 會在本主題稍後說明。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p121">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![執行個體計數和比對正確性選項](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="6b0ef-p122">當您建立規則運算式時，請記住，要注意潛在問題。例如，如果您撰寫及上傳會識別太多內容的 regex，則會影響到效能。若要深入了解這些潛在問題，請參閱稍後的[要注意的潛在驗證問題](#potential-validation-issues-to-be-aware-of)一節。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p122">When you create your regular expression, keep in mind that there are potential issues to be aware of. For example, if you write and upload a regex that identifies too much content, this can impact performance. To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="6b0ef-p123">是否想要要求其他辨識項？[Match 元素、minCount 屬性]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p123">Do you want to require additional evidence? [Match element, minCount attribute]</span></span>

<span data-ttu-id="6b0ef-183">除了 IdMatch 之外，模式可以使用 Match 元素來要求其他支援辨識項，例如關鍵字、regex，日期或地址。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-183">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="6b0ef-p124">模式可以包含多個 Match 元素；它們可以直接包含在 Pattern 元素中，或是使用 Any 元素來合併。Match 是由隱含的 AND 運算子來加入；所有 Match 元素必須滿足要比對的模式。您可以使用 Any 元素來引入 AND 或 OR 運算子 (稍後章節會詳加說明)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p124">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element. Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched. You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="6b0ef-p125">您可以使用選擇性的 minCount 屬性，來指定針對每個 Match 元素必須找到多少個相符項目的執行個體。例如，您可以指定只有在找到關鍵字清單中的至少兩個關鍵字時，模式才會獲得滿足。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p125">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements. For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![XML 標記，顯示具有 minOccurs 屬性的 Match 元素](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="6b0ef-190">關鍵字 [Keyword、Group 及 Term 元素、matchStyle 和 caseSensitive 屬性]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-190">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="6b0ef-p126">當您識別機密資訊 (例如員工識別碼) 時，通常想要要求關鍵字作為確切辨識項。例如，除了比對 9 位數數字之外，您可能想要尋找例如 "card"、"badge" 或 "ID" 的字詞。若要完成這項操作，您會使用 Keyword 元素。Keyword 元素具有 id 屬性，可以由多個模式或實體中的多個 Match 元素參考。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p126">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence. For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID". To do this, you use the Keyword element. The Keyword element has an id attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="6b0ef-p127">系統包含關鍵字作為 Group 元素中 Term 元素的清單。Group 元素具有 matchStyle 屬性，有兩個可能值：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p127">Keywords are included as a list of Term elements in a Group element. The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="6b0ef-p128">**matchStyle="word"** 字詞比對會識別空格或其他分隔符號圍繞的完整字詞。您應該永遠使用字詞，除非需要比對部分字詞或比對亞洲語言的字詞。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p128">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters. You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="6b0ef-p129">**matchStyle="string"** 字串比對會識別字串，無論有任何符號圍繞。例如，"id" 會比對 "bid" 和 "idea"。只有在您需要比對亞洲字詞，或者如果您的關鍵字可能包含作為其他字串的一部分時，才使用字串。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p129">**matchStyle="string"** String match identifies strings no matter what they're surrounded by. For example, "id" will match "bid" and "idea". Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="6b0ef-202">最後，您可以使用 Term 元素的 caseSensitive 屬性，指定內容必須完全符合關鍵字，包括小寫和大寫字母。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-202">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![XML 標記，顯示參考關鍵字的 Match 元素](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="6b0ef-204">規則運算式 [Regex 元素]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-204">Regular expressions [Regex element]</span></span>

<span data-ttu-id="6b0ef-p130">在此範例中，員工識別碼實體已經使用 IdMatch 元素來參考 regex 的模式 - 空格圍繞的 9 位數數字。此外，模式可以使用 Match 元素來參考額外的 Regex 元素，以識別確切識別碼，例如 5 位數或 9 位數數字格式的美國郵遞區號。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p130">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern - a nine-digit number surrounded by whitespace. In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="6b0ef-207">其他模式，例如日期或地址 [內建函式]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-207">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="6b0ef-p131">除了內建機密資訊類型之外，DLP 也包含內建函式，可以識別確切識別碼，例如美國日期、歐洲日期、到期日或美國地址。DLP 不支援上傳您自己的自訂函式，但是當您建立自訂機密資訊類型時，您的實體可以參考內建函式。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p131">In addition to the built-in sensitive information types, DLP also includes built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address. DLP does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="6b0ef-210">例如，員工識別碼識別證上面有雇用日期，因此這個自訂實體可以使用內建函式 `Func_us_date` 來識別以美國通用格式表示的日期。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-210">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="6b0ef-211">如需詳細資訊，請參閱 [DLP 功能所尋找的項目](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-211">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![XML 標記，顯示參考內建函式的 Match 元素](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="6b0ef-213">不同的辨識項組合 [Any 元素、minMatches 和 maxMatches 屬性]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-213">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="6b0ef-p132">在 Pattern 元素中，所有 IdMatch 和 Match 元素是由隱含的 AND 運算子聯結 - 在滿足模式之前，必須滿足所有相符項目。但是，您可以藉由使用 Any 元素將 Match 元素群組在一起，建立更具彈性的比對邏輯。例如，您可以使用 Any 元素讓其子 Match 元素的子集完全相符、完全不相符或準確相符。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p132">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator - all of the matches must be satisfied before the pattern can be satisfied. However, you can create more flexible matching logic by using the Any element to group Match elements. For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="6b0ef-p133">Any 元素具有選擇性的 minMatches 和 maxMatches 屬性，您可以用來定義在模式相符之前，必須滿足多少子 Match 元素。請注意，這些屬性會定義必須滿足的 Match 元素數目，而不是針對相符項目找到的辨識項執行個體數目。若要定義特定相符項目執行個體數目的下限 (例如清單中的關鍵字)，請針對 Match 元素使用 minCount 屬性 (如上所述)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p133">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched. Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches. To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="6b0ef-220">與至少一個子 Match 元素相符</span><span class="sxs-lookup"><span data-stu-id="6b0ef-220">Match at least one child Match element</span></span>

<span data-ttu-id="6b0ef-p134">如果您想要要求只需符合 Match 元素數目的下限，可以使用 minMatches 屬性，事實上，這些 Match 元素是由隱含的 OR 運算子聯結。如果找到美國格式日期或清單中的關鍵字時，這個 Any 元素會獲得滿足。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p134">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute. In effect, these Match elements are joined by an implicit OR operator. This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="6b0ef-224">比對任一子 Match 元素的精確子集</span><span class="sxs-lookup"><span data-stu-id="6b0ef-224">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="6b0ef-p135">如果您想要要求必須符合 Match 元素的準確數目，可以將 minMatches 和 maxMatches 設為相同值。只有在確實找到一個日期或關鍵字時，這個 Any 元素才會獲得滿足，超過的話，模式就不會相符。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p135">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value. This Any element is satisfied only if exactly one date or keyword is found - any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="6b0ef-227">與子 Match 元素完全不相符</span><span class="sxs-lookup"><span data-stu-id="6b0ef-227">Match none of children Match elements</span></span>

<span data-ttu-id="6b0ef-p136">如果您想要要求排除特定辨識項以讓模式獲得滿足，可以將 minMatches 和 maxMatches 都設為 0。如果您有很可能會誤判的關鍵字清單或辨識項時，這個方法很有用。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p136">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0. This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="6b0ef-p137">例如，員工識別碼實體會尋找關鍵字 "card"，因為它可能代表 "ID card"。但是，如果卡片只出現在片語 "credit card" 中，則該內容中的 "card" 不太可能是指 "ID card"。因此您可以將 "credit card" 作為關鍵字新增至術語清單，此清單是用來排除以免滿足模式。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p137">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card". However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card". So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="6b0ef-233">比對數個唯一術語</span><span class="sxs-lookup"><span data-stu-id="6b0ef-233">Match a number of unique terms</span></span>

<span data-ttu-id="6b0ef-234">如果您要比對數個唯一術語，請使用 *uniqueResults* 參數，設為 *true*，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-234">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="6b0ef-235">在此範例中，使用至少三個唯一相符項目定義薪資修訂的模式。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-235">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="6b0ef-p138">其他辨識項必須多接近實體？[patternsProximity 屬性]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p138">How close to the entity must the other evidence be? [patternsProximity attribute]</span></span>

<span data-ttu-id="6b0ef-p139">您的機密資訊類型正在尋找代表員工識別碼的模式，該模式的一部分正在尋找像是關鍵字 (例如 "ID") 的確切辨識項。此辨識項越接近，模式就更有可能是真正的員工識別碼。您可以使用 Entity 元素的必要 patternsProximity 屬性，決定模式中的其他辨識項必須與實體有多接近。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p139">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID". It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID. You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![XML 標記，顯示 patternsProximity 屬性](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="6b0ef-p140">對實體中的每個模式來說，patternsProximity 屬性值可以定義所有其他針對該模式所指定的 Match 與 IdMatch 位置相隔的距離 (以 Unicode 字元形式)。近似值視窗會由 IdMatch 的位置來定位，且視窗會延展到 IdMatch 的左右兩側。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p140">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern. The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![近似值視窗的圖表](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="6b0ef-p141">以下範例說明近似值視窗會如何影響模式比對，其中員工識別碼自訂實體的 IdMatch 元素需要至少一個確切相符的關鍵字或日期。只有 ID1 相符，因為對於 ID2 和 ID3，在近似值視窗中只找到部分確切辨識項，或完全找不到。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p141">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date. Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="6b0ef-p142">請注意，對於電子郵件，系統會將郵件內文和每個附件視為個別項目。這表示近似值視窗不會延伸超過每個項目結尾。對於每個項目 (附件或內文)，idMatch 和確切辨識項都必須位於該項目內。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p142">Note that for email, the message body and each attachment are treated as separate items. This means that the proximity window does not extend beyond the end of each of these items. For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="6b0ef-p143">不同模式的正確信賴等級為何？[confidenceLevel 屬性、recommendedConfidence 屬性]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p143">What are the right confidence levels for different patterns? [confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="6b0ef-p144">模式需要的辨識項越多，您就可以對於在模式相符時識別出真正實體 (例如員工識別碼) 更具信心。例如，相較於只需要 9 位數識別碼，您對於需要 9 位數數字、雇用日期、接近近似性的關鍵字的模式會更具信心。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p144">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched. For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="6b0ef-p145">Pattern 元素具有必要的 confidenceLevel 屬性。您可以將 confidenceLevel (介於 1 與 100 之間的整數) 的值視為實體中每個模式的唯一識別碼 - 實體中的模式必須具有與您所指派不同的信賴等級。準確的整數值無關緊要 - 只要挑選對於您的合規性小組有意義的數字即可。在您上傳自訂機密資訊類型然後建立 DLP 原則之後，可以在您建立的規則條件中參考這些信賴等級。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p145">The Pattern element has a required confidenceLevel attribute. You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity - the patterns in an entity must have different confidence levels that you assign. The precise value of the integer doesn't matter - simply pick numbers that make sense to your compliance team. After you upload your custom sensitive information type and then create a DLP policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![XML 標記，顯示具有不同 confidenceLevel 屬性值的 Pattern 元素](../media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
<span data-ttu-id="6b0ef-p146">除了每個 Pattern 的 confidenceLevel 之外，Entity 具有 recommendedConfidence 屬性。可以將建議的 confidence 屬性視為規則的預設信賴等級。當您在 DLP 原則中建立規則時，如果您未指定要讓規則使用的信賴等級，該規則會根據實體的建議信賴等級進行比對。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p146">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute. The recommended confidence attribute can be thought of as the default confidence level for the rule. When you create a rule in a DLP policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span>
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-security-amp-compliance-center-localizedstrings-element"></a><span data-ttu-id="6b0ef-p147">您是否要在安全性與合規性中心的 UI 中支援其他語言？[LocalizedStrings 元素]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p147">Do you want to support other languages in the UI of the Security &amp; Compliance Center? [LocalizedStrings element]</span></span>

<span data-ttu-id="6b0ef-p148">如果您的合規性小組使用 Microsoft 365 安全性與合規性中心，以不同的地區設定和語言建立 DLP 原則，您可以提供當地語系化版本的自訂敏感性資訊類型名稱和描述。當您的合規性小組以您支援的語言使用 Microsoft 365 時，他們會在 UI 中看到當地語系化名稱。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p148">If your compliance team uses the Microsoft 365 Security &amp; Compliance Center to create DLP policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type. When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![執行個體計數和比對正確性選項](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="6b0ef-p149">Rules 元素必須包含 LocalizedStrings 元素，後者包含 Resource 元素，它會參考您的自訂實體的 GUID。接下來，每個 Resource 元素包含一或多個 Name 和 Description 元素，每個元素會使用 langcode 屬性來提供特定語言的當地語系化字串。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p149">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity. In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![XML 標記，顯示 LocalizedStrings 元素的內容](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="6b0ef-p150">請注意，您只有針對自訂機密資訊類型在安全性與合規性中心 UI 中的外觀，才使用當地語系化字串。您無法使用當地語系化字串來提供不同當地語系化版本的關鍵字清單或規則運算式。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p150">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Security &amp; Compliance Center. You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="6b0ef-273">其他規則套件標記 [RulePack GUID]</span><span class="sxs-lookup"><span data-stu-id="6b0ef-273">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="6b0ef-p151">最後，每個 RulePackage 的開頭都包含您必須填入的一些一般資訊。您可以使用下列標記作為範本，並且以您自己的資訊來取代 ". . ." 預留位置。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p151">Finally, the beginning of each RulePackage contains some general information that you need to fill in. You can use the following markup as a template and replace the ". . ." placeholders with your own info.</span></span>
  
<span data-ttu-id="6b0ef-p152">最重要的是，您必須為 RulePack 產生 GUID。前面您已經為實體產生 GUID；這是適用於 RulePack 的第二個 GUID。有數種方式可以產生 GUID，但是您可以藉由在 PowerShell 中輸入 [guid]::NewGuid()，輕易地完成。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p152">Most importantly, you'll need to generate a GUID for the RulePack. Above, you generated a GUID for the entity; this is a second GUID for the RulePack. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="6b0ef-p153">Version 元素也很重要。當您第一次上傳規則套件時，Microsoft 365 會記下版本號碼。稍後如果您更新規則套件並且上傳新版本，請務必更新版本號碼，否則 Microsoft 365 不會部署規則套件。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p153">The Version element is also important. When you upload your rule package for the first time, Microsoft 365 notes the version number. Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
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
    . . .
 </Rules>
</RulePackage>

```

<span data-ttu-id="6b0ef-285">完成後，您的 RulePack 元素看起來應該像這樣。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-285">When complete, your RulePack element should look like this.</span></span>
  
![XML 標記，顯示 RulePack 元素](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="6b0ef-287">針對 Exchange Online 變更</span><span class="sxs-lookup"><span data-stu-id="6b0ef-287">Changes for Exchange Online</span></span>

<span data-ttu-id="6b0ef-p154">以前，您可能已使用 Exchange Online PowerShell，針對 DLP 匯入您的自訂機密資訊類型。現在您的自訂機密資訊類型可以在 Exchange 系統管理中心及安全性與合規性中心中使用。作為此改進的一部分，您應該使用安全性與合規性中心 PowerShell 來匯入您的自訂機密資訊類型 - 您無法再從 Exchange PowerShell 匯入。您的自訂機密資訊類型會繼續如同以往一般運作；但是，在安全性與合規性中心中對於自訂機密資訊類型所做的變更，可能需要最多一個小時才會在 Exchange 系統管理中心中顯示。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p154">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP. Now your custom sensitive information types can be used in both the Exchange admin center and the Security &amp; Compliance Center. As part of this improvement, you should use Security &amp; Compliance Center PowerShell to import your custom sensitive information types - you can't import them from the Exchange PowerShell anymore. Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Security &amp; Compliance Center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="6b0ef-p155">請注意，在安全性與合規性中心中，您使用的是 **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage?view=exchange-ps)** Cmdlet 來上傳規則套件。(以前，在 Exchange 系統管理中心中，您使用的是 **ClassificationRuleCollection** Cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p155">Note that in the Security &amp; Compliance Center, you use the **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage?view=exchange-ps)** cmdlet to upload a rule package. (Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="6b0ef-294">上傳您的規則套件</span><span class="sxs-lookup"><span data-stu-id="6b0ef-294">Upload your rule package</span></span>



<span data-ttu-id="6b0ef-295">若要上傳您的規則套件，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-295">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="6b0ef-296">使用 Unicode 編碼方式將它儲存為 .xml 檔。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-296">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="6b0ef-297">連線到安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b0ef-297">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. <span data-ttu-id="6b0ef-298">請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-298">Use the following syntax:</span></span>

```powershell
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte) -ReadCount 0
```

    This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.

```powershell
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte) -ReadCount 0
```

    For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage).

> [!NOTE]
> <span data-ttu-id="6b0ef-299">自訂敏感性資訊類型集合的上限為 10。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-299">The limit for custom sensitive information type collections is 10.</span></span>

4. <span data-ttu-id="6b0ef-300">若要確認您已成功建立新的機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-300">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="6b0ef-301">執行 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) Cmdlet 來驗證新的規則套件，列於：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-301">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet to verify the new rule package is listed:</span></span>

```powershell
Get-DlpSensitiveInformationTypeRulePackage
``` 

  - <span data-ttu-id="6b0ef-302">執行 [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) Cmdlet 來驗證機密資訊類型，列於：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-302">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information type is listed:</span></span>

```powershell
Get-DlpSensitiveInformationType
``` 

    For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.

  - <span data-ttu-id="6b0ef-303">將 \<Name\> 取代為機密資訊類型的名稱值 (例如，員工識別碼)，然後執行 [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-303">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet:</span></span>

```powershell
Get-DlpSensitiveInformationType -Identity "<Name>"
```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="6b0ef-304">要注意的潛在驗證問題</span><span class="sxs-lookup"><span data-stu-id="6b0ef-304">Potential validation issues to be aware of</span></span>

<span data-ttu-id="6b0ef-p156">當您上傳規則套件 XML 檔案時，系統會驗證 XML 並且檢查已知錯誤模式和明顯的效能問題。以下是驗證會針對規則運算式檢查的一些已知問題：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p156">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues. Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="6b0ef-307">不得以垂直線 "|" 開頭或結尾，它會比對所有項目，因為系統會將它視為空白比對。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-307">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
    <span data-ttu-id="6b0ef-308">例如，"|a" 或 "b|" 不會通過驗證。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-308">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="6b0ef-309">不得以 ".{0,m}" 模式開頭或結尾，它沒有功能目的，只會妨礙效能。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-309">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
    <span data-ttu-id="6b0ef-310">例如，".{0,50}ASDF" 或 "ASDF.{0,50}" 不會通過驗證。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-310">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="6b0ef-311">在群組中不能有 ".{0,m}" 或 ".{1,m}"，以及在群組中不能有 ".\*" 或 ".+"。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-311">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
    <span data-ttu-id="6b0ef-312">例如，"(.{0,50000})" 不會通過驗證。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-312">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="6b0ef-313">在群組中不能有具有 "{0,m}" 或 "{1,m}" 中繼器的任何字元。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-313">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
    <span data-ttu-id="6b0ef-314">例如，"(a\*)" 不會通過驗證。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-314">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="6b0ef-315">不得以 ".{1,m}" 開頭或結尾；請改用 "."</span><span class="sxs-lookup"><span data-stu-id="6b0ef-315">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
    <span data-ttu-id="6b0ef-316">例如，".{1,m}asdf" 不會通過驗證。請改用 ".asdf"。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-316">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="6b0ef-317">群組中不能有無限制的中繼器 (例如 "\*" 或 "+")。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-317">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
    <span data-ttu-id="6b0ef-318">例如，"(xx)\*" 和 "(xx)+" 不會通過驗證。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-318">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
    
<span data-ttu-id="6b0ef-319">如果自訂機密資訊類型包含可能會影響效能的問題，則無法上傳，您可能會看到下列其中一個錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-319">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="6b0ef-320">**比預期符合更多內容的一般數量詞 (例如 '+'、'\*')**</span><span class="sxs-lookup"><span data-stu-id="6b0ef-320">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="6b0ef-321">**查詢斷定**</span><span class="sxs-lookup"><span data-stu-id="6b0ef-321">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="6b0ef-322">**與一般數量詞搭配使用的複雜群組**</span><span class="sxs-lookup"><span data-stu-id="6b0ef-322">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="6b0ef-323">重新編目內容以識別機密資訊</span><span class="sxs-lookup"><span data-stu-id="6b0ef-323">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="6b0ef-p157">DLP 會使用搜尋編目程式來識別及分類網站內容中的機密資訊。SharePoint Online 和商務用 OneDrive 中的內容會在每次更新時自動重新編目。但是若要識別所有現有內容中，您的新自訂類型機密資訊，該內容必須重新編目。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p157">DLP uses the search crawler to identify and classify sensitive information in site content. Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated. But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="6b0ef-327">在 Microsoft 365 中，您無法手動要求對整個租用戶重新編目，但是您可以為網站集合、清單或文件庫這麼做，請參閱[手動要求網站、文件庫或清單的編目和重新編製索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-327">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library - see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>
  
## <a name="remove-a-custom-sensitive-information-type"></a><span data-ttu-id="6b0ef-328">移除自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="6b0ef-328">Remove a custom sensitive information type</span></span>

> [!NOTE]
> <span data-ttu-id="6b0ef-329">在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-329">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

<span data-ttu-id="6b0ef-330">在安全性與合規性中心 PowerShell 中，有兩種方法可以移除自訂機密資訊類型：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-330">In Security & Compliance Center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="6b0ef-p158">**移除個別的自訂機密資訊類型**： 使用[修改自訂機密資訊類型](#modify-a-custom-sensitive-information-type)中所述的方法。您可以匯出包含自訂機密資訊類型的自訂規則套件、從 XML 檔中移除機密資訊類型，以及將已更新的 XML 檔匯入到現有的自訂規則套件。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-p158">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type). You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="6b0ef-333">**移除自訂規則套件及其包含的所有自訂機密資訊類型**：本節會描述此方法。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-333">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

1. [<span data-ttu-id="6b0ef-334">連線到安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b0ef-334">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)

2. <span data-ttu-id="6b0ef-335">若要移除自訂規則套件，請使用 [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage?view=exchange-ps) Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-335">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet:</span></span>

```powershell
Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
```

    You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.

    This example removes the rule package named "Employee ID Custom Rule Pack".

```powershell
Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
```

    For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage).

3. <span data-ttu-id="6b0ef-336">若要確認您已成功移除自訂機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-336">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="6b0ef-337">執行 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) Cmdlet，並驗證規則套件，不再列於：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-337">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet and verify the rule package is no longer listed:</span></span>

```powershell
Get-DlpSensitiveInformationTypeRulePackage
``` 

  - <span data-ttu-id="6b0ef-338">執行 [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) Cmdlet，並驗證不再列出已移除之規則套件中的機密資訊類型：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-338">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

```powershell
Get-DlpSensitiveInformationType
``` 

    For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.

  - <span data-ttu-id="6b0ef-339">將 \<Name\> 取代為機密資訊類型的名稱值 (例如，員工識別碼)，然後執行 [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) Cmdlet，以驗證不再列出機密資訊類型：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-339">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to verify the sensitive information type is no longer listed:</span></span>

```powershell
Get-DlpSensitiveInformationType -Identity "<Name>"
```

## <a name="modify-a-custom-sensitive-information-type"></a><span data-ttu-id="6b0ef-340">修改自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="6b0ef-340">Modify a custom sensitive information type</span></span>

<span data-ttu-id="6b0ef-341">在安全性與合規性中心 PowerShell 中，修改自訂機密資訊類型，需要您：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-341">In Security & Compliance Center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="6b0ef-342">將包含自訂機密資訊類型的現有規則套件匯出至 XML 檔 (或使用現有的 XML 檔，若您有一個的話)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-342">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span> 

2. <span data-ttu-id="6b0ef-343">修改已匯出之 XML 檔中的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-343">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="6b0ef-344">將更新的 XML 檔匯入至現有的規則套件。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-344">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="6b0ef-345">若要連線到安全性與合規性中心 PowerShell，請參閱[連線到安全性與合規性中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-345">To connect to Security & Compliance Center PowerShell, see [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

#### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="6b0ef-346">步驟 1：將現有規則套件匯出至 XML 檔</span><span class="sxs-lookup"><span data-stu-id="6b0ef-346">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="6b0ef-347">如果您有 XML 檔的複本 (例如，您剛建立並匯入它)，則可以跳到下一個步驟來修改 XML 檔。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-347">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="6b0ef-348">如果您不清楚，請執行 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) Cmdlet 來尋找自訂規則套件的名稱：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-348">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtype?view=exchange-ps) cmdlet to find the name of the custom rule package:</span></span>

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```

> [!NOTE]
> <span data-ttu-id="6b0ef-349">包含內建敏感性資訊類型的內建規則套件稱為 Microsoft 規則套件。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-349">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package.</span></span> <span data-ttu-id="6b0ef-350">此規則套件名為 Microsoft.SCCManaged.CustomRulePack，其中包含您已在安全性與合規性中心 UI 中建立的自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-350">The rule package that contains the custom sensitive information types that you created in the Security & Compliance Center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="6b0ef-351">使用 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) Cmdlet，將自訂規則套件儲存至變數：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-351">Use the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet to store the custom rule package to a variable:</span></span>

```powershell
$rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
```

   <span data-ttu-id="6b0ef-352">例如，如果規則套件的名稱為 "Employee ID Custom Rule Pack"，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-352">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

```powershell
$rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
```

3. <span data-ttu-id="6b0ef-353">請使用 [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) Cmdlet 將自訂規則套件匯出至 XML 檔：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-353">Use the [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) cmdlet to export the custom rule package to an XML file:</span></span>

```powershell
Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
```

    This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.

```powershell
Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="6b0ef-354">步驟 2：修改已匯出之 XML 檔中的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-354">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="6b0ef-355">稍早已在本主題中描述 XML 檔中的機密資訊類型和檔案中的其他元素。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-355">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="6b0ef-356">步驟 3：將更新的 XML 檔匯入至現有的規則套件。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-356">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="6b0ef-357">若要更新的 XML 重新匯入現有規則套件，請使用 [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage?view=exchange-ps) Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6b0ef-357">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage?view=exchange-ps) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="6b0ef-358">如需詳細的語法和參數資訊，請參閱 [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-358">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage).</span></span>

## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="6b0ef-359">參考：規則套件 XML 結構描述定義</span><span class="sxs-lookup"><span data-stu-id="6b0ef-359">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="6b0ef-360">您可以複製此標記、將它儲存為 XSD 檔，然後用它來驗證規則套件 XML 檔。</span><span class="sxs-lookup"><span data-stu-id="6b0ef-360">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="https://schemas.microsoft.com/office/2011/mce"
           targetNamespace="https://schemas.microsoft.com/office/2011/mce" 
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>        
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>

```

## <a name="more-information"></a><span data-ttu-id="6b0ef-361">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6b0ef-361">More information</span></span>

- [<span data-ttu-id="6b0ef-362">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="6b0ef-362">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="6b0ef-363">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="6b0ef-363">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="6b0ef-364">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="6b0ef-364">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)