---
title: SharePoint 分類法的 SKOS 格式參照
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SharePoint 分類法的 SKOS 格式參照
ms.openlocfilehash: 4c08073f453ef0b6a224829b7d4cb4034b74ed14
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228732"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint 分類法的 SKOS 格式參照

本文包括用於表示 [SharePoint 分類法](/dotnet/api/microsoft.sharepoint.taxonomy)的 RDF 詞彙，它基於 [SKOS](https://www.w3.org/TR/skos-primer/)。 如需此 RDF 語法的序列化，請使用 RDF [TURTLE](https://www.w3.org/TR/turtle/)。

下表顯示了 [SharePoint 分類法](/dotnet/api/microsoft.sharepoint.taxonomy)詞彙的 [SKOS](https://www.w3.org/TR/skos-primer/) 對等用法。 SharePoint 不支援沒有 SharePoint 分類法對等用法的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。

|SharePoint 分類法|SKOS 對等用法|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

下表顯示了從 [OWL](https://www.w3.org/TR/owl2-primer/) 衍生的 SharePoint 分類法詞彙的實體。

|SharePoint 分類法詞彙|自 OWL 衍生|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint 分類法詞彙

分類法是一種正式分類系統。分類法將描述事物的單詞、標籤和字詞分組，然後將這些群組排列成階層圖。

**sharepoint-taxonomy:Term**

代表受管理的中繼資料階層圖中的字詞或關鍵字。

[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的原子單元。 每個[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)都屬於屬於 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) 的 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。

定義[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)的語法如下：

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)強制存在於 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中。 DefaultLabel 是[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)在視覺呈現方式中顯示的名稱。 定義[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)的必要欄位包括：

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)可以：

- 在階層上與另一[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)相關，前提是這兩個[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)屬於同一個 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。
- 有多個子系[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)，但只有單一父系[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)。
- 如果是 topLevelTermOf [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)，則不會定義父系[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)。
- 每個 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言都有一個 defaultLabel。
- 如果它既不包含父系[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不是 topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)，則不存在。
- 在相同的階層層級中，只有唯一的 defaultLabel。

**sharepoint-taxonomy:TermSet**

表示字詞物件的階層或平面集，稱為「TermSet」。

顧名思義，TermSet 是[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)的集合。 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 中的[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)必須屬於 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 沒有單獨存在的[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)。

定義[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)的語法如下：

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 會以邏輯方式組入 [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group)。 定義[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.termset)的必要欄位是：

- sharepoint-taxonomy:termSetName

如果提供的 termSetName 在 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) 中不是唯一的，SharePoint 會在名稱末尾附加一個數位，以保持 termSetName 的唯一性。

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint 使用此内容對應 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中最頂層的[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)，該字詞集是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)階層圖的進入點。 這是 SharePoint 分類法的反關係： topLevelTermOf。

定義此項語法如下：

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> 您無法定父系[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)的頂層[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)。

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy：topLevelTermOf 是反 sharepoint-taxonomy：hasTopLevelTerm

定義此項語法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

使用此項可將[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)對應到 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 單一[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)只能存在於單一 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。 [定義字詞](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)時，SharePoint 就需要使用這個屬性。

## <a name="required-labels"></a>必要標籤

在開始使用受托管的中繼資料之前，貴組織可能需要仔細規劃。 您必須執行的規劃量取決於分類法的正式程度。 它也取決於您想對中繼資料施加多少控制。 在階層的各個層級，您需要為字詞或 TermSet 設定所需的標籤。

一個字詞可以有一個或多個預設語言標籤，以及零個或多個非預設語言標籤。 如果字詞在語言中有標籤，則其中一個標籤必須是預設標籤。

**sharepoint-taxonomy:defaultLabel**

將此預設詞法標籤用於作為[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)必要參數的[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)。 用以視覺化表示[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)。

定義 defaultLabel 的語法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel 包含兩部分：字串和語言標籤。 該語言必須是 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言之一。 defaultLabel 對同一 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中同一階層級的所有[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term) 必須是唯一的。

**sharepoint-taxonomy:termSetName**

取得並設定目前 TermSet 物件的名稱。

