---
title: 在高級電子檔探索中設定律師-用戶端許可權偵測
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用律師-用戶端許可權偵測模型，在查看高級 eDiscovery 案例中的內容時，使用具備許可權內容的機器學習式偵測。
ms.openlocfilehash: e8e64fac2994b515bf6bc582673fa7e47d427d02
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528388"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="d0dfb-103">在高級電子檔探索中設定律師-用戶端許可權偵測</span><span class="sxs-lookup"><span data-stu-id="d0dfb-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="d0dfb-104">任何 eDiscovery 程式的「檢查」階段中，主要和昂貴的層面都是查看檔中的許可權內容。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="d0dfb-105">Advanced eDiscovery 提供許可權內容的機器教學型偵測，以提高此程式的效率。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="d0dfb-106">這項功能稱為「*律師-用戶端許可權偵測*」。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="d0dfb-107">它的運作方式為何？</span><span class="sxs-lookup"><span data-stu-id="d0dfb-107">How does it work?</span></span>

<span data-ttu-id="d0dfb-108">當已啟用律師-用戶端許可權偵測時，當您分析審閱集中[的資料](analyzing-data-in-review-set.md)時，律師-用戶端許可權偵測模型會處理所有審閱集中的檔。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="d0dfb-109">模型會尋找兩件事：</span><span class="sxs-lookup"><span data-stu-id="d0dfb-109">The model looks for two things:</span></span>

