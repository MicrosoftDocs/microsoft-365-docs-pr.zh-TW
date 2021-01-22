---
title: 瞭解敏感性資訊類型
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 896a529d67faddb45b2672ca077f5a8e3b19827e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933077"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="0a8cb-102">瞭解敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="0a8cb-102">Learn about sensitive information types</span></span>

<span data-ttu-id="0a8cb-103">識別及分類組織控制下的機密專案，是資訊保護分項 [的第一個步驟](protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="0a8cb-104">Microsoft 365 提供三種識別專案的方式，以便分類：</span><span class="sxs-lookup"><span data-stu-id="0a8cb-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="0a8cb-105">使用者手動</span><span class="sxs-lookup"><span data-stu-id="0a8cb-105">manually by users</span></span>
- <span data-ttu-id="0a8cb-106">自動化模式識別，例如敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="0a8cb-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="0a8cb-107">機器學習</span><span class="sxs-lookup"><span data-stu-id="0a8cb-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="0a8cb-108">敏感性資訊類型是以模式為基礎的分類器。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="0a8cb-109">它們可偵測敏感性資訊 ，例如社會安全、信用卡或銀行帳戶號碼以識別敏感性專案，請參閱敏感性 [資訊類型實體定義](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="0a8cb-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="0a8cb-110">敏感性資訊類型用於</span><span class="sxs-lookup"><span data-stu-id="0a8cb-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="0a8cb-111">資料外洩防護原則</span><span class="sxs-lookup"><span data-stu-id="0a8cb-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="0a8cb-112">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="0a8cb-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="0a8cb-113">保留標籤</span><span class="sxs-lookup"><span data-stu-id="0a8cb-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="0a8cb-114">通訊合規性</span><span class="sxs-lookup"><span data-stu-id="0a8cb-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="0a8cb-115">自動標籤策略</span><span class="sxs-lookup"><span data-stu-id="0a8cb-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="0a8cb-116">敏感性資訊類型的基本部分</span><span class="sxs-lookup"><span data-stu-id="0a8cb-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="0a8cb-117">每個敏感性資訊類型實體是由這些欄位定義：</span><span class="sxs-lookup"><span data-stu-id="0a8cb-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="0a8cb-118">名稱：如何參考敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="0a8cb-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="0a8cb-119">描述：描述敏感性資訊類型尋找的內容</span><span class="sxs-lookup"><span data-stu-id="0a8cb-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="0a8cb-120">模式：模式會定義敏感性資訊類型偵測到的資訊。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="0a8cb-121">它包含下列元件</span><span class="sxs-lookup"><span data-stu-id="0a8cb-121">It consists of the following components</span></span>
    - <span data-ttu-id="0a8cb-122">主要元素是敏感性資訊類型要尋找的主要元素。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="0a8cb-123">它可以是 **包含或不含檢查** 和驗證、關鍵字清單 **、關鍵字字典** 或函數的 **正則運算式**。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="0a8cb-124">支援元素 – 做為支援證據的元素，可協助提高比對的信賴度。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="0a8cb-125">例如，鄰近 SSN 數位的關鍵字 "SSN"。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="0a8cb-126">它可以是包含或不含檢查和驗證、關鍵字清單、關鍵字字典的正則運算式。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="0a8cb-127">信賴等級 - 信賴等級 (、中、低) 反應與主要元素一起偵測到的支援證據量。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="0a8cb-128">專案包含的支援證據越多，相符專案的信賴度越高，就表示您正在尋找的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="0a8cb-129">鄰近-主要與支援元素之間的字元數</span><span class="sxs-lookup"><span data-stu-id="0a8cb-129">Proximity – Number of characters between primary and supporting element</span></span>

![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="0a8cb-131">在這段影片中深入瞭解信賴等級</span><span class="sxs-lookup"><span data-stu-id="0a8cb-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="0a8cb-132">敏感性資訊類型範例</span><span class="sxs-lookup"><span data-stu-id="0a8cb-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="0a8cb-133">阿根廷國家/ (身分識別) 號碼</span><span class="sxs-lookup"><span data-stu-id="0a8cb-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="0a8cb-134">格式</span><span class="sxs-lookup"><span data-stu-id="0a8cb-134">Format</span></span>

<span data-ttu-id="0a8cb-135">以句點分隔的八位數</span><span class="sxs-lookup"><span data-stu-id="0a8cb-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="0a8cb-136">模式</span><span class="sxs-lookup"><span data-stu-id="0a8cb-136">Pattern</span></span>

<span data-ttu-id="0a8cb-137">八位數：</span><span class="sxs-lookup"><span data-stu-id="0a8cb-137">Eight digits:</span></span>
- <span data-ttu-id="0a8cb-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="0a8cb-138">two digits</span></span>
- <span data-ttu-id="0a8cb-139">a period</span><span class="sxs-lookup"><span data-stu-id="0a8cb-139">a period</span></span>
- <span data-ttu-id="0a8cb-140">三位數</span><span class="sxs-lookup"><span data-stu-id="0a8cb-140">three digits</span></span>
- <span data-ttu-id="0a8cb-141">a period</span><span class="sxs-lookup"><span data-stu-id="0a8cb-141">a period</span></span>
- <span data-ttu-id="0a8cb-142">三位數</span><span class="sxs-lookup"><span data-stu-id="0a8cb-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0a8cb-143">校驗</span><span class="sxs-lookup"><span data-stu-id="0a8cb-143">Checksum</span></span>

<span data-ttu-id="0a8cb-144">否</span><span class="sxs-lookup"><span data-stu-id="0a8cb-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="0a8cb-145">定義</span><span class="sxs-lookup"><span data-stu-id="0a8cb-145">Definition</span></span>

<span data-ttu-id="0a8cb-146">DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：</span><span class="sxs-lookup"><span data-stu-id="0a8cb-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0a8cb-147">正則運算式會Regex_argentina_national_id找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0a8cb-148">系統找到Keyword_argentina_national_id關鍵字。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0a8cb-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0a8cb-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="0a8cb-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="0a8cb-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="0a8cb-151">阿根廷國家身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="0a8cb-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="0a8cb-152">身分識別</span><span class="sxs-lookup"><span data-stu-id="0a8cb-152">Identity</span></span> 
- <span data-ttu-id="0a8cb-153">身分識別身分識別卡</span><span class="sxs-lookup"><span data-stu-id="0a8cb-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="0a8cb-154">DNI</span><span class="sxs-lookup"><span data-stu-id="0a8cb-154">DNI</span></span> 
- <span data-ttu-id="0a8cb-155">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="0a8cb-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="0a8cb-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="0a8cb-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="0a8cb-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="0a8cb-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="0a8cb-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="0a8cb-158">Identidad</span></span> 
- <span data-ttu-id="0a8cb-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="0a8cb-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="0a8cb-160">進一步瞭解信賴等級</span><span class="sxs-lookup"><span data-stu-id="0a8cb-160">More on confidence levels</span></span>

<span data-ttu-id="0a8cb-161">在敏感性資訊類型實體定義中，信賴 **等級會反映** 除了主要元素外，還偵測到多少支援證據。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="0a8cb-162">專案包含的支援證據越多，相符專案的信賴度越高，就表示您正在尋找的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="0a8cb-163">例如，高信賴等級的比對值會包含較接近主要元素的更多支援證據，而信賴等級低的比對值在接近鄰近區中則包含很少或沒有支援證據。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="0a8cb-164">高信賴等級會回回最小的誤誤，但可能會導致漏報。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="0a8cb-165">低或中信賴等級會回回更多的誤誤，但少到零的漏報。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="0a8cb-166">**低信賴** 度：值 65，相符的專案會包含最小的漏報，但負數最多。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="0a8cb-167">**中信賴**：值 75，相符的專案會包含平均的誤正和負數。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="0a8cb-168">**高信賴** 度：值 85，相符的專案會包含最小的誤數，但負數最高。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="0a8cb-169">您應使用高信賴等級模式與低計數，例如 5 到 10 個，以及計數較高的低信賴度模式 ，例如 20 或更多。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="0a8cb-170">建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="0a8cb-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="0a8cb-171">若要在安全性與合規性中心建立自訂敏感性資訊類型，您可以從數個選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="0a8cb-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="0a8cb-172">**使用 UI** 您可以使用安全性與合規性中心 UI 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="0a8cb-173">使用此方法，您可以使用規則運算式、關鍵字和關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="0a8cb-174">若要進一步了解，請參閱[建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="0a8cb-175">**使用 EDM** 您可以使用以精確資料比對 (EDM) 為基礎的分類來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="0a8cb-176">此方法可讓您使用您可以定期更新的安全資料庫來建立動態敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="0a8cb-177">請參閱[使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="0a8cb-178">**使用 PowerShell** 您可以使用 PowerShell 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="0a8cb-179">雖然此方法比使用 UI 更複雜，但是您有多個組態選項。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="0a8cb-180">請參閱[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="0a8cb-181">Microsoft 365 資訊保護目前在預覽版中支援下列雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="0a8cb-181">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="0a8cb-182">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="0a8cb-182">Chinese (simplified)</span></span>
> - <span data-ttu-id="0a8cb-183">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="0a8cb-183">Chinese (traditional)</span></span>
> - <span data-ttu-id="0a8cb-184">韓文</span><span class="sxs-lookup"><span data-stu-id="0a8cb-184">Korean</span></span>
> - <span data-ttu-id="0a8cb-185">日文</span><span class="sxs-lookup"><span data-stu-id="0a8cb-185">Japanese</span></span>

><span data-ttu-id="0a8cb-186">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-186">This support is available for sensitive information types.</span></span> <span data-ttu-id="0a8cb-187">如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-187">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="0a8cb-188">進一步資訊</span><span class="sxs-lookup"><span data-stu-id="0a8cb-188">For further information</span></span>
- [<span data-ttu-id="0a8cb-189">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="0a8cb-189">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="0a8cb-190">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="0a8cb-190">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="0a8cb-191">在 PowerShell 中建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="0a8cb-191">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->