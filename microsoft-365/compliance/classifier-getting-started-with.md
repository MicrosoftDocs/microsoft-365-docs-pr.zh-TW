---
title: 開始使用可訓練的分類器 (預覽)
f1.keywords:
- NOCSH
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
description: Microsoft 365 trainable 類別器是內容的的工具，您可以訓練，讓它正值與負值的範例，來查看辨識各種類型。 類別器調校完成之後，您確認它的結果正確無誤。 然後您可以用它來搜尋整個組織的內容及分類它納入資料外洩防護 (DLP) 或保留原則或套用保留或敏感度標籤。
ms.openlocfilehash: 75cf79e162c2e371821b4329fc1be949f0b3a81c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078806"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="4acfd-105">開始使用可訓練的分類器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="4acfd-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="4acfd-106">來分類和標籤內容，以便將其受保護，並適當地處理是的起始位置的資訊保護法則。</span><span class="sxs-lookup"><span data-stu-id="4acfd-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="4acfd-107">Microsoft 365 有三種方法可以將內容分類。</span><span class="sxs-lookup"><span data-stu-id="4acfd-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="4acfd-108">手動</span><span class="sxs-lookup"><span data-stu-id="4acfd-108">Manually</span></span>

<span data-ttu-id="4acfd-109">此方法需要人工判斷和巨集指令。</span><span class="sxs-lookup"><span data-stu-id="4acfd-109">This method requires human judgment and action.</span></span> <span data-ttu-id="4acfd-110">系統管理員可能是使用既有的標籤和敏感資訊類型或建立自己並將它們發行。</span><span class="sxs-lookup"><span data-stu-id="4acfd-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="4acfd-111">使用者與系統管理員將其套用至內容為他們發生。</span><span class="sxs-lookup"><span data-stu-id="4acfd-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="4acfd-112">然後可以保護內容，並管理其處理。</span><span class="sxs-lookup"><span data-stu-id="4acfd-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="4acfd-113">自動的模式比對</span><span class="sxs-lookup"><span data-stu-id="4acfd-113">Automated pattern matching</span></span>