- <span data-ttu-id="d0dfb-110">許可權內容–該模型使用電腦學習，判斷檔中包含法律性質內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="d0dfb-111">參與者–在設定律師-用戶端許可權偵測時，您必須提交組織的律師清單。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="d0dfb-112">然後，模型會比較檔的參與者清單與律師清單，以判斷檔是否至少有一個律師參與者。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="d0dfb-113">模型產生每個檔的下列三個屬性：</span><span class="sxs-lookup"><span data-stu-id="d0dfb-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="d0dfb-114">**AttorneyClientPrivilegeScore：** 檔本質上為法律檔的可能性。分數的值介於**0**與**1**之間。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="d0dfb-115">**HasAttorney：** 如果其中一位檔參與者已列在律師清單中，則此屬性會設為**true** ;否則值為**false**。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="d0dfb-116">如果您的組織未上傳律師清單，此值也會設定為**false** 。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="d0dfb-117">**IsPrivilege：** 如果**AttorneyClientPrivilegeScore**的值高於臨界值*或*檔有律師人員，則此屬性會設為**true** 。否則，此值會設為**false**。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="d0dfb-118">這些屬性（及其對應值）會新增至審閱集內檔的檔案中繼資料中，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="d0dfb-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![律師-檔中繼資料中顯示的用戶端許可權屬性](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="d0dfb-120">這三個屬性也可在審閱集中搜尋。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="d0dfb-121">如需詳細資訊，請參閱[查詢評審集中的資料](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="d0dfb-122">設定律師-用戶端許可權偵測模型</span><span class="sxs-lookup"><span data-stu-id="d0dfb-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="d0dfb-123">若要啟用律師-用戶端許可權偵測模型，您的組織必須將其開啟，然後上傳律師清單。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="d0dfb-124">步驟1：開啟律師-用戶端許可權偵測</span><span class="sxs-lookup"><span data-stu-id="d0dfb-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="d0dfb-125">您組織中的 eDiscovery 系統管理員（eDiscovery 管理員角色群組中的 eDiscovery 管理員子群組成員）的人員必須在您的高級 eDiscovery 案例中使用該模型。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="d0dfb-126">在安全性 & 規範中心內，移至**eDiscovery > Advanced ediscovery**。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="d0dfb-127">在 [ **Advanced eDiscovery** ] 首頁上，按一下 [**設定**] 方塊中的 [**設定全域分析設定**]。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![選取「設定實驗功能」](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="d0dfb-129">在 [**分析設定**] 索引標籤上，選取 [**管理律師-用戶端許可權] 設定**。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="d0dfb-130">在 [**律師-用戶端許可權**] 飛入頁面上，使用 [切換] 開啟功能，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="d0dfb-131">步驟2：上傳律師清單（選用）</span><span class="sxs-lookup"><span data-stu-id="d0dfb-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="d0dfb-132">若要充分利用律師-用戶端許可權偵測模型，並使用先前所**述的律師或**可能的**特權**偵測，我們建議您針對您的組織運作的律師和法務人員，上傳電子郵件地址清單。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="d0dfb-133">若要上傳律師清單以供律師-用戶端許可權偵測模型使用：</span><span class="sxs-lookup"><span data-stu-id="d0dfb-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="d0dfb-134">建立 .csv 檔案（沒有標頭列），並在不同的行新增每個適當人員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="d0dfb-135">將此檔案儲存到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="d0dfb-136">在 [ **Advanced eDiscovery**首頁] 的 [**設定**] 磚中，選取 [設定**實驗功能**]，然後選取 [**管理律師-用戶端許可權] 設定**。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="d0dfb-137">隨即會顯示 [**律師-用戶端許可權**] 頁面，且已開啟「**律師-用戶端」許可權偵測**切換功能。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![律師-用戶端許可權飛出頁面](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="d0dfb-139">選取 **[流覽]** ，然後尋找並選取您在步驟1中建立的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="d0dfb-140">選取 [**儲存**] 以上傳律師清單。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="d0dfb-141">使用律師-用戶端許可權偵測模型</span><span class="sxs-lookup"><span data-stu-id="d0dfb-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="d0dfb-142">請遵循本節中的步驟，針對審閱集中的檔使用律師-用戶端許可權偵測。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="d0dfb-143">步驟1：使用律師-用戶端許可權偵測模型建立智慧標籤群組</span><span class="sxs-lookup"><span data-stu-id="d0dfb-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="d0dfb-144">透過智慧標籤群組查看律師中的律師-用戶端許可權偵測的其中一個主要方式是使用智慧標籤群組。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="d0dfb-145">智慧標籤群組會指出律師費-用戶端許可權偵測的結果，並在智慧標籤群組中的標記旁邊以行顯示結果。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="d0dfb-146">這可讓您在檔檢查期間快速識別可能的許可權檔。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="d0dfb-147">此外，您也可以使用智慧標籤群組中的標記，將檔標記為特權或非特權。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="d0dfb-148">如需智慧標籤的相關資訊，請參閱[在 Advanced eDiscovery 中設定智慧標籤](smart-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="d0dfb-149">在包含您在步驟1中分析的檔的 [檢查] 集中，選取 [**管理複查集**]，然後選取 [**管理標記**]。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="d0dfb-150">在 [**標記**] 底下，選取 [**新增群組**] 旁邊的下拉式清單，然後選取 [**新增智慧標籤群組**]。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![選取「新增智慧標籤群組」](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="d0dfb-152">在 [**選擇智慧標籤的模型**] 頁面上，選擇 [按**律師-用戶端許可權**] 旁的 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="d0dfb-153">隨即會顯示名為「**律師-用戶端許可權**的標籤群組。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="d0dfb-154">它包含兩個子標記，其名稱為**正值**和**負值**，對應于模型所產生的可能結果。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![律師-用戶端許可權智慧標籤群組](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="d0dfb-156">請視需要重新命名標記群組和標記。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="d0dfb-157">例如，您可以將**肯定**重新命名為**特權**，將**負數**重新命名為**無許可權**。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="d0dfb-158">步驟2：分析複查集</span><span class="sxs-lookup"><span data-stu-id="d0dfb-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="d0dfb-159">當您分析審閱集中的檔時，也會執行律師-用戶端許可權偵測模型和對應的屬性（如[有何作用？](#how-does-it-work)將會新增至審閱集中的每個檔。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="d0dfb-160">如需分析「複查集中的資料」的詳細資訊，請參閱[在 Advanced eDiscovery 中分析複查集中的資料](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="d0dfb-161">步驟3：使用智慧標籤群組檢查許可權內容</span><span class="sxs-lookup"><span data-stu-id="d0dfb-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="d0dfb-162">分析複查集和設定智慧標籤之後，下一步是審閱檔。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="d0dfb-163">如果模型決定檔有潛在的許可權，則 [**標記] 面板**中對應的智慧標籤會指出由律師-用戶端許可權偵測所產生的下列結果：</span><span class="sxs-lookup"><span data-stu-id="d0dfb-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="d0dfb-164">如果檔中有可能是合法的內容，則會在對應的智慧標籤旁邊顯示標籤**legal 內容**（此例中為預設的**正**標籤）。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="d0dfb-165">如果檔有在您組織的律師清單中找到的參與者，則標籤**律師**會顯示在對應的智慧標籤旁邊（此例也是預設的**正**標籤）。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="d0dfb-166">如果檔中的內容可能是合法的 *，且*在律師清單中找到了參與者，則會顯示**法律內容**和**律師**標籤。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="d0dfb-167">如果模型決定檔不包含擁有法律性質的內容，或是未包含律師清單中的參與者，則 [標記] 面板中不會顯示任何標籤。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="d0dfb-168">例如，下列螢幕擷取畫面顯示兩份檔。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="d0dfb-169">第一個會包含有法律性質的內容，且具有在律師清單中找到的參與者。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="d0dfb-170">第二個包含不會顯示任何標籤，因此不會顯示任何標籤。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-170">The second contains neither and therefore doesn't display any labels.</span></span>

![使用律師和法律內容標籤的檔](../media/AeDTaggingPanelLegalContentAttorney.png)

![沒有任何標籤的檔](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="d0dfb-173">檢查檔是否包含許可權內容之後，您可以使用適當的標記來標記檔。</span><span class="sxs-lookup"><span data-stu-id="d0dfb-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
