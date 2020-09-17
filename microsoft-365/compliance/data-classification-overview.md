---
title: 開始使用資料分類
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 資料分類儀表板可讓您深入了解貴組織所發現及分類的敏感性資料。
ms.openlocfilehash: aff6d2c30fe8036448a8816426896f080b86b9e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948503"
---
# <a name="know-your-data---data-classification-overview"></a><span data-ttu-id="b48b8-103">了解您的資料 - 資料分類概觀</span><span class="sxs-lookup"><span data-stu-id="b48b8-103">Know your data - data classification overview</span></span>

<span data-ttu-id="b48b8-104">身為 Microsoft 365 系統管理員或合規性系統管理員，您可以評估並標記組織中的內容，以控制其目標位置、隨時隨地加以保護，並確保根據組織的需求來保存及刪除內容。</span><span class="sxs-lookup"><span data-stu-id="b48b8-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according to your organizations needs.</span></span> <span data-ttu-id="b48b8-105">您可以透過[敏感度標籤](sensitivity-labels.md)、[保留標籤](retention.md#retention-labels)和敏感性資訊類型分類來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b48b8-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](retention.md#retention-labels), and sensitive information type classification.</span></span> <span data-ttu-id="b48b8-106">執行探索、評估和標記有多種方法，但最後您可能會有大量以其中一個或兩個標籤標記及分類的文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b48b8-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large number of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="b48b8-107">套用保留標籤和敏感度標籤後，您會想要查看租用戶使用標籤的情況，以及對這些項目進行的動作。</span><span class="sxs-lookup"><span data-stu-id="b48b8-107">After you apply your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="b48b8-108">資料分類頁面可讓您了解此內容，具體如下：</span><span class="sxs-lookup"><span data-stu-id="b48b8-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="b48b8-109">已分類為敏感性資訊類型的項目數量，以及分類的名稱</span><span class="sxs-lookup"><span data-stu-id="b48b8-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="b48b8-110">Microsoft 365 和 Azure 資訊保護中已套用最高層級的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="b48b8-111">已套用最高層級的保留標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-111">the top applied retention labels</span></span>
- <span data-ttu-id="b48b8-112">使用者對敏感性內容所採取之活動的摘要</span><span class="sxs-lookup"><span data-stu-id="b48b8-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="b48b8-113">敏感性資料和保留資料的位置</span><span class="sxs-lookup"><span data-stu-id="b48b8-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="b48b8-114">您也可以在 [資料分類] 頁面上管理這些功能：</span><span class="sxs-lookup"><span data-stu-id="b48b8-114">You also manage these features on the data classification page:</span></span>
- [<span data-ttu-id="b48b8-115">可訓練分類器</span><span class="sxs-lookup"><span data-stu-id="b48b8-115">trainable classifiers</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="b48b8-116">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b48b8-116">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)

<span data-ttu-id="b48b8-117">您可以在 [Microsoft 365 合規性中心]\*\*\*\* 或 [Microsoft 365 安全性中心]\*\*\*\* > [分類]\*\*\*\* > [資料分析]\*\*\*\* 中找到資料分析。</span><span class="sxs-lookup"><span data-stu-id="b48b8-117">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

<span data-ttu-id="b48b8-118">觀看我們的資料分類功能影片。</span><span class="sxs-lookup"><span data-stu-id="b48b8-118">Take a video tour of our data classification features.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

<span data-ttu-id="b48b8-119">在您建立任何原則之前，資料分類將會掃描您的敏感性內容和標籤內容。</span><span class="sxs-lookup"><span data-stu-id="b48b8-119">Data classification will scan your sensitive content and labeled content before you create any policies.</span></span> <span data-ttu-id="b48b8-120">這稱為**零變更管理**。</span><span class="sxs-lookup"><span data-stu-id="b48b8-120">This is called **zero change management**.</span></span> <span data-ttu-id="b48b8-121">這可讓您查看所有保留和敏感度標籤對環境的影響，並協助您開始評估自己的保護和控管原則需求。</span><span class="sxs-lookup"><span data-stu-id="b48b8-121">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b48b8-122">必要條件</span><span class="sxs-lookup"><span data-stu-id="b48b8-122">Prerequisites</span></span>

<span data-ttu-id="b48b8-123">每個存取並使用資料分類的帳戶，都必須有從下列其中一個訂閱中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="b48b8-123">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="b48b8-124">Microsoft 365 (E5/A5)</span><span class="sxs-lookup"><span data-stu-id="b48b8-124">Microsoft 365 (E5/A5)</span></span>
- <span data-ttu-id="b48b8-125">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="b48b8-125">Office 365 (E5)</span></span>
- <span data-ttu-id="b48b8-126">進階合規性 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="b48b8-126">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="b48b8-127">進階威脅情報 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="b48b8-127">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="b48b8-128">權限</span><span class="sxs-lookup"><span data-stu-id="b48b8-128">Permissions</span></span>

 <span data-ttu-id="b48b8-129">若要存取 [資料分類頁面]，帳戶必須在其中任一角色或角色群組中獲派成員資格。</span><span class="sxs-lookup"><span data-stu-id="b48b8-129">In order to get access to the data classification page, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="b48b8-130">**Microsoft 365 角色群組**</span><span class="sxs-lookup"><span data-stu-id="b48b8-130">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="b48b8-131">全域管理員</span><span class="sxs-lookup"><span data-stu-id="b48b8-131">Global administrator</span></span>
- <span data-ttu-id="b48b8-132">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b48b8-132">Compliance administrator</span></span>
- <span data-ttu-id="b48b8-133">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b48b8-133">Security administrator</span></span>
- <span data-ttu-id="b48b8-134">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="b48b8-134">Compliance data administrator</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="b48b8-135">內容中最常使用的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b48b8-135">Sensitive information types used most in your content</span></span>

<span data-ttu-id="b48b8-136">Microsoft 365 隨附許多敏感性資訊類型的定義，例如包含社會安全號碼或信用卡號的項目。</span><span class="sxs-lookup"><span data-stu-id="b48b8-136">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="b48b8-137">如需有關敏感性資訊類型的詳細資訊，請參閱[敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="b48b8-137">For more information on sensitive information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="b48b8-138">敏感性資訊類型卡片會顯示貴組織中找到及套用標籤的最高敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b48b8-138">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![最高敏感性資訊類型](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="b48b8-140">若要找出任何指定分類類別中的項目數量，請將游標暫留在該類別的列上方。</span><span class="sxs-lookup"><span data-stu-id="b48b8-140">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![最高敏感性資訊類型暫留詳細資料](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="b48b8-142">如果卡片顯示「包含敏感性資訊的資料」訊息，</span><span class="sxs-lookup"><span data-stu-id="b48b8-142">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="b48b8-143">這表示貴組織沒有分類為敏感性資訊類型的項目，或沒有已編目的項目。</span><span class="sxs-lookup"><span data-stu-id="b48b8-143">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="b48b8-144">若要開始使用標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b48b8-144">To get started with labels, see:</span></span>
>- [<span data-ttu-id="b48b8-145">開始使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-145">Get started with sensitivity labels</span></span>](get-started-with-sensitivity-labels.md)
>- [<span data-ttu-id="b48b8-146">開始使用保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-146">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)
>- [<span data-ttu-id="b48b8-147">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="b48b8-147">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="b48b8-148">套用至內容的最高敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-148">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="b48b8-149">當您將敏感度標籤套用至 Microsoft 365 或 Azure 資訊保護 (AIP) 項目時，會發生兩件事：</span><span class="sxs-lookup"><span data-stu-id="b48b8-149">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="b48b8-150">指示貴組織項目值的標籤會嵌入至文件，並將隨文件移動</span><span class="sxs-lookup"><span data-stu-id="b48b8-150">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="b48b8-151">標籤的存在會啟用各種防護行為，例如強制浮水印或加密。</span><span class="sxs-lookup"><span data-stu-id="b48b8-151">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="b48b8-152">啟用端點保護後，您甚至可以防止項目離開組織控制。</span><span class="sxs-lookup"><span data-stu-id="b48b8-152">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="b48b8-153">如需敏感度標籤的詳細資訊，請參閱[了解敏感度標籤](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="b48b8-153">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="b48b8-154">SharePoint 和 OneDrive 中的檔案必須啟用敏感度標籤，以便在資料分類頁面中顯示對應資料。</span><span class="sxs-lookup"><span data-stu-id="b48b8-154">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="b48b8-155">如需詳細資訊，請參閱[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="b48b8-155">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="b48b8-156">敏感度標籤卡片會依敏感度等級顯示項目數量 (電子郵件或文件)。</span><span class="sxs-lookup"><span data-stu-id="b48b8-156">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![依敏感度標籤分類預留位置的內容細目螢幕擷取畫面](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="b48b8-158">如果您未建立或發佈任何敏感度標籤，或沒有套用敏感度標籤的內容，則此卡片會顯示「未偵測到敏感度標籤」訊息。</span><span class="sxs-lookup"><span data-stu-id="b48b8-158">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="b48b8-159">若要開始使用敏感度標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b48b8-159">To get started with sensitivity labels, see:</span></span>
>- <span data-ttu-id="b48b8-160">[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)或針對 AIP [設定 Azure 資訊保護原則](https://docs.microsoft.com/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="b48b8-160">[Get started with sensitivity labels](get-started-with-sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="b48b8-161">套用至內容的最高保留標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-161">Top retention labels applied to content</span></span>

<span data-ttu-id="b48b8-162">保留標籤用於管理組織中內容的保留和處置。</span><span class="sxs-lookup"><span data-stu-id="b48b8-162">Retention labels are used to manage the retention and disposition of content in your organization.</span></span> <span data-ttu-id="b48b8-163">套用後，可用於控制項目在刪除前的保留方式、是否應在刪除前檢閱、保留期間的到期時間，或是否應將項目標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="b48b8-163">When applied, they can be used to control how an item will be kept before deletion, whether it should be reviewed prior to deletion, when its retention period expires, and whether it should be marked as a record.</span></span> <span data-ttu-id="b48b8-164">如需詳細資訊，請參閱[瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="b48b8-164">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="b48b8-165">套用最高保留標籤的卡片會顯示具有指定保留標籤的項目數量。</span><span class="sxs-lookup"><span data-stu-id="b48b8-165">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![套用最高保留標籤預留位置的螢幕擷取畫面](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="b48b8-167">如果此卡片顯示 [未偵測到保留標籤] 訊息，則表示您未建立或發佈任何保留標籤，或沒有套用保留標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="b48b8-167">If this card displays the message, "No retention labels detected", it means you haven't created or published any retention labels or no content has had a retention label applied.</span></span> <span data-ttu-id="b48b8-168">若要開始使用保留標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b48b8-168">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="b48b8-169">開始使用保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-169">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)

## <a name="top-activities-detected"></a><span data-ttu-id="b48b8-170">偵測到的常見活動</span><span class="sxs-lookup"><span data-stu-id="b48b8-170">Top activities detected</span></span>

<span data-ttu-id="b48b8-171">此卡片可快速摘要顯示使用者對套用敏感性標籤的項目所採取的常見動作。</span><span class="sxs-lookup"><span data-stu-id="b48b8-171">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="b48b8-172">您可以使用[活動總管](data-classification-activity-explorer.md)，向下深入切入 Microsoft 365 在標籤內容和 Windows 10 端點內容上追蹤的八個不同活動。</span><span class="sxs-lookup"><span data-stu-id="b48b8-172">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="b48b8-173">若此卡片顯示「未偵測到活動」訊息，表示檔案沒有任何活動，或未開啟使用者與系統管理員稽核。</span><span class="sxs-lookup"><span data-stu-id="b48b8-173">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="b48b8-174">若要開啟稽核記錄，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b48b8-174">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="b48b8-175">在安全性與合規性中心搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="b48b8-175">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="b48b8-176">依位置套用敏感性標籤和保留標籤的資料</span><span class="sxs-lookup"><span data-stu-id="b48b8-176">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="b48b8-177">資料分類報告的重點是讓您了解具有標籤的項目數量、標籤類型和位置。</span><span class="sxs-lookup"><span data-stu-id="b48b8-177">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="b48b8-178">這些卡片可讓您了解 Exchange、SharePoint 和 OneDrive 等具有標籤的項目數量。</span><span class="sxs-lookup"><span data-stu-id="b48b8-178">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="b48b8-179">如果此卡片顯示「未偵測到位置」訊息，則表示您未建立或發佈任何敏感性標籤，或沒有套用保留標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="b48b8-179">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="b48b8-180">若要開始使用敏感度標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b48b8-180">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="b48b8-181">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-181">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="b48b8-182">請參閱</span><span class="sxs-lookup"><span data-stu-id="b48b8-182">See also</span></span>

- [<span data-ttu-id="b48b8-183">檢視標籤活動</span><span class="sxs-lookup"><span data-stu-id="b48b8-183">View label activity</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="b48b8-184">檢視已套用標籤的內容</span><span class="sxs-lookup"><span data-stu-id="b48b8-184">View labeled content</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="b48b8-185">了解敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-185">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="b48b8-186">瞭解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="b48b8-186">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="b48b8-187">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="b48b8-187">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="b48b8-188">開始使用可訓練的分類器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b48b8-188">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