這是 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言中 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的詞法標籤。 這是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必要參數。 用以視覺化表示[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。

定義 termSetName 的語法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

取得並設定目前 TermSet 物件的使用者定義樣式。

這是 sharepoint-taxonomy 的詞法標籤： SharedCustomPropertyForTerm、sharepoint-taxonomy： LocalCustomPropertyForTerm 和 sharepoint-taxonomy：[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言中的 CustomPropertyForTermSet。

sharepoint-taxonomy： propertyName 被視為 CustomProperty 的鑰匙。

定義 propetyName 的語法如下：

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>選用標籤

您也可以向分類法中添加選用標籤。

**sharepoint-taxonomy:otherLabel**

這是[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)的替代詞法標籤。

定義 otherLabel 的語法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>語意關聯性

分類法有階層和有時的一個簡單「相關字詞」關聯關係，但有些分類法有「語意關係」或自訂建立的關聯性。

**sharepoint-taxonomy:parent**

這種分層將一個[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)與另一個[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。 [字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)可以是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)的頂層[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)，否則一定有父系[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)。

定義父系的語法如下：

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

這表示 TermA 是父系，而 TermA 是子系。

**sharepoint-taxonomy:child**

物件包含一個或多個子系 TermSet 實例，且可透過 TermSets 屬性存取。 這個類別也提供建立新子系 TermSet 物件的方法。 在群組上指定了編輯子系字詞和 TermSet 實例的權限。

這種分層將一個[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)與另一個[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。

定義子系的語法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

這表示 TermA 是父系，而 TermA 是子系。

## <a name="documentation-notes"></a>文件附註

本節討論在 Microsoft.SharePoint.Taxonomy 命名空間中詳細描述的分類資訊。

**sharepoint-taxonomy:description**

這是對任何 [SharePoint 分類法](/dotnet/api/microsoft.sharepoint.taxonomy)詞彙實體的詳細說明。

新增描述的語法是：

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>自訂屬性

從只讀字典中取得目前字詞對象的自訂屬性物件的集合。

自訂屬性是可以為[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 定義的機碼值對，以進一步描述[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 SharePoint 在 propertyName 的協助下指定自訂屬性的鍵。

**sharepoint-taxonomy:CustomPropertyForTermSet**

定義此項語法如下：

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

如果[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)的自訂屬性需要與[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，那麼當您在其他地方重用該[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)時，則需要在 SharedCustomPropertyForTerm 下定義它。

定義此項語法如下：

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

如果[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)的自訂屬性不需要與[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，那麼當您在其他地方重用該[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)時，則需要在 LocalCustomPropertyForTerm 下定義它。

定義此項語法如下：

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>資料內容

在階層的各個層級，您需要為字詞或 TermSet 設定指定的資料内容。

**sharepoint-taxonomy:isAvailableForTagging**

使用此項可指定在 SharePoint 清單和庫中是否有可用的[字詞](/dotnet/api/microsoft.sharepoint.taxonomy.term)或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。

此項的語法是：

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>網域和範圍

下表說明 SharePoint 分類法詞彙的網域和範圍。

|Predicates/verb|意義|網域|範圍|
|:--------------|:------|:-----|:----|
inTermSet|字詞組中|字詞|字詞組|
inTermGroup|字詞群組中|TermSet|TermGroup|
topLevelTermOf|頂層字詞屬於|字詞|TermSet|
hasTopLevelTerm|具有頂層字詞|字詞組|字詞|
termSetName|字詞組有名稱|字詞|純文字|
defaultLabel|字詞有預設標籤|字詞|純文字|
otherLabel|字詞有其他標籤|字詞|純文字|
propertyName|具有屬性標籤|SharedCustomPropertyForTerm，LocalCustomPropertyForTerm，CustomPropertyForTermSet |布林值、字串、整數、小數點、雙精確度|
|描述|具有描述|全部|純文字|
|父系|具有父系|字詞|字詞|
|子系|具有子系|字詞|字詞|
|isAvailableForTagging|可用於標記|字詞、字詞組|布林值|
|SharedCustomPropertyForTerm|具有共用自訂屬性|字詞|布林值、字串、整數、小數點、雙精確度|
|LocalCustomPropertyForTerm|具有本地自訂屬性|字詞|布林值、字串、整數、小數點、雙精確度|
|CustomPropertyForTermSet|具有自訂屬性|TermSet|布林值、字串、整數、小數點、雙精確度|

[SKOS](https://www.w3.org/TR/skos-primer/) [SharePoint 分類法](/dotnet/api/microsoft.sharepoint.taxonomy)不允許的有效案例：

- 分層冗餘 - [SKOS](https://www.w3.org/TR/skos-primer/) 概念可以同時附加到多個更廣泛的概念，但 sharepoint-taxonomy：字詞只有一個 sharepoint-taxonomy：父系，因此也不允許字詞的循環相依。
- SharePoint 分類法中不允許孤立字詞。每個 sharepoint-taxonomy：字詞應該要麼有一個 sharepoint-taxonomy：父系或應該是 sharepoint-taxonomy：TermSet 的topLevelTermOf。
- SharePoint 分類法不支援關聯關係。
- SharePoint 分類法只允許 2 種類型的階層關係 – sharepoint-taxonomy：父系和 sharepoint-taxonomy：子系。
- 與 [SKOS](https://www.w3.org/TR/skos-primer/) 不同，SharePoint 分類法詞彙中的階層關係只能用同一 TermSet 中的字詞建立。

## <a name="see-also"></a>請參閱

[使用 SKOS 格式匯入字詞組](import-term-set-skos.md)