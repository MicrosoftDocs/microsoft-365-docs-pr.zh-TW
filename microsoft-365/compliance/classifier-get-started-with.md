---
title: 開始使用可訓練的分類器 (預覽)
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。 本文說明如何建立及訓練自訂的分類器，以及如何重新導流以提高精確度。
ms.openlocfilehash: fd6bc68a8bc373d9d02e23b73971b28ce8761cd9
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132313"
---
# <a name="get-started-with-trainable-classifiers-preview"></a><span data-ttu-id="2bf44-104">開始使用可訓練的分類器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="2bf44-104">Get started with trainable classifiers (preview)</span></span>

<span data-ttu-id="2bf44-105">Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。</span><span class="sxs-lookup"><span data-stu-id="2bf44-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="2bf44-106">經過訓練之後，您可以使用它來識別應用 Office 敏感度標籤、通訊合規性原則及保留標籤原則的專案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="2bf44-107">建立自訂的 trainable 分類器優先于提供以人工方式挑選並正確符合類別的範例。</span><span class="sxs-lookup"><span data-stu-id="2bf44-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="2bf44-108">然後，在處理完這類功能之後，您可以透過提供正負樣本的混合來測試分類器的預測能力。</span><span class="sxs-lookup"><span data-stu-id="2bf44-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="2bf44-109">本文說明如何建立及訓練自訂的分類器，以及如何透過重新培訓，改善自訂 trainable 分類器和預先訓練的分類器的效能。</span><span class="sxs-lookup"><span data-stu-id="2bf44-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="2bf44-110">若要深入瞭解不同類型的分類器，請參閱 [瞭解如何 trainable 的分類器 (預覽) ](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf44-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bf44-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="2bf44-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="2bf44-112">授權需求</span><span class="sxs-lookup"><span data-stu-id="2bf44-112">Licensing requirements</span></span>

<span data-ttu-id="2bf44-113">分類器是 Microsoft 365 E5 或 E5 規範功能。</span><span class="sxs-lookup"><span data-stu-id="2bf44-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="2bf44-114">您必須具有這些訂閱中的其中一項，才能使用這些訂閱。</span><span class="sxs-lookup"><span data-stu-id="2bf44-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="2bf44-115">權限</span><span class="sxs-lookup"><span data-stu-id="2bf44-115">Permissions</span></span>

<span data-ttu-id="2bf44-116">在 UI 中存取分類器：</span><span class="sxs-lookup"><span data-stu-id="2bf44-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="2bf44-117">全域管理員需要加入宣告租使用者才能建立自訂分類器</span><span class="sxs-lookup"><span data-stu-id="2bf44-117">the Global admin needs to opt in for the tenant to create custom classifiers</span></span>
- <span data-ttu-id="2bf44-118">合規性管理員角色或符合性資料管理員是訓練分類器所需的</span><span class="sxs-lookup"><span data-stu-id="2bf44-118">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="2bf44-119">在下列情況下，您將需要具有這些許可權的帳戶才能使用分類器：</span><span class="sxs-lookup"><span data-stu-id="2bf44-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="2bf44-120">保留標籤原則案例：記錄管理和保留管理角色</span><span class="sxs-lookup"><span data-stu-id="2bf44-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="2bf44-121">敏感度標籤原則案例：安全性管理員、合規性管理員、規範資料管理員</span><span class="sxs-lookup"><span data-stu-id="2bf44-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="2bf44-122">通訊相容性原則案例：內幕人士風險管理管理員、主管審查管理員</span><span class="sxs-lookup"><span data-stu-id="2bf44-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2bf44-123">根據預設，只有建立自訂分類器的使用者可以訓練及審核該分類器所進行的預測。</span><span class="sxs-lookup"><span data-stu-id="2bf44-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="2bf44-124">如果您想要讓其他人訓練及審閱分類器預測，請參閱 [授與其他人訓練及審查許可權](#give-others-train-and-review-rights)。</span><span class="sxs-lookup"><span data-stu-id="2bf44-124">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](#give-others-train-and-review-rights).</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="2bf44-125">準備自訂 trainable 分類器</span><span class="sxs-lookup"><span data-stu-id="2bf44-125">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="2bf44-126">深入瞭解建立自訂 trainable 分類器之前，請先瞭解相關專案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-126">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="2bf44-127">時間表</span><span class="sxs-lookup"><span data-stu-id="2bf44-127">Timeline</span></span>

<span data-ttu-id="2bf44-128">此時程表會反映 trainable 分類器的範例部署。</span><span class="sxs-lookup"><span data-stu-id="2bf44-128">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-分類器-時程表](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="2bf44-130">Trainable 分類器第一次需要自願加入。</span><span class="sxs-lookup"><span data-stu-id="2bf44-130">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="2bf44-131">Microsoft 365 需要12天的時間來完成組織內容的基準評估。</span><span class="sxs-lookup"><span data-stu-id="2bf44-131">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="2bf44-132">請與您的全域系統管理員聯繫，以啟動自願加入處理常式。</span><span class="sxs-lookup"><span data-stu-id="2bf44-132">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="2bf44-133">整體工作流程</span><span class="sxs-lookup"><span data-stu-id="2bf44-133">Overall workflow</span></span>

<span data-ttu-id="2bf44-134">若要深入瞭解建立自訂 trainable 分類程式的整體工作流程，請參閱[建立客戶 trainable 分類](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)器的處理流程</span><span class="sxs-lookup"><span data-stu-id="2bf44-134">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span></span>

### <a name="seed-content"></a><span data-ttu-id="2bf44-135">Seed 內容</span><span class="sxs-lookup"><span data-stu-id="2bf44-135">Seed content</span></span>

<span data-ttu-id="2bf44-136">當您想要 trainable 的分類器獨立且準確地將專案識別為屬於特定類別的內容時，您必須先呈現該類別中內容類型的許多範例。</span><span class="sxs-lookup"><span data-stu-id="2bf44-136">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="2bf44-137">Trainable 分類器的此樣本饋送稱為「 *植*入」。</span><span class="sxs-lookup"><span data-stu-id="2bf44-137">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="2bf44-138">Seed content 是由人類選取，並會判斷代表內容的類別。</span><span class="sxs-lookup"><span data-stu-id="2bf44-138">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="2bf44-139">您必須具有至少50的肯定範例，以及多達500。</span><span class="sxs-lookup"><span data-stu-id="2bf44-139">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="2bf44-140">Trainable 分類程式會處理最多500最近建立的範例 (按檔建立的日期/時間戳記) 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-140">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="2bf44-141">您提供的範例越多，分類器所做的預測就越精確。</span><span class="sxs-lookup"><span data-stu-id="2bf44-141">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="2bf44-142">測試內容</span><span class="sxs-lookup"><span data-stu-id="2bf44-142">Testing content</span></span>

<span data-ttu-id="2bf44-143">Trainable 分類器處理足夠的肯定樣本來建立預測模型之後，您必須測試所做的預測，以查看分類器是否可以正確辨別與類別及專案不符的專案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-143">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="2bf44-144">若要這麼做，您可以將它放在另一個中，但願其包含的範例應屬於類別，而不是使用的範例。</span><span class="sxs-lookup"><span data-stu-id="2bf44-144">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="2bf44-145">一旦處理好，您就可以手動流覽結果，並確認每個預測是否正確、不正確或不確定。</span><span class="sxs-lookup"><span data-stu-id="2bf44-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="2bf44-146">Trainable 分類器使用這種意見反應來改善其預測模型。</span><span class="sxs-lookup"><span data-stu-id="2bf44-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="2bf44-147">為了獲得最佳結果，您的測試範例集合中至少有200個專案，且具有正值和負比對的均勻分佈。</span><span class="sxs-lookup"><span data-stu-id="2bf44-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="2bf44-148">如何建立 trainable 的分類器</span><span class="sxs-lookup"><span data-stu-id="2bf44-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="2bf44-149">在 50-500 seed content 專案之間收集。</span><span class="sxs-lookup"><span data-stu-id="2bf44-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="2bf44-150">這兩個範例都必須是強烈代表您想要讓 trainable 分類器正確識別為分類類別中的內容類型的範例。</span><span class="sxs-lookup"><span data-stu-id="2bf44-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="2bf44-151">如需支援的檔案類型，請參閱 [SharePoint Server 中的預設編目副檔名和分析檔案類型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bf44-152">Seed 及 test 範例專案不能加密，必須是英文。</span><span class="sxs-lookup"><span data-stu-id="2bf44-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bf44-153">請確定 seed 集合中的專案是類別的 **強** 範例。</span><span class="sxs-lookup"><span data-stu-id="2bf44-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="2bf44-154">Trainable 分類器最初會根據您植入的模型來建立模型。</span><span class="sxs-lookup"><span data-stu-id="2bf44-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="2bf44-155">分類器假設所有種子範例都是強陽性的，而且沒有任何方式知道樣本是否與類別弱或消極。</span><span class="sxs-lookup"><span data-stu-id="2bf44-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="2bf44-156">將 seed 內容放在專為 *只保留 seed 內容*的 SharePoint Online 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="2bf44-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="2bf44-157">請記下網站、文件庫和資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="2bf44-157">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="2bf44-158">如果您為種子資料建立新的網站和資料夾，至少要有一個小時的時間進行索引，才可建立會使用該植入資料的 trainable 分類器。</span><span class="sxs-lookup"><span data-stu-id="2bf44-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="2bf44-159">使用合規性管理員或安全性管理員角色存取及開啟**microsoft 365 規範中心**或**microsoft 365 安全中心**  >  **資料分類**，登入 Microsoft 365 合規性中心</span><span class="sxs-lookup"><span data-stu-id="2bf44-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="2bf44-160">選擇 [ **Trainable 類元** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2bf44-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="2bf44-161">選擇 [ **建立 trainable 的分類器**]。</span><span class="sxs-lookup"><span data-stu-id="2bf44-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="2bf44-162">填寫適當的值 `Name` ，以及 `Description` 您想要此 trainable 分類器識別之專案類別的欄位。</span><span class="sxs-lookup"><span data-stu-id="2bf44-162">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="2bf44-163">從步驟2挑選 seed 內容網站的 SharePoint 線上網站、程式庫和資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="2bf44-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="2bf44-164">選擇 `Add` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-164">Choose `Add`.</span></span>

8. <span data-ttu-id="2bf44-165">複查設定並選擇 `Create trainable classifier` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="2bf44-166">在24小時內，trainable 分類程式會處理 seed 資料，並建立預測模型。</span><span class="sxs-lookup"><span data-stu-id="2bf44-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="2bf44-167">分類器狀態是在 `In progress` 處理 seed 資料時。</span><span class="sxs-lookup"><span data-stu-id="2bf44-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="2bf44-168">當分類器完成處理 seed 資料時，狀態變更為 `Need test items` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="2bf44-169">您現在可以選擇分類器來查看 [詳細資料] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2bf44-169">You can now view the details page by choosing the classifier.</span></span>


![trainable 分類器準備好用於測試](../media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="2bf44-171">請至少收集200測試內容專案 (10000 最大) 以取得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="2bf44-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="2bf44-172">這些專案應該混合使用強陽性、強負片和有些專案，但其性質卻不明顯。</span><span class="sxs-lookup"><span data-stu-id="2bf44-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="2bf44-173">如需支援的檔案類型，請參閱 [SharePoint Server 中的預設編目副檔名和分析檔案類型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bf44-174">範例專案不能加密，必須是英文。</span><span class="sxs-lookup"><span data-stu-id="2bf44-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="2bf44-175">將測試內容放入專用於 *只保留測試內容*的 SharePoint Online 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="2bf44-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="2bf44-176">請記下 SharePoint 線上網站、文件庫和資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="2bf44-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="2bf44-177">如果您為測試資料建立新的網站和資料夾，至少要有一個小時的時間，才能建立會使用該植入資料的 trainable 分類程式。</span><span class="sxs-lookup"><span data-stu-id="2bf44-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="2bf44-178">選擇 `Add items to test` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="2bf44-179">從步驟12的測試內容網站，挑選 SharePoint 線上網站、程式庫和資料夾 URL。</span><span class="sxs-lookup"><span data-stu-id="2bf44-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="2bf44-180">選擇 `Add` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-180">Choose `Add`.</span></span>

15. <span data-ttu-id="2bf44-181">選擇 [完成] `Done` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="2bf44-182">您的 trainable 分類程式會需要長達一小時才能處理測試檔案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="2bf44-183">當 trainable 分類器完成處理測試檔案時，[詳細資料] 頁面上的狀態會變更為 `Ready to review` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="2bf44-184">如果您需要增加測試樣本大小，請選擇 `Add items to test` 並允許 trainable 的分類器處理其他專案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![準備好回顧螢幕擷取畫面](../media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="2bf44-186">選擇 [索引標籤 `Tested items to review` ] 以查看專案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="2bf44-187">Microsoft 365 一次會出現30個專案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="2bf44-188">請加以檢查，然後在方塊中 `We predict this item is "Relevant". Do you agree?` 選擇 [ `Yes` 或] 或] `No` `Not sure, skip to next item` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="2bf44-189">模型準確性會在每30個專案之後自動更新。</span><span class="sxs-lookup"><span data-stu-id="2bf44-189">Model accuracy is automatically updated after every 30 items.</span></span>

![[複查專案] 對話方塊](../media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="2bf44-191">回顧 *至少* 200 個專案。</span><span class="sxs-lookup"><span data-stu-id="2bf44-191">Review *at least* 200 items.</span></span> <span data-ttu-id="2bf44-192">當精確度分數穩定之後，[ **發行** ] 選項就會變成可用，分類程式的狀態將會說 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="2bf44-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

![精確度分數並準備發佈](../media/classifier-trainable-review-ready-to-publish.png)

20. <span data-ttu-id="2bf44-194">發佈分類器。</span><span class="sxs-lookup"><span data-stu-id="2bf44-194">Publish the classifier.</span></span>

21. <span data-ttu-id="2bf44-195">一旦發佈您的分類符，就會在[使用靈敏度標籤的 Office 自動標籤](apply-sensitivity-label-automatically.md)中提供條件，根據狀況和[通訊規範](communication-compliance.md)[自動套用保留標籤原則](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="2bf44-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>

## <a name="give-others-train-and-review-rights"></a><span data-ttu-id="2bf44-196">讓其他人訓練和審閱許可權</span><span class="sxs-lookup"><span data-stu-id="2bf44-196">Give others train and review rights</span></span>

<span data-ttu-id="2bf44-197">使用此程式可提供其他人訓練、審閱及調整自訂 trainable 分類器的許可權。</span><span class="sxs-lookup"><span data-stu-id="2bf44-197">Use this procedure to give others permissions to train, review and tune your custom trainable classifier.</span></span>  
 
1. <span data-ttu-id="2bf44-198">就像是分類器的建立者，全域系統管理員或 eDiscovery 系統管理員會使用 PowerShell，使用 [connect To Security & 規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true)中的程式來連接至規範中心。</span><span class="sxs-lookup"><span data-stu-id="2bf44-198">As the creator of the classifier, a global admin or eDiscovery admin connect to the Compliance center using PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span></span>
2. <span data-ttu-id="2bf44-199">執行此命令︰</span><span class="sxs-lookup"><span data-stu-id="2bf44-199">Run this command:</span></span>
```powershell
Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
```
<span data-ttu-id="2bf44-200">例如：`Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2bf44-200">For example: `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span></span>

<span data-ttu-id="2bf44-201">您可以多次執行此命令來新增多個使用者。</span><span class="sxs-lookup"><span data-stu-id="2bf44-201">You can run this command multiple times to add multiple users.</span></span> <span data-ttu-id="2bf44-202">請注意，您只能將 Exchange Online Protection (EOP) 角色群組和 Azure 角色群組。</span><span class="sxs-lookup"><span data-stu-id="2bf44-202">Note that you can only add Exchange Online Protection (EOP) Role Groups and not Azure Role Groups.</span></span>