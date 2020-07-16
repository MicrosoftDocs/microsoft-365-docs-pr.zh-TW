---
title: 使用保留標籤測試內建的分類器（預覽）
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
ms.openlocfilehash: 1d645cc79075c41ce94b0f9b4fc347450a8df8c6
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146217"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a><span data-ttu-id="311cc-104">使用保留標籤測試內建的分類器（預覽）</span><span class="sxs-lookup"><span data-stu-id="311cc-104">Testing built-in classifiers using retention labels (preview)</span></span>

<span data-ttu-id="311cc-105">Microsoft 已訓練及測試五個分類器，可協助識別特定的內容類別別。</span><span class="sxs-lookup"><span data-stu-id="311cc-105">Microsoft has trained and tested five classifiers which can help to identify certain categories of content.</span></span> <span data-ttu-id="311cc-106">這些分類器預設會顯示在 `Ready to use` 群組中，並使用大量的範例資料集進行訓練。</span><span class="sxs-lookup"><span data-stu-id="311cc-106">These classifiers show up in the `Ready to use` group by default and were trained using very large sample data sets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="311cc-107">在您的分類和標籤工作流程中使用內建的分類器之前，您應該針對組織內容的範例進行測試，以確認類別的分類預測符合您的預期。</span><span class="sxs-lookup"><span data-stu-id="311cc-107">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

<span data-ttu-id="311cc-108">如需 trainable 的分類器的詳細資訊，請參閱[trainable 分類器（預覽）快速](classifier-getting-started-with.md)入門。</span><span class="sxs-lookup"><span data-stu-id="311cc-108">For more information on trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="311cc-109">Microsoft 365 隨附了五個建議的內建分類器：</span><span class="sxs-lookup"><span data-stu-id="311cc-109">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="311cc-110">我們正在淘汰 [粗穢言語]\*\*\*\* 內建分類器，因為這個分類器產生了大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="311cc-110">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="311cc-111">請勿使用它，如果您目前使用它，您應該將商務程式移出它。</span><span class="sxs-lookup"><span data-stu-id="311cc-111">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="311cc-112">建議您改為使用**威脅**、**猥褻**和**騷擾**內建的分類符。</span><span class="sxs-lookup"><span data-stu-id="311cc-112">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="311cc-113">**簡歷**：偵測屬於申請人個人、教育、專業資格、工作經驗及其他個人識別資訊的文字帳戶的專案</span><span class="sxs-lookup"><span data-stu-id="311cc-113">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="311cc-114">**原始程式碼**：偵測包含一組指令和語句的專案，這些專案是以前25種使用的電腦程式設計語言所撰寫的 GitHub</span><span class="sxs-lookup"><span data-stu-id="311cc-114">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="311cc-115">**語言名稱**</span><span class="sxs-lookup"><span data-stu-id="311cc-115">**Language Name**</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="311cc-116">ActionScript</span><span class="sxs-lookup"><span data-stu-id="311cc-116">ActionScript</span></span>|<span data-ttu-id="311cc-117">C</span><span class="sxs-lookup"><span data-stu-id="311cc-117">C</span></span>        |<span data-ttu-id="311cc-118">C#</span><span class="sxs-lookup"><span data-stu-id="311cc-118">C#</span></span>       |<span data-ttu-id="311cc-119">C++</span><span class="sxs-lookup"><span data-stu-id="311cc-119">C++</span></span>     |<span data-ttu-id="311cc-120">Clojure</span><span class="sxs-lookup"><span data-stu-id="311cc-120">Clojure</span></span>  |
  |<span data-ttu-id="311cc-121">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="311cc-121">CoffeeScript</span></span>|<span data-ttu-id="311cc-122">Css</span><span class="sxs-lookup"><span data-stu-id="311cc-122">CSS</span></span>     |<span data-ttu-id="311cc-123">移至</span><span class="sxs-lookup"><span data-stu-id="311cc-123">Go</span></span>       |<span data-ttu-id="311cc-124">Haskell</span><span class="sxs-lookup"><span data-stu-id="311cc-124">Haskell</span></span> |<span data-ttu-id="311cc-125">HTML</span><span class="sxs-lookup"><span data-stu-id="311cc-125">HTML</span></span>     |
  |<span data-ttu-id="311cc-126">JAVA</span><span class="sxs-lookup"><span data-stu-id="311cc-126">Java</span></span>     |<span data-ttu-id="311cc-127">JavaScript</span><span class="sxs-lookup"><span data-stu-id="311cc-127">JavaScript</span></span>|<span data-ttu-id="311cc-128">Lua</span><span class="sxs-lookup"><span data-stu-id="311cc-128">Lua</span></span>      |<span data-ttu-id="311cc-129">Matlab</span><span class="sxs-lookup"><span data-stu-id="311cc-129">MATLAB</span></span>   |<span data-ttu-id="311cc-130">目標-C</span><span class="sxs-lookup"><span data-stu-id="311cc-130">Objective-C</span></span>|
  |<span data-ttu-id="311cc-131">Perl</span><span class="sxs-lookup"><span data-stu-id="311cc-131">Perl</span></span>     |<span data-ttu-id="311cc-132">Php</span><span class="sxs-lookup"><span data-stu-id="311cc-132">PHP</span></span>      |<span data-ttu-id="311cc-133">Python</span><span class="sxs-lookup"><span data-stu-id="311cc-133">Python</span></span>   |<span data-ttu-id="311cc-134">R</span><span class="sxs-lookup"><span data-stu-id="311cc-134">R</span></span>        |<span data-ttu-id="311cc-135">紅寶石</span><span class="sxs-lookup"><span data-stu-id="311cc-135">Ruby</span></span>     |
  |<span data-ttu-id="311cc-136">Scala</span><span class="sxs-lookup"><span data-stu-id="311cc-136">Scala</span></span>    |<span data-ttu-id="311cc-137">命令介面</span><span class="sxs-lookup"><span data-stu-id="311cc-137">Shell</span></span>    |<span data-ttu-id="311cc-138">迅速</span><span class="sxs-lookup"><span data-stu-id="311cc-138">Swift</span></span>    |<span data-ttu-id="311cc-139">Tex</span><span class="sxs-lookup"><span data-stu-id="311cc-139">Tex</span></span>      |<span data-ttu-id="311cc-140">Vim 腳本</span><span class="sxs-lookup"><span data-stu-id="311cc-140">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="311cc-141">原始程式碼經過訓練，可在大量文字是原始程式碼時進行偵測。</span><span class="sxs-lookup"><span data-stu-id="311cc-141">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="311cc-142">它不會偵測到以純文字交錯的原始程式碼文字。</span><span class="sxs-lookup"><span data-stu-id="311cc-142">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="311cc-143">**騷擾**：偵測特定類別的冒犯性語言的文字專案，這些專案會根據下列特性，針對一或多個個人設定相關的冒犯性語言：種族、ethnicity、宗教、本國原產地、性別、性方向、年齡、傷殘</span><span class="sxs-lookup"><span data-stu-id="311cc-143">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="311cc-144">**猥褻**語言：偵測特定類別的冒犯性語言的文字專案，包含 embarrass 大部分人員的運算式</span><span class="sxs-lookup"><span data-stu-id="311cc-144">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="311cc-145">**威脅**：偵測特定類別的冒犯性語言的文字專案與威脅以認可暴力或對人員或財產造成實體損毀或損毀的威脅</span><span class="sxs-lookup"><span data-stu-id="311cc-145">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

