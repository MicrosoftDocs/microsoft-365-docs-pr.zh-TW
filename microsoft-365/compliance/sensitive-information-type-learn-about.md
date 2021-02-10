---
title: 了解敏感性資訊類型
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
ms.openlocfilehash: 91366e8f255d277d4d40de4c4cd3330283da718c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166448"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="f6bea-102">了解敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="f6bea-102">Learn about sensitive information types</span></span>

<span data-ttu-id="f6bea-103">識別和分類組織控制底下的敏感專案是 [資訊保護訓練科目](protect-information.md)中的第一步。</span><span class="sxs-lookup"><span data-stu-id="f6bea-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="f6bea-104">Microsoft 365 提供三種方式來識別專案，使其可進行分類：</span><span class="sxs-lookup"><span data-stu-id="f6bea-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="f6bea-105">由使用者手動</span><span class="sxs-lookup"><span data-stu-id="f6bea-105">manually by users</span></span>
- <span data-ttu-id="f6bea-106">自動化的模式識別，像是敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="f6bea-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="f6bea-107">機器學習</span><span class="sxs-lookup"><span data-stu-id="f6bea-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="f6bea-108">敏感資訊類型是以模式為基礎的分類器。</span><span class="sxs-lookup"><span data-stu-id="f6bea-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="f6bea-109">它們會偵測敏感資訊，例如社會保險、信用卡或銀行帳戶號碼，以識別敏感專案，請參閱 [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="f6bea-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="f6bea-110">敏感資訊類型是用於</span><span class="sxs-lookup"><span data-stu-id="f6bea-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="f6bea-111">資料外洩防護原則</span><span class="sxs-lookup"><span data-stu-id="f6bea-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="f6bea-112">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="f6bea-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="f6bea-113">保留標籤</span><span class="sxs-lookup"><span data-stu-id="f6bea-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="f6bea-114">通訊合規性</span><span class="sxs-lookup"><span data-stu-id="f6bea-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="f6bea-115">自動標籤型原則</span><span class="sxs-lookup"><span data-stu-id="f6bea-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="f6bea-116">敏感資訊類型的基礎部分</span><span class="sxs-lookup"><span data-stu-id="f6bea-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="f6bea-117">每個機密資訊類型實體都是由下欄欄位定義：</span><span class="sxs-lookup"><span data-stu-id="f6bea-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="f6bea-118">名稱：機密資訊類型的參考方式</span><span class="sxs-lookup"><span data-stu-id="f6bea-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="f6bea-119">描述：描述敏感資訊類型所要尋找的專案</span><span class="sxs-lookup"><span data-stu-id="f6bea-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="f6bea-120">模式：模式定義敏感資訊類型偵測的內容。</span><span class="sxs-lookup"><span data-stu-id="f6bea-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="f6bea-121">它包含下列元件</span><span class="sxs-lookup"><span data-stu-id="f6bea-121">It consists of the following components</span></span>
    - <span data-ttu-id="f6bea-122">主要元素–敏感資訊類型要尋找的主要元素。</span><span class="sxs-lookup"><span data-stu-id="f6bea-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="f6bea-123">它可以是使用或不含校驗和驗證、**關鍵字清單**、**關鍵字字典** 或 **函數** 的 **正則運算式**。</span><span class="sxs-lookup"><span data-stu-id="f6bea-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="f6bea-124">支援元素–做為支援證據的元素，可協助增加相符的置信度。</span><span class="sxs-lookup"><span data-stu-id="f6bea-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="f6bea-125">例如，關鍵字 "SSN" 是在 SSN 號碼的接近。</span><span class="sxs-lookup"><span data-stu-id="f6bea-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="f6bea-126">它可以是使用或不含校驗和驗證、關鍵字清單、關鍵字字典的正則運算式。</span><span class="sxs-lookup"><span data-stu-id="f6bea-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="f6bea-127">信賴等級-信賴層級 (高、中、低) 會反映出與主要元素一起偵測到的支援證據的數量。</span><span class="sxs-lookup"><span data-stu-id="f6bea-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="f6bea-128">專案所包含的支援證據越多，符合專案所要尋找之敏感資訊的信賴越高。</span><span class="sxs-lookup"><span data-stu-id="f6bea-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="f6bea-129">近程–主要和支援元素之間的字元數</span><span class="sxs-lookup"><span data-stu-id="f6bea-129">Proximity – Number of characters between primary and supporting element</span></span>

