---
title: 自訂敏感資訊類型篩選器參考
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 本文提供可編碼為自訂敏感資訊類型的篩選清單。
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322569"
---
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="55b7d-103">自訂敏感資訊類型篩選器參考</span><span class="sxs-lookup"><span data-stu-id="55b7d-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="55b7d-104">在 Microsoft 中，您可以在建立自訂敏感資訊類型 (SIT) 時定義篩選或其他檢查。</span><span class="sxs-lookup"><span data-stu-id="55b7d-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="55b7d-105">支援的篩選和使用案例清單</span><span class="sxs-lookup"><span data-stu-id="55b7d-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="55b7d-106">AllDigitsSame 排除</span><span class="sxs-lookup"><span data-stu-id="55b7d-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="55b7d-107">描述：可讓您排除所有位數都是重複數位的相符專案，例如111111111或111-111-111</span><span class="sxs-lookup"><span data-stu-id="55b7d-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="55b7d-108">定義篩選</span><span class="sxs-lookup"><span data-stu-id="55b7d-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="55b7d-109">在實體層級的規則套件中使用</span><span class="sxs-lookup"><span data-stu-id="55b7d-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="55b7d-110">在模式層級的規則套件中使用它</span><span class="sxs-lookup"><span data-stu-id="55b7d-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="55b7d-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="55b7d-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="55b7d-112">描述：可讓您定義實體的開始字元。</span><span class="sxs-lookup"><span data-stu-id="55b7d-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="55b7d-113">有兩種變種，包含和排除。</span><span class="sxs-lookup"><span data-stu-id="55b7d-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="55b7d-114">例如，若要從清單中排除以0500、91、091、010開始的數位，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="55b7d-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="55b7d-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="55b7d-115">0500-4500-027</span></span>
- <span data-ttu-id="55b7d-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="55b7d-116">91564721450</span></span>
- <span data-ttu-id="55b7d-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="55b7d-117">91-8523697410</span></span>
- <span data-ttu-id="55b7d-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="55b7d-118">700-8956-7844</span></span>
- <span data-ttu-id="55b7d-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="55b7d-119">1000-3265-9874</span></span>
- <span data-ttu-id="55b7d-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="55b7d-120">0100-7892-3012</span></span>

<span data-ttu-id="55b7d-121">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-121">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
<span data-ttu-id="55b7d-122">例如，若要在清單中包含從0500、91、091、0100開始的數位，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="55b7d-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="55b7d-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="55b7d-123">0500-4500-027</span></span>
- <span data-ttu-id="55b7d-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="55b7d-124">91564721450</span></span>
- <span data-ttu-id="55b7d-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="55b7d-125">91-8523697410</span></span>
- <span data-ttu-id="55b7d-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="55b7d-126">700-8956-7844</span></span>
- <span data-ttu-id="55b7d-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="55b7d-127">1000-3265-9874</span></span>
- <span data-ttu-id="55b7d-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="55b7d-128">0100-7892-3012</span></span>

<span data-ttu-id="55b7d-129">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="55b7d-130">TextMatchFilter 以</span><span class="sxs-lookup"><span data-stu-id="55b7d-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="55b7d-131">描述：可讓您定義實體的終止字元。</span><span class="sxs-lookup"><span data-stu-id="55b7d-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="55b7d-132">例如，若要排除以0500、91091、0100結尾的數位，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55b7d-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="55b7d-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="55b7d-133">1234567891</span></span>
- <span data-ttu-id="55b7d-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="55b7d-134">1234-5678-0091</span></span>
- <span data-ttu-id="55b7d-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="55b7d-135">1234.4567.7091</span></span>
- <span data-ttu-id="55b7d-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="55b7d-136">1234-8091-4564</span></span>

<span data-ttu-id="55b7d-137">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-137">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="55b7d-138">例如，若要將結尾為0500、91、091、0100的數位包含在清單中，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="55b7d-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="55b7d-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="55b7d-139">1234567891</span></span>
- <span data-ttu-id="55b7d-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="55b7d-140">1234-5678-0091</span></span>
- <span data-ttu-id="55b7d-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="55b7d-141">1234.4567.7091</span></span>
- <span data-ttu-id="55b7d-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="55b7d-142">1234-8091-4564</span></span>

<span data-ttu-id="55b7d-143">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="55b7d-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="55b7d-144">TextMatchFilter Full</span></span>

<span data-ttu-id="55b7d-145">描述：可讓您禁止某些相符專案，以防止其觸發規則。</span><span class="sxs-lookup"><span data-stu-id="55b7d-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="55b7d-146">例如，從有效的信用卡符合專案清單中排除4111111111111111。</span><span class="sxs-lookup"><span data-stu-id="55b7d-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="55b7d-147">例如，若要將信用卡號碼（如4111111111111111和3241891031113111）排除在清單中，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="55b7d-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="55b7d-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="55b7d-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="55b7d-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="55b7d-149">4111111111111111</span></span>
- <span data-ttu-id="55b7d-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="55b7d-150">3241891031113111</span></span>

<span data-ttu-id="55b7d-151">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-151">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="55b7d-152">例如，若要在清單中包含信用卡號碼（如4111111111111111和3241891031113111），請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="55b7d-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="55b7d-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="55b7d-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="55b7d-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="55b7d-154">4111111111111111</span></span>
- <span data-ttu-id="55b7d-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="55b7d-155">3241891031113111</span></span>

