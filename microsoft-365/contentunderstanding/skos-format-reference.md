---
title: SharePoint 分類法的 SKOS 格式參考
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SharePoint 分類法的 SKOS 格式參考
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295797"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint 分類法的 SKOS 格式參考

本文包含 RDF 詞彙，用來代表 [SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) ，並以 [SKOS](https://www.w3.org/TR/skos-primer/)為基礎。 如需此 RDF 語法的序列化，請使用 RDF [龜標](https://www.w3.org/TR/turtle/)。

下表顯示[SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)詞彙的[SKOS](https://www.w3.org/TR/skos-primer/)對等專案。 SharePoint 不支援沒有 SharePoint 分類法對等值的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。

|SharePoint 分類法|SKOS 對等|
|:-----------------|:--------------|
|sharepoint-分類法：字詞|skos：概念|
|sharepoint-分類法： TermSet|skos:ConceptScheme|
|sharepoint-分類法： inTermSet|skos:inScheme|
|sharepoint-分類法： hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-分類法： topLevelTermOf|skos:topConceptOf|
|sharepoint-分類法： defaultLabel|skos:prefLabel|
|sharepoint-分類法： termSetName|skos:prefLabel|
|sharepoint-分類法： propertyName|skos:prefLabel|
|sharepoint-分類法： otherLabel|skos:altLabel|
|sharepoint-分類法：說明|skos：定義|
|sharepoint-分類法： parent|skos：更廣泛|
|sharepoint-分類法：子項|skos：變窄|

下表顯示派生自 [OWL](https://www.w3.org/TR/owl2-primer/)的 SharePoint 分類詞彙實體。

|SharePoint 分類詞彙|派生自 OWL|
|:-----------------------------|:----------------------|
|sharepoint-分類法： isAvailableForTagging|owl:datatypeproperty|
|sharepoint-分類法： SharedCustomPropertyForTerm|owl： Property|
|sharepoint-分類法： LocalCustomPropertyForTerm|owl： Property|
|sharepoint-分類法： CustomPropertyForTermSet|owl： Property|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint 分類詞彙

分類法是正式的分類系統。 分類法會群組描述某項專案的字、標籤和字詞，然後將群組排列到階層中。

**sharepoint-分類法：字詞**

代表受管理的中繼資料階層中的字詞或關鍵字。

[關鍵字](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)的基本單位。 每個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)屬於屬於[TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)的[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 。 

定義 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的語法如下：

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)compulsorily 存在於[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。 DefaultLabel 是出現在視覺標記法中的 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 名稱。 定義 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 所需的欄位包括：

- sharepoint-分類法： defaultLabel
- sharepoint-分類法： inTermSet

[詞彙](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以：

- 與另一個 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 相關聯，而這兩個 [詞彙](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 都屬於相同的 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。
- 具有多個子 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但只能有單一父項 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。
- 未定義上層 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ，如果是 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。
- 具有一個 defaultLabel，每個 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作語言。
- 不存在如果它不包含父 [項字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不會 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 
- 在相同的階層層級中只具有唯一的 defaultLabel。

**sharepoint-分類法： TermSet**

代表一組階層或平面的 Term 物件，稱為 "TermSet"。

顧名思義，TermSet 是一組 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)中的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)必須屬於[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 不可以個別存在 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 。 

定義 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的語法為：

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中的[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)邏輯群組在一起。 定義 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必要欄位是：

- sharepoint-分類法： termSetName

在 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中提供的 termSetName 不是唯一的情況下，sharepoint 會在名稱的結尾附加一個數位，以維護 termSetName (s) 的唯一性。

**sharepoint-分類法： hasTopLevelTerm**

SharePoint 會使用此屬性來對應[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的最上層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，也就是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)階層的進入點。 這是 sharepoint 分類法的逆轉關係： topLevelTermOf。 

定義此專案的語法為：

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> 您無法定義上層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的上一級[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。

**sharepoint-分類法： topLevelTermOf**

Sharepoint 分類法： topLevelTermOf 是 sharepoint 分類法的逆向分類法： hasTopLevelTerm

定義此專案的語法為：

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-分類法： inTermSet**

使用此來將 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 對應至 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)只能存在於單一[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。 當 [定義字詞](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)時，SharePoint 需要此屬性。

## <a name="required-labels"></a>必要標籤

您的組織可能會想要在開始使用受管理的中繼資料之前進行周密的規劃。 您必須執行的規劃量取決於您的分類的正式形式。 它也取決於您想要對中繼資料施加多少控制項。 在階層的每一個層級，您必須設定字詞或 TermSet 所需的 lables。

字詞可以有一個或多個預設語言的標籤，以及非預設語言的零個或多個標籤。 如果字詞的標籤為語言，其中一個標籤必須是預設標籤。

**sharepoint-分類法： defaultLabel**

針對[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)[的必要參數，使用](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)此預設的詞法標籤。 用於以視覺方式代表 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。

定義 defaultLabel 的語法為：

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel 包含兩個元件–字串及語言標記。 語言必須是 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的其中一個運作語言。 在相同的階層層級，defaultLabel 在相同[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的所有[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)都必須是唯一的。

**sharepoint-分類法： termSetName**

取得及設定目前的 TermSet 物件的名稱。

這是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的詞法標籤，採用 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作語言。 這是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的必要參數。 用於以視覺方式代表 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。

定義 termSetName 的語法為：

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-分類法： propertyName**

取得及設定目前 TermSet 物件的屬性名稱。

這是 sharepoint 分類法的詞法標籤： SharedCustomPropertyForTerm、sharepoint 分類法： LocalCustomPropertyForTerm 和 sharepoint 分類法： CustomPropertyForTermSet in [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言。

Sharepoint 分類法： propertyName 會被視為 CustomProperty 的索引鍵。

定義 propetyName 的語法為：

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>選用標籤

您也可以將選用的標籤新增至您的分類。

**sharepoint-分類法： otherLabel**

這是 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的替代詞法標籤。 

定義 otherLabel 的語法為：

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>語義關聯

分類的階層很低，有時是一種簡單的「相關的字詞」關聯關聯性，但是有些具有「語義關聯」或自訂建立的關係。 

**sharepoint-分類法： parent**

這會以分層方式將 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 與另一個 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的最上層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但如果不是必須有父[項字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。 

定義父系的語法如下：

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

這表示 TermA1 具有父系 TermA。 同時也表示 TermA1 是 TermA 的子項。 父子關係是 inversible 關聯。

**sharepoint-分類法：子項**

物件包含一或多個子 TermSet 實例，而且可以透過 TermSets 屬性來存取。 此類別也提供用來建立新的子 TermSet 物件的方法。 在群組上指定編輯子字詞和 TermSet 實例的許可權。 

這會以分層方式將 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 與另一個 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。

定義子系的語法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

這表示 TermA 具有子 TermA1。 另外，也表示 TermA 是 TermA1 父子關係的父項是 inversible 關聯。

## <a name="documentation-notes"></a>檔附注

本節討論 Microsoft.SharePoint 分類命名空間中詳細的分類。

**sharepoint-分類法：說明**

這是任何 [SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 詞彙實體的詳細說明。 

新增描述的語法為：

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>自訂屬性

從唯讀字典中取得目前字詞物件的自訂屬性物件集合。

自訂屬性是可為 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)定義的索引鍵值對，以進一步說明 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的描述。 SharePoint 會指定具有 propertyName 之 help 的自訂屬性的索引鍵。

**sharepoint-分類法： CustomPropertyForTermSet**

定義此專案的語法為：

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-分類法： SharedCustomPropertyForTerm**

若 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自訂屬性需要與 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，當您重複使用該 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 時，您必須在 SharedCustomPropertyForTerm 下加以定義。

定義此專案的語法為：

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-分類法： LocalCustomPropertyForTerm**

如果 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自訂屬性不需要與 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，則當您重複使用 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 時，您必須在 LocalCustomPropertyForTerm 中定義它。

定義此專案的語法為：

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>資料屬性

您可以在階層的每個層級，設定字詞或 TermSet 的特定資料屬性。

**sharepoint-分類法： isAvailableForTagging**

使用此功能可指定 SharePoint 清單和文件庫中可用的 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 。  

其語法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>網域和範圍

下表說明 SharePoint 分類詞彙的網域和範圍。

|謂詞/動詞|意義|網域|範圍|
|:--------------|:------|:-----|:----|
inTermSet|在詞彙集中|術語|字詞集|
inTermGroup|在「字詞群組」|TermSet|TermGroup|
topLevelTermOf|是最高層級的字詞|術語|TermSet|
hasTopLevelTerm|具有最高層級字詞|字詞集|術語|
termSetName|字片語具有名稱|術語|純文字|
defaultLabel|字詞具有預設標籤|術語|純文字|
otherLabel|字詞有其他標籤|術語|純文字|
propertyName|具有屬性標籤|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean、String、Integer、Decimal、Double|
|描述|具有 Description|全部|純文字|
|母|具有 parent|術語|術語|
|孩子|具有子項|術語|術語|
|isAvailableForTagging|可用於標記|字詞、字詞集|布林值|
|SharedCustomPropertyForTerm|已共用自訂屬性|術語|Boolean、string、Integer、Decimal、Double|
|LocalCustomPropertyForTerm|具有本機自訂屬性|術語|Boolean、String、Integer、Decimal、Double|
|CustomPropertyForTermSet|具有 Custom 屬性|TermSet|Boolean、String、Integer、Decimal、Double|

[SKOS](https://www.w3.org/TR/skos-primer/) [分類法 SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 的有效案例不允許：

- 階層式冗余- [SKOS](https://www.w3.org/TR/skos-primer/) 概念可以同時附加到數個更廣泛的概念，但 sharepoint 分類法：字詞只可以有一個 sharepoint 分類法： parent，因此，也不允許對字詞的迴圈相關性。
- SharePoint 分類法中不允許使用孤立字詞。 每個 sharepoint 分類法：字詞應具備 sharepoint 分類法： parent 或應為 sharepoint 分類法： topLevelTermOf a TermSet。
- SharePoint 分類不支援關聯關係。
- SharePoint 分類只允許兩種階層式關聯類型-sharepoint 分類法： parent and sharepoint-分類法： child。 
- 不同于 [SKOS](https://www.w3.org/TR/skos-primer/) SharePoint 分類詞彙中的階層關聯，只能使用相同 TermSet 內的字詞建立。

## <a name="see-also"></a>請參閱

[使用以 SKOS 為基礎的格式匯入字詞集](import-term-set-skos.md)

