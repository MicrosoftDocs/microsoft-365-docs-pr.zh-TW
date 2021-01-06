---
title: 深入瞭解 trainable 的分類器
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，方法是將它肯定和否定的範例，以查看。 在訓練分類器之後，請確認其結果是否正確。 然後，您可以使用它來搜尋組織的內容，並將其分類，以套用保留或敏感度標籤，或將其包含在資料遺失防護 (DLP) 或保留原則。
ms.openlocfilehash: 0e5f712b76af2fba3d456997a47352773d92d766
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759897"
---
# <a name="learn-about-trainable-classifiers"></a><span data-ttu-id="56419-105">深入瞭解 trainable 的分類器</span><span class="sxs-lookup"><span data-stu-id="56419-105">Learn about trainable classifiers</span></span>

<span data-ttu-id="56419-106">分類及標示內容，使其能受到保護和正確處理，是資訊保護訓練科目的開始位置。</span><span class="sxs-lookup"><span data-stu-id="56419-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="56419-107">Microsoft 365 有三種方式可對內容進行分類。</span><span class="sxs-lookup"><span data-stu-id="56419-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="56419-108">手動</span><span class="sxs-lookup"><span data-stu-id="56419-108">Manually</span></span>

<span data-ttu-id="56419-109">此方法需要人工判斷和動作。</span><span class="sxs-lookup"><span data-stu-id="56419-109">This method requires human judgment and action.</span></span> <span data-ttu-id="56419-110">系統管理員可以使用預先存在的標籤和敏感資訊類型，或自行建立，然後加以發佈。</span><span class="sxs-lookup"><span data-stu-id="56419-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="56419-111">使用者和系統管理員會在遇到時，將其套用至內容。</span><span class="sxs-lookup"><span data-stu-id="56419-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="56419-112">然後您就可以保護內容並管理其部署。</span><span class="sxs-lookup"><span data-stu-id="56419-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="56419-113">自動模式對應</span><span class="sxs-lookup"><span data-stu-id="56419-113">Automated pattern matching</span></span>