<span data-ttu-id="4acfd-114">這個類別的分類機制包括尋找內容：</span><span class="sxs-lookup"><span data-stu-id="4acfd-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="4acfd-115">關鍵字或中繼資料值 （關鍵字查詢語言）</span><span class="sxs-lookup"><span data-stu-id="4acfd-115">keywords or metadata values (keyword query language)</span></span>
- <span data-ttu-id="4acfd-116">使用先前識別社會安全、 信用卡或銀行帳戶號碼[（敏感資訊類型）](what-the-sensitive-information-types-look-for.md)相似的敏感資訊的模式</span><span class="sxs-lookup"><span data-stu-id="4acfd-116">using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(sensitive information types)](what-the-sensitive-information-types-look-for.md)</span></span>
- <span data-ttu-id="4acfd-117">辨識項目，因為它是一項變異範本[（文件手指列印）](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="4acfd-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md)</span></span>
- <span data-ttu-id="4acfd-118">使用管制的確切字串[（符合確切資料）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="4acfd-118">using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="4acfd-119">若要讓內容可供使用中[資料外洩防護 (DLP)](data-loss-prevention-policies.md)和[保留原則](retention-policies.md)可以再是自動套用敏感度和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="4acfd-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="4acfd-120">Trainable 相關性</span><span class="sxs-lookup"><span data-stu-id="4acfd-120">Trainable classifiers</span></span>

<span data-ttu-id="4acfd-121">此分類方法是特別適用於不容易辨識，由任一手動或自動模式比對方法的內容。</span><span class="sxs-lookup"><span data-stu-id="4acfd-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="4acfd-122">分類的這個方法是更多關於訓練器來識別哪些項目，不由 （模式比對） 的項目中的項目為基礎的項目。</span><span class="sxs-lookup"><span data-stu-id="4acfd-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="4acfd-123">類別器可學習如何識別類型的內容可以查看數百個內容的範例您感興趣來分類。</span><span class="sxs-lookup"><span data-stu-id="4acfd-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="4acfd-124">您啟動饋送肯定都是類別中的範例。</span><span class="sxs-lookup"><span data-stu-id="4acfd-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="4acfd-125">它會處理那些，一旦您進行測試給予混合的比對和非比對的範例。</span><span class="sxs-lookup"><span data-stu-id="4acfd-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="4acfd-126">類別器接著讓預測想指定的任何項目是否落在類別，您正在建立的。</span><span class="sxs-lookup"><span data-stu-id="4acfd-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="4acfd-127">您然後確認它的結果，其排序出 positive、 負號、 誤判，以協助增進及其預測的正確性漏報中。</span><span class="sxs-lookup"><span data-stu-id="4acfd-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="4acfd-128">當您發佈受過訓練類別器時，它透過像 SharePoint Online、 Exchange 和 OneDrive 的位置中的項目排序，並將內容分類。</span><span class="sxs-lookup"><span data-stu-id="4acfd-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4acfd-129">這兩種相關性可做為[自動套用保留標籤原則式根據條件](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[通訊符合性](communication-compliance.md)條件。</span><span class="sxs-lookup"><span data-stu-id="4acfd-129">Both types of classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [Communication compliance](communication-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4acfd-130">Trainable 相關性只使用未加密，都會以英文顯示的項目。</span><span class="sxs-lookup"><span data-stu-id="4acfd-130">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="4acfd-131">授權需求</span><span class="sxs-lookup"><span data-stu-id="4acfd-131">Licensing requirements</span></span>

<span data-ttu-id="4acfd-132">Trainable 相關性為 Microsoft 365 E5 或 E5 合規性功能。</span><span class="sxs-lookup"><span data-stu-id="4acfd-132">Trainable classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="4acfd-133">您必須有一個進行這些訂閱加以使用。</span><span class="sxs-lookup"><span data-stu-id="4acfd-133">You must have one of these subscriptions to make use of them.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="4acfd-134">類型的相關性</span><span class="sxs-lookup"><span data-stu-id="4acfd-134">Types of classifiers</span></span>

<span data-ttu-id="4acfd-135">有已準備好使用相關性和 trainable 相關性。</span><span class="sxs-lookup"><span data-stu-id="4acfd-135">There are ready to use classifiers and trainable classifiers.</span></span> <span data-ttu-id="4acfd-136">取得 trainable 類別器可發行狀態需要訓練時間投資。</span><span class="sxs-lookup"><span data-stu-id="4acfd-136">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="4acfd-137">若要協助您開始使用相關性、 Microsoft 365 隨附一些準備好使用相關性。</span><span class="sxs-lookup"><span data-stu-id="4acfd-137">To help you get started using classifiers, Microsoft 365 comes with a few ready to use classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="4acfd-138">使用之前任何準備使用分類和標示的工作流程中的類別器，您應測試其對您組織的範例內容您認為符合要確認其分類預測符合您預期的類別。</span><span class="sxs-lookup"><span data-stu-id="4acfd-138">Before using any ready to use classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-ready-to-use-classifiers"></a><span data-ttu-id="4acfd-139">了解準備好使用相關性</span><span class="sxs-lookup"><span data-stu-id="4acfd-139">Understanding ready to use classifiers</span></span>

<span data-ttu-id="4acfd-140">Microsoft 365 隨附六個準備好使用相關性：</span><span class="sxs-lookup"><span data-stu-id="4acfd-140">Microsoft 365 comes with six ready to use classifiers:</span></span>

- <span data-ttu-id="4acfd-141">**冒犯**： 偵測到包含 profanities、 slurs、 嘲諷和偽裝的運算式 （也就是具有相同的意義更冒犯性字詞運算式） 的文字項目。</span><span class="sxs-lookup"><span data-stu-id="4acfd-141">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="4acfd-142">**履歷表**： 偵測到之應徵者個人、 教育、 專業資格、 工作經驗及其他個人識別資訊的文字帳戶的項目。</span><span class="sxs-lookup"><span data-stu-id="4acfd-142">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="4acfd-143">**SourceCode**： 偵測到項目包含一組指示和廣泛使用電腦程式設計語言所撰寫的陳述式。</span><span class="sxs-lookup"><span data-stu-id="4acfd-143">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="4acfd-144">**騷擾**： 偵測到特定類別的冒犯的語言文字項目與目標根據下列特性的一或多個個人的不良管理辦法： 競爭、 ethnicity、 宗教、 國家原點、 性別、 性別方向、 保留、 行動不便。</span><span class="sxs-lookup"><span data-stu-id="4acfd-144">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="4acfd-145">**褻瀆**： 偵測到特定類別冒犯的語言文字包含的項目讓大多數人的運算式。</span><span class="sxs-lookup"><span data-stu-id="4acfd-145">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="4acfd-146">**威脅**： 偵測到特定類別的威脅，從而認可暴力或執行實體損害或損壞的人員或屬性相關的不良的語言文字項目。</span><span class="sxs-lookup"><span data-stu-id="4acfd-146">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property.</span></span>

<span data-ttu-id="4acfd-147">這些會出現在**Microsoft 365 合規性中心** > **資料分類 （預覽）** > **Trainable 相關性**檢視狀態的`Ready to use`。</span><span class="sxs-lookup"><span data-stu-id="4acfd-147">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![相關性-準備-要-使用-相關性](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="4acfd-149">請注意冒犯、 騷擾、 褻瀆和威脅相關性只使用可搜尋的文字不詳盡或完整。</span><span class="sxs-lookup"><span data-stu-id="4acfd-149">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="4acfd-150">此外，語言和文化的標準不斷變更，並根據這些最新資訊，Microsoft 保留來更新其自行斟酌中的這些相關性的權限。</span><span class="sxs-lookup"><span data-stu-id="4acfd-150">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="4acfd-151">雖然相關性可能會協助您組織中監視冒犯與使用其他語言，相關性沒有解決這種語言的後果，而不提供監視或所使用之回應的貴組織的唯一方法這類的語言。</span><span class="sxs-lookup"><span data-stu-id="4acfd-151">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="4acfd-152">您的組織，並不 Microsoft 或其子公司，會維持負責監視、 強制執行、 封鎖、 移除和保留的預先受過訓練類別器所識別的所有內容的相關的所有決策。</span><span class="sxs-lookup"><span data-stu-id="4acfd-152">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-ready-to-use-classifiers"></a><span data-ttu-id="4acfd-153">使用準備好使用相關性的程序流程</span><span class="sxs-lookup"><span data-stu-id="4acfd-153">Process flow for using ready to use classifiers</span></span>

<span data-ttu-id="4acfd-154">若要使用相關性不需要訓練，但您需要確認他們會識別類型的內容，您會需要他們協助您在合規性解決方案中使用它們之前，已準備好。</span><span class="sxs-lookup"><span data-stu-id="4acfd-154">Ready to use classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="4acfd-155">測試前受過訓練類別器遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="4acfd-155">Testing a pre-trained classifier follows this flow.</span></span>

![測試前受過訓練類別器的程序流程](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="4acfd-157">了解 trainable 相關性</span><span class="sxs-lookup"><span data-stu-id="4acfd-157">Understanding trainable classifiers</span></span>

<span data-ttu-id="4acfd-158">當準備好使用相關性不符合您的需求時，您可以建立及訓練您自己的相關性。</span><span class="sxs-lookup"><span data-stu-id="4acfd-158">When the ready to use classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="4acfd-159">沒有建立您自己，所涉及的更多工作，但他們將會更好量身訂做您組織的需求。</span><span class="sxs-lookup"><span data-stu-id="4acfd-159">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="4acfd-160">如需有關如何使用預先受過訓練類別器的詳細資訊，請參閱[使用準備好使用類別器](classifier-using-a-ready-to-use-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="4acfd-160">For more detail on how to use a pre-trained classifier, see [Using a ready to use classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4acfd-161">只會建立 trainable 類別器使用者可以訓練，並檢閱該類別器所做的預測。</span><span class="sxs-lookup"><span data-stu-id="4acfd-161">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="4acfd-162">建立 trainable 相關性的程序流程</span><span class="sxs-lookup"><span data-stu-id="4acfd-162">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="4acfd-163">建立及發佈使用 trainable 類別器在合規性解決方案，例如保留原則和通訊監督，後面這個的流程。</span><span class="sxs-lookup"><span data-stu-id="4acfd-163">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="4acfd-164">如需詳細資訊，在建立 trainable 類別器，請參閱[建立 trainable 類別器](classifier-creating-a-trainable-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="4acfd-164">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![處理程序流程 trainable 類別器](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="4acfd-166">請參閱</span><span class="sxs-lookup"><span data-stu-id="4acfd-166">See also</span></span>

- [<span data-ttu-id="4acfd-167">保留標籤</span><span class="sxs-lookup"><span data-stu-id="4acfd-167">retention labels</span></span>](labels.md)
- [<span data-ttu-id="4acfd-168">保留原則</span><span class="sxs-lookup"><span data-stu-id="4acfd-168">retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="4acfd-169">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="4acfd-169">data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4acfd-170">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="4acfd-170">sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="4acfd-171">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="4acfd-171">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="4acfd-172">文件手指列印</span><span class="sxs-lookup"><span data-stu-id="4acfd-172">document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="4acfd-173">精確資料相符項目</span><span class="sxs-lookup"><span data-stu-id="4acfd-173">exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
