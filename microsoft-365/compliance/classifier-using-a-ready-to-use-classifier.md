---
title: 使用內建的分類器（預覽）
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
description: Microsoft 365 隨附許多內建的分類符，您可以用來識別及標記整個組織中的內容。 本主題將告訴您如何準備使用這些分類器。
ms.openlocfilehash: b8e4b51300bee86682924245bbf530e1e954b483
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826244"
---
# <a name="using-a-built-in-classifier-preview"></a><span data-ttu-id="71b89-104">使用內建的分類器（預覽）</span><span class="sxs-lookup"><span data-stu-id="71b89-104">Using a built-in classifier (preview)</span></span>

<span data-ttu-id="71b89-105">Microsoft 已使用極大的範例資料集訓練及測試了許多分類器，可協助識別特定的內容類別別。</span><span class="sxs-lookup"><span data-stu-id="71b89-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="71b89-106">請參閱[trainable 類元的快速入門（預覽）](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="71b89-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="71b89-107">這些分類器預設會顯示`Ready to use`在群組中。</span><span class="sxs-lookup"><span data-stu-id="71b89-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="71b89-108">**冒犯性語言**：偵測包含 profanities、slurs、taunts 及偽裝運算式（也就是具有更具冒犯性字詞之意義的運算式）的文字專案。</span><span class="sxs-lookup"><span data-stu-id="71b89-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="71b89-109">**簡歷**：偵測屬於申請人個人、教育、專業資格、工作經驗及其他個人識別資訊的文字帳戶的專案。</span><span class="sxs-lookup"><span data-stu-id="71b89-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="71b89-110">**原始程式碼**：偵測包含一組指令和語句的專案，這些專案是以前25種使用電腦程式設計語言的 GitHub 上所撰寫。</span><span class="sxs-lookup"><span data-stu-id="71b89-110">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub.</span></span>

|<span data-ttu-id="71b89-111">語言名稱</span><span class="sxs-lookup"><span data-stu-id="71b89-111">language name</span></span>|||||
|---------|---------|---------|---------|---------|
|<span data-ttu-id="71b89-112">ActionScript</span><span class="sxs-lookup"><span data-stu-id="71b89-112">ActionScript</span></span>|<span data-ttu-id="71b89-113">C</span><span class="sxs-lookup"><span data-stu-id="71b89-113">C</span></span>        |<span data-ttu-id="71b89-114">C#</span><span class="sxs-lookup"><span data-stu-id="71b89-114">C#</span></span>       |<span data-ttu-id="71b89-115">C++</span><span class="sxs-lookup"><span data-stu-id="71b89-115">C++</span></span>     |<span data-ttu-id="71b89-116">Clojure</span><span class="sxs-lookup"><span data-stu-id="71b89-116">Clojure</span></span>  |
|<span data-ttu-id="71b89-117">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="71b89-117">CoffeeScript</span></span>|<span data-ttu-id="71b89-118">Css</span><span class="sxs-lookup"><span data-stu-id="71b89-118">CSS</span></span>     |<span data-ttu-id="71b89-119">移至</span><span class="sxs-lookup"><span data-stu-id="71b89-119">Go</span></span>       |<span data-ttu-id="71b89-120">Haskell</span><span class="sxs-lookup"><span data-stu-id="71b89-120">Haskell</span></span> |<span data-ttu-id="71b89-121">HTML</span><span class="sxs-lookup"><span data-stu-id="71b89-121">HTML</span></span>     |
|<span data-ttu-id="71b89-122">JAVA</span><span class="sxs-lookup"><span data-stu-id="71b89-122">Java</span></span>     |<span data-ttu-id="71b89-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="71b89-123">JavaScript</span></span>|<span data-ttu-id="71b89-124">Lua</span><span class="sxs-lookup"><span data-stu-id="71b89-124">Lua</span></span>      |<span data-ttu-id="71b89-125">Matlab</span><span class="sxs-lookup"><span data-stu-id="71b89-125">MATLAB</span></span>   |<span data-ttu-id="71b89-126">目標-C</span><span class="sxs-lookup"><span data-stu-id="71b89-126">Objective-C</span></span>|
|<span data-ttu-id="71b89-127">Perl</span><span class="sxs-lookup"><span data-stu-id="71b89-127">Perl</span></span>     |<span data-ttu-id="71b89-128">Php</span><span class="sxs-lookup"><span data-stu-id="71b89-128">PHP</span></span>      |<span data-ttu-id="71b89-129">Python</span><span class="sxs-lookup"><span data-stu-id="71b89-129">Python</span></span>   |<span data-ttu-id="71b89-130">R</span><span class="sxs-lookup"><span data-stu-id="71b89-130">R</span></span>        |<span data-ttu-id="71b89-131">紅寶石</span><span class="sxs-lookup"><span data-stu-id="71b89-131">Ruby</span></span>     |
|<span data-ttu-id="71b89-132">Scala</span><span class="sxs-lookup"><span data-stu-id="71b89-132">Scala</span></span>    |<span data-ttu-id="71b89-133">命令介面</span><span class="sxs-lookup"><span data-stu-id="71b89-133">Shell</span></span>    |<span data-ttu-id="71b89-134">迅速</span><span class="sxs-lookup"><span data-stu-id="71b89-134">Swift</span></span>    |<span data-ttu-id="71b89-135">Tex</span><span class="sxs-lookup"><span data-stu-id="71b89-135">Tex</span></span>      |<span data-ttu-id="71b89-136">Vim 腳本</span><span class="sxs-lookup"><span data-stu-id="71b89-136">Vim Script</span></span>|

