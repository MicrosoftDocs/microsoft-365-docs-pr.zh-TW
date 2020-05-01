---
title: 開始使用資料分類 (預覽)
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
ms.openlocfilehash: 15beb3c0716aeb780fb3bfed3b3a8fa74557574d
ms.sourcegitcommit: fa6a1e432747e150df945050a3744b4408ceb2d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "43957273"
---
# <a name="know-your-data---data-classification-overview-preview"></a><span data-ttu-id="35810-103">了解您的資料 - 資料分類概觀 (預覽)</span><span class="sxs-lookup"><span data-stu-id="35810-103">Know your data - data classification overview (preview)</span></span>

<span data-ttu-id="35810-104">身為 Microsoft 365 系統管理員或合規性系統管理員，您可以評估並標記貴組織的內容，以控制其目標位置、隨時隨地加以保護，並確保根據貴組織的需求來保存及刪除內容。</span><span class="sxs-lookup"><span data-stu-id="35810-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="35810-105">您可以透過[敏感度標籤](sensitivity-labels.md)、[保留標籤](labels.md)和敏感性資訊類型分類來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="35810-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](labels.md), and sensitive information type classification.</span></span> <span data-ttu-id="35810-106">執行探索、評估和標記有多種方法，但最後您可能會有大量以其中一個或兩個標籤標記及分類的文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="35810-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large numbers of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="35810-107">套用保留標籤和敏感度標籤後，您會想要查看租用戶使用標籤的情況，以及對這些項目進行的動作。</span><span class="sxs-lookup"><span data-stu-id="35810-107">After you apply  your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="35810-108">資料分類頁面可讓您了解此內容，具體如下：</span><span class="sxs-lookup"><span data-stu-id="35810-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="35810-109">已分類為敏感性資訊類型的項目數量，以及分類的名稱</span><span class="sxs-lookup"><span data-stu-id="35810-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="35810-110">Microsoft 365 和 Azure 資訊保護中已套用最高層級的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="35810-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="35810-111">已套用最高層級的保留標籤</span><span class="sxs-lookup"><span data-stu-id="35810-111">the top applied retention labels</span></span>
- <span data-ttu-id="35810-112">使用者對敏感性內容所採取之活動的摘要</span><span class="sxs-lookup"><span data-stu-id="35810-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="35810-113">敏感性資料和保留資料的位置</span><span class="sxs-lookup"><span data-stu-id="35810-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="35810-114">您可以在 **Microsoft 365 合規性中心**或 **Microsoft 365 安全性中心** > **[分類]** > **[資料分析]** 中找到資料分析。</span><span class="sxs-lookup"><span data-stu-id="35810-114">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="35810-115">內容中最常使用的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="35810-115">Sensitive information types used most in your content</span></span>