> [!IMPORTANT]
> <span data-ttu-id="311cc-146">請注意，冒犯性語言、騷擾、猥褻和威脅分類器只會使用可搜尋文字，並非完整或完整。</span><span class="sxs-lookup"><span data-stu-id="311cc-146">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="311cc-147">此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新這些分類器的權利。</span><span class="sxs-lookup"><span data-stu-id="311cc-147">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="311cc-148">雖然分類程式可協助您的組織監控冒犯性和其他語言，但分類程式不會解決這類語言的影響，而且不是為了提供組織的唯一監視或回應這類語言的使用方式。</span><span class="sxs-lookup"><span data-stu-id="311cc-148">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="311cc-149">您的組織，而不是 Microsoft 或其子公司，仍然負責所有與監控、強制執行、封鎖、移除及保留預先訓練的分類器所識別的內容相關的決策。</span><span class="sxs-lookup"><span data-stu-id="311cc-149">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a><span data-ttu-id="311cc-150">如何確認內建的分類器符合您的需求</span><span class="sxs-lookup"><span data-stu-id="311cc-150">How to verify that a built-in classifier will meet your needs</span></span>

1. <span data-ttu-id="311cc-151">收集您認為屬於內建分類器（肯定比對）類別的可處置內容專案，以及您要測試之類別中不應該包含的專案（負數相符）。</span><span class="sxs-lookup"><span data-stu-id="311cc-151">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="311cc-152">範例專案不能加密，必須是英文。</span><span class="sxs-lookup"><span data-stu-id="311cc-152">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="311cc-153">建立專用的 SharePoint 線上資料夾;至少等候一個小時的資料夾新增至搜尋索引。</span><span class="sxs-lookup"><span data-stu-id="311cc-153">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="311cc-154">請記下資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="311cc-154">Make note of the folder URL.</span></span>