<span data-ttu-id="55b7d-156">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="55b7d-157">TextMatchFilter 前置詞</span><span class="sxs-lookup"><span data-stu-id="55b7d-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="55b7d-158">描述：可讓您定義應該永遠包含或排除的前一個字元。</span><span class="sxs-lookup"><span data-stu-id="55b7d-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="55b7d-159">例如，如果信用卡號碼前面加上 "Order ID:"，則會移除有效的相符專案中的相符專案。</span><span class="sxs-lookup"><span data-stu-id="55b7d-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="55b7d-160">例如，若要排除有 **電話號碼** 的電話號碼，並在電話號碼之前以字串 **呼叫 me** ，請在清單中做如下：</span><span class="sxs-lookup"><span data-stu-id="55b7d-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="55b7d-161">電話號碼091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="55b7d-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="55b7d-162">電話45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="55b7d-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="55b7d-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="55b7d-163">45-124576532-123</span></span>

<span data-ttu-id="55b7d-164">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-164">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="55b7d-165">例如，若要在清單中包含 **信用卡** 號碼和 **卡片 #** 字串之前的事件，請在清單中做如下：</span><span class="sxs-lookup"><span data-stu-id="55b7d-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="55b7d-166">信用卡45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="55b7d-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="55b7d-167">45-124576532-123 (可能是電話號碼) </span><span class="sxs-lookup"><span data-stu-id="55b7d-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="55b7d-168">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-168">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="55b7d-169">TextMatchFilter 尾碼</span><span class="sxs-lookup"><span data-stu-id="55b7d-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="55b7d-170">描述：可讓您定義應永遠包含或排除的下列字元。</span><span class="sxs-lookup"><span data-stu-id="55b7d-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="55b7d-171">例如，如果信用卡號碼後接 '/xuid '，請從有效的相符專案中移除相符專案。</span><span class="sxs-lookup"><span data-stu-id="55b7d-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="55b7d-172">例如，如果在清單中有5個以上的實例做為尾碼（如下列所示），則會包含上一個例外項。</span><span class="sxs-lookup"><span data-stu-id="55b7d-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="55b7d-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="55b7d-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="55b7d-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="55b7d-174">1234-5678-9321</span></span>

<span data-ttu-id="55b7d-175">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="55b7d-176">例如，若要排除的事件，請在其後加上 **/xuidsuffix**（如清單中的其中一個）：</span><span class="sxs-lookup"><span data-stu-id="55b7d-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="55b7d-177">1234-5678-9321/xuid</span><span class="sxs-lookup"><span data-stu-id="55b7d-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="55b7d-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="55b7d-178">1234-5678-9321</span></span>

<span data-ttu-id="55b7d-179">您可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="55b7d-179">you can use this xml</span></span>

<span data-ttu-id="55b7d-180">' ' xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="55b7d-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="55b7d-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="55b7d-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="55b7d-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="55b7d-182">/xuid</span></span></Term>
    <span data-ttu-id="55b7d-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="55b7d-183"></Group> </Keyword></span></span>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="55b7d-184">在規則套件中使用篩選</span><span class="sxs-lookup"><span data-stu-id="55b7d-184">Using filters in rule packages</span></span>

<span data-ttu-id="55b7d-185">您可以在整個 SIT 或模式上定義篩選器。</span><span class="sxs-lookup"><span data-stu-id="55b7d-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="55b7d-186">以下是一些程式碼片段範例。</span><span class="sxs-lookup"><span data-stu-id="55b7d-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="55b7d-187">敏感資訊類型層級</span><span class="sxs-lookup"><span data-stu-id="55b7d-187">At sensitive information type level</span></span>

<span data-ttu-id="55b7d-188">實體中的篩選器將涵蓋所有子模式</span><span class="sxs-lookup"><span data-stu-id="55b7d-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="55b7d-189">篩選會套用至 **所有** 由該實體/敏感類型的模式分類的實例。</span><span class="sxs-lookup"><span data-stu-id="55b7d-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="55b7d-190">在機密資訊類型層級的個別模式</span><span class="sxs-lookup"><span data-stu-id="55b7d-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="55b7d-191">篩選只在模式層級。</span><span class="sxs-lookup"><span data-stu-id="55b7d-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="55b7d-192">篩選會套用到與模式相符的實例。</span><span class="sxs-lookup"><span data-stu-id="55b7d-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="55b7d-193">在敏感資訊類型層級，針對該實體的一些模式進行其他篩選</span><span class="sxs-lookup"><span data-stu-id="55b7d-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="55b7d-194">實體 + 模式篩選</span><span class="sxs-lookup"><span data-stu-id="55b7d-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="55b7d-195">篩選會套用至 **所有** 由該實體/敏感類型的模式所分類的實例。</span><span class="sxs-lookup"><span data-stu-id="55b7d-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="55b7d-196">模式層級篩選會篩選該模式所符合的實例。</span><span class="sxs-lookup"><span data-stu-id="55b7d-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="55b7d-197">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="55b7d-197">More information</span></span>

- [<span data-ttu-id="55b7d-198">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="55b7d-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="55b7d-199">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="55b7d-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="55b7d-200">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="55b7d-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