![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="f6bea-131">深入瞭解這段影片的信賴層級</span><span class="sxs-lookup"><span data-stu-id="f6bea-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="f6bea-132">範例機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="f6bea-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="f6bea-133">阿根廷國家身分識別 (DNI) 號碼</span><span class="sxs-lookup"><span data-stu-id="f6bea-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="f6bea-134">格式</span><span class="sxs-lookup"><span data-stu-id="f6bea-134">Format</span></span>

<span data-ttu-id="f6bea-135">以句點隔開的八位數</span><span class="sxs-lookup"><span data-stu-id="f6bea-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="f6bea-136">模式</span><span class="sxs-lookup"><span data-stu-id="f6bea-136">Pattern</span></span>

<span data-ttu-id="f6bea-137">八位數：</span><span class="sxs-lookup"><span data-stu-id="f6bea-137">Eight digits:</span></span>
- <span data-ttu-id="f6bea-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="f6bea-138">two digits</span></span>
- <span data-ttu-id="f6bea-139">一個句點</span><span class="sxs-lookup"><span data-stu-id="f6bea-139">a period</span></span>
- <span data-ttu-id="f6bea-140">三位數</span><span class="sxs-lookup"><span data-stu-id="f6bea-140">three digits</span></span>
- <span data-ttu-id="f6bea-141">一個句點</span><span class="sxs-lookup"><span data-stu-id="f6bea-141">a period</span></span>
- <span data-ttu-id="f6bea-142">三位數</span><span class="sxs-lookup"><span data-stu-id="f6bea-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="f6bea-143">校驗</span><span class="sxs-lookup"><span data-stu-id="f6bea-143">Checksum</span></span>

<span data-ttu-id="f6bea-144">否</span><span class="sxs-lookup"><span data-stu-id="f6bea-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="f6bea-145">定義</span><span class="sxs-lookup"><span data-stu-id="f6bea-145">Definition</span></span>

<span data-ttu-id="f6bea-146">當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。</span><span class="sxs-lookup"><span data-stu-id="f6bea-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="f6bea-147">正則運算式 Regex_argentina_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="f6bea-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="f6bea-148">會找到來自 Keyword_argentina_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="f6bea-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f6bea-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="f6bea-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="f6bea-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="f6bea-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="f6bea-151">阿根廷國內身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="f6bea-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="f6bea-152">身分識別</span><span class="sxs-lookup"><span data-stu-id="f6bea-152">Identity</span></span> 
- <span data-ttu-id="f6bea-153">身分識別的國內身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="f6bea-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="f6bea-154">DNI</span><span class="sxs-lookup"><span data-stu-id="f6bea-154">DNI</span></span> 
- <span data-ttu-id="f6bea-155">個人的 NIC 註冊人員</span><span class="sxs-lookup"><span data-stu-id="f6bea-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="f6bea-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="f6bea-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="f6bea-157">Registro Nacional de 拉斯維加斯角色</span><span class="sxs-lookup"><span data-stu-id="f6bea-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="f6bea-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="f6bea-158">Identidad</span></span> 
- <span data-ttu-id="f6bea-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="f6bea-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="f6bea-160">信賴層級的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f6bea-160">More on confidence levels</span></span>

<span data-ttu-id="f6bea-161">在機密資訊類型實體定義中， **信賴等級** 會反映出除了主要專案之外，偵測到多少支援證據。</span><span class="sxs-lookup"><span data-stu-id="f6bea-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="f6bea-162">專案所包含的支援證據越多，符合專案所要尋找之敏感資訊的信賴越高。</span><span class="sxs-lookup"><span data-stu-id="f6bea-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="f6bea-163">例如，具有高信賴度的比對會在主要元素的接近鄰近性中包含更多支援證據，而符合低信賴度的情況會包含很少無支援證據的近距離。</span><span class="sxs-lookup"><span data-stu-id="f6bea-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="f6bea-164">高信賴等級會傳回最少的誤報，但是可能會產生較多的漏報。</span><span class="sxs-lookup"><span data-stu-id="f6bea-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="f6bea-165">低或中度信賴等級會傳回更多的誤報，但很少為零的否定。</span><span class="sxs-lookup"><span data-stu-id="f6bea-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="f6bea-166">**低信賴度**：65的值，相符的專案會包含最少的 false 負值，但是最少的誤報。</span><span class="sxs-lookup"><span data-stu-id="f6bea-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="f6bea-167">**適中信賴**：值為75，相符的專案會包含平均的誤報和漏報的平均金額。</span><span class="sxs-lookup"><span data-stu-id="f6bea-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="f6bea-168">**高信賴度**：值為85，相符的專案會包含最少的誤報，但最少為 false 的負值。</span><span class="sxs-lookup"><span data-stu-id="f6bea-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="f6bea-169">您應該使用具有較低計數的高信賴度模式、5到10個，以及具有較高數量的低可信度模式，例如20或更高。</span><span class="sxs-lookup"><span data-stu-id="f6bea-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="f6bea-170">建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="f6bea-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="f6bea-171">若要在安全性與合規性中心建立自訂敏感性資訊類型，您可以從數個選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="f6bea-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="f6bea-172">**使用 UI** 您可以使用安全性與合規性中心 UI 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f6bea-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="f6bea-173">使用此方法，您可以使用規則運算式、關鍵字和關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="f6bea-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="f6bea-174">若要進一步了解，請參閱[建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bea-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="f6bea-175">**使用 EDM** 您可以使用以精確資料比對 (EDM) 為基礎的分類來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f6bea-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="f6bea-176">此方法可讓您使用您可以定期更新的安全資料庫來建立動態敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f6bea-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="f6bea-177">請參閱[使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bea-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="f6bea-178">**使用 PowerShell** 您可以使用 PowerShell 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f6bea-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="f6bea-179">雖然此方法比使用 UI 更複雜，但是您有多個組態選項。</span><span class="sxs-lookup"><span data-stu-id="f6bea-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="f6bea-180">請參閱[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bea-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="f6bea-181">在 Microsoft 365 服務的資料遺失防護內，可立即使用的信賴層級已增強，microsoft 365 服務、通訊相容性、資訊管理及記錄管理的 Microsoft 資訊保護功能均可供立即使用。</span><span class="sxs-lookup"><span data-stu-id="f6bea-181">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="f6bea-182">Microsoft 365 資訊保護目前在預覽版中支援下列雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="f6bea-182">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="f6bea-183">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="f6bea-183">Chinese (simplified)</span></span>
> - <span data-ttu-id="f6bea-184">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="f6bea-184">Chinese (traditional)</span></span>
> - <span data-ttu-id="f6bea-185">韓文</span><span class="sxs-lookup"><span data-stu-id="f6bea-185">Korean</span></span>
> - <span data-ttu-id="f6bea-186">日文</span><span class="sxs-lookup"><span data-stu-id="f6bea-186">Japanese</span></span>

><span data-ttu-id="f6bea-187">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f6bea-187">This support is available for sensitive information types.</span></span> <span data-ttu-id="f6bea-188">如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bea-188">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="f6bea-189">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f6bea-189">For further information</span></span>
- [<span data-ttu-id="f6bea-190">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="f6bea-190">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="f6bea-191">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="f6bea-191">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="f6bea-192">在 PowerShell 中建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="f6bea-192">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