3. <span data-ttu-id="311cc-155">使用合規性管理員或安全性系統管理員角色存取，登入 microsoft 365 合規性中心，並開啟**microsoft 365 規範中心**  >  **記錄管理（預覽）**  >  **標籤原則] 索引標籤**。</span><span class="sxs-lookup"><span data-stu-id="311cc-155">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="311cc-156">選擇 `Auto-apply a label` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-156">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="311cc-157">選擇 `Choose a label to auto-apply` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-157">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="311cc-158">選擇 `Create new labels` 並建立標籤，以用於此測試。</span><span class="sxs-lookup"><span data-stu-id="311cc-158">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="311cc-159">當您執行此動作時，請 `Retention` 將設定為 `off` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-159">When you do this, leave `Retention` set to `off`.</span></span> <span data-ttu-id="311cc-160">您不想開啟任何保留或其他動作。</span><span class="sxs-lookup"><span data-stu-id="311cc-160">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="311cc-161">在此情況下，您只會使用保留標籤做為文字標籤，而不會強制執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="311cc-161">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="311cc-162">例如，您可以建立一個名為 "SourceCode 分類程式 test" 的保留標籤，但不會執行任何動作，然後將該保留標籤自動套用至來原始程式碼分類器為條件的內容。</span><span class="sxs-lookup"><span data-stu-id="311cc-162">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="311cc-163">若要深入瞭解保留標籤，請參閱[瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="311cc-163">To learn more about retention labels, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
7. <span data-ttu-id="311cc-164">選擇 [ `Auto-apply a label` 和] `Choose a label to auto-apply` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-164">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="311cc-165">若要深入瞭解使用條件自動套用標籤的詳細資訊，請參閱，設定[自動套用保留標籤的條件](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="311cc-165">To learn more about using condition based auto-apply a label see, [Configuring conditions for auto-apply retention labels](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels).</span></span>

8. <span data-ttu-id="311cc-166">從清單中選擇您的測試卷標，然後選擇 [ `Next` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-166">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="311cc-167">選擇 `Apply label to content that matches a trainable classifier` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-167">Choose `Apply label to content that matches a trainable classifier`.</span></span>

   ![選取分類器做為條件](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. <span data-ttu-id="311cc-169">在此情況下，從清單中選擇您的分類器`Source Code`</span><span class="sxs-lookup"><span data-stu-id="311cc-169">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="311cc-170">命名原則，例如「原始程式碼內建的分類程式測試」。</span><span class="sxs-lookup"><span data-stu-id="311cc-170">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="311cc-171">選擇 `Let me choose specific locations` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-171">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="311cc-172">關閉除 `SharePoint sites` 及選擇以外的所有位置 `Choose sites` 。</span><span class="sxs-lookup"><span data-stu-id="311cc-172">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="311cc-173">輸入步驟2中之網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="311cc-173">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="311cc-174">完成該嚮導並選擇`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="311cc-174">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="311cc-175">將測試專案放入專用的 SharePoint 線上資料夾中。</span><span class="sxs-lookup"><span data-stu-id="311cc-175">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="311cc-176">允許套用標籤的小時數。</span><span class="sxs-lookup"><span data-stu-id="311cc-176">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="311cc-177">檢查標籤的檔內容，查看是否有分類程式包含與您預期的測試內容。</span><span class="sxs-lookup"><span data-stu-id="311cc-177">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="311cc-178">查看已標示的專案。</span><span class="sxs-lookup"><span data-stu-id="311cc-178">Review the items that were labeled.</span></span>

20. <span data-ttu-id="311cc-179">如果您已經完成測試，請刪除內容和標籤原則。</span><span class="sxs-lookup"><span data-stu-id="311cc-179">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="311cc-180">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="311cc-180">See also:</span></span>

- [<span data-ttu-id="311cc-181">開始使用可訓練的分類器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="311cc-181">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="311cc-182">瞭解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="311cc-182">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="311cc-183">自動將保留標籤套用保留或刪除內容</span><span class="sxs-lookup"><span data-stu-id="311cc-183">Automatically apply a retention label to retain or delete content</span></span>](apply-retention-labels-automatically.md)