<span data-ttu-id="56419-114">這種分類機制類別包括尋找內容的方式如下：</span><span class="sxs-lookup"><span data-stu-id="56419-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="56419-115">關鍵字或中繼資料值 (關鍵字查詢語言) 。</span><span class="sxs-lookup"><span data-stu-id="56419-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="56419-116">使用先前識別的敏感資訊模式，例如社會保險、信用卡或銀行帳戶號碼 [ (敏感資訊類型實體定義) ](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="56419-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="56419-117">識別專案，因為它是範本的變化 (的 [ 檔指紋列印) ](document-fingerprinting.md)。</span><span class="sxs-lookup"><span data-stu-id="56419-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="56419-118">使用完全字串的目前狀態 [ (完全相符的資料) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="56419-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="56419-119">敏感度和保留標籤可以自動套用，讓內容可用於 [資料遺失防護 (DLP) ](data-loss-prevention-policies.md) 和 [自動套用保留標籤](apply-retention-labels-automatically.md)的原則。</span><span class="sxs-lookup"><span data-stu-id="56419-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="56419-120">分類</span><span class="sxs-lookup"><span data-stu-id="56419-120">Classifiers</span></span>

<span data-ttu-id="56419-121">這種分類方法特別適合無法透過手動或自動模式相符方法輕易識別的內容。</span><span class="sxs-lookup"><span data-stu-id="56419-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="56419-122">這種分類方法更詳細地訓練分類器，以根據專案 (模式相符) 中的元素來識別專案。</span><span class="sxs-lookup"><span data-stu-id="56419-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="56419-123">分類器透過查看您要分類之內容的數百個範例，瞭解如何識別內容類型。</span><span class="sxs-lookup"><span data-stu-id="56419-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="56419-124">您可以在類別中進一步送入明確的範例。</span><span class="sxs-lookup"><span data-stu-id="56419-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="56419-125">一旦處理這些程式，您可以讓它混合使用比對和不相符的範例。</span><span class="sxs-lookup"><span data-stu-id="56419-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="56419-126">分類器接著會作出預測，以判斷是否有任何指定的專案屬於您所建立的類別。</span><span class="sxs-lookup"><span data-stu-id="56419-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="56419-127">然後，您可以確認其結果、將 true 正值、true 負片、誤報和漏報排序，以提升其預測的準確性。</span><span class="sxs-lookup"><span data-stu-id="56419-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="56419-128">當您發佈分類器時，它會在 SharePoint Online、Exchange 及 OneDrive 等位置中排序專案，並將內容分類。</span><span class="sxs-lookup"><span data-stu-id="56419-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="56419-129">在您發佈分類器之後，您可以繼續使用類似于初始訓練程式的意見反應進行訓練。</span><span class="sxs-lookup"><span data-stu-id="56419-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="56419-130">您可以使用 trainable 的分類器</span><span class="sxs-lookup"><span data-stu-id="56419-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="56419-131">內建的分類器和 trainable 分類器皆可作為[使用靈敏度標籤的 Office autolabeling](apply-sensitivity-label-automatically.md)條件，並根據狀況和[通訊規範](communication-compliance.md)[自動套用保留標籤原則](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="56419-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="56419-132">敏感度標籤可以使用分類器做為條件，請參閱 [自動套用敏感度標籤至內容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="56419-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56419-133">分類器只會使用未加密及英文的專案。</span><span class="sxs-lookup"><span data-stu-id="56419-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="56419-134">分類器類型</span><span class="sxs-lookup"><span data-stu-id="56419-134">Types of classifiers</span></span>

- <span data-ttu-id="56419-135">**預先訓練的分類** 器-Microsoft 已建立並預先訓練許多的分類器，您可以開始使用而不訓練它們。</span><span class="sxs-lookup"><span data-stu-id="56419-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="56419-136">這些分類器的狀態會顯示為 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="56419-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="56419-137">**自訂分類** 器-如果您需要擴充預先訓練的分類器所涵蓋專案以外的分類需求，您可以建立及訓練您自己的分類器。</span><span class="sxs-lookup"><span data-stu-id="56419-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="56419-138">預先訓練的分類器</span><span class="sxs-lookup"><span data-stu-id="56419-138">Pre-trained classifiers</span></span>

<span data-ttu-id="56419-139">Microsoft 365 隨附五個預先訓練的分類器：</span><span class="sxs-lookup"><span data-stu-id="56419-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="56419-140">我們正在取代 **冒犯性語言** 的預先訓練分類符，因為它已經產生大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="56419-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="56419-141">請勿使用它，如果您目前使用它，您應該將商務程式移出它。</span><span class="sxs-lookup"><span data-stu-id="56419-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="56419-142">建議您改為使用 **威脅**、 **猥褻** 和 **騷擾** 預先訓練的分類器。</span><span class="sxs-lookup"><span data-stu-id="56419-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="56419-143">**簡歷**：偵測屬於申請人個人、教育、專業資格、工作經驗及其他個人識別資訊的文字帳戶的專案</span><span class="sxs-lookup"><span data-stu-id="56419-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="56419-144">**原始程式碼**：偵測包含一組指令和語句的專案，這些專案是以前25種使用的電腦程式設計語言所撰寫的 GitHub</span><span class="sxs-lookup"><span data-stu-id="56419-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="56419-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="56419-145">ActionScript</span></span>
    - <span data-ttu-id="56419-146">C</span><span class="sxs-lookup"><span data-stu-id="56419-146">C</span></span>
    - <span data-ttu-id="56419-147">C#</span><span class="sxs-lookup"><span data-stu-id="56419-147">C#</span></span>
    - <span data-ttu-id="56419-148">C++</span><span class="sxs-lookup"><span data-stu-id="56419-148">C++</span></span>
    - <span data-ttu-id="56419-149">Clojure</span><span class="sxs-lookup"><span data-stu-id="56419-149">Clojure</span></span>
    - <span data-ttu-id="56419-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="56419-150">CoffeeScript</span></span>
    - <span data-ttu-id="56419-151">移至</span><span class="sxs-lookup"><span data-stu-id="56419-151">Go</span></span>
    - <span data-ttu-id="56419-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="56419-152">Haskell</span></span>
    - <span data-ttu-id="56419-153">JAVA</span><span class="sxs-lookup"><span data-stu-id="56419-153">Java</span></span>
    - <span data-ttu-id="56419-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="56419-154">JavaScript</span></span>
    - <span data-ttu-id="56419-155">Lua</span><span class="sxs-lookup"><span data-stu-id="56419-155">Lua</span></span>
    - <span data-ttu-id="56419-156">Matlab</span><span class="sxs-lookup"><span data-stu-id="56419-156">MATLAB</span></span>
    - <span data-ttu-id="56419-157">目標-C</span><span class="sxs-lookup"><span data-stu-id="56419-157">Objective-C</span></span>
    - <span data-ttu-id="56419-158">Perl</span><span class="sxs-lookup"><span data-stu-id="56419-158">Perl</span></span>
    - <span data-ttu-id="56419-159">Php</span><span class="sxs-lookup"><span data-stu-id="56419-159">PHP</span></span>
    - <span data-ttu-id="56419-160">Python</span><span class="sxs-lookup"><span data-stu-id="56419-160">Python</span></span>
    - <span data-ttu-id="56419-161">R</span><span class="sxs-lookup"><span data-stu-id="56419-161">R</span></span>
    - <span data-ttu-id="56419-162">紅寶石</span><span class="sxs-lookup"><span data-stu-id="56419-162">Ruby</span></span>
    - <span data-ttu-id="56419-163">Scala</span><span class="sxs-lookup"><span data-stu-id="56419-163">Scala</span></span>
    - <span data-ttu-id="56419-164">命令介面</span><span class="sxs-lookup"><span data-stu-id="56419-164">Shell</span></span>
    - <span data-ttu-id="56419-165">迅速</span><span class="sxs-lookup"><span data-stu-id="56419-165">Swift</span></span>
    - <span data-ttu-id="56419-166">Tex</span><span class="sxs-lookup"><span data-stu-id="56419-166">Tex</span></span>
    - <span data-ttu-id="56419-167">Vim 腳本</span><span class="sxs-lookup"><span data-stu-id="56419-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="56419-168">原始程式碼經過訓練，可在大量文字是原始程式碼時進行偵測。</span><span class="sxs-lookup"><span data-stu-id="56419-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="56419-169">它不會偵測到以純文字交錯的原始程式碼文字。</span><span class="sxs-lookup"><span data-stu-id="56419-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="56419-170">**騷擾**：偵測特定類別的冒犯性語言的文字專案，這些專案會根據下列特性，針對一或多個個人設定相關的冒犯性語言：種族、ethnicity、宗教、本國原產地、性別、性方向、年齡、傷殘</span><span class="sxs-lookup"><span data-stu-id="56419-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="56419-171">**猥褻** 語言：偵測特定類別的冒犯性語言的文字專案，包含 embarrass 大部分人員的運算式</span><span class="sxs-lookup"><span data-stu-id="56419-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="56419-172">**威脅**：偵測特定類別的冒犯性語言的文字專案與威脅以認可暴力或對人員或財產造成實體損毀或損毀的威脅</span><span class="sxs-lookup"><span data-stu-id="56419-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="56419-173">這些會出現在 **Microsoft 365 規範中心**  >  **資料分類** Trainable 使用中的分類器視圖中，  >  狀態為 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="56419-173">These appear in the **Microsoft 365 compliance center** > **Data classification** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分類器-預先訓練的分類器](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="56419-175">請注意，冒犯性語言、騷擾、猥褻和威脅分類器只會使用可搜尋文字，並非完整或完整。</span><span class="sxs-lookup"><span data-stu-id="56419-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="56419-176">此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新這些分類器的權利。</span><span class="sxs-lookup"><span data-stu-id="56419-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="56419-177">雖然分類程式可協助您的組織監控冒犯性和其他語言，但分類程式不會解決這類語言的影響，而且不是為了提供組織的唯一監視或回應這類語言的使用方式。</span><span class="sxs-lookup"><span data-stu-id="56419-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="56419-178">您的組織，而不是 Microsoft 或其子公司，仍然負責所有與監控、強制執行、封鎖、移除及保留預先訓練的分類器所識別的內容相關的決策。</span><span class="sxs-lookup"><span data-stu-id="56419-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="56419-179">自訂分類器</span><span class="sxs-lookup"><span data-stu-id="56419-179">Custom classifiers</span></span>

<span data-ttu-id="56419-180">當預先訓練的分類器不符合您的需求時，您可以建立及訓練您自己的分類器。</span><span class="sxs-lookup"><span data-stu-id="56419-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="56419-181">建立您自己的工作會相當多，但他們會更適合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="56419-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="56419-182">例如，您可以為下列專案建立 trainable 的分類器：</span><span class="sxs-lookup"><span data-stu-id="56419-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="56419-183">法律檔，例如律師用戶端許可權、結束集、工作帳單</span><span class="sxs-lookup"><span data-stu-id="56419-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="56419-184">戰略性商務檔-類似電子報、合併與收購、交易、商務或行銷計畫、智慧財產權、專利權、設計檔</span><span class="sxs-lookup"><span data-stu-id="56419-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="56419-185">定價資訊-類似發票、價格報價單、工作訂單、投標檔</span><span class="sxs-lookup"><span data-stu-id="56419-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="56419-186">財務資訊，例如組織投資、季度或年度結果</span><span class="sxs-lookup"><span data-stu-id="56419-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="56419-187">建立自訂分類程式的程式流程</span><span class="sxs-lookup"><span data-stu-id="56419-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="56419-188">在此流程中，建立及發行用於規範解決方案（例如保留原則及通訊監督）的分類程式。</span><span class="sxs-lookup"><span data-stu-id="56419-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="56419-189">如需建立自訂 trainable 分類器的詳細資訊，請參閱 [建立自訂分類器](classifier-get-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="56419-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![處理常式流程自訂分類符](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="56419-191">重新培訓分類器</span><span class="sxs-lookup"><span data-stu-id="56419-191">Retraining classifiers</span></span>

<span data-ttu-id="56419-192">您可以透過提供其所執行分類的意見反應，協助改善所有自訂分類器和某些預先訓練的分類器的準確性。</span><span class="sxs-lookup"><span data-stu-id="56419-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="56419-193">這稱為重新培訓，遵循此工作流程。</span><span class="sxs-lookup"><span data-stu-id="56419-193">This is called retraining and follow this workflow.</span></span>

![分類器重新培訓工作流程](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="56419-195">另請參閱</span><span class="sxs-lookup"><span data-stu-id="56419-195">See also</span></span>

- [<span data-ttu-id="56419-196">保留標籤</span><span class="sxs-lookup"><span data-stu-id="56419-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="56419-197">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="56419-197">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="56419-198">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="56419-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="56419-199">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="56419-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="56419-200">檔指紋列印</span><span class="sxs-lookup"><span data-stu-id="56419-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="56419-201">完全相符的資料</span><span class="sxs-lookup"><span data-stu-id="56419-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
