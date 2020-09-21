---
title: '如何在通訊合規性 (預覽中重新培訓分類器) '
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
description: 瞭解如何在通訊合規性中提供對 trainable 分類器的意見反應。
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132307"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a><span data-ttu-id="461cc-103">如何在通訊合規性 (預覽中重新培訓分類器) </span><span class="sxs-lookup"><span data-stu-id="461cc-103">How to retrain a classifier in communications compliance (preview)</span></span>

<span data-ttu-id="461cc-104">Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。</span><span class="sxs-lookup"><span data-stu-id="461cc-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="461cc-105">經過訓練之後，您可以使用它來識別應用 Office 敏感度標籤、通訊合規性原則及保留標籤原則的專案。</span><span class="sxs-lookup"><span data-stu-id="461cc-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="461cc-106">本文說明如何透過提供額外的意見反應，以改善自訂 trainable 分類器和部分預先訓練的分類器的效能。</span><span class="sxs-lookup"><span data-stu-id="461cc-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="461cc-107">若要深入瞭解不同類型的分類器，請參閱 [瞭解如何 trainable 的分類器 (預覽) ](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="461cc-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="461cc-108">權限</span><span class="sxs-lookup"><span data-stu-id="461cc-108">Permissions</span></span>

<span data-ttu-id="461cc-109">若要在 Microsoft 365 規範中心存取分類器：</span><span class="sxs-lookup"><span data-stu-id="461cc-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="461cc-110">合規性管理員角色或符合性資料管理員是訓練分類器所需的</span><span class="sxs-lookup"><span data-stu-id="461cc-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="461cc-111">在下列情況下，您將需要具有這些許可權的帳戶才能使用分類器：</span><span class="sxs-lookup"><span data-stu-id="461cc-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="461cc-112">通訊相容性原則案例：內幕人士風險管理管理員、主管審查管理員</span><span class="sxs-lookup"><span data-stu-id="461cc-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="461cc-113">整體工作流程</span><span class="sxs-lookup"><span data-stu-id="461cc-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="461cc-114">您可以在使用分類器做為條件的規範解決方案中提供意見反應。</span><span class="sxs-lookup"><span data-stu-id="461cc-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="461cc-115">**如果您沒有以分類器為條件的通訊相容性原則，請在這裡停用。**</span><span class="sxs-lookup"><span data-stu-id="461cc-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="461cc-116">當您使用分類器時，您可能會想要增加所進行之分類的精確度。</span><span class="sxs-lookup"><span data-stu-id="461cc-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="461cc-117">為此，您需要評估其所識別為符合或不符合專案之專案的分類品質。</span><span class="sxs-lookup"><span data-stu-id="461cc-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="461cc-118">在您對分類器進行30個評估之後，就會使用該意見反應，並自動 retrains 自身。</span><span class="sxs-lookup"><span data-stu-id="461cc-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="461cc-119">若要深入瞭解重新培訓分類器的整體工作流程，請參閱 [用於重新培訓分類器的處理](classifier-learn-about.md#retraining-classifiers)流程。</span><span class="sxs-lookup"><span data-stu-id="461cc-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="461cc-120">分類器必須已發佈且在使用之前才能 retrained。</span><span class="sxs-lookup"><span data-stu-id="461cc-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a><span data-ttu-id="461cc-121">如何在通訊相容性原則中重新培訓分類 (預覽) </span><span class="sxs-lookup"><span data-stu-id="461cc-121">How to retrain a classifier in communication compliance policies (preview)</span></span>

1. <span data-ttu-id="461cc-122">開啟以分類器為條件的通訊相容性原則，並從 [ **暫** 止] 清單中選擇一個已識別的專案。</span><span class="sxs-lookup"><span data-stu-id="461cc-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="461cc-123">選擇省略號並 **改進分類**。</span><span class="sxs-lookup"><span data-stu-id="461cc-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="461cc-124">在 [ **詳細意見** 反應] 窗格中，如果專案為 true，請選擇 [ **符合**]。</span><span class="sxs-lookup"><span data-stu-id="461cc-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="461cc-125">如果專案是誤報，表示它不正確地包含在類別中，請選擇 [ **不相符**]。</span><span class="sxs-lookup"><span data-stu-id="461cc-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="461cc-126">如果有其他的分類器更適合該專案，您可以從 [ **建議其他 trainable** 系系] 清單中加以選擇。</span><span class="sxs-lookup"><span data-stu-id="461cc-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="461cc-127">這會觸發其他分類器來評估專案。</span><span class="sxs-lookup"><span data-stu-id="461cc-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="461cc-128">您可以選擇所有專案，然後選擇 [在命令列中 **提供詳細資訊** ]，以同時提供多個專案的意見反應。</span><span class="sxs-lookup"><span data-stu-id="461cc-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="461cc-129">選擇 [ **傳送意見** 反應] 以傳送您的評價 `match` 、 `not a match` 分類及建議其他 trainable 的分類程式。</span><span class="sxs-lookup"><span data-stu-id="461cc-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="461cc-130">當您向分類器提供30個反應實例時，它會自動重新導流。</span><span class="sxs-lookup"><span data-stu-id="461cc-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="461cc-131">重新培訓可能需要1-4 小時。</span><span class="sxs-lookup"><span data-stu-id="461cc-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="461cc-132">分類器每日只能有兩次 retrained。</span><span class="sxs-lookup"><span data-stu-id="461cc-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="461cc-133">此資訊會前往您租使用者中的分類器， **不會傳回 Microsoft**。</span><span class="sxs-lookup"><span data-stu-id="461cc-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="461cc-134">開啟**Microsoft 365 規範中心**的 [**資料分類**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="461cc-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="461cc-135">開啟 \*\*Trainable 的分類 (預覽) \*\*。</span><span class="sxs-lookup"><span data-stu-id="461cc-135">Open **Trainable classifiers (preview)**.</span></span>
8. <span data-ttu-id="461cc-136">通訊合規性原則中使用的分類程式會出現在 [ **重新訓練** ] 標題下。</span><span class="sxs-lookup"><span data-stu-id="461cc-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![以重新培訓狀態分類的分類器](../media/classifier-retraining.png)

9. <span data-ttu-id="461cc-138">重新培訓完成後，請選擇分類器以開啟 [重新培訓一覽表]。</span><span class="sxs-lookup"><span data-stu-id="461cc-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分類器重新培訓結果概述](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="461cc-140">查看建議的動作，以及 retrained 及目前發佈之版本的分類器的預測比較。</span><span class="sxs-lookup"><span data-stu-id="461cc-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="461cc-141">如果您已滿意重新培訓的結果，請選擇 [ **重新發佈**]。</span><span class="sxs-lookup"><span data-stu-id="461cc-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="461cc-142">如果您不滿意重新培訓的結果，您可以選擇在通訊規範介面中為分類器提供額外的意見反應，並開始另一種重新培訓週期; 或者，在這種情況下，將繼續使用分類器目前發行的版本。</span><span class="sxs-lookup"><span data-stu-id="461cc-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="461cc-143">重新發佈建議的詳細資料</span><span class="sxs-lookup"><span data-stu-id="461cc-143">Details on republishing recommendations</span></span>

<span data-ttu-id="461cc-144">以下是關於如何提出建議以重新發佈 retrained 分類器或建議進一步重新培訓的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="461cc-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="461cc-145">這需要稍微深入瞭解 trainable 的分類器的運作方式。</span><span class="sxs-lookup"><span data-stu-id="461cc-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="461cc-146">在重新導流之後，我們會使用意見反應，以及原來用於訓練分類器的任何專案，來評估分類程式的效能。</span><span class="sxs-lookup"><span data-stu-id="461cc-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="461cc-147">針對內建模型，用來訓練分類器的專案是 Microsoft 用來建立模型的專案。</span><span class="sxs-lookup"><span data-stu-id="461cc-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="461cc-148">針對自訂模型，在原始訓練中使用的專案分類器來自您已新增以進行測試及檢查的網站。</span><span class="sxs-lookup"><span data-stu-id="461cc-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="461cc-149">我們比較 retrained 和發行的分類器之兩組專案的效能值，以提供是否有改進重新發佈的建議。</span><span class="sxs-lookup"><span data-stu-id="461cc-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="461cc-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="461cc-150">See also</span></span>

- [<span data-ttu-id="461cc-151">深入瞭解 trainable 的分類器 (預覽) </span><span class="sxs-lookup"><span data-stu-id="461cc-151">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="461cc-152">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="461cc-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
