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
# <a name="custom-sensitive-information-type-filters-reference"></a>自訂敏感資訊類型篩選器參考

在 Microsoft 中，您可以在建立自訂敏感資訊類型 (SIT) 時定義篩選或其他檢查。

## <a name="list-of-supported-filters-and-use-cases"></a>支援的篩選和使用案例清單

### <a name="alldigitssame-exclude"></a>AllDigitsSame 排除

描述：可讓您排除所有位數都是重複數位的相符專案，例如111111111或111-111-111

定義篩選
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

在實體層級的規則套件中使用
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

在模式層級的規則套件中使用它
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

描述：可讓您定義實體的開始字元。 有兩種變種，包含和排除。

例如，若要從清單中排除以0500、91、091、010開始的數位，請執行下列操作：

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

您可以使用此 xml

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
例如，若要在清單中包含從0500、91、091、0100開始的數位，請執行下列作業： 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

您可以使用此 xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter 以 

描述：可讓您定義實體的終止字元。 

例如，若要排除以0500、91091、0100結尾的數位，如下所示：

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

您可以使用此 xml

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

例如，若要將結尾為0500、91、091、0100的數位包含在清單中，請執行下列操作：

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

您可以使用此 xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

描述：可讓您禁止某些相符專案，以防止其觸發規則。 例如，從有效的信用卡符合專案清單中排除4111111111111111。

例如，若要將信用卡號碼（如4111111111111111和3241891031113111）排除在清單中，請執行下列操作：

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

您可以使用此 xml

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

例如，若要在清單中包含信用卡號碼（如4111111111111111和3241891031113111），請執行下列操作：

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

您可以使用此 xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>TextMatchFilter 前置詞

描述：可讓您定義應該永遠包含或排除的前一個字元。 例如，如果信用卡號碼前面加上 "Order ID:"，則會移除有效的相符專案中的相符專案。

例如，若要排除有 **電話號碼** 的電話號碼，並在電話號碼之前以字串 **呼叫 me** ，請在清單中做如下：

- 電話號碼091-8974-653278
- 電話45-124576532-123
- 45-124576532-123

您可以使用此 xml

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

例如，若要在清單中包含 **信用卡** 號碼和 **卡片 #** 字串之前的事件，請在清單中做如下：

- 信用卡45-124576532-123 
- 45-124576532-123 (可能是電話號碼) 

您可以使用此 xml

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

### <a name="textmatchfilter-suffix"></a>TextMatchFilter 尾碼

描述：可讓您定義應永遠包含或排除的下列字元。 例如，如果信用卡號碼後接 '/xuid '，請從有效的相符專案中移除相符專案。

例如，如果在清單中有5個以上的實例做為尾碼（如下列所示），則會包含上一個例外項。

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

您可以使用此 xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
例如，若要排除的事件，請在其後加上 **/xuidsuffix**（如清單中的其中一個）：

- 1234-5678-9321/xuid
- 1234-5678-9321

您可以使用此 xml

' ' xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
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

## <a name="using-filters-in-rule-packages"></a>在規則套件中使用篩選

您可以在整個 SIT 或模式上定義篩選器。 以下是一些程式碼片段範例。 

### <a name="at-sensitive-information-type-level"></a>敏感資訊類型層級

實體中的篩選器將涵蓋所有子模式

篩選會套用至 **所有** 由該實體/敏感類型的模式分類的實例。

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>在機密資訊類型層級的個別模式

篩選只在模式層級。

篩選會套用到與模式相符的實例。

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>在敏感資訊類型層級，針對該實體的一些模式進行其他篩選

實體 + 模式篩選

篩選會套用至 **所有** 由該實體/敏感類型的模式所分類的實例。 模式層級篩選會篩選該模式所符合的實例。

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>詳細資訊

- [深入了解資料外洩防護](dlp-learn-about-dlp.md)

- [敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)

- [DLP 功能所尋找的項目](what-the-dlp-functions-look-for.md)
