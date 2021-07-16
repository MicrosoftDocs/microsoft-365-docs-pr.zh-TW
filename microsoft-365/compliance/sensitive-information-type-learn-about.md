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
description: 本文概述敏感資訊類型，以及如何偵測敏感資訊，例如社會保險、信用卡或銀行帳戶號碼，以識別敏感專案
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453618"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="013c9-103">了解敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="013c9-103">Learn about sensitive information types</span></span>

<span data-ttu-id="013c9-104">識別和分類組織控制底下的敏感專案是 [資訊保護訓練科目](./information-protection.md)中的第一步。</span><span class="sxs-lookup"><span data-stu-id="013c9-104">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="013c9-105">Microsoft 365 提供三種方式來識別專案，以進行分類：</span><span class="sxs-lookup"><span data-stu-id="013c9-105">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="013c9-106">由使用者手動</span><span class="sxs-lookup"><span data-stu-id="013c9-106">manually by users</span></span>
- <span data-ttu-id="013c9-107">自動化的模式識別，像是敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="013c9-107">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="013c9-108">機器學習</span><span class="sxs-lookup"><span data-stu-id="013c9-108">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="013c9-109">敏感資訊類型是以模式為基礎的分類器。</span><span class="sxs-lookup"><span data-stu-id="013c9-109">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="013c9-110">它們會偵測敏感資訊，例如社會保險、信用卡或銀行帳戶號碼，以識別敏感專案，請參閱 [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="013c9-110">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="013c9-111">敏感資訊類型是用於</span><span class="sxs-lookup"><span data-stu-id="013c9-111">Sensitive information types are used in</span></span>

- [<span data-ttu-id="013c9-112">資料遺失防護原則</span><span class="sxs-lookup"><span data-stu-id="013c9-112">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="013c9-113">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="013c9-113">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="013c9-114">保留標籤</span><span class="sxs-lookup"><span data-stu-id="013c9-114">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="013c9-115">內部風險管理</span><span class="sxs-lookup"><span data-stu-id="013c9-115">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="013c9-116">通訊合規性</span><span class="sxs-lookup"><span data-stu-id="013c9-116">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="013c9-117">自動標籤型原則</span><span class="sxs-lookup"><span data-stu-id="013c9-117">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [<span data-ttu-id="013c9-118">隱私權管理 (預覽) </span><span class="sxs-lookup"><span data-stu-id="013c9-118">Privacy management (preview)</span></span>](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="013c9-119">敏感資訊類型的基礎部分</span><span class="sxs-lookup"><span data-stu-id="013c9-119">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="013c9-120">每個機密資訊類型實體都是由下欄欄位定義：</span><span class="sxs-lookup"><span data-stu-id="013c9-120">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="013c9-121">名稱：機密資訊類型的參考方式</span><span class="sxs-lookup"><span data-stu-id="013c9-121">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="013c9-122">描述：描述敏感資訊類型所要尋找的專案</span><span class="sxs-lookup"><span data-stu-id="013c9-122">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="013c9-123">模式：模式定義敏感資訊類型偵測的內容。</span><span class="sxs-lookup"><span data-stu-id="013c9-123">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="013c9-124">它包含下列元件</span><span class="sxs-lookup"><span data-stu-id="013c9-124">It consists of the following components</span></span>
    - <span data-ttu-id="013c9-125">主要元素–敏感資訊類型要尋找的主要元素。</span><span class="sxs-lookup"><span data-stu-id="013c9-125">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="013c9-126">它可以是使用或不含校驗和驗證、**關鍵字清單**、**關鍵字字典** 或 **函數** 的 **正則運算式**。</span><span class="sxs-lookup"><span data-stu-id="013c9-126">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="013c9-127">支援元素–做為支援證據的元素，可協助增加相符的置信度。</span><span class="sxs-lookup"><span data-stu-id="013c9-127">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="013c9-128">例如，關鍵字 "SSN" 是在 SSN 號碼的接近。</span><span class="sxs-lookup"><span data-stu-id="013c9-128">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="013c9-129">它可以是使用或不含校驗和驗證、關鍵字清單、關鍵字字典的正則運算式。</span><span class="sxs-lookup"><span data-stu-id="013c9-129">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="013c9-130">信賴等級-信賴層級 (高、中、低) 會反映出與主要元素一起偵測到的支援證據的數量。</span><span class="sxs-lookup"><span data-stu-id="013c9-130">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="013c9-131">專案所包含的支援證據越多，符合專案所要尋找之敏感資訊的信賴越高。</span><span class="sxs-lookup"><span data-stu-id="013c9-131">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="013c9-132">近程–主要和支援元素之間的字元數</span><span class="sxs-lookup"><span data-stu-id="013c9-132">Proximity – Number of characters between primary and supporting element</span></span>

![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="013c9-134">深入瞭解這段影片的信賴層級</span><span class="sxs-lookup"><span data-stu-id="013c9-134">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="013c9-135">範例機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="013c9-135">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="013c9-136">阿根廷國家身分識別 (DNI) 號碼</span><span class="sxs-lookup"><span data-stu-id="013c9-136">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="013c9-137">格式</span><span class="sxs-lookup"><span data-stu-id="013c9-137">Format</span></span>

<span data-ttu-id="013c9-138">以句點隔開的八位數</span><span class="sxs-lookup"><span data-stu-id="013c9-138">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="013c9-139">模式</span><span class="sxs-lookup"><span data-stu-id="013c9-139">Pattern</span></span>

<span data-ttu-id="013c9-140">八位數：</span><span class="sxs-lookup"><span data-stu-id="013c9-140">Eight digits:</span></span>
- <span data-ttu-id="013c9-141">兩位數</span><span class="sxs-lookup"><span data-stu-id="013c9-141">two digits</span></span>
- <span data-ttu-id="013c9-142">一個句點</span><span class="sxs-lookup"><span data-stu-id="013c9-142">a period</span></span>
- <span data-ttu-id="013c9-143">三位數</span><span class="sxs-lookup"><span data-stu-id="013c9-143">three digits</span></span>
- <span data-ttu-id="013c9-144">一個句點</span><span class="sxs-lookup"><span data-stu-id="013c9-144">a period</span></span>
- <span data-ttu-id="013c9-145">三位數</span><span class="sxs-lookup"><span data-stu-id="013c9-145">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="013c9-146">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="013c9-146">Checksum</span></span>

<span data-ttu-id="013c9-147">否</span><span class="sxs-lookup"><span data-stu-id="013c9-147">No</span></span>

### <a name="definition"></a><span data-ttu-id="013c9-148">定義</span><span class="sxs-lookup"><span data-stu-id="013c9-148">Definition</span></span>

<span data-ttu-id="013c9-149">當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。</span><span class="sxs-lookup"><span data-stu-id="013c9-149">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="013c9-150">正則運算式 Regex_argentina_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="013c9-150">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="013c9-151">會找到來自 Keyword_argentina_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="013c9-151">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="013c9-152">關鍵字</span><span class="sxs-lookup"><span data-stu-id="013c9-152">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="013c9-153">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="013c9-153">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="013c9-154">阿根廷國內身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="013c9-154">Argentina National Identity number</span></span> 
- <span data-ttu-id="013c9-155">身分識別</span><span class="sxs-lookup"><span data-stu-id="013c9-155">Identity</span></span> 
- <span data-ttu-id="013c9-156">身分識別的國內身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="013c9-156">Identification National Identity Card</span></span> 
- <span data-ttu-id="013c9-157">DNI</span><span class="sxs-lookup"><span data-stu-id="013c9-157">DNI</span></span> 
- <span data-ttu-id="013c9-158">個人的 NIC 註冊人員</span><span class="sxs-lookup"><span data-stu-id="013c9-158">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="013c9-159">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="013c9-159">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="013c9-160">Registro Nacional de 拉斯維加斯角色</span><span class="sxs-lookup"><span data-stu-id="013c9-160">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="013c9-161">Identidad</span><span class="sxs-lookup"><span data-stu-id="013c9-161">Identidad</span></span> 
- <span data-ttu-id="013c9-162">Identificación</span><span class="sxs-lookup"><span data-stu-id="013c9-162">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="013c9-163">信賴層級的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="013c9-163">More on confidence levels</span></span>

<span data-ttu-id="013c9-164">在機密資訊類型實體定義中， **信賴等級** 會反映出除了主要專案之外，偵測到多少支援證據。</span><span class="sxs-lookup"><span data-stu-id="013c9-164">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="013c9-165">專案所包含的支援證據越多，符合專案所要尋找之敏感資訊的信賴越高。</span><span class="sxs-lookup"><span data-stu-id="013c9-165">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="013c9-166">例如，具有高信賴度的比對會在主要元素的接近鄰近性中包含更多支援證據，而符合低信賴度的情況會包含很少無支援證據的近距離。</span><span class="sxs-lookup"><span data-stu-id="013c9-166">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="013c9-167">高信賴等級會傳回最少的誤報，但是可能會產生較多的漏報。</span><span class="sxs-lookup"><span data-stu-id="013c9-167">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="013c9-168">低或中度信賴等級會傳回更多的誤報，但很少為零的否定。</span><span class="sxs-lookup"><span data-stu-id="013c9-168">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="013c9-169">**低信賴度**：65的值，相符的專案會包含最少的 false 負值，但是最少的誤報。</span><span class="sxs-lookup"><span data-stu-id="013c9-169">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="013c9-170">低信賴會傳回所有低、中和高信賴度的相符專案。</span><span class="sxs-lookup"><span data-stu-id="013c9-170">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="013c9-171">**適中信賴**：值為75，相符的專案會包含平均的誤報和漏報的平均金額。</span><span class="sxs-lookup"><span data-stu-id="013c9-171">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="013c9-172">中度信賴會傳回所有中和高信賴度的相符專案。</span><span class="sxs-lookup"><span data-stu-id="013c9-172">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="013c9-173">**高信賴度**：值為85，相符的專案會包含最少的誤報，但最少為 false 的負值。</span><span class="sxs-lookup"><span data-stu-id="013c9-173">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="013c9-174">高信賴度只會傳回高可信度比對。</span><span class="sxs-lookup"><span data-stu-id="013c9-174">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="013c9-175">您應該使用具有較低計數的高信賴度模式、5到10個，以及具有較高數量的低可信度模式，例如20或更高。</span><span class="sxs-lookup"><span data-stu-id="013c9-175">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="013c9-176">如果您有現有的原則或自訂敏感資訊類型 (是使用以數位為基礎的信賴等級) 定義 (也知道精確度) ，它們就會自動對應至三個不同的信賴等級;安全性 @ 合規性中心 UI 中的低信心、中置信度和高信賴度。</span><span class="sxs-lookup"><span data-stu-id="013c9-176">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="013c9-177">所有原則的精確度或自訂 SIT 模式，在76和100之間具有信賴層級，將會對應至高信賴度。</span><span class="sxs-lookup"><span data-stu-id="013c9-177">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="013c9-178">所有原則的精確度或自訂 SIT 模式，在66和75之間具有信賴層級，將會對應至中的置信度。</span><span class="sxs-lookup"><span data-stu-id="013c9-178">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="013c9-179">具有最低精確度或自訂 SIT 模式且信賴等級小於或等於65的所有原則都會對應至低信賴度。</span><span class="sxs-lookup"><span data-stu-id="013c9-179">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="013c9-180">建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="013c9-180">Creating custom sensitive information types</span></span>

<span data-ttu-id="013c9-181">若要在安全性與合規性中心建立自訂敏感性資訊類型，您可以從數個選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="013c9-181">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="013c9-182">**使用 UI** 您可以使用安全性與合規性中心 UI 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="013c9-182">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="013c9-183">使用此方法，您可以使用規則運算式、關鍵字和關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="013c9-183">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="013c9-184">若要進一步了解，請參閱[建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="013c9-184">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="013c9-185">**使用 EDM** 您可以使用以精確資料比對 (EDM) 為基礎的分類來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="013c9-185">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="013c9-186">此方法可讓您使用您可以定期更新的安全資料庫來建立動態敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="013c9-186">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="013c9-187">請參閱[使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="013c9-187">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="013c9-188">**使用 PowerShell** 您可以使用 PowerShell 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="013c9-188">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="013c9-189">雖然此方法比使用 UI 更複雜，但是您有多個組態選項。</span><span class="sxs-lookup"><span data-stu-id="013c9-189">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="013c9-190">請參閱[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="013c9-190">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="013c9-191">在 Microsoft 365 服務的資料遺失防護功能、Microsoft 資訊保護 Microsoft 365 服務、通訊法規遵從性、資訊管理及記錄管理等情況下，可以立即使用的增強信賴等級。</span><span class="sxs-lookup"><span data-stu-id="013c9-191">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="013c9-192">Microsoft 365資訊保護現在支援雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="013c9-192">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="013c9-193">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="013c9-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="013c9-194">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="013c9-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="013c9-195">韓文</span><span class="sxs-lookup"><span data-stu-id="013c9-195">Korean</span></span>
> - <span data-ttu-id="013c9-196">日文</span><span class="sxs-lookup"><span data-stu-id="013c9-196">Japanese</span></span>
> 
> <span data-ttu-id="013c9-197">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="013c9-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="013c9-198">如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="013c9-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="013c9-199">若要偵測包含中文/日文字元和單一位元組字元的模式，或偵測包含中文/日文和英文的模式，請定義關鍵字或 RegEx 的兩個變體。</span><span class="sxs-lookup"><span data-stu-id="013c9-199">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="013c9-200">例如，若要偵測關鍵字 ，例如「机密的document」，請使用關鍵字的兩個變體；一個在日文和英文文字之間具有空格，另一個在日文和英文文字之間沒有空格。</span><span class="sxs-lookup"><span data-stu-id="013c9-200">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="013c9-201">因此，要新增到 SIT 中的關鍵字應該是「机密的 document」和「机密的document」。</span><span class="sxs-lookup"><span data-stu-id="013c9-201">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="013c9-202">同樣地，若要偵測片語「東京オリンピック2020」，應該使用兩個變體；「東京オリンピック 2020」和「東京オリンピック2020」。</span><span class="sxs-lookup"><span data-stu-id="013c9-202">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="013c9-p118">使用雙位元組連字號或雙位元組句號來建立 RegEx 時，請務必逸出這兩個字元，就像一個字元會逸出 RegEx 中的連字號或句號一樣。以下是供參考的範例 RegEx:</span><span class="sxs-lookup"><span data-stu-id="013c9-p118">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="013c9-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="013c9-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="013c9-206">我們建議您在關鍵字清單中使用 string match，而不是字比對。</span><span class="sxs-lookup"><span data-stu-id="013c9-206">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="013c9-207">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="013c9-207">For further information</span></span>
- [<span data-ttu-id="013c9-208">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="013c9-208">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="013c9-209">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="013c9-209">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="013c9-210">在 PowerShell 中建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="013c9-210">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="013c9-211">若要瞭解如何使用敏感資訊類型來遵守資料隱私權規定，請參閱使用 Microsoft 365 (aka.ms/m365dataprivacy) [部署資料隱私權法規的資訊保護](../solutions/information-protection-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="013c9-211">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
