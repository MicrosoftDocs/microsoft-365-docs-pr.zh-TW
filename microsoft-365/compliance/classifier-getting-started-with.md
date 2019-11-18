---
title: 開始使用 Microsoft 365 相關性 （預覽）
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 類別器是內容的的工具，您可以訓練，讓它正值與負值的範例，來查看辨識各種類型。 一旦訓練類別器並確認其結果是正確的您會使用它來搜尋整個組織內容、 分類它納入資料外洩防護 (DLP) 或保留原則或套用保留或敏感度標籤。
ms.openlocfilehash: 6b8574b7c87f0b038c46894940cb8d15b152ab5c
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "38690212"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="0ed8a-104">開始使用可訓練的分類器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="0ed8a-104">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="0ed8a-105">來分類和標籤內容，以便將其受保護，並適當地處理是的起始位置的資訊保護法則。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-105">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="0ed8a-106">Microsoft 365 有三種方法可以將內容分類。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-106">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="0ed8a-107">手動</span><span class="sxs-lookup"><span data-stu-id="0ed8a-107">Manually</span></span>

<span data-ttu-id="0ed8a-108">這需要人工 judgement 和巨集指令。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-108">This requires human judgement and action.</span></span> <span data-ttu-id="0ed8a-109">系統管理員可能是使用既有的標籤和敏感資訊類型或建立自己並將它們發行。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-109">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="0ed8a-110">使用者與系統管理員將其套用至內容為他們發生。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-110">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="0ed8a-111">然後可以保護內容，並管理其處理。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-111">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="0ed8a-112">自動的模式比對</span><span class="sxs-lookup"><span data-stu-id="0ed8a-112">Automated pattern matching</span></span>