- <span data-ttu-id="71b89-137">**騷擾**：偵測特定類別的冒犯性語言的文字專案，這些專案會根據下列特性，偵測一或多個個人：種族、ethnicity、宗教、全國原始、性別、性方向、年齡、傷殘等相關的攻擊性設定。</span><span class="sxs-lookup"><span data-stu-id="71b89-137">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="71b89-138">**猥褻**語言：偵測特定類別的冒犯性語言文字專案，包含 embarrass 大部分人員的運算式。</span><span class="sxs-lookup"><span data-stu-id="71b89-138">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="71b89-139">**威脅**：偵測特定類別的冒犯性語言的文字專案與威脅，以認可暴力或對人員或財產造成實體損毀或損毀。</span><span class="sxs-lookup"><span data-stu-id="71b89-139">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="71b89-140">在您的分類和標籤工作流程中使用內建的分類器之前，您應該針對組織內容的範例進行測試，以確認類別的分類預測符合您的預期。</span><span class="sxs-lookup"><span data-stu-id="71b89-140">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71b89-141">請注意，冒犯性語言、騷擾、猥褻和威脅分類器只會使用可搜尋文字，並非完整或完整。</span><span class="sxs-lookup"><span data-stu-id="71b89-141">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="71b89-142">此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新這些分類器的權利。</span><span class="sxs-lookup"><span data-stu-id="71b89-142">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="71b89-143">雖然分類程式可協助您的組織監控冒犯性及其他使用的語言，但是分類程式不會解決這類語言的影響，而且不是為了提供組織的唯一監視或回應使用的方式這類語言。</span><span class="sxs-lookup"><span data-stu-id="71b89-143">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="71b89-144">您的組織，而不是 Microsoft 或其子公司，仍然負責所有與監控、強制執行、封鎖、移除及保留預先訓練的分類器所識別的內容相關的決策。</span><span class="sxs-lookup"><span data-stu-id="71b89-144">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a><span data-ttu-id="71b89-145">如何準備及使用內建的分類器</span><span class="sxs-lookup"><span data-stu-id="71b89-145">How to prepare for and use a built-in classifier</span></span>

1. <span data-ttu-id="71b89-146">收集您認為屬於內建分類器（肯定比對）類別的可處置內容專案，以及您要測試之類別中不應該包含的專案（負數相符）。</span><span class="sxs-lookup"><span data-stu-id="71b89-146">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71b89-147">範例專案不能加密，必須是英文。</span><span class="sxs-lookup"><span data-stu-id="71b89-147">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="71b89-148">建立專用的 SharePoint 線上資料夾;至少等候一個小時的資料夾新增至搜尋索引。</span><span class="sxs-lookup"><span data-stu-id="71b89-148">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="71b89-149">請記下資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="71b89-149">Make note of the folder URL.</span></span>

