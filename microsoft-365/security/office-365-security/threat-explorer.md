---
title: 威脅瀏覽器和即時偵測
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在安全性與合規性中心使用 Explorer 和即時偵測， &amp; 以有效地調查和回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 810b5c99aa239f295fd930c1d13a6a817012b18b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245561"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="ac167-103">威脅瀏覽器和即時偵測</span><span class="sxs-lookup"><span data-stu-id="ac167-103">Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="ac167-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="ac167-104">**Applies to**</span></span>
- [<span data-ttu-id="ac167-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="ac167-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ac167-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac167-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ac167-107">如果您的組織有 [Office 365 的 Microsoft Defender](defender-for-office-365.md)，而且您具有 [必要的許可權](#required-licenses-and-permissions)，您就會有 **瀏覽器** 或 **即時** 偵測 (以前的 *即時報告*-[請參閱「新增功能](#new-features-in-threat-explorer-and-real-time-detections)！ ) 」。</span><span class="sxs-lookup"><span data-stu-id="ac167-107">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="ac167-108">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="ac167-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="ac167-109">使用 Microsoft Defender Office 365 方案2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="ac167-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="ac167-110">使用 Microsoft Defender Office 365 方案1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="ac167-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="ac167-113">瀏覽器或即時偵測可協助您的安全性作業小組調查並有效地回應威脅。</span><span class="sxs-lookup"><span data-stu-id="ac167-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="ac167-114">報告類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="ac167-114">The report resembles the following image:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="ac167-116">您可以使用此報告：</span><span class="sxs-lookup"><span data-stu-id="ac167-116">With this report, you can:</span></span>

- [<span data-ttu-id="ac167-117">查看 Microsoft 365 安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="ac167-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="ac167-118">[查看網路釣魚 URL，然後按一下 [已判定資料]](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="ac167-118">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- <span data-ttu-id="ac167-119">[從瀏覽器的視圖中啟動自動調查和回應](#start-automated-investigation-and-response)程式 (Office 365 僅限方案 2) </span><span class="sxs-lookup"><span data-stu-id="ac167-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="ac167-120">調查惡意電子郵件及其他</span><span class="sxs-lookup"><span data-stu-id="ac167-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="ac167-121">威脅搜尋體驗的增強功能</span><span class="sxs-lookup"><span data-stu-id="ac167-121">Improvements to Threat Hunting Experience</span></span>

### <a name="introduction-of-alert-id-for-mdo-alerts-within-explorerreal-time-detections-preview"></a><span data-ttu-id="ac167-122">Explorer/即時偵測內 MDO 警示的警示識別碼簡介 (預覽) </span><span class="sxs-lookup"><span data-stu-id="ac167-122">Introduction of Alert ID for MDO alerts within Explorer/Real-time detections (Preview)</span></span>

<span data-ttu-id="ac167-123">現在，如果您從警示流覽至威脅瀏覽器，它就會在瀏覽器中開啟篩選的視圖，並以警示原則識別碼篩選 (原則識別碼為警示原則) 的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="ac167-123">Today, if you navigate from an alert to Threat Explorer, it opens a filtered view within the Explorer, with the view filtered by Alert policy ID (policy ID being a unique identifier for an Alert policy).</span></span>
<span data-ttu-id="ac167-124">在威脅瀏覽器和即時偵測中引入警示識別碼，使這項整合更為相關 (在威脅瀏覽器和即時偵測中看到警示) 識別碼的範例，這樣您就能看到與特定警示相關的訊息，以及電子郵件的計數。</span><span class="sxs-lookup"><span data-stu-id="ac167-124">We are making this integration more relevant by introducing the alert ID (see an example of alert ID below) in Threat Explorer and Real-time detections so that you see messages which are relevant to the specific alert, as well as a count of emails.</span></span> <span data-ttu-id="ac167-125">您也可以查看郵件是否為警示的一部分，以及從該郵件流覽至特定警示。</span><span class="sxs-lookup"><span data-stu-id="ac167-125">You will also be able to see if a message was part of an alert, as well as navigate from that message to the specific alert.</span></span>

<span data-ttu-id="ac167-126">當您查看個別的警示時，URL 內可使用警示識別碼;範例為 `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1` 。</span><span class="sxs-lookup"><span data-stu-id="ac167-126">Alert ID is available within the URL when you are viewing an individual alert; an example being `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-127">![警示識別碼的篩選](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-127">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-128">![詳細資料快顯視窗中的警示識別碼](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-128">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a><span data-ttu-id="ac167-129">將瀏覽器的 (和即時的偵測功能延伸) 從7天到30天 (預覽的試用承租人的資料保留和搜尋限制) </span><span class="sxs-lookup"><span data-stu-id="ac167-129">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days (Preview)</span></span>

<span data-ttu-id="ac167-130">在這項變更中，您將可以搜尋和篩選超過30天的電子郵件資料 (在威脅瀏覽器/即時偵測中，針對 Office P1 和 P2 試用租使用者的 Defender，進行過去7天) 中的增加。</span><span class="sxs-lookup"><span data-stu-id="ac167-130">As part of this change, you will be able to search for, and filter email data across 30 days (an increase from the previous 7 days) in Threat Explorer/Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span>
<span data-ttu-id="ac167-131">這不會影響 P1 和 P2/E5 客戶的任何實際執行承租人，其已有30天的資料保留和搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="ac167-131">This does not impact any production tenants for both P1 and P2/E5 customers, which already has the 30 day data retention and search capabilities.</span></span>

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a><span data-ttu-id="ac167-132">更新威脅瀏覽器的記錄匯出 (預覽的限制) </span><span class="sxs-lookup"><span data-stu-id="ac167-132">Updated limits for Export of records for Threat Explorer (Preview)</span></span>

<span data-ttu-id="ac167-133">做為此更新的一部分，可從威脅瀏覽器匯出的電子郵件記錄的列數會從9990增加為200000記錄。</span><span class="sxs-lookup"><span data-stu-id="ac167-133">As part of this update, the number of rows for Email records that can be exported from Threat Explorer is increased from 9990 to 200,000 records.</span></span> <span data-ttu-id="ac167-134">目前可匯出的一組資料行將保持不變，但是列數會從目前的限制增加。</span><span class="sxs-lookup"><span data-stu-id="ac167-134">The set of columns that can be exported currently will remain the same, but the number of rows will increase from the current limit.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="ac167-135">威脅瀏覽器中的標記</span><span class="sxs-lookup"><span data-stu-id="ac167-135">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="ac167-136">使用者標記功能是在 *預覽* 中，並非所有人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="ac167-136">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="ac167-137">如需發行排程的相關資訊，請參閱 Microsoft 365 藍圖。</span><span class="sxs-lookup"><span data-stu-id="ac167-137">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="ac167-138">使用者標記識別 Microsoft Defender 中 Office 365 的特定使用者群組。</span><span class="sxs-lookup"><span data-stu-id="ac167-138">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ac167-139">如需標記的相關資訊（包括授權和設定），請參閱 [User tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="ac167-139">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="ac167-140">在威脅瀏覽器中，您可以在下列體驗中看到使用者標記的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ac167-140">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="ac167-141">電子郵件格線視圖</span><span class="sxs-lookup"><span data-stu-id="ac167-141">Email grid view</span></span>

<span data-ttu-id="ac167-142">電子郵件窗格中的 [ **標記** ] 欄包含已套用至寄件者或收件者信箱的所有標記。</span><span class="sxs-lookup"><span data-stu-id="ac167-142">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="ac167-143">依預設，會先顯示「優先順序」帳戶之類的系統標記。</span><span class="sxs-lookup"><span data-stu-id="ac167-143">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-144">![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-144">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="ac167-145">篩選</span><span class="sxs-lookup"><span data-stu-id="ac167-145">Filtering</span></span>

<span data-ttu-id="ac167-146">您可以使用標記做為篩選。</span><span class="sxs-lookup"><span data-stu-id="ac167-146">You can use tags as a filter.</span></span> <span data-ttu-id="ac167-147">只需在優先順序帳戶或特定使用者標記案例中尋找。</span><span class="sxs-lookup"><span data-stu-id="ac167-147">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="ac167-148">您也可以排除包含某些標記的結果。</span><span class="sxs-lookup"><span data-stu-id="ac167-148">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="ac167-149">將此功能與其他篩選器結合，以縮小您的調查範圍。</span><span class="sxs-lookup"><span data-stu-id="ac167-149">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="ac167-150">[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ac167-150">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-151">![不篩選標記](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-151">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="ac167-152">電子郵件詳細資料快顯視窗</span><span class="sxs-lookup"><span data-stu-id="ac167-152">Email detail flyout</span></span>

<span data-ttu-id="ac167-153">若要查看寄件者和收件者的個別標記，請選取 [主旨] 以開啟 [郵件詳細資料] 浮出。</span><span class="sxs-lookup"><span data-stu-id="ac167-153">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="ac167-154">在 [ **摘要** ] 索引標籤上，[寄件者] 和 [收件者] 標記會分開顯示（如果它們是針對電子郵件）</span><span class="sxs-lookup"><span data-stu-id="ac167-154">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="ac167-155">寄件者和收件者個別標記的相關資訊也會延伸至匯出的 CSV 資料，您可以在兩個不同的欄中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac167-155">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-156">![電子郵件詳細資料標記](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-156">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="ac167-157">標記資訊也會顯示在 URL 中按一下 [飛入]。</span><span class="sxs-lookup"><span data-stu-id="ac167-157">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="ac167-158">若要查看，請移至 [網路釣魚] 或 [所有電子郵件] 視圖，然後按一下 [ **URLs** ] 或 [URL] [ **按一下** ]選取個別的 [URL] 浮出視窗，以查看有關該 URL 之按一下的其他詳細資料，包括與該按一下關聯的標記。</span><span class="sxs-lookup"><span data-stu-id="ac167-158">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="ac167-159">更新時程表視圖</span><span class="sxs-lookup"><span data-stu-id="ac167-159">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-160">![URL 標記](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-160">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="ac167-161">觀看[此影片](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ac167-161">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="ac167-162">對即將推出之威脅搜尋體驗的增強 () </span><span class="sxs-lookup"><span data-stu-id="ac167-162">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="ac167-163">更新的電子郵件威脅資訊</span><span class="sxs-lookup"><span data-stu-id="ac167-163">Updated threat information for emails</span></span>

<span data-ttu-id="ac167-164">我們已著重于平臺和資料品質改進，以提升電子郵件記錄的資料準確性和一致性。</span><span class="sxs-lookup"><span data-stu-id="ac167-164">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="ac167-165">增強功能包括將預先傳遞和交付後資訊的整合，例如，將電子郵件上執行的動作當做處理成單一記錄。</span><span class="sxs-lookup"><span data-stu-id="ac167-165">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="ac167-166">其他詳細資料，例如垃圾郵件決定、實體層級威脅 (例如，哪些 URL 為惡意) ，以及最近的傳遞位置也包含在內。</span><span class="sxs-lookup"><span data-stu-id="ac167-166">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="ac167-167">在這些更新後，不論會影響郵件的不同傳遞事件為何，您都會看到每一封郵件的單一專案。</span><span class="sxs-lookup"><span data-stu-id="ac167-167">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="ac167-168">動作可包含 ZAP、手動修正 (，這表示系統管理動作) 、動態傳遞等等。</span><span class="sxs-lookup"><span data-stu-id="ac167-168">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="ac167-169">除了顯示惡意程式碼和網路釣魚威脅之外，您還會看到與電子郵件相關聯的垃圾郵件結論。</span><span class="sxs-lookup"><span data-stu-id="ac167-169">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="ac167-170">在電子郵件內，查看與電子郵件相關的所有威脅，以及對應的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="ac167-170">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="ac167-171">電子郵件可以有零個、一或多個威脅。</span><span class="sxs-lookup"><span data-stu-id="ac167-171">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="ac167-172">您會在 [電子郵件] 浮出控制項的 [ **詳細資料** ] 區段中看到目前的威脅。</span><span class="sxs-lookup"><span data-stu-id="ac167-172">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="ac167-173">針對多種威脅 (例如惡意程式碼和網路釣魚) ，「 **偵測技術** 」欄位會顯示威脅偵測對應，也就是識別威脅的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="ac167-173">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="ac167-174">一組偵測技術現在包含新的偵測方法，也包含垃圾郵件偵測技術。</span><span class="sxs-lookup"><span data-stu-id="ac167-174">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="ac167-175">您可以使用相同的偵測技術集合，在不同的電子郵件視圖中篩選結果， (惡意程式碼、網路釣魚程式、所有電子郵件) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-175">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="ac167-176">判定分析可能不一定要與實體關聯。</span><span class="sxs-lookup"><span data-stu-id="ac167-176">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="ac167-177">舉例來說，電子郵件可能會分類為網路釣魚或垃圾郵件，但沒有以網路釣魚/垃圾郵件判定的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ac167-177">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="ac167-178">這是因為篩選器也會在指派判定之前，評估電子郵件的內容和其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac167-178">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="ac167-179">URLs 中的威脅</span><span class="sxs-lookup"><span data-stu-id="ac167-179">Threats in URLs</span></span>

<span data-ttu-id="ac167-180">您現在可以在 [電子郵件彈出 **詳細資料** ] 索引標籤上看到 URL 的特定威脅。威脅可能是 *惡意* 代碼、 *網路釣魚*、 *垃圾郵件* 或 *無*。 ) </span><span class="sxs-lookup"><span data-stu-id="ac167-180">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-181">![URL 威脅](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-181">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="ac167-182"> (即將開始的時程表視圖更新) </span><span class="sxs-lookup"><span data-stu-id="ac167-182">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-183">![更新時程表視圖](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-183">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="ac167-184">時程表視圖會識別所有傳遞和傳遞投遞事件。</span><span class="sxs-lookup"><span data-stu-id="ac167-184">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="ac167-185">它包含針對這些事件子集在該時間點所識別之威脅的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ac167-185">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="ac167-186">時程表視圖也提供有關 (執行的任何其他動作（如 ZAP 或手動修正) ）的相關資訊，以及該動作的結果。</span><span class="sxs-lookup"><span data-stu-id="ac167-186">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="ac167-187">時程表視圖資訊包含：</span><span class="sxs-lookup"><span data-stu-id="ac167-187">Timeline view information includes:</span></span>

- <span data-ttu-id="ac167-188">**來源：** 事件的來源。</span><span class="sxs-lookup"><span data-stu-id="ac167-188">**Source:** Source of the event.</span></span> <span data-ttu-id="ac167-189">可以是 admin/system/user。</span><span class="sxs-lookup"><span data-stu-id="ac167-189">It can be admin/system/user.</span></span>
- <span data-ttu-id="ac167-190">**事件：** 包含最上層的事件，例如原始傳遞、手動修復、ZAP、報送及動態傳遞。</span><span class="sxs-lookup"><span data-stu-id="ac167-190">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="ac167-191">**動作：** 做為 ZAP 或 admin 動作一部分所採取的特定動作 (例如，soft delete) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-191">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="ac167-192">**威脅：** 涵蓋該時間點所識別的威脅 (惡意程式碼、網路釣魚和垃圾郵件) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-192">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="ac167-193">**結果/詳細資料：** 有關動作結果的詳細資訊，例如是否以 ZAP/系統管理動作的一部分執行。</span><span class="sxs-lookup"><span data-stu-id="ac167-193">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="ac167-194">原始及最近的傳遞位置</span><span class="sxs-lookup"><span data-stu-id="ac167-194">Original and latest delivery location</span></span>

<span data-ttu-id="ac167-195">目前，我們在電子郵件格線和電子郵件飛入位置中呈現的方式。</span><span class="sxs-lookup"><span data-stu-id="ac167-195">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="ac167-196">[**傳遞位置**] 欄位取得 [重新命名 **_原始傳遞位置_]*。我們正在引進另一個欄位，_*_最新的傳遞位置_**。</span><span class="sxs-lookup"><span data-stu-id="ac167-196">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="ac167-197">**原始傳遞位置** 將會提供有關電子郵件最初傳遞位置的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ac167-197">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="ac167-198">**最新的傳遞位置** 會在系統動作（如 *ZAP* 或系統動作）之後的電子郵件進入，例如 *移至 [刪除的專案*]。</span><span class="sxs-lookup"><span data-stu-id="ac167-198">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="ac167-199">最新的傳遞位置是用來告訴系統管理員郵件的最後一個已知位置後置或任何系統/系統管理員動作。</span><span class="sxs-lookup"><span data-stu-id="ac167-199">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="ac167-200">它不會包含電子郵件上的任何使用者動作。</span><span class="sxs-lookup"><span data-stu-id="ac167-200">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="ac167-201">例如，如果使用者刪除郵件或將郵件移至封存/pst，則不會更新郵件的 [傳遞] 位置。</span><span class="sxs-lookup"><span data-stu-id="ac167-201">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="ac167-202">不過，如果系統動作更新了位置 (例如，ZAP 產生的電子郵件移至隔離) 中，則 **最新的傳遞位置** 會顯示為「隔離」。</span><span class="sxs-lookup"><span data-stu-id="ac167-202">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-203">![更新的傳遞位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-203">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="ac167-204">在某些情況下， **傳送位置** 和 **傳遞動作** 可能會顯示為「未知」：</span><span class="sxs-lookup"><span data-stu-id="ac167-204">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="ac167-205">如果郵件已傳遞，您可能 **會看到 [** 已傳遞] 和 [送達] **位置** 為 "Unknown"，但是收件匣規則會將郵件移至預設資料夾 (例如草稿或封存) ，而不是 [收件匣] 或 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ac167-205">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="ac167-206">如果已嘗試使用系統管理員/系統動作 (（例如 ZAP) ），但找不到該郵件，則 **最新的傳遞位置** 可能是未知的。</span><span class="sxs-lookup"><span data-stu-id="ac167-206">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="ac167-207">通常動作會在使用者移動或刪除郵件之後發生。</span><span class="sxs-lookup"><span data-stu-id="ac167-207">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="ac167-208">在這種情況下，請在時程表視圖中驗證 [ **結果/詳細資料** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="ac167-208">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="ac167-209">尋找 [使用者已移動或刪除的郵件] 語句。</span><span class="sxs-lookup"><span data-stu-id="ac167-209">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-210">![時程表的傳遞位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-210">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="ac167-211">其他動作</span><span class="sxs-lookup"><span data-stu-id="ac167-211">Additional actions</span></span>

<span data-ttu-id="ac167-212">在傳送電子郵件之後套用 *其他動作*。</span><span class="sxs-lookup"><span data-stu-id="ac167-212">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="ac167-213">它們可以包含由系統管理員採取的 *ZAP*、 *手動修正* (動作（如虛刪除) 、 *動態傳遞*） *，以及重新處理 (（* 已偵測為良好) 的電子郵件）。</span><span class="sxs-lookup"><span data-stu-id="ac167-213">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> <span data-ttu-id="ac167-214">在擱置中的變更中，目前出現在 [傳遞動作篩選] 中的「已移除的 ZAP」值將會不復存在。</span><span class="sxs-lookup"><span data-stu-id="ac167-214">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="ac167-215">您可以使用此方法，透過 **其他動作** 來搜尋所有 ZAP 嘗試的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-215">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-216">![瀏覽器中的其他動作](../../media/Additional_Actions.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-216">![Additional Actions in Explorer](../../media/Additional_Actions.png)</span></span>

### <a name="system-overrides"></a><span data-ttu-id="ac167-217">系統覆寫</span><span class="sxs-lookup"><span data-stu-id="ac167-217">System overrides</span></span>

<span data-ttu-id="ac167-218">*系統覆寫* 可讓您對郵件的預定送達位置產生例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ac167-218">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="ac167-219">您可以根據威脅及篩選堆疊所識別的其他偵測，覆寫系統所提供的傳遞位置。</span><span class="sxs-lookup"><span data-stu-id="ac167-219">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="ac167-220">系統覆寫可透過租使用者或使用者原則加以設定，以依照原則所建議的方式傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-220">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="ac167-221">覆寫可識別因設定缺口而無意間傳遞的惡意郵件，例如使用者設定的過於廣泛的安全寄件者原則。</span><span class="sxs-lookup"><span data-stu-id="ac167-221">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="ac167-222">這些覆寫值可以是：</span><span class="sxs-lookup"><span data-stu-id="ac167-222">These override values can be:</span></span>

- <span data-ttu-id="ac167-223">使用者原則允許：使用者在信箱層級建立原則，以允許網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="ac167-223">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>

- <span data-ttu-id="ac167-224">使用者原則封鎖：使用者會在信箱層級建立原則，以封鎖網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="ac167-224">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>

- <span data-ttu-id="ac167-225">組織原則所允許：組織的安全小組設定原則或 Exchange 郵件流程規則 (也稱為傳輸) 規則，可讓其組織中的使用者能夠使用寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="ac167-225">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="ac167-226">這可供一組使用者或整個組織使用。</span><span class="sxs-lookup"><span data-stu-id="ac167-226">This can be for a set of users or the entire organization.</span></span>

- <span data-ttu-id="ac167-227">由組織原則封鎖：組織的安全小組會設定原則或郵件流程規則，以封鎖組織中使用者的寄件者、網域、郵件語言或來源 Ip。</span><span class="sxs-lookup"><span data-stu-id="ac167-227">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="ac167-228">這可以套用到一組使用者或整個組織。</span><span class="sxs-lookup"><span data-stu-id="ac167-228">This can be applied to a set of users or the entire organization.</span></span>

- <span data-ttu-id="ac167-229">組織原則封鎖的檔案副檔名：組織的安全性小組會透過反惡意程式碼原則設定封鎖副檔名。</span><span class="sxs-lookup"><span data-stu-id="ac167-229">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="ac167-230">這些值現在會顯示在電子郵件詳細資料中，以協助調查。</span><span class="sxs-lookup"><span data-stu-id="ac167-230">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="ac167-231">Secops 小組也可以使用 rtf 篩選功能來篩選封鎖的副檔名。</span><span class="sxs-lookup"><span data-stu-id="ac167-231">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="ac167-232">[![瀏覽器中的系統覆寫](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ac167-232">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-233">![瀏覽器中的系統覆寫格線](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-233">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="ac167-234">URL 及點擊體驗的增強功能</span><span class="sxs-lookup"><span data-stu-id="ac167-234">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="ac167-235">改進功能包括：</span><span class="sxs-lookup"><span data-stu-id="ac167-235">The improvements include:</span></span>

- <span data-ttu-id="ac167-236">顯示已完全按一下的 URL (包括 url 任何部分之 URL 的任何查詢參數) 在 URL 快顯視窗的 [ **點擊** ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="ac167-236">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="ac167-237">目前，URL 網域和路徑會出現在標題列中。</span><span class="sxs-lookup"><span data-stu-id="ac167-237">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="ac167-238">我們正在擴充該資訊以顯示完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-238">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="ac167-239">跨 URL 篩選器的修正 (*url* 與 *url 網域* *，以及 url 網域和路徑*) ：更新會影響包含 URL/按一下判定之郵件的搜尋。</span><span class="sxs-lookup"><span data-stu-id="ac167-239">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="ac167-240">我們為通訊協定不可知的搜尋啟用支援，因此您可以在不使用的情況下搜尋 URL `http` 。</span><span class="sxs-lookup"><span data-stu-id="ac167-240">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="ac167-241">根據預設，URL 搜尋會對應至 HTTP，除非明確指定另一個值。</span><span class="sxs-lookup"><span data-stu-id="ac167-241">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="ac167-242">例如：</span><span class="sxs-lookup"><span data-stu-id="ac167-242">For example:</span></span>
  - <span data-ttu-id="ac167-243">`http://`在 [ **url**]、[ **url 網域**] 及 [ **url 網域] 和 [路徑** 篩選] 欄位中，使用或不使用前置詞進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="ac167-243">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="ac167-244">搜尋應該會顯示相同的結果。</span><span class="sxs-lookup"><span data-stu-id="ac167-244">The searches should show the same results.</span></span>
  - <span data-ttu-id="ac167-245">`https://`在 **URL** 中搜尋前置詞。</span><span class="sxs-lookup"><span data-stu-id="ac167-245">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="ac167-246">若未指定任何值，則 `http://` 會假設首碼。</span><span class="sxs-lookup"><span data-stu-id="ac167-246">When no value is specified, the `http://` prefix is assumed.</span></span>
  - <span data-ttu-id="ac167-247">`/` 會在 **url 路徑**、 **url 網域**、 **URL 網域及路徑** 欄位的開頭和結尾略過。</span><span class="sxs-lookup"><span data-stu-id="ac167-247">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="ac167-248">`/` 在 [ **URL** ] 欄位的結尾會被忽略。</span><span class="sxs-lookup"><span data-stu-id="ac167-248">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="ac167-249">網路釣魚信賴等級</span><span class="sxs-lookup"><span data-stu-id="ac167-249">Phish confidence level</span></span>

<span data-ttu-id="ac167-250">網路釣魚信賴等級可協助識別將電子郵件分類為 "網路釣魚" 的置信度。</span><span class="sxs-lookup"><span data-stu-id="ac167-250">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="ac167-251">這兩個可能的值為 *High* 和 *Normal*。</span><span class="sxs-lookup"><span data-stu-id="ac167-251">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="ac167-252">在初始階段中，此篩選器只會在威脅瀏覽器的網路釣魚視圖中使用。</span><span class="sxs-lookup"><span data-stu-id="ac167-252">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="ac167-253">[![瀏覽器中的網路釣魚信賴等級](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ac167-253">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="ac167-254">ZAP URL 信號</span><span class="sxs-lookup"><span data-stu-id="ac167-254">ZAP URL signal</span></span>

<span data-ttu-id="ac167-255">ZAP URL 信號通常用於 ZAP 網路釣魚警示案例，其中的電子郵件已識別為網路釣魚並在傳遞後移除。</span><span class="sxs-lookup"><span data-stu-id="ac167-255">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="ac167-256">此信號會在瀏覽器中使用對應的結果來連接警示。</span><span class="sxs-lookup"><span data-stu-id="ac167-256">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="ac167-257">這是警示的其中一個 IOCs。</span><span class="sxs-lookup"><span data-stu-id="ac167-257">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="ac167-258">為了改進搜尋程式，我們已更新威脅瀏覽器和即時偵測，使搜尋體驗更為一致。</span><span class="sxs-lookup"><span data-stu-id="ac167-258">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="ac167-259">這些變更如下所述：</span><span class="sxs-lookup"><span data-stu-id="ac167-259">The changes are outlined here:</span></span>

- [<span data-ttu-id="ac167-260">時區改進</span><span class="sxs-lookup"><span data-stu-id="ac167-260">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="ac167-261">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="ac167-261">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="ac167-262">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="ac167-262">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="ac167-263">在產品資訊更新</span><span class="sxs-lookup"><span data-stu-id="ac167-263">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="ac167-264">依使用者標記篩選</span><span class="sxs-lookup"><span data-stu-id="ac167-264">Filter by user tags</span></span>

<span data-ttu-id="ac167-265">您現在可以排序和篩選系統或自訂使用者標記，以快速抓住威脅的範圍。</span><span class="sxs-lookup"><span data-stu-id="ac167-265">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="ac167-266">若要深入瞭解，請參閱 [使用者標記](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="ac167-266">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac167-267">依使用者標記篩選和排序目前是公開預覽。</span><span class="sxs-lookup"><span data-stu-id="ac167-267">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="ac167-268">在正式發行之前，您可能會充分修改此功能。</span><span class="sxs-lookup"><span data-stu-id="ac167-268">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ac167-269">Microsoft 對本所提供的資訊不提供任何明示或默示的保證。</span><span class="sxs-lookup"><span data-stu-id="ac167-269">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-270">![瀏覽器中的標記欄](../../media/threat-explorer-tags.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-270">![Tags column in Explorer](../../media/threat-explorer-tags.png)</span></span>

### <a name="timezone-improvements"></a><span data-ttu-id="ac167-271">時區改進</span><span class="sxs-lookup"><span data-stu-id="ac167-271">Timezone improvements</span></span>

<span data-ttu-id="ac167-272">您會看到入口網站中的電子郵件記錄以及匯出資料的時區。</span><span class="sxs-lookup"><span data-stu-id="ac167-272">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="ac167-273">透過電子郵件格線、[詳細資料] 飛出、電子郵件時程表及類似的電子郵件，它會在體驗上看到，所以結果集的時區也是清除的。</span><span class="sxs-lookup"><span data-stu-id="ac167-273">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-274">![在瀏覽器中查看時區](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-274">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="ac167-275">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="ac167-275">Update in the refresh process</span></span>

<span data-ttu-id="ac167-276">有些使用者對自動重新整理的混淆有批註 (例如，當您變更日期時，此頁面會立即重新整理) 和手動重新整理 (其他篩選) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-276">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="ac167-277">同樣地，移除篩選器也會導致自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="ac167-277">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="ac167-278">修改查詢時變更篩選可能會造成不一致的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="ac167-278">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="ac167-279">若要解決這些問題，我們會移至手動篩選機制。</span><span class="sxs-lookup"><span data-stu-id="ac167-279">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="ac167-280">從經驗的觀點來看，使用者可以從 [篩選器集和日期) 中，套用及移除不同的篩選範圍 (，然後選取 [重新整理] 按鈕，以在定義查詢之後篩選結果。</span><span class="sxs-lookup"><span data-stu-id="ac167-280">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="ac167-281">[重新整理] 按鈕現在也會在螢幕上強調。</span><span class="sxs-lookup"><span data-stu-id="ac167-281">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="ac167-282">我們也更新相關的工具提示及產品內檔。</span><span class="sxs-lookup"><span data-stu-id="ac167-282">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-283">![選取 [重新整理] 以篩選結果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-283">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="ac167-284">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="ac167-284">Chart drilldown to add to filters</span></span>

<span data-ttu-id="ac167-285">您現在可以圖表圖例值新增為篩選器。</span><span class="sxs-lookup"><span data-stu-id="ac167-285">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="ac167-286">選取 [重新整理 **] 按鈕以** 篩選結果。</span><span class="sxs-lookup"><span data-stu-id="ac167-286">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-287">![深入查看圖表以進行篩選](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-287">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="ac167-288">產品內資訊更新</span><span class="sxs-lookup"><span data-stu-id="ac167-288">In-product information updates</span></span>

<span data-ttu-id="ac167-289">產品內現在已提供其他詳細資料，例如格線內的搜尋結果總數 (請參閱) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-289">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="ac167-290">我們已改進標籤、錯誤訊息及工具提示，以提供有關篩選、搜尋經驗及結果集的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ac167-290">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-291">![View in 產品資訊](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-291">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="ac167-292">威脅瀏覽器中的延伸功能</span><span class="sxs-lookup"><span data-stu-id="ac167-292">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="ac167-293">主要目標使用者</span><span class="sxs-lookup"><span data-stu-id="ac167-293">Top targeted users</span></span>

<span data-ttu-id="ac167-294">如今，我們會在惡意程式碼的 [ **主要惡意程式碼系列** ] 區段中，公開電子郵件的惡意程式碼視圖中主要目標使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="ac167-294">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="ac167-295">我們也會在網路釣魚和所有電子郵件視圖中擴充此視圖。</span><span class="sxs-lookup"><span data-stu-id="ac167-295">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="ac167-296">您將可以查看前5位目標使用者，以及每位使用者對對應視圖的嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="ac167-296">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="ac167-297">例如，針對網路釣魚視圖，您會看到網路釣魚嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="ac167-297">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="ac167-298">您可以將目標使用者的清單匯出至3000的限制，以及每個電子郵件 view 的離線分析嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="ac167-298">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="ac167-299">此外，選取 [嘗試次數] (例如，13在下一個影像嘗試) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就能看到該使用者的電子郵件和威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac167-299">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-300">![主要目標使用者](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-300">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="ac167-301">傳輸規則 Exchange</span><span class="sxs-lookup"><span data-stu-id="ac167-301">Exchange transport rules</span></span>

<span data-ttu-id="ac167-302">在 [資料豐富] 的一部分中，您將可以查看套用至郵件的所有不同 Exchange 傳輸規則 (ETR) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-302">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="ac167-303">此資訊將會出現在 [電子郵件格線] 視圖中。</span><span class="sxs-lookup"><span data-stu-id="ac167-303">This information will be available in the Email grid view.</span></span> <span data-ttu-id="ac167-304">若要進行查看，請選取格線中的 [**欄選項**]，然後從 [欄] 選項 **新增 Exchange 傳輸規則**。</span><span class="sxs-lookup"><span data-stu-id="ac167-304">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="ac167-305">它也會顯示在電子郵件中的 [ **詳細資料** ] 快顯視窗中。</span><span class="sxs-lookup"><span data-stu-id="ac167-305">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="ac167-306">您將能看到 GUID 及已套用至郵件的傳輸規則名稱。</span><span class="sxs-lookup"><span data-stu-id="ac167-306">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="ac167-307">您將能夠使用傳輸規則的名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-307">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="ac167-308">這是「包含」搜尋，也就是您也可以進行部分搜尋。</span><span class="sxs-lookup"><span data-stu-id="ac167-308">This is a "Contains" search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac167-309">ETR 搜尋和名稱可用性取決於指派給您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="ac167-309">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="ac167-310">您必須具有下列其中一個角色/許可權，才能查看 ETR 名稱和搜尋。</span><span class="sxs-lookup"><span data-stu-id="ac167-310">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="ac167-311">如果您未指派任何這些角色，您就無法看到傳輸規則的名稱，或使用 ETR 名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-311">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="ac167-312">不過，您可以在電子郵件詳細資料中看到 ETR 標籤及 GUID 資訊。</span><span class="sxs-lookup"><span data-stu-id="ac167-312">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="ac167-313">其他記錄流覽的電子郵件格線、電子郵件 flyouts、篩選和匯出不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="ac167-313">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="ac167-314">僅限 EXO-資料遺失防護：全部</span><span class="sxs-lookup"><span data-stu-id="ac167-314">EXO Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="ac167-315">僅限 EXO-O365SupportViewConfig： All</span><span class="sxs-lookup"><span data-stu-id="ac167-315">EXO Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="ac167-316">Microsoft Azure Active Directory 或 EXO-安全性系統管理員： All</span><span class="sxs-lookup"><span data-stu-id="ac167-316">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
> - <span data-ttu-id="ac167-317">AAD 或 EXO-Security Reader： All</span><span class="sxs-lookup"><span data-stu-id="ac167-317">AAD or EXO - Security Reader: All</span></span>
> - <span data-ttu-id="ac167-318">僅限 EXO-Transport Rules： All</span><span class="sxs-lookup"><span data-stu-id="ac167-318">EXO Only - Transport Rules: All</span></span>
> - <span data-ttu-id="ac167-319">僅限 EXO-View-Only 設定： All</span><span class="sxs-lookup"><span data-stu-id="ac167-319">EXO Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="ac167-320">在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。</span><span class="sxs-lookup"><span data-stu-id="ac167-320">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="ac167-321">![Exchange傳輸規則](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-321">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="ac167-322">輸入連接器</span><span class="sxs-lookup"><span data-stu-id="ac167-322">Inbound connectors</span></span>

<span data-ttu-id="ac167-323">連接器是一組指示，可自訂您的電子郵件進出 Microsoft 365 或 Office 365 組織的方式。</span><span class="sxs-lookup"><span data-stu-id="ac167-323">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="ac167-324">它們可讓您套用任何安全性限制或控制項。</span><span class="sxs-lookup"><span data-stu-id="ac167-324">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="ac167-325">在威脅瀏覽器內，您現在可以查看與電子郵件相關的連接器，並使用連接器名稱搜尋電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-325">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="ac167-326">在 [自然] 中，連接器的搜尋是「包含」，這表示部分關鍵字搜尋也應該可以運作。</span><span class="sxs-lookup"><span data-stu-id="ac167-326">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="ac167-327">在主格線視圖中，[詳細資料] 飛入和匯出的 CSV，連接器會以如下所示的名稱/GUID 格式顯示：</span><span class="sxs-lookup"><span data-stu-id="ac167-327">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-328">![連接器詳細資料](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-328">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="ac167-329">威脅瀏覽器和即時偵測中的新功能</span><span class="sxs-lookup"><span data-stu-id="ac167-329">New features in Threat Explorer and Real-time detections</span></span>

- [<span data-ttu-id="ac167-330">查看傳送給類比使用者和網域的網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="ac167-330">View phishing emails sent to impersonated users and domains</span></span>](#view-phishing-emails-sent-to-impersonated-users-and-domains)
- [<span data-ttu-id="ac167-331">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="ac167-331">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="ac167-332">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="ac167-332">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="ac167-333">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="ac167-333">Export URL click data</span></span>](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a><span data-ttu-id="ac167-334">查看傳送給類比使用者和網域的網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="ac167-334">View phishing emails sent to impersonated users and domains</span></span>

<span data-ttu-id="ac167-335">若要識別對類比使用者的使用者和網域的網頁網路嘗試，必須新增至 *要保護的使用者* 清單中。</span><span class="sxs-lookup"><span data-stu-id="ac167-335">To identify phishing attempts against users and domains that are impersonated users must be added to the list of *Users to protect*.</span></span> <span data-ttu-id="ac167-336">對於網域，系統管理員必須啟用 *組織網域*，或將功能變數名稱新增至 *要保護的網域*。</span><span class="sxs-lookup"><span data-stu-id="ac167-336">For domains, admins must either enable *Organization domains*, or add a domain name to *Domains to protect*.</span></span> <span data-ttu-id="ac167-337">您 *可以在模擬區段的*[*反網路釣魚原則] 頁面* 上找到要保護的網域。</span><span class="sxs-lookup"><span data-stu-id="ac167-337">The domains to protect are found on the *Anti-Phishing policy page* in the *Impersonation* section.</span></span>

<span data-ttu-id="ac167-338">若要查看網路釣魚郵件和搜尋模擬的使用者或網域，請使用瀏覽器的 [電子郵件 > 網路釣魚視圖](threat-explorer-views.md) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-338">To review phish messages and search for impersonated users or domains, use the [Email > Phish view](threat-explorer-views.md) of Explorer.</span></span>

<span data-ttu-id="ac167-339">本範例會使用威脅瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="ac167-339">This example uses Threat Explorer.</span></span>

1. <span data-ttu-id="ac167-340">在 [ [安全性 & 規範中心](https://protection.office.com) ] (中 https://protection.office.com) ，選擇 [威脅管理] > Explorer (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-340">In the [Security & Compliance Center](https://protection.office.com) (https://protection.office.com), choose Threat management > Explorer (or Real-time detections).</span></span>

2. <span data-ttu-id="ac167-341">在 [View] 功能表中，選擇 [電子郵件 > 網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="ac167-341">In the View menu, choose Email > Phish.</span></span>

   <span data-ttu-id="ac167-342">您可以在這裡選擇模擬的 **網域** 或 **模仿的使用者**。</span><span class="sxs-lookup"><span data-stu-id="ac167-342">Here you can choose **impersonated domain** or **impersonated user**.</span></span>

3. <span data-ttu-id="ac167-343">**請選取 [** 模擬 **網域**]，然後在 textbox 中輸入受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="ac167-343">**EITHER** select **Impersonated domain**, and then type a protected domain in the textbox.</span></span>

   <span data-ttu-id="ac167-344">例如，搜尋受保護的功能變數名稱（如 *contoso*、 *contoso.com* 或 *contoso.com.au*）。</span><span class="sxs-lookup"><span data-stu-id="ac167-344">For example, search for protected domain names like *contoso*, *contoso.com*, or *contoso.com.au*.</span></span>

4. <span data-ttu-id="ac167-345">在 [電子郵件] 索引標籤 > 詳細資料] 索引標籤下，選取任何郵件的主旨，以查看類比網域/偵測到的位置等其他類比</span><span class="sxs-lookup"><span data-stu-id="ac167-345">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span></span>

    <span data-ttu-id="ac167-346">**OR**</span><span class="sxs-lookup"><span data-stu-id="ac167-346">**OR**</span></span>

    <span data-ttu-id="ac167-347">選取 [模擬 **使用者** ]，然後在 textbox 中輸入受保護使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ac167-347">Select **Impersonated user** and type a protected user's email address in the textbox.</span></span>

    > [!TIP]
    > <span data-ttu-id="ac167-348">**為了獲得最佳結果**，請使用 *完整電子郵件地址* 來搜尋受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="ac167-348">**For best results**, use *full email addresses* to search protected users.</span></span> <span data-ttu-id="ac167-349">當您搜尋 *firstname.lastname@contoso.com* 時（例如，調查使用者模擬時），您可以更快速且更順利地找到您的受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="ac167-349">You will find your protected user quicker and more successfully if you search for *firstname.lastname@contoso.com*, for example, when investigating user impersonation.</span></span> <span data-ttu-id="ac167-350">搜尋受保護的網域時，搜尋會以根域 (contoso.com，例如) ，以及功能變數名稱 (*contoso*) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-350">When searching for a protected domain the search will take the root domain (contoso.com, for example), and the domain name (*contoso*).</span></span> <span data-ttu-id="ac167-351">搜尋根網域 *contoso.com* 將同時傳回 *contoso.com* 和功能變數名稱 *contoso* 的 impersonations。</span><span class="sxs-lookup"><span data-stu-id="ac167-351">Searching for the root domain *contoso.com* will return both impersonations of *contoso.com* and the domain name *contoso*.</span></span>

5. <span data-ttu-id="ac167-352">在 [**電子郵件** 索引標籤詳細資料] 索引標籤中選取任何 **郵件的主旨**  >   ，以查看有關使用者或網域的其他模擬資訊和偵測 *到的位置*。</span><span class="sxs-lookup"><span data-stu-id="ac167-352">Select the **Subject** of any message under **Email tab** > **Details tab** to see additional impersonation information about the user or domain, and the *Detected location*.</span></span>

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="顯示偵測位置之受保護使用者的威脅瀏覽器詳細資料窗格，以及偵測到使用者) 的網路釣魚模擬 (所偵測到的威脅。":::

> [!NOTE]
> <span data-ttu-id="ac167-354">在步驟3或5中，如果您選擇 [**偵測技術**]，並分別選取 [**類比網域**] 或 [模擬 **使用者**]，則使用者或網域的 [**電子郵件]** 索引標籤詳細資料] 索引標籤中的資訊，  >  只會顯示在 [*反網路釣魚原則\*\*\*]*\* 頁面上所列之使用者或網域相關聯的訊息。 </span><span class="sxs-lookup"><span data-stu-id="ac167-354">In step 3 or 5, if you choose **Detection Technology** and select **Impersonation domain** or **Impersonation user** respectively, the information in the **Email tab** > **Details tab** about the user or domain, and the *Detected location* will be shown only on the messages that are related to the user or domain listed on the *Anti-Phishing policy* page.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="ac167-355">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="ac167-355">Preview email header and download email body</span></span>

<span data-ttu-id="ac167-356">您現在可以預覽電子郵件頭，並下載威脅瀏覽器中的電子郵件內文。</span><span class="sxs-lookup"><span data-stu-id="ac167-356">You can now preview an email header and download the email body in Threat Explorer.</span></span> <span data-ttu-id="ac167-357">系統管理員可以分析已下載的郵件頭/電子郵件，以取得威脅。</span><span class="sxs-lookup"><span data-stu-id="ac167-357">Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="ac167-358">因為下載電子郵件可能會危及資訊的危險性，所以此程式是由以角色為基礎的存取控制 (RBAC) 所控制。</span><span class="sxs-lookup"><span data-stu-id="ac167-358">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="ac167-359">新的角色、 *預覽*，必須新增至其他角色群組 (例如安全作業或安全性系統管理員) ，以授與透過所有電子郵件消息查看下載郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="ac167-359">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="ac167-360">不過，若要在威脅瀏覽器) 中查看郵件所需的 (以外，查看電子郵件標頭並不需要任何其他角色。</span><span class="sxs-lookup"><span data-stu-id="ac167-360">However, viewing the email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="ac167-361">瀏覽器和即時偵測也會取得新的欄位，可提供您的電子郵件所在位置更完整的畫面。</span><span class="sxs-lookup"><span data-stu-id="ac167-361">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="ac167-362">這些變更可使搜尋更輕鬆進行安全性 Op。</span><span class="sxs-lookup"><span data-stu-id="ac167-362">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="ac167-363">不過，主要結果是您可以快速知道問題電子郵件訊息的位置。</span><span class="sxs-lookup"><span data-stu-id="ac167-363">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="ac167-364">這是如何達成？</span><span class="sxs-lookup"><span data-stu-id="ac167-364">How is this done?</span></span> <span data-ttu-id="ac167-365">傳遞狀態現在會分解成兩個欄：</span><span class="sxs-lookup"><span data-stu-id="ac167-365">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="ac167-366">**傳遞動作** -電子郵件的狀態。</span><span class="sxs-lookup"><span data-stu-id="ac167-366">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="ac167-367">**傳遞位置** -傳送電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="ac167-367">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="ac167-368">*傳遞動作* 是由於現有的原則或偵測，而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ac167-368">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="ac167-369">電子郵件可能的動作如下：</span><span class="sxs-lookup"><span data-stu-id="ac167-369">Here are the possible actions for an email:</span></span>

<br>

****

|<span data-ttu-id="ac167-370">已傳遞</span><span class="sxs-lookup"><span data-stu-id="ac167-370">Delivered</span></span>|<span data-ttu-id="ac167-371">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="ac167-371">Junked</span></span>|<span data-ttu-id="ac167-372">已封鎖</span><span class="sxs-lookup"><span data-stu-id="ac167-372">Blocked</span></span>|<span data-ttu-id="ac167-373">已取代</span><span class="sxs-lookup"><span data-stu-id="ac167-373">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="ac167-374">電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以存取。</span><span class="sxs-lookup"><span data-stu-id="ac167-374">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="ac167-375">電子郵件已傳送至使用者的 [垃圾郵件] 或 [已刪除] 資料夾，使用者可以存取它。</span><span class="sxs-lookup"><span data-stu-id="ac167-375">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="ac167-376">隔離、失敗或丟棄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-376">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="ac167-377">使用者無法存取這些郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-377">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="ac167-378">電子郵件具有惡意附件，其 .txt 的檔會以附件為惡意。</span><span class="sxs-lookup"><span data-stu-id="ac167-378">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|
|

<span data-ttu-id="ac167-379">以下是使用者可及無法看到的專案：</span><span class="sxs-lookup"><span data-stu-id="ac167-379">Here is what the user can and can't see:</span></span>

<br>

****

|<span data-ttu-id="ac167-380">使用者可以存取</span><span class="sxs-lookup"><span data-stu-id="ac167-380">Accessible to end users</span></span>|<span data-ttu-id="ac167-381">使用者無法存取 </span><span class="sxs-lookup"><span data-stu-id="ac167-381">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="ac167-382">已傳遞</span><span class="sxs-lookup"><span data-stu-id="ac167-382">Delivered</span></span>|<span data-ttu-id="ac167-383">已封鎖</span><span class="sxs-lookup"><span data-stu-id="ac167-383">Blocked</span></span>|
|<span data-ttu-id="ac167-384">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="ac167-384">Junked</span></span>|<span data-ttu-id="ac167-385">已取代</span><span class="sxs-lookup"><span data-stu-id="ac167-385">Replaced</span></span>|
|

<span data-ttu-id="ac167-386">**傳遞位置** 顯示執行後續傳遞的原則及偵測結果。</span><span class="sxs-lookup"><span data-stu-id="ac167-386">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="ac167-387">它會連結至 **_傳遞動作_**。</span><span class="sxs-lookup"><span data-stu-id="ac167-387">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="ac167-388">可能的值如下：</span><span class="sxs-lookup"><span data-stu-id="ac167-388">These are the possible values:</span></span>

- <span data-ttu-id="ac167-389">*收件匣或資料夾*：電子郵件的收件匣或資料夾 (會根據您的電子郵件規則) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-389">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="ac167-390">*部署或外部*：信箱不存在於雲端上，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="ac167-390">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="ac167-391">[垃圾郵件]*資料夾*：電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="ac167-391">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="ac167-392">「*刪除的郵件」資料夾*：在使用者的 [刪除的郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-392">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="ac167-393">*隔離*：電子郵件是隔離的，而不是在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="ac167-393">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="ac167-394">*失敗*；電子郵件無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="ac167-394">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="ac167-395">*丟斷*：電子郵件在郵件流程中遺失。</span><span class="sxs-lookup"><span data-stu-id="ac167-395">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="ac167-396">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="ac167-396">Email timeline</span></span>

<span data-ttu-id="ac167-397">**電子郵件時程表** 是新的瀏覽器功能，可改善系統管理員的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="ac167-397">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="ac167-398">它會削減檢查不同位置所花費的時間，以嘗試瞭解該事件。</span><span class="sxs-lookup"><span data-stu-id="ac167-398">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="ac167-399">當電子郵件到達時，發生多個事件或接近該郵件時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="ac167-399">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="ac167-400">您的電子郵件投遞之後所發生的某些事件會在 [ **特殊動作** ] 欄中捕獲。</span><span class="sxs-lookup"><span data-stu-id="ac167-400">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="ac167-401">系統管理員可以合併時程表中的資訊，並在郵件投遞後採取特殊的動作，以深入瞭解其原則的運作方式（即最後一次路由傳送郵件的位置），而且在某些情況下，最後評估是什麼。</span><span class="sxs-lookup"><span data-stu-id="ac167-401">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="ac167-402">如需詳細資訊，請參閱[調查並修正 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="ac167-402">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="ac167-403">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="ac167-403">Export URL click data</span></span>

<span data-ttu-id="ac167-404">您現在可以將 url 按一下的報告匯出至 Microsoft Excel 以查看其 **網路消息識別碼**，並 **按一下 [判定**]，以協助說明您的 URL 按一下流量的來源。</span><span class="sxs-lookup"><span data-stu-id="ac167-404">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="ac167-405">其運作方式如下：在威脅管理的 Office 365 快速啟動列上，請遵循下列連結：</span><span class="sxs-lookup"><span data-stu-id="ac167-405">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="ac167-406">**瀏覽器** \>**查看網路釣魚** \>**按一下** \>**Top URLs** Or **URL 上擊** \> 選取 [任何記錄] 以開啟 [URL] 浮出控制項。</span><span class="sxs-lookup"><span data-stu-id="ac167-406">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="ac167-407">當您在清單中選取 URL 時，您會在飛出面板上看到新的 [ **匯出** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ac167-407">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="ac167-408">使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。</span><span class="sxs-lookup"><span data-stu-id="ac167-408">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="ac167-409">請遵循此路徑，以取得即時偵測報告中的相同位置：</span><span class="sxs-lookup"><span data-stu-id="ac167-409">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="ac167-410">**瀏覽器** \>**即時偵測** \>**查看網路釣魚** \>**URLs** \>**Top URLs** 或 **top 按一下** \> 選取 [任何記錄] 以開啟 [URL] 浮出 \> ] 流覽至 [**點擊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ac167-410">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="ac167-411">當您使用瀏覽器或關聯的協力廠商工具來搜尋識別碼時，網路郵件識別碼會對應按一下 [回復至特定郵件]。</span><span class="sxs-lookup"><span data-stu-id="ac167-411">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="ac167-412">這類搜尋會識別與按一下結果關聯的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac167-412">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="ac167-413">讓相關網路郵件識別碼能夠更快速且更強大的分析。</span><span class="sxs-lookup"><span data-stu-id="ac167-413">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac167-414">![瀏覽器中的按一下 tab 鍵](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-414">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="ac167-415">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="ac167-415">See malware detected in email by technology</span></span>

<span data-ttu-id="ac167-416">假設您想要查看以 Microsoft 365 技術排序的電子郵件中偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="ac167-416">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="ac167-417">若要這麼做，請使用瀏覽器的 [電子郵件 > 惡意](threat-explorer-views.md#email--malware) 代碼視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-417">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="ac167-418">在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-418">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="ac167-419">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="ac167-419">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="ac167-420">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="ac167-420">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-421">![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-421">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="ac167-422">按一下 [ **寄件者**]，然後選擇 [ **基本** \> **偵測技術**]。</span><span class="sxs-lookup"><span data-stu-id="ac167-422">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="ac167-423">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="ac167-423">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-424">![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-424">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="ac167-425">選擇 [選項]。</span><span class="sxs-lookup"><span data-stu-id="ac167-425">Choose an option.</span></span> <span data-ttu-id="ac167-426">然後選取 [重新整理] **按鈕，套用** 該篩選。</span><span class="sxs-lookup"><span data-stu-id="ac167-426">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-427">![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-427">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="ac167-428">報告會進行重新整理，以顯示惡意程式碼在電子郵件中偵測到的結果，並使用您選取的技術選項。</span><span class="sxs-lookup"><span data-stu-id="ac167-428">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="ac167-429">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="ac167-429">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="ac167-430">查看網路釣魚 URL，然後按一下 [已判定資料]</span><span class="sxs-lookup"><span data-stu-id="ac167-430">View phishing URL and click verdict data</span></span>

<span data-ttu-id="ac167-431">假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="ac167-431">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="ac167-432">若要識別所按一下的 URLs，必須設定 [安全連結](safe-links.md) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-432">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="ac167-433">請確定您已設定 [安全連結原則](set-up-safe-links-policies.md) 的 [保護] 和 [記錄] 按一下 [安全連結] 中的 [verdicts]。</span><span class="sxs-lookup"><span data-stu-id="ac167-433">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="ac167-434">若要查看郵件中的網路釣魚 URLs，並按一下網路釣魚郵件中 URLs，請使用瀏覽器或即時偵測的 [**電子郵件**  >  **網路釣魚**](threat-explorer-views.md#email--phish)視圖。</span><span class="sxs-lookup"><span data-stu-id="ac167-434">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="ac167-435">在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-435">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="ac167-436">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="ac167-436">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="ac167-437">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **釣魚網絡**]。</span><span class="sxs-lookup"><span data-stu-id="ac167-437">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-438">![網路釣魚內容中瀏覽器的視圖功能表](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-438">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="ac167-439">按一下 [ **寄件者**]，然後選擇 **URLs** \> **按一下 [判定**]。</span><span class="sxs-lookup"><span data-stu-id="ac167-439">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="ac167-440">選取一個或多個選項（例如 **封鎖** 和 **封鎖**），然後在與套用該篩選的選項相同的列上選取 [重新整理 **] 按鈕。**</span><span class="sxs-lookup"><span data-stu-id="ac167-440">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="ac167-441">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="ac167-441">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-442">![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-442">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="ac167-443">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="ac167-443">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="ac167-444">**Top URLs** 是您篩選的郵件中 URLs，以及每個 URL 的電子郵件傳遞動作計數。</span><span class="sxs-lookup"><span data-stu-id="ac167-444">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="ac167-445">在網路釣魚電子郵件視圖中，此清單通常包含合法的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ac167-445">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="ac167-446">攻擊者會在其郵件中混合使用良好和不良的 URLs，以嘗試傳遞，但它們會使惡意連結看起來更有趣。</span><span class="sxs-lookup"><span data-stu-id="ac167-446">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="ac167-447">URLs 的表格依總的電子郵件總數排序，但是此欄位是隱藏的，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="ac167-447">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="ac167-448">**上** 指按一下的安全連結-包裝 URLs，依總按一下計數排序。</span><span class="sxs-lookup"><span data-stu-id="ac167-448">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="ac167-449">此欄位也不會顯示，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="ac167-449">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="ac167-450">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="ac167-450">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="ac167-451">在網路釣魚電子郵件視圖中，這些通常是可疑或惡意的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ac167-451">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="ac167-452">不過，此視圖可以包含不是威脅的 URLs，但位於網路釣魚郵件中。</span><span class="sxs-lookup"><span data-stu-id="ac167-452">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="ac167-453">在這裡未顯示 URL 按一下已開啟的連結。</span><span class="sxs-lookup"><span data-stu-id="ac167-453">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="ac167-454">這兩個 URL 表格會依照傳送動作和位置，顯示網路釣魚電子郵件中的最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="ac167-454">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="ac167-455">[！注意] 表格會顯示因警告而封鎖或訪問的 URL 按一下，因此您可以看到使用者的潛在不良連結，以及使用者已按一下的連結。</span><span class="sxs-lookup"><span data-stu-id="ac167-455">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="ac167-456">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="ac167-456">From here, you can conduct further analysis.</span></span> <span data-ttu-id="ac167-457">例如，在圖表下方，您可以在組織環境中所封鎖的電子郵件訊息中看到最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="ac167-457">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-458">![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-458">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="ac167-459">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ac167-459">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ac167-460">在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="ac167-460">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="ac167-461">這可讓您在瀏覽器中篩選您關心的電子郵件訊息，找出潛在威脅的特定 URLs，然後透過 [URL 詳細資料] 對話方塊，展開您環境中的 URL 公開知識 () 而不必將 URL 篩選器新增至瀏覽器視圖本身。</span><span class="sxs-lookup"><span data-stu-id="ac167-461">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="ac167-462">按一下 verdicts 的轉譯</span><span class="sxs-lookup"><span data-stu-id="ac167-462">Interpretation of click verdicts</span></span>

<span data-ttu-id="ac167-463">在電子郵件或 URL flyouts 中，按一下上方和篩選體驗內，您會看到不同的按一下判定值：</span><span class="sxs-lookup"><span data-stu-id="ac167-463">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="ac167-464">**無：** 無法捕獲 URL 的判定。</span><span class="sxs-lookup"><span data-stu-id="ac167-464">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="ac167-465">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-465">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="ac167-466">**允許：** 允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-466">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="ac167-467">**封鎖：** 已封鎖使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-467">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="ac167-468">**擱置的判定：** 使用者呈現在引爆擱置的頁面上。</span><span class="sxs-lookup"><span data-stu-id="ac167-468">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="ac167-469">**封鎖已被取代：** 封鎖使用者直接流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-469">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="ac167-470">但使用者 overrode 區塊以流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-470">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="ac167-471">**擱置的判定略過：** 使用者呈現的是 [引爆] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ac167-471">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="ac167-472">但使用者 overrode 郵件以存取 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-472">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="ac167-473">**錯誤：** 使用者呈現錯誤頁面，或捕獲判定結果時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="ac167-473">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="ac167-474">**失敗：** 捕獲判定時，發生未知的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ac167-474">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="ac167-475">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="ac167-475">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="ac167-476">檢閱使用者回報的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="ac167-476">Review email messages reported by users</span></span>

<span data-ttu-id="ac167-477">假設您想要查看組織中的使用者已透過 [報告郵件增益集](enable-the-report-message-add-in.md)或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為 *垃圾* 郵件、*非垃圾* 郵件或 *網路釣魚* 的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="ac167-477">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="ac167-478">若要查看，請使用瀏覽器的 [**電子郵件**  >  **提交**](threat-explorer-views.md#email--submissions)視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-478">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="ac167-479">在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-479">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="ac167-480">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="ac167-480">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="ac167-481">在 [ **View** ] 功能表中，選擇 [ **電子郵件** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="ac167-481">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-482">![電子郵件瀏覽器的視圖功能表](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-482">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="ac167-483">按一下 [ **寄件者**]，然後選擇 [ **基本** \> **報表類型**]。</span><span class="sxs-lookup"><span data-stu-id="ac167-483">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="ac167-484">選取選項，**例如 [** **網路釣魚**]，然後選取 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ac167-484">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac167-485">![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="ac167-485">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="ac167-486">報告會重新整理以顯示組織中的人員報告為網路釣魚企圖的電子郵件相關資料。</span><span class="sxs-lookup"><span data-stu-id="ac167-486">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="ac167-487">您可以使用這項資訊進行進一步的分析，並在必要時，調整[Microsoft Defender 中 Office 365 的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ac167-487">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="ac167-488">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="ac167-488">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="ac167-489">您可以在 *Microsoft Defender Office 365 方案 2* 和 *Office 365 E5* 中取得自動化調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="ac167-489">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="ac167-490">[自動化調查和回應](automated-investigation-response-office.md) 可儲存您的安全性運作小組時間和精力，以調查及緩解 cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="ac167-490">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="ac167-491">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="ac167-491">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="ac167-492">如需詳細資訊，請參閱 [範例：安全性管理員會從瀏覽器觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="ac167-492">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="ac167-493">更多使用 Explorer 和即時偵測的方式</span><span class="sxs-lookup"><span data-stu-id="ac167-493">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="ac167-494">除了本文所述的案例之外，您還可以使用更多報表選項，以供 Explorer (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="ac167-494">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="ac167-495">請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="ac167-495">See the following articles:</span></span>

- [<span data-ttu-id="ac167-496">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="ac167-496">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="ac167-497">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="ac167-497">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](./mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="ac167-498">取得威脅瀏覽器中的視圖 (和即時偵測的概覽) </span><span class="sxs-lookup"><span data-stu-id="ac167-498">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="ac167-499">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="ac167-499">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="ac167-500">Microsoft 365 Defender 中的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="ac167-500">Automated investigation and response in Microsoft 365 Defender</span></span>](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ac167-501">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="ac167-501">Required licenses and permissions</span></span>

<span data-ttu-id="ac167-502">您必須具有[Microsoft Defender Office 365](defender-for-office-365.md) ，才能使用 Explorer 或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="ac167-502">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="ac167-503">Explorer 會包含在 Office 365 方案2的 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="ac167-503">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="ac167-504">在 Office 365 方案1的 Defender 中包含即時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="ac167-504">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="ac167-505">規劃為所有應受 Office 365 Defender 保護的使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="ac167-505">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="ac167-506">瀏覽器和即時偵測顯示已授權使用者的偵測資料。</span><span class="sxs-lookup"><span data-stu-id="ac167-506">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="ac167-507">若要查看和使用 Explorer 或即時偵測，您必須具有適當的許可權，例如授與安全性管理員或安全性讀者的許可權。</span><span class="sxs-lookup"><span data-stu-id="ac167-507">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="ac167-508">針對安全性 & 合規性中心，您必須已指派下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="ac167-508">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="ac167-509">組織管理</span><span class="sxs-lookup"><span data-stu-id="ac167-509">Organization Management</span></span>
  - <span data-ttu-id="ac167-510">安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) </span><span class="sxs-lookup"><span data-stu-id="ac167-510">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="ac167-511">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="ac167-511">Security Reader</span></span>

- <span data-ttu-id="ac167-512">針對 Exchange Online，您必須在 Exchange 系統管理中心中指派下列角色之一 (<https://admin.protection.outlook.com/ecp/>) 或[Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)：</span><span class="sxs-lookup"><span data-stu-id="ac167-512">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="ac167-513">組織管理</span><span class="sxs-lookup"><span data-stu-id="ac167-513">Organization Management</span></span>
  - <span data-ttu-id="ac167-514">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="ac167-514">View-Only Organization Management</span></span>
  - <span data-ttu-id="ac167-515">僅限檢視收件者</span><span class="sxs-lookup"><span data-stu-id="ac167-515">View-Only Recipients</span></span>
  - <span data-ttu-id="ac167-516">合規性管理</span><span class="sxs-lookup"><span data-stu-id="ac167-516">Compliance Management</span></span>

<span data-ttu-id="ac167-517">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="ac167-517">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="ac167-518">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="ac167-518">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="ac167-519">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="ac167-519">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="ac167-520">威脅瀏覽器與即時偵測的差異</span><span class="sxs-lookup"><span data-stu-id="ac167-520">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="ac167-521">您可以在 Office 365 方案1的 Defender 中取得 *即時* 偵測報告。</span><span class="sxs-lookup"><span data-stu-id="ac167-521">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="ac167-522">您可以在 Office 365 方案2的 Defender 中取得 *威脅瀏覽器*。</span><span class="sxs-lookup"><span data-stu-id="ac167-522">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="ac167-523">即時偵測報告可讓您即時查看偵測。</span><span class="sxs-lookup"><span data-stu-id="ac167-523">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="ac167-524">威脅瀏覽器也會這麼做，但也會提供特定攻擊的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac167-524">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="ac167-525">*所有的電子郵件* view 都可用於威脅瀏覽器，但不會出現在即時偵測報告中。</span><span class="sxs-lookup"><span data-stu-id="ac167-525">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="ac167-526">威脅瀏覽器中包含更多篩選功能和可用的動作。</span><span class="sxs-lookup"><span data-stu-id="ac167-526">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="ac167-527">如需詳細資訊，請參閱[Microsoft defender for Office 365 Service Description：每個 defender 的功能可用性以取得 Office 365 計畫](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="ac167-527">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="other-articles"></a><span data-ttu-id="ac167-528">其他文章</span><span class="sxs-lookup"><span data-stu-id="ac167-528">Other articles</span></span>

[<span data-ttu-id="ac167-529">使用電子郵件實體頁面調查電子郵件</span><span class="sxs-lookup"><span data-stu-id="ac167-529">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