<span data-ttu-id="35810-116">Microsoft 365 隨附許多敏感性資訊類型的定義，例如包含社會安全號碼或信用卡號的項目。</span><span class="sxs-lookup"><span data-stu-id="35810-116">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="35810-117">如需有關敏感性資訊類型的詳細資訊，請參閱[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="35810-117">For more information on sensitive information types, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="35810-118">敏感性資訊類型卡片會顯示貴組織中找到及套用標籤的最高敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="35810-118">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![最高敏感性資訊類型](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="35810-120">若要找出任何指定分類類別中的項目數量，請將游標暫留在該類別的列上方。</span><span class="sxs-lookup"><span data-stu-id="35810-120">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![最高敏感性資訊類型暫留詳細資料](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="35810-122">如果卡片顯示「包含敏感性資訊的資料」訊息，</span><span class="sxs-lookup"><span data-stu-id="35810-122">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="35810-123">這表示貴組織沒有分類為敏感性資訊類型的項目，或沒有已編目的項目。</span><span class="sxs-lookup"><span data-stu-id="35810-123">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="35810-124">若要開始使用標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="35810-124">To get started with labels, see:</span></span>
>- [<span data-ttu-id="35810-125">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="35810-125">Sensitivity labels</span></span>](sensitivity-labels.md)
>- [<span data-ttu-id="35810-126">保留標籤</span><span class="sxs-lookup"><span data-stu-id="35810-126">Retention labels</span></span>](labels.md)
>- [<span data-ttu-id="35810-127">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="35810-127">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="35810-128">套用至內容的最高敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="35810-128">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="35810-129">當您將敏感度標籤套用至 Microsoft 365 或 Azure 資訊保護 (AIP) 項目時，會發生兩件事：</span><span class="sxs-lookup"><span data-stu-id="35810-129">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="35810-130">指示貴組織項目值的標籤會嵌入至文件，並將隨文件移動</span><span class="sxs-lookup"><span data-stu-id="35810-130">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="35810-131">標籤的存在會啟用各種防護行為，例如強制浮水印或加密。</span><span class="sxs-lookup"><span data-stu-id="35810-131">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="35810-132">啟用端點保護後，您甚至可以防止項目離開組織控制。</span><span class="sxs-lookup"><span data-stu-id="35810-132">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="35810-133">如需敏感度標籤的詳細資訊，請參閱[了解敏感度標籤](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="35810-133">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="35810-134">SharePoint 和 OneDrive 中的檔案必須啟用敏感度標籤，以便在資料分類頁面中顯示對應資料。</span><span class="sxs-lookup"><span data-stu-id="35810-134">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="35810-135">如需詳細資訊，請參閱[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="35810-135">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="35810-136">敏感度標籤卡片會依敏感度等級顯示項目數量 (電子郵件或文件)。</span><span class="sxs-lookup"><span data-stu-id="35810-136">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![依敏感度標籤分類預留位置的內容細目螢幕擷取畫面](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="35810-138">如果您未建立或發佈任何敏感度標籤，或沒有套用敏感度標籤的內容，則此卡片會顯示「未偵測到敏感度標籤」訊息。</span><span class="sxs-lookup"><span data-stu-id="35810-138">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="35810-139">若要開始使用標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="35810-139">To get started with labels, see:</span></span>
>- <span data-ttu-id="35810-140">[敏感度標籤](sensitivity-labels.md)或針對 AIP [設定 Azure 資訊保護原則](https://docs.microsoft.com/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="35810-140">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="35810-141">套用至內容的最高保留標籤</span><span class="sxs-lookup"><span data-stu-id="35810-141">Top retention labels applied to content</span></span>

<span data-ttu-id="35810-142">保留標籤是用於管理貴組織內容的處置。</span><span class="sxs-lookup"><span data-stu-id="35810-142">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="35810-143">套用時，可用於控制文件在刪除前保留的時間、是否在刪除前檢閱、保留期間到期的時間，或是否應將文件標示為永遠不能刪除的記錄。</span><span class="sxs-lookup"><span data-stu-id="35810-143">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="35810-144">如需詳細資訊，請參閱[保留標籤概觀](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="35810-144">For more information see, [Overview of retention labels](labels.md).</span></span>

<span data-ttu-id="35810-145">套用最高保留標籤的卡片會顯示具有指定保留標籤的項目數量。</span><span class="sxs-lookup"><span data-stu-id="35810-145">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![套用最高保留標籤預留位置的螢幕擷取畫面](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="35810-147">如果此卡片顯示「未偵測到保留標籤」訊息，則表示您未建立或發佈任何保留標籤，或沒有套用保留標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="35810-147">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="35810-148">若要開始使用保留標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="35810-148">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="35810-149">保留標籤概觀</span><span class="sxs-lookup"><span data-stu-id="35810-149">Overview of retention labels</span></span>](labels.md)

## <a name="top-activities-detected"></a><span data-ttu-id="35810-150">偵測到的常見活動</span><span class="sxs-lookup"><span data-stu-id="35810-150">Top activities detected</span></span>

<span data-ttu-id="35810-151">此卡片可快速摘要顯示使用者對套用敏感性標籤的項目所採取的常見動作。</span><span class="sxs-lookup"><span data-stu-id="35810-151">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="35810-152">您可以使用[活動總管](data-classification-activity-explorer.md)，向下深入切入 Microsoft 365 在標籤內容和 Windows 10 端點內容上追蹤的八個不同活動。</span><span class="sxs-lookup"><span data-stu-id="35810-152">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="35810-153">若此卡片顯示「未偵測到活動」訊息，表示檔案沒有任何活動，或未開啟使用者與系統管理員稽核。</span><span class="sxs-lookup"><span data-stu-id="35810-153">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="35810-154">若要開啟稽核記錄，請參閱：</span><span class="sxs-lookup"><span data-stu-id="35810-154">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="35810-155">在安全性與合規性中心搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="35810-155">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="35810-156">依位置套用敏感性標籤和保留標籤的資料</span><span class="sxs-lookup"><span data-stu-id="35810-156">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="35810-157">資料分類報告的重點是讓您了解具有標籤的項目數量、標籤類型和位置。</span><span class="sxs-lookup"><span data-stu-id="35810-157">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="35810-158">這些卡片可讓您了解 Exchange、SharePoint 和 OneDrive 等具有標籤的項目數量。</span><span class="sxs-lookup"><span data-stu-id="35810-158">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="35810-159">如果此卡片顯示「未偵測到位置」訊息，則表示您未建立或發佈任何敏感性標籤，或沒有套用保留標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="35810-159">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="35810-160">若要開始使用敏感度標籤，請參閱：</span><span class="sxs-lookup"><span data-stu-id="35810-160">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="35810-161">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="35810-161">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="35810-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="35810-162">See also</span></span>

- [<span data-ttu-id="35810-163">查看標籤活動 (預覽)</span><span class="sxs-lookup"><span data-stu-id="35810-163">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="35810-164">檢視已套用標籤的內容 (預覽)</span><span class="sxs-lookup"><span data-stu-id="35810-164">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="35810-165">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="35810-165">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="35810-166">保留標籤</span><span class="sxs-lookup"><span data-stu-id="35810-166">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="35810-167">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="35810-167">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="35810-168">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="35810-168">Overview of retention policies</span></span>](retention-policies.md)
