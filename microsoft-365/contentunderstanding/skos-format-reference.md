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
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087273"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="9169e-103">SharePoint 分類法的 SKOS 格式參照</span><span class="sxs-lookup"><span data-stu-id="9169e-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="9169e-104">本文包括用於表示 [SharePoint 分類法](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)的 RDF 詞彙，它基於 [SKOS](https://www.w3.org/TR/skos-primer/)。</span><span class="sxs-lookup"><span data-stu-id="9169e-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="9169e-105">如需此 RDF 語法的序列化，請使用 RDF [TURTLE](https://www.w3.org/TR/turtle/)。</span><span class="sxs-lookup"><span data-stu-id="9169e-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="9169e-106">下表顯示了 [SharePoint 分類法](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)詞彙的 [SKOS](https://www.w3.org/TR/skos-primer/) 對等用法。</span><span class="sxs-lookup"><span data-stu-id="9169e-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="9169e-107">SharePoint 不支援沒有 SharePoint 分類法對等用法的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。</span><span class="sxs-lookup"><span data-stu-id="9169e-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="9169e-108">SharePoint 分類法</span><span class="sxs-lookup"><span data-stu-id="9169e-108">SharePoint taxonomy</span></span>|<span data-ttu-id="9169e-109">SKOS 對等用法</span><span class="sxs-lookup"><span data-stu-id="9169e-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="9169e-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="9169e-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="9169e-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="9169e-111">skos:Concept</span></span>|
|<span data-ttu-id="9169e-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="9169e-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="9169e-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="9169e-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="9169e-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="9169e-115">skos:inScheme</span></span>|
|<span data-ttu-id="9169e-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="9169e-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="9169e-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="9169e-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="9169e-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="9169e-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="9169e-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="9169e-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="9169e-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="9169e-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-121">skos:prefLabel</span></span>|
|<span data-ttu-id="9169e-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="9169e-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="9169e-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-123">skos:prefLabel</span></span>|
|<span data-ttu-id="9169e-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="9169e-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="9169e-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-125">skos:prefLabel</span></span>|
|<span data-ttu-id="9169e-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="9169e-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-127">skos:altLabel</span></span>|
|<span data-ttu-id="9169e-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="9169e-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="9169e-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="9169e-129">skos:definition</span></span>|
|<span data-ttu-id="9169e-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="9169e-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="9169e-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="9169e-131">skos:broader</span></span>|
|<span data-ttu-id="9169e-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="9169e-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="9169e-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="9169e-133">skos:narrower</span></span>|

<span data-ttu-id="9169e-134">下表顯示了從 [OWL](https://www.w3.org/TR/owl2-primer/) 衍生的 SharePoint 分類法詞彙的實體。</span><span class="sxs-lookup"><span data-stu-id="9169e-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="9169e-135">SharePoint 分類法詞彙</span><span class="sxs-lookup"><span data-stu-id="9169e-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="9169e-136">自 OWL 衍生</span><span class="sxs-lookup"><span data-stu-id="9169e-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="9169e-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="9169e-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="9169e-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="9169e-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="9169e-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="9169e-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="9169e-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="9169e-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="9169e-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="9169e-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="9169e-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="9169e-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="9169e-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="9169e-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="9169e-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="9169e-145">SharePoint 分類法詞彙</span><span class="sxs-lookup"><span data-stu-id="9169e-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="9169e-146">分類法是正式分類系統。</span><span class="sxs-lookup"><span data-stu-id="9169e-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="9169e-147">分類法將描述事物的單詞、標籤和字詞分組，然後將這些群組排列成階層圖。</span><span class="sxs-lookup"><span data-stu-id="9169e-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="9169e-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="9169e-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="9169e-149">代表受管理的中繼資料階層圖中的字詞或關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9169e-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="9169e-150">[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的原子單元。</span><span class="sxs-lookup"><span data-stu-id="9169e-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="9169e-151">每個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)都屬於屬於 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) 的 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="9169e-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="9169e-152">定義[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="9169e-153">[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)強制存在於 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中。</span><span class="sxs-lookup"><span data-stu-id="9169e-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="9169e-154">DefaultLabel 是[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)在視覺呈現方式中顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="9169e-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="9169e-155">定義[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的必要欄位包括：</span><span class="sxs-lookup"><span data-stu-id="9169e-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="9169e-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="9169e-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="9169e-158">[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以：</span><span class="sxs-lookup"><span data-stu-id="9169e-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="9169e-159">在階層上與另一[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相關，前提是這兩個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)屬於同一個 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="9169e-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="9169e-160">有多個子系[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但只有單一父系[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="9169e-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="9169e-161">如果是 topLevelTermOf [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)，則不會定義父系[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="9169e-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="9169e-162">每個 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言都有一個 defaultLabel。</span><span class="sxs-lookup"><span data-stu-id="9169e-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="9169e-163">如果它既不包含父系[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不是 topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)，則不存在。</span><span class="sxs-lookup"><span data-stu-id="9169e-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="9169e-164">在相同的階層層級中，只有唯一的 defaultLabel。</span><span class="sxs-lookup"><span data-stu-id="9169e-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="9169e-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="9169e-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="9169e-166">表示字詞物件的階層或平面集，稱為「TermSet」。</span><span class="sxs-lookup"><span data-stu-id="9169e-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="9169e-167">顧名思義，TermSet 是[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的集合。</span><span class="sxs-lookup"><span data-stu-id="9169e-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="9169e-168">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 中的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)必須屬於 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="9169e-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="9169e-169">沒有單獨存在的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="9169e-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="9169e-170">定義[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="9169e-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 會以邏輯方式組入 [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)。</span><span class="sxs-lookup"><span data-stu-id="9169e-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="9169e-172">定義[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的必要欄位是：</span><span class="sxs-lookup"><span data-stu-id="9169e-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="9169e-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="9169e-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="9169e-174">如果提供的 termSetName 在 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) 中不是唯一的，SharePoint 會在名稱末尾附加一個數位，以保持 termSetName 的唯一性。</span><span class="sxs-lookup"><span data-stu-id="9169e-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="9169e-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="9169e-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="9169e-176">SharePoint 使用此内容對應 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中最頂層的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，該字詞集是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)階層圖的進入點。</span><span class="sxs-lookup"><span data-stu-id="9169e-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="9169e-177">這是 SharePoint 分類法的反關係： topLevelTermOf。</span><span class="sxs-lookup"><span data-stu-id="9169e-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="9169e-178">定義此項語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="9169e-179">您無法定父系[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的頂層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="9169e-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="9169e-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="9169e-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="9169e-181">Sharepoint-taxonomy：topLevelTermOf 是反 sharepoint-taxonomy：hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="9169e-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="9169e-182">定義此項語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="9169e-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="9169e-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="9169e-184">使用此項可將[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)對應到 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="9169e-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="9169e-185">單一[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)只能存在於單一 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。</span><span class="sxs-lookup"><span data-stu-id="9169e-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="9169e-186">[定義字詞](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)時，SharePoint 就需要使用這個屬性。</span><span class="sxs-lookup"><span data-stu-id="9169e-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="9169e-187">必要標籤</span><span class="sxs-lookup"><span data-stu-id="9169e-187">Required labels</span></span>

<span data-ttu-id="9169e-188">在開始使用受托管的中繼資料之前，貴組織可能需要仔細規劃。</span><span class="sxs-lookup"><span data-stu-id="9169e-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="9169e-189">您必須執行的規劃量取決於分類法的正式程度。</span><span class="sxs-lookup"><span data-stu-id="9169e-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="9169e-190">它也取決於您想對中繼資料施加多少控制。</span><span class="sxs-lookup"><span data-stu-id="9169e-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="9169e-191">在階層的各個層級，您需要為字詞或 TermSet 設定所需的標籤。</span><span class="sxs-lookup"><span data-stu-id="9169e-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="9169e-192">一個字詞可以有一個或多個預設語言標籤，以及零個或多個非預設語言標籤。</span><span class="sxs-lookup"><span data-stu-id="9169e-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="9169e-193">如果字詞在語言中有標籤，則其中一個標籤必須是預設標籤。</span><span class="sxs-lookup"><span data-stu-id="9169e-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="9169e-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="9169e-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="9169e-195">將此預設詞法標籤用於作為[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)必要參數的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="9169e-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="9169e-196">用以視覺化表示[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="9169e-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="9169e-197">定義 defaultLabel 的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="9169e-198">DefaultLabel 包含兩部分：字串和語言標籤。</span><span class="sxs-lookup"><span data-stu-id="9169e-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="9169e-199">該語言必須是 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言之一。</span><span class="sxs-lookup"><span data-stu-id="9169e-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="9169e-200">defaultLabel 對同一 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中同一階層級的所有[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9169e-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="9169e-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="9169e-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="9169e-202">取得並設定目前 TermSet 物件的名稱。</span><span class="sxs-lookup"><span data-stu-id="9169e-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="9169e-203">這是 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言中 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的詞法標籤。</span><span class="sxs-lookup"><span data-stu-id="9169e-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="9169e-204">這是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必要參數。</span><span class="sxs-lookup"><span data-stu-id="9169e-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="9169e-205">用以視覺化表示[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="9169e-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="9169e-206">定義 termSetName 的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="9169e-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="9169e-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="9169e-208">取得並設定目前 TermSet 物件的使用者定義樣式。</span><span class="sxs-lookup"><span data-stu-id="9169e-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="9169e-209">這是 sharepoint-taxonomy 的詞法標籤： SharedCustomPropertyForTerm、sharepoint-taxonomy： LocalCustomPropertyForTerm 和 sharepoint-taxonomy：[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作語言中的 CustomPropertyForTermSet。</span><span class="sxs-lookup"><span data-stu-id="9169e-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="9169e-210">sharepoint-taxonomy： propertyName 被視為 CustomProperty 的鑰匙。</span><span class="sxs-lookup"><span data-stu-id="9169e-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="9169e-211">定義 propetyName 的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="9169e-212">選用標籤</span><span class="sxs-lookup"><span data-stu-id="9169e-212">Optional labels</span></span>

<span data-ttu-id="9169e-213">您也可以向分類法中添加選用標籤。</span><span class="sxs-lookup"><span data-stu-id="9169e-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="9169e-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="9169e-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="9169e-215">這是[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的替代詞法標籤。</span><span class="sxs-lookup"><span data-stu-id="9169e-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="9169e-216">定義 otherLabel 的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="9169e-217">語意關聯性</span><span class="sxs-lookup"><span data-stu-id="9169e-217">Semantic relationships</span></span>

<span data-ttu-id="9169e-218">分類法有階層和有時的一個簡單「相關字詞」關聯關係，但有些分類法有「語意關係」或自訂建立的關聯性。</span><span class="sxs-lookup"><span data-stu-id="9169e-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="9169e-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="9169e-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="9169e-220">這種分層將一個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)與另一個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。</span><span class="sxs-lookup"><span data-stu-id="9169e-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="9169e-221">[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的頂層[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，否則一定有父系[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="9169e-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="9169e-222">定義父系的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="9169e-223">這表示 TermA 是父系，而 TermA 是子系。</span><span class="sxs-lookup"><span data-stu-id="9169e-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="9169e-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="9169e-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="9169e-225">物件包含一個或多個子系 TermSet 實例，且可透過 TermSets 屬性存取。</span><span class="sxs-lookup"><span data-stu-id="9169e-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="9169e-226">這個類別也提供建立新子系 TermSet 物件的方法。</span><span class="sxs-lookup"><span data-stu-id="9169e-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="9169e-227">在群組上指定了編輯子系字詞和 TermSet 實例的權限。</span><span class="sxs-lookup"><span data-stu-id="9169e-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="9169e-228">這種分層將一個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)與另一個[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相關聯。</span><span class="sxs-lookup"><span data-stu-id="9169e-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="9169e-229">定義子系的語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="9169e-230">這表示 TermA 是父系，而 TermA 是子系。</span><span class="sxs-lookup"><span data-stu-id="9169e-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="9169e-231">文件附註</span><span class="sxs-lookup"><span data-stu-id="9169e-231">Documentation notes</span></span>

<span data-ttu-id="9169e-232">本節討論在 Microsoft.SharePoint.Taxonomy 命名空間中詳細描述的分類資訊。</span><span class="sxs-lookup"><span data-stu-id="9169e-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="9169e-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="9169e-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="9169e-234">這是對任何 [SharePoint 分類法](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)詞彙實體的詳細說明。</span><span class="sxs-lookup"><span data-stu-id="9169e-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="9169e-235">新增描述的語法是：</span><span class="sxs-lookup"><span data-stu-id="9169e-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="9169e-236">自訂屬性</span><span class="sxs-lookup"><span data-stu-id="9169e-236">Custom properties</span></span>

<span data-ttu-id="9169e-237">從只讀字典中取得目前字詞對象的自訂屬性物件的集合。</span><span class="sxs-lookup"><span data-stu-id="9169e-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="9169e-238">自訂屬性是可以為[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 定義的機碼值對，以進一步描述[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="9169e-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="9169e-239">SharePoint 在 propertyName 的協助下指定自訂屬性的鍵。</span><span class="sxs-lookup"><span data-stu-id="9169e-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="9169e-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="9169e-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="9169e-241">定義此項語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="9169e-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="9169e-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="9169e-243">如果[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的自訂屬性需要與[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，那麼當您在其他地方重用該[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)時，則需要在 SharedCustomPropertyForTerm 下定義它。</span><span class="sxs-lookup"><span data-stu-id="9169e-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="9169e-244">定義此項語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="9169e-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="9169e-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="9169e-246">如果[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的自訂屬性不需要與[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，那麼當您在其他地方重用該[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)時，則需要在 LocalCustomPropertyForTerm 下定義它。</span><span class="sxs-lookup"><span data-stu-id="9169e-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="9169e-247">定義此項語法如下：</span><span class="sxs-lookup"><span data-stu-id="9169e-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="9169e-248">資料內容</span><span class="sxs-lookup"><span data-stu-id="9169e-248">Data properties</span></span>

<span data-ttu-id="9169e-249">在階層的各個層級，您需要為字詞或 TermSet 設定指定的資料内容。</span><span class="sxs-lookup"><span data-stu-id="9169e-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="9169e-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="9169e-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="9169e-251">使用此項可指定在 SharePoint 清單和庫中是否有可用的[字詞](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="9169e-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="9169e-252">此項的語法是：</span><span class="sxs-lookup"><span data-stu-id="9169e-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="9169e-253">網域和範圍</span><span class="sxs-lookup"><span data-stu-id="9169e-253">Domain and range</span></span>

<span data-ttu-id="9169e-254">下表說明 SharePoint 分類法詞彙的網域和範圍。</span><span class="sxs-lookup"><span data-stu-id="9169e-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="9169e-255">Predicates/verb</span><span class="sxs-lookup"><span data-stu-id="9169e-255">Predicates/verb</span></span>|<span data-ttu-id="9169e-256">意義</span><span class="sxs-lookup"><span data-stu-id="9169e-256">Meaning</span></span>|<span data-ttu-id="9169e-257">網域</span><span class="sxs-lookup"><span data-stu-id="9169e-257">Domain</span></span>|<span data-ttu-id="9169e-258">範圍</span><span class="sxs-lookup"><span data-stu-id="9169e-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="9169e-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-259">inTermSet</span></span>|<span data-ttu-id="9169e-260">字詞組中</span><span class="sxs-lookup"><span data-stu-id="9169e-260">In term set</span></span>|<span data-ttu-id="9169e-261">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-261">Term</span></span>|<span data-ttu-id="9169e-262">字詞組</span><span class="sxs-lookup"><span data-stu-id="9169e-262">Term Set</span></span>|
<span data-ttu-id="9169e-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="9169e-263">inTermGroup</span></span>|<span data-ttu-id="9169e-264">字詞群組中</span><span class="sxs-lookup"><span data-stu-id="9169e-264">In term group</span></span>|<span data-ttu-id="9169e-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-265">TermSet</span></span>|<span data-ttu-id="9169e-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="9169e-266">TermGroup</span></span>|
<span data-ttu-id="9169e-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="9169e-267">topLevelTermOf</span></span>|<span data-ttu-id="9169e-268">頂層字詞屬於</span><span class="sxs-lookup"><span data-stu-id="9169e-268">Is Top Level Term Of</span></span>|<span data-ttu-id="9169e-269">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-269">Term</span></span>|<span data-ttu-id="9169e-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-270">TermSet</span></span>|
<span data-ttu-id="9169e-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="9169e-271">hasTopLevelTerm</span></span>|<span data-ttu-id="9169e-272">具有頂層字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-272">Has top level term</span></span>|<span data-ttu-id="9169e-273">字詞組</span><span class="sxs-lookup"><span data-stu-id="9169e-273">Term Set</span></span>|<span data-ttu-id="9169e-274">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-274">Term</span></span>|
<span data-ttu-id="9169e-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="9169e-275">termSetName</span></span>|<span data-ttu-id="9169e-276">字詞組有名稱</span><span class="sxs-lookup"><span data-stu-id="9169e-276">Term set has Name</span></span>|<span data-ttu-id="9169e-277">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-277">Term</span></span>|<span data-ttu-id="9169e-278">純文字</span><span class="sxs-lookup"><span data-stu-id="9169e-278">Plain literal</span></span>|
<span data-ttu-id="9169e-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-279">defaultLabel</span></span>|<span data-ttu-id="9169e-280">字詞有預設標籤</span><span class="sxs-lookup"><span data-stu-id="9169e-280">Term has default label</span></span>|<span data-ttu-id="9169e-281">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-281">Term</span></span>|<span data-ttu-id="9169e-282">純文字</span><span class="sxs-lookup"><span data-stu-id="9169e-282">Plain literal</span></span>|
<span data-ttu-id="9169e-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="9169e-283">otherLabel</span></span>|<span data-ttu-id="9169e-284">字詞有其他標籤</span><span class="sxs-lookup"><span data-stu-id="9169e-284">Term has other label</span></span>|<span data-ttu-id="9169e-285">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-285">Term</span></span>|<span data-ttu-id="9169e-286">純文字</span><span class="sxs-lookup"><span data-stu-id="9169e-286">Plain literal</span></span>|
<span data-ttu-id="9169e-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="9169e-287">propertyName</span></span>|<span data-ttu-id="9169e-288">具有屬性標籤</span><span class="sxs-lookup"><span data-stu-id="9169e-288">Has Property Label</span></span>|<span data-ttu-id="9169e-289">SharedCustomPropertyForTerm，LocalCustomPropertyForTerm，CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="9169e-290">布林值、字串、整數、小數點、雙精確度</span><span class="sxs-lookup"><span data-stu-id="9169e-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="9169e-291">描述</span><span class="sxs-lookup"><span data-stu-id="9169e-291">description</span></span>|<span data-ttu-id="9169e-292">具有描述</span><span class="sxs-lookup"><span data-stu-id="9169e-292">Has Description</span></span>|<span data-ttu-id="9169e-293">全部</span><span class="sxs-lookup"><span data-stu-id="9169e-293">All</span></span>|<span data-ttu-id="9169e-294">純文字</span><span class="sxs-lookup"><span data-stu-id="9169e-294">Plain literal</span></span>|
|<span data-ttu-id="9169e-295">父系</span><span class="sxs-lookup"><span data-stu-id="9169e-295">parent</span></span>|<span data-ttu-id="9169e-296">具有父系</span><span class="sxs-lookup"><span data-stu-id="9169e-296">Has parent</span></span>|<span data-ttu-id="9169e-297">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-297">Term</span></span>|<span data-ttu-id="9169e-298">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-298">Term</span></span>|
|<span data-ttu-id="9169e-299">子系</span><span class="sxs-lookup"><span data-stu-id="9169e-299">child</span></span>|<span data-ttu-id="9169e-300">具有子系</span><span class="sxs-lookup"><span data-stu-id="9169e-300">Has Child</span></span>|<span data-ttu-id="9169e-301">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-301">Term</span></span>|<span data-ttu-id="9169e-302">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-302">Term</span></span>|
|<span data-ttu-id="9169e-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="9169e-303">isAvailableForTagging</span></span>|<span data-ttu-id="9169e-304">可用於標記</span><span class="sxs-lookup"><span data-stu-id="9169e-304">Is available for tagging</span></span>|<span data-ttu-id="9169e-305">字詞、字詞組</span><span class="sxs-lookup"><span data-stu-id="9169e-305">Term, Term Set</span></span>|<span data-ttu-id="9169e-306">布林值</span><span class="sxs-lookup"><span data-stu-id="9169e-306">Boolean</span></span>|
|<span data-ttu-id="9169e-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="9169e-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="9169e-308">具有共用自訂屬性</span><span class="sxs-lookup"><span data-stu-id="9169e-308">Has shared custom property</span></span>|<span data-ttu-id="9169e-309">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-309">Term</span></span>|<span data-ttu-id="9169e-310">布林值、字串、整數、小數點、雙精確度</span><span class="sxs-lookup"><span data-stu-id="9169e-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="9169e-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="9169e-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="9169e-312">具有本地自訂屬性</span><span class="sxs-lookup"><span data-stu-id="9169e-312">Has local custom property</span></span>|<span data-ttu-id="9169e-313">字詞</span><span class="sxs-lookup"><span data-stu-id="9169e-313">Term</span></span>|<span data-ttu-id="9169e-314">布林值、字串、整數、小數點、雙精確度</span><span class="sxs-lookup"><span data-stu-id="9169e-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="9169e-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="9169e-316">具有自訂屬性</span><span class="sxs-lookup"><span data-stu-id="9169e-316">Has Custom Property</span></span>|<span data-ttu-id="9169e-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="9169e-317">TermSet</span></span>|<span data-ttu-id="9169e-318">布林值、字串、整數、小數點、雙精確度</span><span class="sxs-lookup"><span data-stu-id="9169e-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="9169e-319">[SKOS](https://www.w3.org/TR/skos-primer/) [SharePoint 分類法](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)不允許的有效案例：</span><span class="sxs-lookup"><span data-stu-id="9169e-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="9169e-320">分層冗餘 - [SKOS](https://www.w3.org/TR/skos-primer/) 概念可以同時附加到多個更廣泛的概念，但 sharepoint-taxonomy：字詞只有一個 sharepoint-taxonomy：父系，因此也不允許字詞的循環相依。</span><span class="sxs-lookup"><span data-stu-id="9169e-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="9169e-321">SharePoint 分類法中不允許孤立字詞。</span><span class="sxs-lookup"><span data-stu-id="9169e-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="9169e-322">每個 sharepoint-taxonomy：字詞應該要麼有一個 sharepoint-taxonomy：父系或應該是 sharepoint-taxonomy：TermSet 的topLevelTermOf。</span><span class="sxs-lookup"><span data-stu-id="9169e-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="9169e-323">SharePoint 分類法不支援關聯關係。</span><span class="sxs-lookup"><span data-stu-id="9169e-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="9169e-324">SharePoint 分類法只允許 2 種類型的階層關係 – sharepoint-taxonomy：父系和 sharepoint-taxonomy：子系。</span><span class="sxs-lookup"><span data-stu-id="9169e-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="9169e-325">與 [SKOS](https://www.w3.org/TR/skos-primer/) 不同，SharePoint 分類法詞彙中的階層關係只能用同一 TermSet 中的字詞建立。</span><span class="sxs-lookup"><span data-stu-id="9169e-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="9169e-326">請參閱</span><span class="sxs-lookup"><span data-stu-id="9169e-326">See also</span></span>

[<span data-ttu-id="9169e-327">使用 SKOS 格式匯入字詞組</span><span class="sxs-lookup"><span data-stu-id="9169e-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

