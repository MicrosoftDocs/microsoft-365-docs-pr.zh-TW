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
description: Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，方法是將它肯定和否定的範例，以查看。 在訓練分類器之後，請確認其結果是否正確。 然後，您可以使用它來搜尋組織的內容，並將其分類，以套用保留或敏感度標籤，或將其包含在資料遺失防護（DLP）或保留原則中。
ms.openlocfilehash: de52c8c7f96d2d3c0383f27b17bcc5162bb662c5
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371461"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="254f7-105">開始使用可訓練的分類器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="254f7-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="254f7-106">分類及標示內容，使其能受到保護和正確處理，是資訊保護訓練科目的開始位置。</span><span class="sxs-lookup"><span data-stu-id="254f7-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="254f7-107">Microsoft 365 有三種方式可對內容進行分類。</span><span class="sxs-lookup"><span data-stu-id="254f7-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="254f7-108">手動</span><span class="sxs-lookup"><span data-stu-id="254f7-108">Manually</span></span>

<span data-ttu-id="254f7-109">此方法需要人工判斷和動作。</span><span class="sxs-lookup"><span data-stu-id="254f7-109">This method requires human judgment and action.</span></span> <span data-ttu-id="254f7-110">系統管理員可以使用預先存在的標籤和敏感資訊類型，或自行建立，然後加以發佈。</span><span class="sxs-lookup"><span data-stu-id="254f7-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="254f7-111">使用者和系統管理員會在遇到時，將其套用至內容。</span><span class="sxs-lookup"><span data-stu-id="254f7-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="254f7-112">然後您就可以保護內容並管理其部署。</span><span class="sxs-lookup"><span data-stu-id="254f7-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="254f7-113">自動模式對應</span><span class="sxs-lookup"><span data-stu-id="254f7-113">Automated pattern matching</span></span>