3. <span data-ttu-id="71b89-150">使用合規性管理員或安全性系統管理員角色存取，登入 microsoft 365 合規性中心，並開啟**microsoft 365 規範中心** > **記錄管理（預覽）** > **標籤原則] 索引標籤**。</span><span class="sxs-lookup"><span data-stu-id="71b89-150">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="71b89-151">選擇`Auto-apply a label`。</span><span class="sxs-lookup"><span data-stu-id="71b89-151">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="71b89-152">選擇`Choose a label to auto-apply`。</span><span class="sxs-lookup"><span data-stu-id="71b89-152">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="71b89-153">選擇`Create new labels`並建立標籤，以用於此測試。</span><span class="sxs-lookup"><span data-stu-id="71b89-153">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="71b89-154">當您執行此動作時`Retention` ，請將設定為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="71b89-154">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="71b89-155">您不想開啟任何保留或其他動作。</span><span class="sxs-lookup"><span data-stu-id="71b89-155">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="71b89-156">在此情況下，您只會使用保留標籤做為文字標籤，而不會強制執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="71b89-156">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="71b89-157">例如，您可以建立一個名為 "SourceCode 分類程式 test" 的保留標籤，但不會執行任何動作，然後將該保留標籤自動套用至來原始程式碼分類器為條件的內容。</span><span class="sxs-lookup"><span data-stu-id="71b89-157">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="71b89-158">若要深入瞭解建立保留標籤的詳細資訊，請參閱[保留標籤簡介](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="71b89-158">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="71b89-159">選擇`Auto-apply a label` [和`Choose a label to auto-apply`]。</span><span class="sxs-lookup"><span data-stu-id="71b89-159">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="71b89-160">若要深入瞭解使用條件自動套用標籤的詳細資訊，請參閱，[根據條件自動套用保留標籤原則](labels.md#applying-a-retention-label-automatically-based-on-conditions)。</span><span class="sxs-lookup"><span data-stu-id="71b89-160">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="71b89-161">從清單中選擇您的測試卷標`Next`，然後選擇 [。</span><span class="sxs-lookup"><span data-stu-id="71b89-161">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="71b89-162">選擇`Apply label to content that matches a trainable classifier`。</span><span class="sxs-lookup"><span data-stu-id="71b89-162">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![選取分類器做為條件](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="71b89-164">.</span><span class="sxs-lookup"><span data-stu-id="71b89-164">.</span></span>

10. <span data-ttu-id="71b89-165">在此情況下，從清單中選擇您的分類器`Source Code`</span><span class="sxs-lookup"><span data-stu-id="71b89-165">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="71b89-166">命名原則，例如「原始程式碼內建的分類程式測試」。</span><span class="sxs-lookup"><span data-stu-id="71b89-166">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="71b89-167">選擇`Let me choose specific locations`。</span><span class="sxs-lookup"><span data-stu-id="71b89-167">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="71b89-168">關閉除及選擇`SharePoint sites` `Choose sites`以外的所有位置。</span><span class="sxs-lookup"><span data-stu-id="71b89-168">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="71b89-169">輸入步驟2中之網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="71b89-169">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="71b89-170">完成該嚮導並選擇`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="71b89-170">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="71b89-171">將測試專案放入專用的 SharePoint 線上資料夾中。</span><span class="sxs-lookup"><span data-stu-id="71b89-171">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="71b89-172">允許套用標籤的小時數。</span><span class="sxs-lookup"><span data-stu-id="71b89-172">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="71b89-173">檢查標籤的檔內容，查看是否有分類程式包含與您預期的測試內容。</span><span class="sxs-lookup"><span data-stu-id="71b89-173">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="71b89-174">查看已標示的專案。</span><span class="sxs-lookup"><span data-stu-id="71b89-174">Review the items that were labeled.</span></span>

20. <span data-ttu-id="71b89-175">如果您已經完成測試，請刪除內容和標籤原則。</span><span class="sxs-lookup"><span data-stu-id="71b89-175">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="71b89-176">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="71b89-176">See also:</span></span>

- [<span data-ttu-id="71b89-177">開始使用可訓練的分類器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="71b89-177">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="71b89-178">保留標籤概觀</span><span class="sxs-lookup"><span data-stu-id="71b89-178">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="71b89-179">根據條件自動套用保留標籤原則</span><span class="sxs-lookup"><span data-stu-id="71b89-179">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
