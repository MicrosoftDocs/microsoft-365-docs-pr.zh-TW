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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="6d2b4-103">SharePoint 分類法的 SKOS 格式參考</span><span class="sxs-lookup"><span data-stu-id="6d2b4-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="6d2b4-104">本文包含 RDF 詞彙，用來代表 [SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) ，並以 [SKOS](https://www.w3.org/TR/skos-primer/)為基礎。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="6d2b4-105">如需此 RDF 語法的序列化，請使用 RDF [龜標](https://www.w3.org/TR/turtle/)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="6d2b4-106">下表顯示[SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)詞彙的[SKOS](https://www.w3.org/TR/skos-primer/)對等專案。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="6d2b4-107">SharePoint 不支援沒有 SharePoint 分類法對等值的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="6d2b4-108">SharePoint 分類法</span><span class="sxs-lookup"><span data-stu-id="6d2b4-108">SharePoint taxonomy</span></span>|<span data-ttu-id="6d2b4-109">SKOS 對等</span><span class="sxs-lookup"><span data-stu-id="6d2b4-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="6d2b4-110">sharepoint-分類法：字詞</span><span class="sxs-lookup"><span data-stu-id="6d2b4-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="6d2b4-111">skos：概念</span><span class="sxs-lookup"><span data-stu-id="6d2b4-111">skos:Concept</span></span>|
|<span data-ttu-id="6d2b4-112">sharepoint-分類法： TermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="6d2b4-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="6d2b4-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="6d2b4-114">sharepoint-分類法： inTermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="6d2b4-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="6d2b4-115">skos:inScheme</span></span>|
|<span data-ttu-id="6d2b4-116">sharepoint-分類法： hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="6d2b4-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="6d2b4-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="6d2b4-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="6d2b4-118">sharepoint-分類法： topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="6d2b4-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="6d2b4-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="6d2b4-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="6d2b4-120">sharepoint-分類法： defaultLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="6d2b4-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-121">skos:prefLabel</span></span>|
|<span data-ttu-id="6d2b4-122">sharepoint-分類法： termSetName</span><span class="sxs-lookup"><span data-stu-id="6d2b4-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="6d2b4-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-123">skos:prefLabel</span></span>|
|<span data-ttu-id="6d2b4-124">sharepoint-分類法： propertyName</span><span class="sxs-lookup"><span data-stu-id="6d2b4-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="6d2b4-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-125">skos:prefLabel</span></span>|
|<span data-ttu-id="6d2b4-126">sharepoint-分類法： otherLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="6d2b4-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-127">skos:altLabel</span></span>|
|<span data-ttu-id="6d2b4-128">sharepoint-分類法：說明</span><span class="sxs-lookup"><span data-stu-id="6d2b4-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="6d2b4-129">skos：定義</span><span class="sxs-lookup"><span data-stu-id="6d2b4-129">skos:definition</span></span>|
|<span data-ttu-id="6d2b4-130">sharepoint-分類法： parent</span><span class="sxs-lookup"><span data-stu-id="6d2b4-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="6d2b4-131">skos：更廣泛</span><span class="sxs-lookup"><span data-stu-id="6d2b4-131">skos:broader</span></span>|
|<span data-ttu-id="6d2b4-132">sharepoint-分類法：子項</span><span class="sxs-lookup"><span data-stu-id="6d2b4-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="6d2b4-133">skos：變窄</span><span class="sxs-lookup"><span data-stu-id="6d2b4-133">skos:narrower</span></span>|