<span data-ttu-id="254f7-114">這種分類機制類別包括尋找內容的方式：</span><span class="sxs-lookup"><span data-stu-id="254f7-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="254f7-115">關鍵字或中繼資料值（關鍵字查詢語言）。</span><span class="sxs-lookup"><span data-stu-id="254f7-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="254f7-116">使用先前識別的敏感資訊模式，如社會保險、信用卡或銀行帳戶號碼[（敏感資訊類型實體定義）](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="254f7-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="254f7-117">識別專案，因為它是範本的變化[（檔指紋列印）](document-fingerprinting.md)。</span><span class="sxs-lookup"><span data-stu-id="254f7-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="254f7-118">使用完全字串的狀態[（完全符合資料）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="254f7-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="254f7-119">然後，您可以自動套用敏感度和保留標籤，讓內容可用於[資料遺失防護（DLP）](data-loss-prevention-policies.md)和[保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="254f7-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="254f7-120">Trainable 分類器</span><span class="sxs-lookup"><span data-stu-id="254f7-120">Trainable classifiers</span></span>

<span data-ttu-id="254f7-121">這種分類方法特別適合無法透過手動或自動模式相符方法輕易識別的內容。</span><span class="sxs-lookup"><span data-stu-id="254f7-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="254f7-122">這種分類方法更詳細地訓練分類器，以根據專案的專案，而不是專案中的元素（模式對應）來識別專案。</span><span class="sxs-lookup"><span data-stu-id="254f7-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="254f7-123">分類器透過查看您要分類之內容的數百個範例，瞭解如何識別內容類型。</span><span class="sxs-lookup"><span data-stu-id="254f7-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="254f7-124">您可以在類別中進一步送入明確的範例。</span><span class="sxs-lookup"><span data-stu-id="254f7-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="254f7-125">一旦處理這些程式，您可以讓它混合使用比對和不相符的範例。</span><span class="sxs-lookup"><span data-stu-id="254f7-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="254f7-126">分類器接著會作出預測，以判斷是否有任何指定的專案屬於您所建立的類別。</span><span class="sxs-lookup"><span data-stu-id="254f7-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="254f7-127">然後，您可以確認其結果、將正值、負、誤報和 false 的否定排序，以提升預測的準確性。</span><span class="sxs-lookup"><span data-stu-id="254f7-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="254f7-128">當您發佈訓練的分類器時，它會在 SharePoint Online、Exchange 及 OneDrive 等位置中排序專案，並將內容分類。</span><span class="sxs-lookup"><span data-stu-id="254f7-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="254f7-129">您可以使用 trainable 的分類器</span><span class="sxs-lookup"><span data-stu-id="254f7-129">Where you can use trainable classifiers</span></span>
<span data-ttu-id="254f7-130">內建的分類器和 trainable 分類器皆為根據條件和[通訊相容性](communication-compliance-configure.md)[自動套用保留標籤原則](labels.md#applying-a-retention-label-automatically-based-on-conditions)的條件。</span><span class="sxs-lookup"><span data-stu-id="254f7-130">Both built-in classifiers and trainable classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [communication compliance](communication-compliance-configure.md).</span></span> 

<span data-ttu-id="254f7-131">敏感度標籤可以使用內建及自行組建的分類器作為條件，請參閱對[內容自動套用靈敏度標籤](apply-sensitivity-label-automatically.md)，並[自動為 Office 應用程式](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)加上標籤。</span><span class="sxs-lookup"><span data-stu-id="254f7-131">Sensitivity labels can use built-in and build-your-own classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md), and [auto-labeling for Office apps](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="254f7-132">Trainable 的分類程式只會使用未加密及英文的專案。</span><span class="sxs-lookup"><span data-stu-id="254f7-132">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="254f7-133">授權需求</span><span class="sxs-lookup"><span data-stu-id="254f7-133">Licensing requirements</span></span>

<span data-ttu-id="254f7-134">Trainable 分類器是 Microsoft 365 E5 或 E5 規範功能。</span><span class="sxs-lookup"><span data-stu-id="254f7-134">Trainable classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="254f7-135">您必須具有這些訂閱中的其中一項，才能使用這些訂閱。</span><span class="sxs-lookup"><span data-stu-id="254f7-135">You must have one of these subscriptions to make use of them.</span></span>

### <a name="pre-requisites"></a><span data-ttu-id="254f7-136">先決條件</span><span class="sxs-lookup"><span data-stu-id="254f7-136">Pre-requisites</span></span>

<span data-ttu-id="254f7-137">在 UI 中存取 trainable 的分類器：</span><span class="sxs-lookup"><span data-stu-id="254f7-137">To access trainable classifiers in the UI:</span></span> 
- <span data-ttu-id="254f7-138">全域管理員需要自願加入租使用者</span><span class="sxs-lookup"><span data-stu-id="254f7-138">the Global admin needs to opt in for the tenant</span></span>
- <span data-ttu-id="254f7-139">合規性管理員角色或合規性資料管理員是訓練分類器所需的</span><span class="sxs-lookup"><span data-stu-id="254f7-139">Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="254f7-140">在下列案例中，您將需要具有這些許可權的帳戶，才能使用 trainable 分類器：</span><span class="sxs-lookup"><span data-stu-id="254f7-140">You'll need accounts with these permissions to use trainable classifiers in these scenarios:</span></span>

- <span data-ttu-id="254f7-141">保留標籤原則案例： RecordManagement 和保留管理角色</span><span class="sxs-lookup"><span data-stu-id="254f7-141">Retention label policy scenario: RecordManagement and Retention Management roles</span></span> 
- <span data-ttu-id="254f7-142">敏感度標籤原則案例：安全性管理員、合規性管理員、規範資料管理員</span><span class="sxs-lookup"><span data-stu-id="254f7-142">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="254f7-143">通訊相容性原則案例：內幕人士風險管理管理員、主管審查管理員</span><span class="sxs-lookup"><span data-stu-id="254f7-143">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="types-of-classifiers"></a><span data-ttu-id="254f7-144">分類器類型</span><span class="sxs-lookup"><span data-stu-id="254f7-144">Types of classifiers</span></span>

<span data-ttu-id="254f7-145">有內建的分類器和 trainable 的分類器。</span><span class="sxs-lookup"><span data-stu-id="254f7-145">There are built-in classifiers and trainable classifiers.</span></span> <span data-ttu-id="254f7-146">若要讓 trainable 分類器成為可發佈的狀態，需要花費時間投資進行訓練。</span><span class="sxs-lookup"><span data-stu-id="254f7-146">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="254f7-147">為了協助您開始使用類元，Microsoft 365 附帶一些內建的分類符。</span><span class="sxs-lookup"><span data-stu-id="254f7-147">To help you get started using classifiers, Microsoft 365 comes with a few built-in classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="254f7-148">在您的分類和標籤工作流程中使用任何內建的分類器之前，您應該針對您想要的組織內容範例進行測試，以確認該類別的分類預測符合您的預期。</span><span class="sxs-lookup"><span data-stu-id="254f7-148">Before using any built-in classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-built-in-classifiers"></a><span data-ttu-id="254f7-149">瞭解內建的分類器</span><span class="sxs-lookup"><span data-stu-id="254f7-149">Understanding built-in classifiers</span></span>

<span data-ttu-id="254f7-150">Microsoft 365 隨附了五個建議的內建分類器：</span><span class="sxs-lookup"><span data-stu-id="254f7-150">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="254f7-151">我們正在取代**冒犯性語言**內建的分類符，因為它所產生的是大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="254f7-151">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="254f7-152">請勿使用它，如果您目前使用它，您應該將商務程式移出它。</span><span class="sxs-lookup"><span data-stu-id="254f7-152">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="254f7-153">建議您改為使用**威脅**、**猥褻**和**騷擾**內建的分類符。</span><span class="sxs-lookup"><span data-stu-id="254f7-153">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="254f7-154">**簡歷**：偵測屬於申請人個人、教育、專業資格、工作經驗及其他個人識別資訊的文字帳戶的專案</span><span class="sxs-lookup"><span data-stu-id="254f7-154">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="254f7-155">**原始程式碼**：偵測包含一組指令和語句的專案，這些專案是以前25種使用的電腦程式設計語言所撰寫的 GitHub</span><span class="sxs-lookup"><span data-stu-id="254f7-155">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="254f7-156">語言名稱</span><span class="sxs-lookup"><span data-stu-id="254f7-156">language name</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="254f7-157">ActionScript</span><span class="sxs-lookup"><span data-stu-id="254f7-157">ActionScript</span></span>|<span data-ttu-id="254f7-158">C</span><span class="sxs-lookup"><span data-stu-id="254f7-158">C</span></span>        |<span data-ttu-id="254f7-159">C#</span><span class="sxs-lookup"><span data-stu-id="254f7-159">C#</span></span>       |<span data-ttu-id="254f7-160">C++</span><span class="sxs-lookup"><span data-stu-id="254f7-160">C++</span></span>     |<span data-ttu-id="254f7-161">Clojure</span><span class="sxs-lookup"><span data-stu-id="254f7-161">Clojure</span></span>  |
  |<span data-ttu-id="254f7-162">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="254f7-162">CoffeeScript</span></span>|<span data-ttu-id="254f7-163">Css</span><span class="sxs-lookup"><span data-stu-id="254f7-163">CSS</span></span>     |<span data-ttu-id="254f7-164">移至</span><span class="sxs-lookup"><span data-stu-id="254f7-164">Go</span></span>       |<span data-ttu-id="254f7-165">Haskell</span><span class="sxs-lookup"><span data-stu-id="254f7-165">Haskell</span></span> |<span data-ttu-id="254f7-166">HTML</span><span class="sxs-lookup"><span data-stu-id="254f7-166">HTML</span></span>     |
  |<span data-ttu-id="254f7-167">JAVA</span><span class="sxs-lookup"><span data-stu-id="254f7-167">Java</span></span>     |<span data-ttu-id="254f7-168">JavaScript</span><span class="sxs-lookup"><span data-stu-id="254f7-168">JavaScript</span></span>|<span data-ttu-id="254f7-169">Lua</span><span class="sxs-lookup"><span data-stu-id="254f7-169">Lua</span></span>      |<span data-ttu-id="254f7-170">Matlab</span><span class="sxs-lookup"><span data-stu-id="254f7-170">MATLAB</span></span>   |<span data-ttu-id="254f7-171">目標-C</span><span class="sxs-lookup"><span data-stu-id="254f7-171">Objective-C</span></span>|
  |<span data-ttu-id="254f7-172">Perl</span><span class="sxs-lookup"><span data-stu-id="254f7-172">Perl</span></span>     |<span data-ttu-id="254f7-173">Php</span><span class="sxs-lookup"><span data-stu-id="254f7-173">PHP</span></span>      |<span data-ttu-id="254f7-174">Python</span><span class="sxs-lookup"><span data-stu-id="254f7-174">Python</span></span>   |<span data-ttu-id="254f7-175">R</span><span class="sxs-lookup"><span data-stu-id="254f7-175">R</span></span>        |<span data-ttu-id="254f7-176">紅寶石</span><span class="sxs-lookup"><span data-stu-id="254f7-176">Ruby</span></span>     |
  |<span data-ttu-id="254f7-177">Scala</span><span class="sxs-lookup"><span data-stu-id="254f7-177">Scala</span></span>    |<span data-ttu-id="254f7-178">命令介面</span><span class="sxs-lookup"><span data-stu-id="254f7-178">Shell</span></span>    |<span data-ttu-id="254f7-179">迅速</span><span class="sxs-lookup"><span data-stu-id="254f7-179">Swift</span></span>    |<span data-ttu-id="254f7-180">Tex</span><span class="sxs-lookup"><span data-stu-id="254f7-180">Tex</span></span>      |<span data-ttu-id="254f7-181">Vim 腳本</span><span class="sxs-lookup"><span data-stu-id="254f7-181">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="254f7-182">原始程式碼經過訓練，可在大量文字是原始程式碼時進行偵測。</span><span class="sxs-lookup"><span data-stu-id="254f7-182">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="254f7-183">它不會偵測到以純文字交錯的原始程式碼文字。</span><span class="sxs-lookup"><span data-stu-id="254f7-183">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="254f7-184">**騷擾**：偵測特定類別的冒犯性語言的文字專案，這些專案會根據下列特性，針對一或多個個人設定相關的冒犯性語言：種族、ethnicity、宗教、本國原產地、性別、性方向、年齡、傷殘</span><span class="sxs-lookup"><span data-stu-id="254f7-184">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="254f7-185">**猥褻**語言：偵測特定類別的冒犯性語言的文字專案，包含 embarrass 大部分人員的運算式</span><span class="sxs-lookup"><span data-stu-id="254f7-185">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="254f7-186">**威脅**：偵測特定類別的冒犯性語言的文字專案與威脅以認可暴力或對人員或財產造成實體損毀或損毀的威脅</span><span class="sxs-lookup"><span data-stu-id="254f7-186">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="254f7-187">這些會出現在**Microsoft 365 規範中心**  >  **資料分類（預覽）**  >  **Trainable 的分類**器視圖中，狀態為 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="254f7-187">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分類器-可供使用-分類器](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="254f7-189">請注意，冒犯性語言、騷擾、猥褻和威脅分類器只會使用可搜尋文字，並非完整或完整。</span><span class="sxs-lookup"><span data-stu-id="254f7-189">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="254f7-190">此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新這些分類器的權利。</span><span class="sxs-lookup"><span data-stu-id="254f7-190">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="254f7-191">雖然分類程式可協助您的組織監控冒犯性和其他語言，但分類程式不會解決這類語言的影響，而且不是為了提供組織的唯一監視或回應這類語言的使用方式。</span><span class="sxs-lookup"><span data-stu-id="254f7-191">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="254f7-192">您的組織，而不是 Microsoft 或其子公司，仍然負責所有與監控、強制執行、封鎖、移除及保留預先訓練的分類器所識別的內容相關的決策。</span><span class="sxs-lookup"><span data-stu-id="254f7-192">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-built-in-classifiers"></a><span data-ttu-id="254f7-193">使用內建分類器的處理流程</span><span class="sxs-lookup"><span data-stu-id="254f7-193">Process flow for using built-in classifiers</span></span>

<span data-ttu-id="254f7-194">內建的分類器不需要經過訓練，但是您必須先確認他們會識別您需要的內容類型，才可在規範方案中使用它們。</span><span class="sxs-lookup"><span data-stu-id="254f7-194">Built-in classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="254f7-195">測試預先訓練的分類器遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="254f7-195">Testing a pre-trained classifier follows this flow.</span></span>

![處理預先訓練的分類器的程式流程測試](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="254f7-197">瞭解 trainable 的分類器</span><span class="sxs-lookup"><span data-stu-id="254f7-197">Understanding trainable classifiers</span></span>

<span data-ttu-id="254f7-198">當內建的分類器不符合您的需求時，您可以建立及訓練您自己的分類器。</span><span class="sxs-lookup"><span data-stu-id="254f7-198">When the built-in classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="254f7-199">建立您自己的工作會相當多，但他們會更適合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="254f7-199">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="254f7-200">如需如何使用預先訓練的分類器的詳細資訊，請參閱[使用內建的分類器](classifier-using-a-ready-to-use-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="254f7-200">For more detail on how to use a pre-trained classifier, see [Using a built-in classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="254f7-201">只有建立 trainable 分類器的使用者可以訓練及審核該分類器所做的預測。</span><span class="sxs-lookup"><span data-stu-id="254f7-201">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="254f7-202">建立 trainable 的分類程式流程</span><span class="sxs-lookup"><span data-stu-id="254f7-202">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="254f7-203">建立及發佈用於規範解決方案（如保留原則及通訊監督）的 trainable 分類程式，遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="254f7-203">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="254f7-204">如需建立 trainable 分類器的詳細資訊，請參閱[建立 trainable 的分類器](classifier-creating-a-trainable-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="254f7-204">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![處理流程 trainable 分類器](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="254f7-206">另請參閱</span><span class="sxs-lookup"><span data-stu-id="254f7-206">See also</span></span>


- [<span data-ttu-id="254f7-207">保留標籤</span><span class="sxs-lookup"><span data-stu-id="254f7-207">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="254f7-208">保留原則</span><span class="sxs-lookup"><span data-stu-id="254f7-208">Retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="254f7-209">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="254f7-209">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="254f7-210">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="254f7-210">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="254f7-211">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="254f7-211">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="254f7-212">檔指紋列印</span><span class="sxs-lookup"><span data-stu-id="254f7-212">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="254f7-213">完全相符的資料</span><span class="sxs-lookup"><span data-stu-id="254f7-213">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