<span data-ttu-id="0ed8a-113">這個類別的分類機制包括尋找內容：</span><span class="sxs-lookup"><span data-stu-id="0ed8a-113">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="0ed8a-114">關鍵字或中繼資料值 （關鍵字查詢語言）</span><span class="sxs-lookup"><span data-stu-id="0ed8a-114">keywords or metadata values (keyword query language)</span></span>
- <span data-ttu-id="0ed8a-115">使用先前識別社會安全、 信用卡或銀行帳戶號碼[（敏感資訊類型）](what-the-sensitive-information-types-look-for.md)相似的敏感資訊的模式</span><span class="sxs-lookup"><span data-stu-id="0ed8a-115">using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(sensitive information types)](what-the-sensitive-information-types-look-for.md)</span></span>
- <span data-ttu-id="0ed8a-116">辨識項目，因為它是一項變異範本[（文件手指列印）](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="0ed8a-116">Recognizing an item because it is a variation on a template [(document finger printing)](document-fingerprinting.md)</span></span>
- <span data-ttu-id="0ed8a-117">使用管制的確切字串[（符合確切資料）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-117">using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="0ed8a-118">敏感度和保留標籤可以再自動套用的[資料外洩防護 (DLP)](data-loss-prevention-policies.md)和[保留原則](retention-policies.md)中，使該內容可供使用。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-118">Sensitivity and retention labels can then be automatically applied that make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="0ed8a-119">Trainable 相關性</span><span class="sxs-lookup"><span data-stu-id="0ed8a-119">Trainable classifiers</span></span>

<span data-ttu-id="0ed8a-120">此分類方法是特別適合的本質上，不 predisposed 來輕鬆地識別任一手動或自動模式比對方法的內容。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-120">This classification method is particularly well suited to content that, by its nature, isn't predisposed to being easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="0ed8a-121">分類的這個方法是更多關於訓練器來識別哪些項目，不由 （模式比對） 的項目中的項目為基礎的項目。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-121">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="0ed8a-122">類別器可學習如何識別類型的內容所要尋找之內容的範例數百您感興趣來分類。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-122">A classifier learns how to identify a type of content by looking a hundreds of examples of the content you are interested in classifying.</span></span> <span data-ttu-id="0ed8a-123">您啟動饋送肯定都是從 [類別] 中的範例，然後它會處理那些，一旦您進行測試給予混合的比對和非比對的範例。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-123">You start by feeding it examples that are definitely in the category, then once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="0ed8a-124">類別器然後進行您要建立新檔指定的任何項目落在類別預測。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-124">The classifier then makes predictions as to whether or not any given item falls into the category you are building.</span></span> <span data-ttu-id="0ed8a-125">您再來確認其結果，排序出 positive、 負號、 誤判和漏報以協助增進及其預測的正確性。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-125">You then confirm its results, sorting out the positives, negatives, false positives and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="0ed8a-126">當您發佈受過訓練類別器時，它透過位置，例如 SharePoint Online、 Exchange 和 OneDrive 中的項目排序，並將內容分類。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-126">When you publish the trained classifier, it sorts through items in locations, like SharePoint Online, Exchange, and OneDrive and classifies the content.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ed8a-127">這兩種相關性可做為[自動套用保留標籤原則式根據條件](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[通訊符合性](communication-compliance.md)條件。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-127">Both types of classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [Communication compliance](communication-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ed8a-128">Trainable 相關性只使用未加密，都會以英文顯示的項目。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-128">Trainable classifiers only work with items that are not encrypted and are in english.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="0ed8a-129">類型的相關性</span><span class="sxs-lookup"><span data-stu-id="0ed8a-129">Types of classifiers</span></span>

<span data-ttu-id="0ed8a-130">有已準備好使用相關性和 trainable 相關性。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-130">There are ready to use classifiers and trainable classifiers.</span></span> <span data-ttu-id="0ed8a-131">取得 trainable 類別器可發行狀態需要訓練時間投資。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-131">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="0ed8a-132">若要協助您開始使用相關性、 Microsoft 365 隨附一些準備好使用相關性。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-132">To help you get started using classifiers, Microsoft 365 comes with a few ready to use classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed8a-133">使用之前任何準備使用分類和標示的工作流程中的類別器，您應測試其對您組織的範例內容您認為符合要確認其分類預測符合您預期的類別。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-133">Before using any ready to use classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-ready-to-use-classifiers"></a><span data-ttu-id="0ed8a-134">了解準備好使用相關性</span><span class="sxs-lookup"><span data-stu-id="0ed8a-134">Understanding ready to use classifiers</span></span>

<span data-ttu-id="0ed8a-135">Microsoft 365 隨附六個準備好使用相關性：</span><span class="sxs-lookup"><span data-stu-id="0ed8a-135">Microsoft 365 comes with six ready to use classifiers:</span></span>

- <span data-ttu-id="0ed8a-136">**冒犯**： 偵測其包含 profanities、 slurs、 嘲諷和偽裝的運算式 （也就是具有相同的意義更冒犯性字詞運算式） 的文字項目。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-136">**Offensive Language**: detects text items which contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="0ed8a-137">**履歷表**： 偵測到項目是文字應徵者個人、 教育、 專業資格、 工作經驗和其他個人識別資訊的帳戶</span><span class="sxs-lookup"><span data-stu-id="0ed8a-137">**Resumes**: detects items which are textual accounts of an applicant's personal, educational, professional qualifications, work experience and other personally identifying information</span></span>
- <span data-ttu-id="0ed8a-138">**SourceCode**： 偵測其包含一組指示和陳述式廣泛使用電腦程式設計語言所撰寫的項目。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-138">**SourceCode**: detects items which contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="0ed8a-139">**騷擾**： 偵測到特定類別的冒犯的語言文字項目與目標根據下列特性的一或多個個人的不良管理辦法： 競爭、 ethnicity、 宗教、 國家原點、 性別、 性別方向、 保留、 行動不便。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-139">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="0ed8a-140">**褻瀆**： 偵測到特定類別的不良的語言文字項目中包含運算式，讓大多數人</span><span class="sxs-lookup"><span data-stu-id="0ed8a-140">**Profanity**: detects a specific category of offensive language text items which contain expressions that embarrass most people</span></span>
- <span data-ttu-id="0ed8a-141">**威脅**： 偵測到特定類別的威脅，從而認可暴力或執行實體損害或損壞的人員或屬性相關的不良的語言文字項目</span><span class="sxs-lookup"><span data-stu-id="0ed8a-141">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="0ed8a-142">這些會出現在**Microsoft 365 合規性中心** > **資料分類 （預覽）** > **Trainable 相關性**檢視狀態的`Ready to use`。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-142">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![相關性-準備-要-使用-相關性](media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="0ed8a-144">請注意冒犯、 騷擾、 褻瀆和威脅相關性只使用可搜尋的文字不詳盡或完整。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-144">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="0ed8a-145">此外，語言和文化的標準不斷變更，並根據這些最新資訊，Microsoft 保留來更新其自行斟酌中的這些相關性的權限。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-145">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="0ed8a-146">雖然相關性可能會協助您組織中監視冒犯與使用其他語言，相關性沒有解決這種語言的後果，而不提供監視或所使用之回應的貴組織的唯一方法這類的語言。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-146">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="0ed8a-147">您的組織，並不 Microsoft 或其子公司，會維持負責監視、 強制執行、 封鎖、 移除和保留的預先受過訓練類別器所識別的所有內容的相關的所有決策。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-147">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-ready-to-use-classifiers"></a><span data-ttu-id="0ed8a-148">使用準備好使用相關性的程序流程</span><span class="sxs-lookup"><span data-stu-id="0ed8a-148">Process flow for using ready to use classifiers</span></span>

<span data-ttu-id="0ed8a-149">若要使用相關性不需要訓練，但您需要確認他們會識別類型的內容，您會需要他們協助您在合規性解決方案中使用它們之前，已準備好。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-149">Ready to use classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="0ed8a-150">測試前受過訓練類別器遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-150">Testing a pre-trained classifier follows this flow.</span></span>

![測試前受過訓練類別器的程序流程](media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="0ed8a-152">了解 trainable 相關性</span><span class="sxs-lookup"><span data-stu-id="0ed8a-152">Understanding trainable classifiers</span></span>

<span data-ttu-id="0ed8a-153">當準備好使用相關性不符合您的需求時，您可以建立及訓練您自己的相關性。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-153">When the ready to use classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="0ed8a-154">沒有建立您自己，所涉及的更多工作，但他們將會更好量身訂做您組織的需求。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-154">There is significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="0ed8a-155">如需有關如何使用預先受過訓練類別器的詳細資訊，請參閱[使用準備好使用類別器](classifier-using-a-ready-to-use-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="0ed8a-155">For more detail on how to use a pre-trained classifier, see [Using a ready to use classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ed8a-156">只會建立 trainable 類別器使用者可以訓練，並檢閱該類別器所做的預測。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-156">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="0ed8a-157">建立 trainable 相關性的程序流程</span><span class="sxs-lookup"><span data-stu-id="0ed8a-157">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="0ed8a-158">建立及發佈使用 trainable 類別器在合規性解決方案，例如保留原則及通訊監督遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-158">Creating and publishing a trainable classifier for use in compliance solutions such as retention policies and communication supervision follows this flow.</span></span> <span data-ttu-id="0ed8a-159">如需詳細資訊，在建立 trainable 類別器，請參閱[建立 trainable 類別器](classifier-creating-a-trainable-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed8a-159">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![處理程序流程 trainable 類別器](media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="0ed8a-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ed8a-161">See also</span></span>

- [<span data-ttu-id="0ed8a-162">保留標籤</span><span class="sxs-lookup"><span data-stu-id="0ed8a-162">retention labels</span></span>](labels.md)
- [<span data-ttu-id="0ed8a-163">保留原則</span><span class="sxs-lookup"><span data-stu-id="0ed8a-163">retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="0ed8a-164">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="0ed8a-164">data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="0ed8a-165">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="0ed8a-165">sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="0ed8a-166">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="0ed8a-166">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="0ed8a-167">文件手指列印</span><span class="sxs-lookup"><span data-stu-id="0ed8a-167">document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="0ed8a-168">精確資料相符項目</span><span class="sxs-lookup"><span data-stu-id="0ed8a-168">exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