<span data-ttu-id="6d2b4-134">下表顯示派生自 [OWL](https://www.w3.org/TR/owl2-primer/)的 SharePoint 分類詞彙實體。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="6d2b4-135">SharePoint 分類詞彙</span><span class="sxs-lookup"><span data-stu-id="6d2b4-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="6d2b4-136">派生自 OWL</span><span class="sxs-lookup"><span data-stu-id="6d2b4-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="6d2b4-137">sharepoint-分類法： isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="6d2b4-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="6d2b4-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="6d2b4-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="6d2b4-139">sharepoint-分類法： SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6d2b4-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="6d2b4-140">owl： Property</span><span class="sxs-lookup"><span data-stu-id="6d2b4-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="6d2b4-141">sharepoint-分類法： LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6d2b4-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="6d2b4-142">owl： Property</span><span class="sxs-lookup"><span data-stu-id="6d2b4-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="6d2b4-143">sharepoint-分類法： CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="6d2b4-144">owl： Property</span><span class="sxs-lookup"><span data-stu-id="6d2b4-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="6d2b4-145">SharePoint 分類詞彙</span><span class="sxs-lookup"><span data-stu-id="6d2b4-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="6d2b4-146">分類法是正式的分類系統。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="6d2b4-147">分類法會群組描述某項專案的字、標籤和字詞，然後將群組排列到階層中。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="6d2b4-148">**sharepoint-分類法：字詞**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="6d2b4-149">代表受管理的中繼資料階層中的字詞或關鍵字。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="6d2b4-150">[關鍵字](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)的基本單位。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="6d2b4-151">每個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)屬於屬於[TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)的[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="6d2b4-152">定義 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的語法如下：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="6d2b4-153">[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)compulsorily 存在於[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6d2b4-154">DefaultLabel 是出現在視覺標記法中的 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 名稱。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="6d2b4-155">定義 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 所需的欄位包括：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="6d2b4-156">sharepoint-分類法： defaultLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="6d2b4-157">sharepoint-分類法： inTermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="6d2b4-158">[詞彙](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="6d2b4-159">與另一個 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 相關聯，而這兩個 [詞彙](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 都屬於相同的 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="6d2b4-160">具有多個子 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但只能有單一父項 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="6d2b4-161">未定義上層 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ，如果是 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="6d2b4-162">具有一個 defaultLabel，每個 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作語言。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="6d2b4-163">不存在如果它不包含父 [項字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不會 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="6d2b4-164">在相同的階層層級中只具有唯一的 defaultLabel。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="6d2b4-165">**sharepoint-分類法： TermSet**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="6d2b4-166">代表一組階層或平面的 Term 物件，稱為 "TermSet"。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="6d2b4-167">顧名思義，TermSet 是一組 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="6d2b4-168">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)中的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)必須屬於[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6d2b4-169">不可以個別存在 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="6d2b4-170">定義 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="6d2b4-171">[TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中的[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)邏輯群組在一起。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="6d2b4-172">定義 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必要欄位是：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="6d2b4-173">sharepoint-分類法： termSetName</span><span class="sxs-lookup"><span data-stu-id="6d2b4-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="6d2b4-174">在 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中提供的 termSetName 不是唯一的情況下，sharepoint 會在名稱的結尾附加一個數位，以維護 termSetName (s) 的唯一性。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="6d2b4-175">**sharepoint-分類法： hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="6d2b4-176">SharePoint 會使用此屬性來對應[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的最上層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，也就是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)階層的進入點。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6d2b4-177">這是 sharepoint 分類法的逆轉關係： topLevelTermOf。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="6d2b4-178">定義此專案的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="6d2b4-179">您無法定義上層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的上一級[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="6d2b4-180">**sharepoint-分類法： topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="6d2b4-181">Sharepoint 分類法： topLevelTermOf 是 sharepoint 分類法的逆向分類法： hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="6d2b4-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="6d2b4-182">定義此專案的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="6d2b4-183">**sharepoint-分類法： inTermSet**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="6d2b4-184">使用此來將 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 對應至 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6d2b4-185">[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)只能存在於單一[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6d2b4-186">當 [定義字詞](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)時，SharePoint 需要此屬性。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="6d2b4-187">必要標籤</span><span class="sxs-lookup"><span data-stu-id="6d2b4-187">Required labels</span></span>

<span data-ttu-id="6d2b4-188">您的組織可能會想要在開始使用受管理的中繼資料之前進行周密的規劃。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="6d2b4-189">您必須執行的規劃量取決於您的分類的正式形式。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="6d2b4-190">它也取決於您想要對中繼資料施加多少控制項。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="6d2b4-191">在階層的每一個層級，您必須設定字詞或 TermSet 所需的 lables。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="6d2b4-192">字詞可以有一個或多個預設語言的標籤，以及非預設語言的零個或多個標籤。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="6d2b4-193">如果字詞的標籤為語言，其中一個標籤必須是預設標籤。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="6d2b4-194">**sharepoint-分類法： defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="6d2b4-195">針對[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)[的必要參數，使用](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)此預設的詞法標籤。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="6d2b4-196">用於以視覺方式代表 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="6d2b4-197">定義 defaultLabel 的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="6d2b4-198">DefaultLabel 包含兩個元件–字串及語言標記。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="6d2b4-199">語言必須是 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的其中一個運作語言。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="6d2b4-200">在相同的階層層級，defaultLabel 在相同[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的所有[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="6d2b4-201">**sharepoint-分類法： termSetName**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="6d2b4-202">取得及設定目前的 TermSet 物件的名稱。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="6d2b4-203">這是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的詞法標籤，採用 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作語言。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="6d2b4-204">這是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的必要參數。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6d2b4-205">用於以視覺方式代表 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="6d2b4-206">定義 termSetName 的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="6d2b4-207">**sharepoint-分類法： propertyName**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="6d2b4-208">取得及設定目前 TermSet 物件的屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="6d2b4-209">這是 sharepoint 分類法的詞法標籤： SharedCustomPropertyForTerm、sharepoint 分類法： LocalCustomPropertyForTerm 和 sharepoint 分類法： CustomPropertyForTermSet in [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="6d2b4-210">Sharepoint 分類法： propertyName 會被視為 CustomProperty 的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="6d2b4-211">定義 propetyName 的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="6d2b4-212">選用標籤</span><span class="sxs-lookup"><span data-stu-id="6d2b4-212">Optional labels</span></span>

<span data-ttu-id="6d2b4-213">您也可以將選用的標籤新增至您的分類。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="6d2b4-214">**sharepoint-分類法： otherLabel**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="6d2b4-215">這是 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的替代詞法標籤。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="6d2b4-216">定義 otherLabel 的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="6d2b4-217">語義關聯</span><span class="sxs-lookup"><span data-stu-id="6d2b4-217">Semantic relationships</span></span>

<span data-ttu-id="6d2b4-218">分類的階層很低，有時是一種簡單的「相關的字詞」關聯關聯性，但是有些具有「語義關聯」或自訂建立的關係。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="6d2b4-219">**sharepoint-分類法： parent**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="6d2b4-220">這會以分層方式將 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 與另一個 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="6d2b4-221">[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的最上層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但如果不是必須有父[項字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="6d2b4-222">定義父系的語法如下：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="6d2b4-223">這表示 TermA1 具有父系 TermA。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="6d2b4-224">同時也表示 TermA1 是 TermA 的子項。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="6d2b4-225">父子關係是 inversible 關聯。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="6d2b4-226">**sharepoint-分類法：子項**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="6d2b4-227">物件包含一或多個子 TermSet 實例，而且可以透過 TermSets 屬性來存取。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="6d2b4-228">此類別也提供用來建立新的子 TermSet 物件的方法。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="6d2b4-229">在群組上指定編輯子字詞和 TermSet 實例的許可權。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="6d2b4-230">這會以分層方式將 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 與另一個 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="6d2b4-231">定義子系的語法如下：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="6d2b4-232">這表示 TermA 具有子 TermA1。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="6d2b4-233">另外，也表示 TermA 是 TermA1 父子關係的父項是 inversible 關聯。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="6d2b4-234">檔附注</span><span class="sxs-lookup"><span data-stu-id="6d2b4-234">Documentation notes</span></span>

<span data-ttu-id="6d2b4-235">本節討論 Microsoft.SharePoint 分類命名空間中詳細的分類。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="6d2b4-236">**sharepoint-分類法：說明**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="6d2b4-237">這是任何 [SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 詞彙實體的詳細說明。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="6d2b4-238">新增描述的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="6d2b4-239">自訂屬性</span><span class="sxs-lookup"><span data-stu-id="6d2b4-239">Custom properties</span></span>

<span data-ttu-id="6d2b4-240">從唯讀字典中取得目前字詞物件的自訂屬性物件集合。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="6d2b4-241">自訂屬性是可為 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)定義的索引鍵值對，以進一步說明 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的描述。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="6d2b4-242">SharePoint 會指定具有 propertyName 之 help 的自訂屬性的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="6d2b4-243">**sharepoint-分類法： CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="6d2b4-244">定義此專案的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="6d2b4-245">**sharepoint-分類法： SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="6d2b4-246">若 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自訂屬性需要與 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，當您重複使用該 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 時，您必須在 SharedCustomPropertyForTerm 下加以定義。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="6d2b4-247">定義此專案的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="6d2b4-248">**sharepoint-分類法： LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="6d2b4-249">如果 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自訂屬性不需要與 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，則當您重複使用 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 時，您必須在 LocalCustomPropertyForTerm 中定義它。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="6d2b4-250">定義此專案的語法為：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="6d2b4-251">資料屬性</span><span class="sxs-lookup"><span data-stu-id="6d2b4-251">Data properties</span></span>

<span data-ttu-id="6d2b4-252">您可以在階層的每個層級，設定字詞或 TermSet 的特定資料屬性。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="6d2b4-253">**sharepoint-分類法： isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="6d2b4-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="6d2b4-254">使用此功能可指定 SharePoint 清單和文件庫中可用的 [字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="6d2b4-255">其語法如下：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="6d2b4-256">網域和範圍</span><span class="sxs-lookup"><span data-stu-id="6d2b4-256">Domain and range</span></span>

<span data-ttu-id="6d2b4-257">下表說明 SharePoint 分類詞彙的網域和範圍。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="6d2b4-258">謂詞/動詞</span><span class="sxs-lookup"><span data-stu-id="6d2b4-258">Predicates/verb</span></span>|<span data-ttu-id="6d2b4-259">意義</span><span class="sxs-lookup"><span data-stu-id="6d2b4-259">Meaning</span></span>|<span data-ttu-id="6d2b4-260">網域</span><span class="sxs-lookup"><span data-stu-id="6d2b4-260">Domain</span></span>|<span data-ttu-id="6d2b4-261">範圍</span><span class="sxs-lookup"><span data-stu-id="6d2b4-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="6d2b4-262">inTermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-262">inTermSet</span></span>|<span data-ttu-id="6d2b4-263">在詞彙集中</span><span class="sxs-lookup"><span data-stu-id="6d2b4-263">In term set</span></span>|<span data-ttu-id="6d2b4-264">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-264">Term</span></span>|<span data-ttu-id="6d2b4-265">字詞集</span><span class="sxs-lookup"><span data-stu-id="6d2b4-265">Term Set</span></span>|
<span data-ttu-id="6d2b4-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="6d2b4-266">inTermGroup</span></span>|<span data-ttu-id="6d2b4-267">在「字詞群組」</span><span class="sxs-lookup"><span data-stu-id="6d2b4-267">In term group</span></span>|<span data-ttu-id="6d2b4-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-268">TermSet</span></span>|<span data-ttu-id="6d2b4-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="6d2b4-269">TermGroup</span></span>|
<span data-ttu-id="6d2b4-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="6d2b4-270">topLevelTermOf</span></span>|<span data-ttu-id="6d2b4-271">是最高層級的字詞</span><span class="sxs-lookup"><span data-stu-id="6d2b4-271">Is Top Level Term Of</span></span>|<span data-ttu-id="6d2b4-272">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-272">Term</span></span>|<span data-ttu-id="6d2b4-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-273">TermSet</span></span>|
<span data-ttu-id="6d2b4-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="6d2b4-274">hasTopLevelTerm</span></span>|<span data-ttu-id="6d2b4-275">具有最高層級字詞</span><span class="sxs-lookup"><span data-stu-id="6d2b4-275">Has top level term</span></span>|<span data-ttu-id="6d2b4-276">字詞集</span><span class="sxs-lookup"><span data-stu-id="6d2b4-276">Term Set</span></span>|<span data-ttu-id="6d2b4-277">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-277">Term</span></span>|
<span data-ttu-id="6d2b4-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="6d2b4-278">termSetName</span></span>|<span data-ttu-id="6d2b4-279">字片語具有名稱</span><span class="sxs-lookup"><span data-stu-id="6d2b4-279">Term set has Name</span></span>|<span data-ttu-id="6d2b4-280">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-280">Term</span></span>|<span data-ttu-id="6d2b4-281">純文字</span><span class="sxs-lookup"><span data-stu-id="6d2b4-281">Plain literal</span></span>|
<span data-ttu-id="6d2b4-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-282">defaultLabel</span></span>|<span data-ttu-id="6d2b4-283">字詞具有預設標籤</span><span class="sxs-lookup"><span data-stu-id="6d2b4-283">Term has default label</span></span>|<span data-ttu-id="6d2b4-284">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-284">Term</span></span>|<span data-ttu-id="6d2b4-285">純文字</span><span class="sxs-lookup"><span data-stu-id="6d2b4-285">Plain literal</span></span>|
<span data-ttu-id="6d2b4-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="6d2b4-286">otherLabel</span></span>|<span data-ttu-id="6d2b4-287">字詞有其他標籤</span><span class="sxs-lookup"><span data-stu-id="6d2b4-287">Term has other label</span></span>|<span data-ttu-id="6d2b4-288">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-288">Term</span></span>|<span data-ttu-id="6d2b4-289">純文字</span><span class="sxs-lookup"><span data-stu-id="6d2b4-289">Plain literal</span></span>|
<span data-ttu-id="6d2b4-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="6d2b4-290">propertyName</span></span>|<span data-ttu-id="6d2b4-291">具有屬性標籤</span><span class="sxs-lookup"><span data-stu-id="6d2b4-291">Has Property Label</span></span>|<span data-ttu-id="6d2b4-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="6d2b4-293">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="6d2b4-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="6d2b4-294">描述</span><span class="sxs-lookup"><span data-stu-id="6d2b4-294">description</span></span>|<span data-ttu-id="6d2b4-295">具有 Description</span><span class="sxs-lookup"><span data-stu-id="6d2b4-295">Has Description</span></span>|<span data-ttu-id="6d2b4-296">全部</span><span class="sxs-lookup"><span data-stu-id="6d2b4-296">All</span></span>|<span data-ttu-id="6d2b4-297">純文字</span><span class="sxs-lookup"><span data-stu-id="6d2b4-297">Plain literal</span></span>|
|<span data-ttu-id="6d2b4-298">母</span><span class="sxs-lookup"><span data-stu-id="6d2b4-298">parent</span></span>|<span data-ttu-id="6d2b4-299">具有 parent</span><span class="sxs-lookup"><span data-stu-id="6d2b4-299">Has parent</span></span>|<span data-ttu-id="6d2b4-300">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-300">Term</span></span>|<span data-ttu-id="6d2b4-301">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-301">Term</span></span>|
|<span data-ttu-id="6d2b4-302">孩子</span><span class="sxs-lookup"><span data-stu-id="6d2b4-302">child</span></span>|<span data-ttu-id="6d2b4-303">具有子項</span><span class="sxs-lookup"><span data-stu-id="6d2b4-303">Has Child</span></span>|<span data-ttu-id="6d2b4-304">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-304">Term</span></span>|<span data-ttu-id="6d2b4-305">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-305">Term</span></span>|
|<span data-ttu-id="6d2b4-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="6d2b4-306">isAvailableForTagging</span></span>|<span data-ttu-id="6d2b4-307">可用於標記</span><span class="sxs-lookup"><span data-stu-id="6d2b4-307">Is available for tagging</span></span>|<span data-ttu-id="6d2b4-308">字詞、字詞集</span><span class="sxs-lookup"><span data-stu-id="6d2b4-308">Term, Term Set</span></span>|<span data-ttu-id="6d2b4-309">布林值</span><span class="sxs-lookup"><span data-stu-id="6d2b4-309">Boolean</span></span>|
|<span data-ttu-id="6d2b4-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6d2b4-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="6d2b4-311">已共用自訂屬性</span><span class="sxs-lookup"><span data-stu-id="6d2b4-311">Has shared custom property</span></span>|<span data-ttu-id="6d2b4-312">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-312">Term</span></span>|<span data-ttu-id="6d2b4-313">Boolean、string、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="6d2b4-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="6d2b4-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="6d2b4-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="6d2b4-315">具有本機自訂屬性</span><span class="sxs-lookup"><span data-stu-id="6d2b4-315">Has local custom property</span></span>|<span data-ttu-id="6d2b4-316">術語</span><span class="sxs-lookup"><span data-stu-id="6d2b4-316">Term</span></span>|<span data-ttu-id="6d2b4-317">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="6d2b4-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="6d2b4-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="6d2b4-319">具有 Custom 屬性</span><span class="sxs-lookup"><span data-stu-id="6d2b4-319">Has Custom Property</span></span>|<span data-ttu-id="6d2b4-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="6d2b4-320">TermSet</span></span>|<span data-ttu-id="6d2b4-321">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="6d2b4-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="6d2b4-322">[SKOS](https://www.w3.org/TR/skos-primer/) [分類法 SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 的有效案例不允許：</span><span class="sxs-lookup"><span data-stu-id="6d2b4-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="6d2b4-323">階層式冗余- [SKOS](https://www.w3.org/TR/skos-primer/) 概念可以同時附加到數個更廣泛的概念，但 sharepoint 分類法：字詞只可以有一個 sharepoint 分類法： parent，因此，也不允許對字詞的迴圈相關性。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="6d2b4-324">SharePoint 分類法中不允許使用孤立字詞。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="6d2b4-325">每個 sharepoint 分類法：字詞應具備 sharepoint 分類法： parent 或應為 sharepoint 分類法： topLevelTermOf a TermSet。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="6d2b4-326">SharePoint 分類不支援關聯關係。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="6d2b4-327">SharePoint 分類只允許兩種階層式關聯類型-sharepoint 分類法： parent and sharepoint-分類法： child。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="6d2b4-328">不同于 [SKOS](https://www.w3.org/TR/skos-primer/) SharePoint 分類詞彙中的階層關聯，只能使用相同 TermSet 內的字詞建立。</span><span class="sxs-lookup"><span data-stu-id="6d2b4-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d2b4-329">請參閱</span><span class="sxs-lookup"><span data-stu-id="6d2b4-329">See also</span></span>

[<span data-ttu-id="6d2b4-330">使用以 SKOS 為基礎的格式匯入字詞集</span><span class="sxs-lookup"><span data-stu-id="6d2b4-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

