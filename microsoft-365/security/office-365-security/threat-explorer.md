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
ms.openlocfilehash: f48bad9d8ae6fc6d68ae27a655f4bdfdefd819d0
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203741"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="79098-103">威脅瀏覽器和即時偵測</span><span class="sxs-lookup"><span data-stu-id="79098-103">Threat Explorer and Real-time detections</span></span>


<span data-ttu-id="79098-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="79098-104">**Applies to**</span></span>
- [<span data-ttu-id="79098-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="79098-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="79098-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79098-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="79098-107">如果您的組織有 [Microsoft Defender For Office 365](defender-for-office-365.md)，而您具有 [必要的許可權](#required-licenses-and-permissions)，則您 **的 Explorer** 或 **即時** 偵測 (以前的 *即時報告* -- [請參閱](#new-features-in-threat-explorer-and-real-time-detections)最近更新！ ) 。</span><span class="sxs-lookup"><span data-stu-id="79098-107">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="79098-108">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="79098-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>


|<span data-ttu-id="79098-109">使用 Microsoft Defender for Office 365 方案2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="79098-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="79098-110">使用 Microsoft Defender for Office 365 方案1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="79098-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="79098-113">瀏覽器或即時偵測可協助您的安全性作業小組調查並有效地回應威脅。</span><span class="sxs-lookup"><span data-stu-id="79098-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="79098-114">報告類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="79098-114">The report resembles the following image:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="79098-116">您可以使用此報告：</span><span class="sxs-lookup"><span data-stu-id="79098-116">With this report, you can:</span></span>

- [<span data-ttu-id="79098-117">查看 Microsoft 365 的安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="79098-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="79098-118">[查看網路釣魚 URL，然後按一下 [已判定資料]](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="79098-118">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- <span data-ttu-id="79098-119">[從瀏覽器中的視圖開始自動調查和回應](#start-automated-investigation-and-response) 程式 (Office 365 的 Defender for Office 方案 2) </span><span class="sxs-lookup"><span data-stu-id="79098-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="79098-120">調查惡意電子郵件及其他</span><span class="sxs-lookup"><span data-stu-id="79098-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="79098-121">威脅搜尋體驗的增強功能</span><span class="sxs-lookup"><span data-stu-id="79098-121">Improvements to Threat Hunting Experience</span></span>

### <a name="introduction-of-alert-id-for-mdo-alerts-within-explorerreal-time-detections-preview"></a><span data-ttu-id="79098-122">Explorer/即時偵測內 MDO 警示的警示識別碼簡介 (預覽) </span><span class="sxs-lookup"><span data-stu-id="79098-122">Introduction of Alert ID for MDO alerts within Explorer/Real-time detections (Preview)</span></span>
<span data-ttu-id="79098-123">現在，如果您從警示流覽至威脅瀏覽器，它就會在瀏覽器中開啟篩選的視圖，並以警示原則識別碼篩選 (原則識別碼為警示原則) 的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="79098-123">Today, if you navigate from an alert to Threat Explorer, it opens a filtered view within the Explorer, with the view filtered by Alert policy ID (policy ID being a unique identifier for an Alert policy).</span></span>
<span data-ttu-id="79098-124">在威脅瀏覽器和即時偵測中引入警示識別碼，使這項整合更為相關 (在威脅瀏覽器和即時偵測中看到警示) 識別碼的範例，這樣您就能看到與特定警示相關的訊息，以及電子郵件的計數。</span><span class="sxs-lookup"><span data-stu-id="79098-124">We are making this integration more relevant by introducing the alert ID (see an example of alert ID below) in Threat Explorer and Real-time detections so that you see messages which are relevant to the specific alert, as well as a count of emails.</span></span> <span data-ttu-id="79098-125">您也可以查看郵件是否為警示的一部分，以及從該郵件流覽至特定警示。</span><span class="sxs-lookup"><span data-stu-id="79098-125">You will also be able to see if a message was part of an alert, as well as navigate from that message to the specific alert.</span></span>  

<span data-ttu-id="79098-126">當您查看個別的警示時，URL 內可使用警示識別碼;範例是 `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span><span class="sxs-lookup"><span data-stu-id="79098-126">Alert ID is available within the URL when you are viewing an individual alert; an example being `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-127">![警示識別碼的篩選](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="79098-127">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-128">![詳細資料快顯視窗中的警示識別碼](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="79098-128">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

 
### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a><span data-ttu-id="79098-129">將瀏覽器的 (和即時的偵測功能延伸) 從7天到30天 (預覽的試用承租人的資料保留和搜尋限制) </span><span class="sxs-lookup"><span data-stu-id="79098-129">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days (Preview)</span></span>  
<span data-ttu-id="79098-130">在這項變更中，您將可以搜尋和篩選超過30天的電子郵件資料 (在威脅瀏覽器/即時偵測中，針對 Office P1 和 P2 試用租使用者的 Defender，進行過去7天) 的增加。</span><span class="sxs-lookup"><span data-stu-id="79098-130">As part of this change, you will be able to search for, and filter email data across 30 days (an increase from the previous 7 days) in Threat Explorer/Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="79098-131">這不會影響 P1 和 P2/E5 客戶的任何實際執行承租人，其已有30天的資料保留和搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="79098-131">This does not impact any production tenants for both P1 and P2/E5 customers, which already has the 30 day data retention and search capabilities.</span></span> 

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a><span data-ttu-id="79098-132">更新威脅瀏覽器的記錄匯出 (預覽的限制) </span><span class="sxs-lookup"><span data-stu-id="79098-132">Updated limits for Export of records for Threat Explorer (Preview)</span></span> 
<span data-ttu-id="79098-133">做為此更新的一部分，可從威脅瀏覽器匯出的電子郵件記錄的列數會從9990增加為200000記錄。</span><span class="sxs-lookup"><span data-stu-id="79098-133">As part of this update, the number of rows for Email records that can be exported from Threat Explorer is increased from 9990 to 200,000 records.</span></span> <span data-ttu-id="79098-134">目前可匯出的一組資料行將保持不變，但是列數會從目前的限制增加。</span><span class="sxs-lookup"><span data-stu-id="79098-134">The set of columns that can be exported currently will remain the same, but the number of rows will increase from the current limit.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="79098-135">威脅瀏覽器中的標記</span><span class="sxs-lookup"><span data-stu-id="79098-135">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="79098-136">使用者標記功能是在 *預覽* 中，並非所有人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="79098-136">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="79098-137">如需發行排程的相關資訊，請參閱 Microsoft 365 藍圖。</span><span class="sxs-lookup"><span data-stu-id="79098-137">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="79098-138">使用者標記識別 Microsoft Defender for Office 365 中的特定使用者群組。</span><span class="sxs-lookup"><span data-stu-id="79098-138">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="79098-139">如需標記的相關資訊（包括授權和設定），請參閱 [User tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="79098-139">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="79098-140">在威脅瀏覽器中，您可以在下列體驗中看到使用者標記的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="79098-140">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="79098-141">電子郵件格線視圖</span><span class="sxs-lookup"><span data-stu-id="79098-141">Email grid view</span></span>

<span data-ttu-id="79098-142">電子郵件窗格中的 [ **標記** ] 欄包含已套用至寄件者或收件者信箱的所有標記。</span><span class="sxs-lookup"><span data-stu-id="79098-142">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="79098-143">依預設，會先顯示「優先順序」帳戶之類的系統標記。</span><span class="sxs-lookup"><span data-stu-id="79098-143">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-144">![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="79098-144">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="79098-145">篩選</span><span class="sxs-lookup"><span data-stu-id="79098-145">Filtering</span></span>

<span data-ttu-id="79098-146">您可以使用標記做為篩選。</span><span class="sxs-lookup"><span data-stu-id="79098-146">You can use tags as a filter.</span></span> <span data-ttu-id="79098-147">只需在優先順序帳戶或特定使用者標記案例中尋找。</span><span class="sxs-lookup"><span data-stu-id="79098-147">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="79098-148">您也可以排除包含某些標記的結果。</span><span class="sxs-lookup"><span data-stu-id="79098-148">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="79098-149">將此功能與其他篩選器結合，以縮小您的調查範圍。</span><span class="sxs-lookup"><span data-stu-id="79098-149">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="79098-150">[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="79098-150">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-151">![不篩選標記](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="79098-151">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="79098-152">電子郵件詳細資料快顯視窗</span><span class="sxs-lookup"><span data-stu-id="79098-152">Email detail flyout</span></span>
<span data-ttu-id="79098-153">若要查看寄件者和收件者的個別標記，請選取 [主旨] 以開啟 [郵件詳細資料] 浮出。</span><span class="sxs-lookup"><span data-stu-id="79098-153">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="79098-154">在 [ **摘要** ] 索引標籤上，[寄件者] 和 [收件者] 標記會分開顯示（如果它們是針對電子郵件）</span><span class="sxs-lookup"><span data-stu-id="79098-154">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="79098-155">寄件者和收件者個別標記的相關資訊也會延伸至匯出的 CSV 資料，您可以在兩個不同的欄中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="79098-155">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-156">![電子郵件詳細資料標記](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="79098-156">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="79098-157">標記資訊也會顯示在 URL 中按一下 [飛入]。</span><span class="sxs-lookup"><span data-stu-id="79098-157">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="79098-158">若要查看，請移至 [網路釣魚] 或 [所有電子郵件] 視圖，然後按一下 [ **URLs** ] 或 [URL] [ **按一下** ]選取個別的 [URL] 浮出視窗，以查看有關該 URL 之按一下的其他詳細資料，包括與該按一下關聯的標記。</span><span class="sxs-lookup"><span data-stu-id="79098-158">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>


### <a name="updated-timeline-view"></a><span data-ttu-id="79098-159">更新時程表視圖</span><span class="sxs-lookup"><span data-stu-id="79098-159">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-160">![URL 標記](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="79098-160">![URL tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="79098-161">對即將推出之威脅搜尋體驗的增強 () </span><span class="sxs-lookup"><span data-stu-id="79098-161">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="79098-162">更新的電子郵件威脅資訊</span><span class="sxs-lookup"><span data-stu-id="79098-162">Updated threat information for emails</span></span>

<span data-ttu-id="79098-163">我們已著重于平臺和資料品質改進，以提升電子郵件記錄的資料準確性和一致性。</span><span class="sxs-lookup"><span data-stu-id="79098-163">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="79098-164">增強功能包括將預先傳遞和交付後資訊的整合，例如，將電子郵件上執行的動作當做處理成單一記錄。</span><span class="sxs-lookup"><span data-stu-id="79098-164">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="79098-165">其他詳細資料，例如垃圾郵件決定、實體層級威脅 (例如，哪些 URL 為惡意) ，以及最近的傳遞位置也包含在內。</span><span class="sxs-lookup"><span data-stu-id="79098-165">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="79098-166">在這些更新後，不論會影響郵件的不同傳遞事件為何，您都會看到每一封郵件的單一專案。</span><span class="sxs-lookup"><span data-stu-id="79098-166">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="79098-167">動作可包含 ZAP、手動修正 (，這表示系統管理動作) 、動態傳遞等等。</span><span class="sxs-lookup"><span data-stu-id="79098-167">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="79098-168">除了顯示惡意程式碼和網路釣魚威脅之外，您還會看到與電子郵件相關聯的垃圾郵件結論。</span><span class="sxs-lookup"><span data-stu-id="79098-168">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="79098-169">在電子郵件內，查看與電子郵件相關的所有威脅，以及對應的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="79098-169">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="79098-170">電子郵件可以有零個、一或多個威脅。</span><span class="sxs-lookup"><span data-stu-id="79098-170">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="79098-171">您會在 [電子郵件] 浮出控制項的 [ **詳細資料** ] 區段中看到目前的威脅。</span><span class="sxs-lookup"><span data-stu-id="79098-171">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="79098-172">針對多種威脅 (例如惡意程式碼和網路釣魚) ，「 **偵測技術** 」欄位會顯示威脅偵測對應，也就是識別威脅的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="79098-172">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="79098-173">一組偵測技術現在包含新的偵測方法，也包含垃圾郵件偵測技術。</span><span class="sxs-lookup"><span data-stu-id="79098-173">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="79098-174">您可以使用相同的偵測技術集合，在不同的電子郵件視圖中篩選結果， (惡意程式碼、網路釣魚程式、所有電子郵件) 。</span><span class="sxs-lookup"><span data-stu-id="79098-174">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="79098-175">判定分析可能不一定要與實體關聯。</span><span class="sxs-lookup"><span data-stu-id="79098-175">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="79098-176">舉例來說，電子郵件可能會分類為網路釣魚或垃圾郵件，但沒有以網路釣魚/垃圾郵件判定的 URLs。</span><span class="sxs-lookup"><span data-stu-id="79098-176">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="79098-177">這是因為篩選器也會在指派判定之前，評估電子郵件的內容和其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="79098-177">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="79098-178">URLs 中的威脅</span><span class="sxs-lookup"><span data-stu-id="79098-178">Threats in URLs</span></span>

<span data-ttu-id="79098-179">您現在可以在 [電子郵件彈出 **詳細資料** ] 索引標籤上看到 URL 的特定威脅。威脅可能是 *惡意* 代碼、 *網路釣魚*、 *垃圾郵件* 或 *無*。 ) </span><span class="sxs-lookup"><span data-stu-id="79098-179">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-180">![URL 威脅](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="79098-180">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="79098-181"> (即將開始的時程表視圖更新) </span><span class="sxs-lookup"><span data-stu-id="79098-181">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-182">![更新時程表視圖](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="79098-182">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="79098-183">時程表視圖會識別所有傳遞和傳遞投遞事件。</span><span class="sxs-lookup"><span data-stu-id="79098-183">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="79098-184">它包含針對這些事件子集在該時間點所識別之威脅的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="79098-184">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="79098-185">時程表視圖也提供有關 (執行的任何其他動作（如 ZAP 或手動修正) ）的相關資訊，以及該動作的結果。</span><span class="sxs-lookup"><span data-stu-id="79098-185">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="79098-186">時程表視圖資訊包含：</span><span class="sxs-lookup"><span data-stu-id="79098-186">Timeline view information includes:</span></span>

- <span data-ttu-id="79098-187">**來源：** 事件的來源。</span><span class="sxs-lookup"><span data-stu-id="79098-187">**Source:** Source of the event.</span></span> <span data-ttu-id="79098-188">可以是 admin/system/user。</span><span class="sxs-lookup"><span data-stu-id="79098-188">It can be admin/system/user.</span></span>
- <span data-ttu-id="79098-189">**事件：** 包含最上層的事件，例如原始傳遞、手動修復、ZAP、報送及動態傳遞。</span><span class="sxs-lookup"><span data-stu-id="79098-189">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="79098-190">**動作：** 做為 ZAP 或 admin 動作一部分所採取的特定動作 (例如，soft delete) 。</span><span class="sxs-lookup"><span data-stu-id="79098-190">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="79098-191">**威脅：** 涵蓋該時間點所識別的威脅 (惡意程式碼、網路釣魚和垃圾郵件) 。</span><span class="sxs-lookup"><span data-stu-id="79098-191">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="79098-192">**結果/詳細資料：** 有關動作結果的詳細資訊，例如是否以 ZAP/系統管理動作的一部分執行。</span><span class="sxs-lookup"><span data-stu-id="79098-192">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="79098-193">原始及最近的傳遞位置</span><span class="sxs-lookup"><span data-stu-id="79098-193">Original and latest delivery location</span></span>

<span data-ttu-id="79098-194">目前，我們在電子郵件格線和電子郵件飛入位置中呈現的方式。</span><span class="sxs-lookup"><span data-stu-id="79098-194">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="79098-195">[**傳遞位置**] 欄位取得 [重新命名 **_原始傳遞位置_]*。我們正在引進另一個欄位，_*_最新的傳遞位置_**。</span><span class="sxs-lookup"><span data-stu-id="79098-195">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="79098-196">**原始傳遞位置** 將會提供有關電子郵件最初傳遞位置的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="79098-196">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="79098-197">**最新的傳遞位置** 會在系統動作（如 *ZAP* 或系統動作）之後的電子郵件進入，例如 *移至 [刪除的專案*]。</span><span class="sxs-lookup"><span data-stu-id="79098-197">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="79098-198">最新的傳遞位置是用來告訴系統管理員郵件的最後一個已知位置後置或任何系統/系統管理員動作。</span><span class="sxs-lookup"><span data-stu-id="79098-198">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="79098-199">它不會包含電子郵件上的任何使用者動作。</span><span class="sxs-lookup"><span data-stu-id="79098-199">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="79098-200">例如，如果使用者刪除郵件或將郵件移至封存/pst，則不會更新郵件的 [傳遞] 位置。</span><span class="sxs-lookup"><span data-stu-id="79098-200">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="79098-201">不過，如果系統動作更新了位置 (例如，ZAP 產生的電子郵件移至隔離) 中，則 **最新的傳遞位置** 會顯示為「隔離」。</span><span class="sxs-lookup"><span data-stu-id="79098-201">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-202">![更新的傳遞位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="79098-202">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="79098-203">在某些情況下， **傳送位置** 和 **傳遞動作** 可能會顯示為「未知」：</span><span class="sxs-lookup"><span data-stu-id="79098-203">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="79098-204">如果郵件已傳遞，您可能 **會看到 [** 已傳遞] 和 [送達] **位置** 為 "Unknown"，但是收件匣規則會將郵件移至預設資料夾 (例如草稿或封存) ，而不是 [收件匣] 或 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="79098-204">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="79098-205">如果已嘗試使用系統管理員/系統動作 (（例如 ZAP) ），但找不到該郵件，則 **最新的傳遞位置** 可能是未知的。</span><span class="sxs-lookup"><span data-stu-id="79098-205">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="79098-206">通常動作會在使用者移動或刪除郵件之後發生。</span><span class="sxs-lookup"><span data-stu-id="79098-206">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="79098-207">在這種情況下，請在時程表視圖中驗證 [ **結果/詳細資料** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="79098-207">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="79098-208">尋找 [使用者已移動或刪除的郵件] 語句。</span><span class="sxs-lookup"><span data-stu-id="79098-208">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-209">![時程表的傳遞位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="79098-209">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="79098-210">其他動作</span><span class="sxs-lookup"><span data-stu-id="79098-210">Additional actions</span></span>

<span data-ttu-id="79098-211">在傳送電子郵件之後套用 *其他動作*。</span><span class="sxs-lookup"><span data-stu-id="79098-211">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="79098-212">它們可以包含由系統管理員採取的 *ZAP*、 *手動修正* (動作（如虛刪除) 、 *動態傳遞*） *，以及重新處理 (（* 已偵測為良好) 的電子郵件）。</span><span class="sxs-lookup"><span data-stu-id="79098-212">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="79098-213">在擱置中的變更中，目前出現在 [傳遞動作篩選] 中的「已移除的 ZAP」值將會不復存在。</span><span class="sxs-lookup"><span data-stu-id="79098-213">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="79098-214">您可以使用此方法，透過 **其他動作** 來搜尋所有 ZAP 嘗試的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-214">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="79098-215">**偵測技術** 和 **其他動作** 會有新的欄位和值，尤其是針對 ZAP 案例) 所做的 (。</span><span class="sxs-lookup"><span data-stu-id="79098-215">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="79098-216">您將需要評估現有的已儲存查詢和追蹤的查詢，以確保它們能夠使用新的值。</span><span class="sxs-lookup"><span data-stu-id="79098-216">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]

> ![瀏覽器中的其他動作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="79098-218">系統覆寫</span><span class="sxs-lookup"><span data-stu-id="79098-218">System overrides</span></span>

<span data-ttu-id="79098-219">*系統覆寫* 可讓您對郵件的預定送達位置產生例外狀況。</span><span class="sxs-lookup"><span data-stu-id="79098-219">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="79098-220">您可以根據威脅及篩選堆疊所識別的其他偵測，覆寫系統所提供的傳遞位置。</span><span class="sxs-lookup"><span data-stu-id="79098-220">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="79098-221">系統覆寫可透過租使用者或使用者原則加以設定，以依照原則所建議的方式傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-221">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="79098-222">覆寫可識別因設定缺口而無意間傳遞的惡意郵件，例如使用者設定的過於廣泛的安全寄件者原則。</span><span class="sxs-lookup"><span data-stu-id="79098-222">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="79098-223">這些覆寫值可以是：</span><span class="sxs-lookup"><span data-stu-id="79098-223">These override values can be:</span></span>

- <span data-ttu-id="79098-224">使用者原則允許：使用者在信箱層級建立原則，以允許網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="79098-224">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>
- <span data-ttu-id="79098-225">使用者原則封鎖：使用者會在信箱層級建立原則，以封鎖網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="79098-225">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>
- <span data-ttu-id="79098-226">組織原則允許：組織的安全小組設定原則或 Exchange 郵件流程規則 (也稱為傳輸規則) ，可允許寄件者和網域的組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="79098-226">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="79098-227">這可供一組使用者或整個組織使用。</span><span class="sxs-lookup"><span data-stu-id="79098-227">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="79098-228">由組織原則封鎖：組織的安全小組會設定原則或郵件流程規則，以封鎖組織中使用者的寄件者、網域、郵件語言或來源 Ip。</span><span class="sxs-lookup"><span data-stu-id="79098-228">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="79098-229">這可以套用到一組使用者或整個組織。</span><span class="sxs-lookup"><span data-stu-id="79098-229">This can be applied to a set of users or the entire organization.</span></span>
- <span data-ttu-id="79098-230">組織原則封鎖的檔案副檔名：組織的安全性小組會透過反惡意程式碼原則設定封鎖副檔名。</span><span class="sxs-lookup"><span data-stu-id="79098-230">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="79098-231">這些值現在會顯示在電子郵件詳細資料中，以協助調查。</span><span class="sxs-lookup"><span data-stu-id="79098-231">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="79098-232">Secops 小組也可以使用 rtf 篩選功能來篩選封鎖的副檔名。</span><span class="sxs-lookup"><span data-stu-id="79098-232">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="79098-233">[![瀏覽器中的系統覆寫](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="79098-233">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-234">![瀏覽器中的系統覆寫格線](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="79098-234">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="79098-235">URL 及點擊體驗的增強功能</span><span class="sxs-lookup"><span data-stu-id="79098-235">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="79098-236">改進功能包括：</span><span class="sxs-lookup"><span data-stu-id="79098-236">The improvements include:</span></span>

- <span data-ttu-id="79098-237">顯示已完全按一下的 URL (包括 url 任何部分之 URL 的任何查詢參數) 在 URL 快顯視窗的 [ **點擊** ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="79098-237">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="79098-238">目前，URL 網域和路徑會出現在標題列中。</span><span class="sxs-lookup"><span data-stu-id="79098-238">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="79098-239">我們正在擴充該資訊以顯示完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-239">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="79098-240">跨 URL 篩選器的修正 (*url* 與 *url 網域* *，以及 url 網域和路徑*) ：更新會影響包含 URL/按一下判定之郵件的搜尋。</span><span class="sxs-lookup"><span data-stu-id="79098-240">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="79098-241">我們為通訊協定不可知的搜尋啟用支援，因此您可以在不使用的情況下搜尋 URL `http` 。</span><span class="sxs-lookup"><span data-stu-id="79098-241">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="79098-242">根據預設，URL 搜尋會對應至 HTTP，除非明確指定另一個值。</span><span class="sxs-lookup"><span data-stu-id="79098-242">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="79098-243">例如：</span><span class="sxs-lookup"><span data-stu-id="79098-243">For example:</span></span>

   -  <span data-ttu-id="79098-244">`http://`在 [ **url**]、[ **url 網域**] 及 [ **url 網域] 和 [路徑** 篩選] 欄位中，使用或不使用前置詞進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="79098-244">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="79098-245">搜尋應該會顯示相同的結果。</span><span class="sxs-lookup"><span data-stu-id="79098-245">The searches should show the same results.</span></span>

   -  <span data-ttu-id="79098-246">`https://`在 **URL** 中搜尋前置詞。</span><span class="sxs-lookup"><span data-stu-id="79098-246">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="79098-247">若未指定任何值，則 `http://` 會假設首碼。</span><span class="sxs-lookup"><span data-stu-id="79098-247">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="79098-248">`/` 會在 **url 路徑**、 **url 網域**、 **URL 網域及路徑** 欄位的開頭和結尾略過。</span><span class="sxs-lookup"><span data-stu-id="79098-248">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="79098-249">`/` 在 [ **URL** ] 欄位的結尾會被忽略。</span><span class="sxs-lookup"><span data-stu-id="79098-249">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="79098-250">網路釣魚信賴等級</span><span class="sxs-lookup"><span data-stu-id="79098-250">Phish confidence level</span></span>

<span data-ttu-id="79098-251">網路釣魚信賴等級可協助識別將電子郵件分類為 "網路釣魚" 的置信度。</span><span class="sxs-lookup"><span data-stu-id="79098-251">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="79098-252">這兩個可能的值為 *High* 和 *Normal*。</span><span class="sxs-lookup"><span data-stu-id="79098-252">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="79098-253">在初始階段中，此篩選器只會在威脅瀏覽器的網路釣魚視圖中使用。</span><span class="sxs-lookup"><span data-stu-id="79098-253">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="79098-254">[![瀏覽器中的網路釣魚信賴等級](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="79098-254">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="79098-255">ZAP URL 信號</span><span class="sxs-lookup"><span data-stu-id="79098-255">ZAP URL signal</span></span>

<span data-ttu-id="79098-256">ZAP URL 信號通常用於 ZAP 網路釣魚警示案例，其中的電子郵件已識別為網路釣魚並在傳遞後移除。</span><span class="sxs-lookup"><span data-stu-id="79098-256">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="79098-257">此信號會在瀏覽器中使用對應的結果來連接警示。</span><span class="sxs-lookup"><span data-stu-id="79098-257">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="79098-258">這是警示的其中一個 IOCs。</span><span class="sxs-lookup"><span data-stu-id="79098-258">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="79098-259">為了改進搜尋程式，我們已更新威脅瀏覽器和即時偵測，使搜尋體驗更為一致。</span><span class="sxs-lookup"><span data-stu-id="79098-259">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="79098-260">這些變更如下所述：</span><span class="sxs-lookup"><span data-stu-id="79098-260">The changes are outlined here:</span></span>

- [<span data-ttu-id="79098-261">時區改進</span><span class="sxs-lookup"><span data-stu-id="79098-261">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="79098-262">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="79098-262">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="79098-263">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="79098-263">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="79098-264">在產品資訊更新</span><span class="sxs-lookup"><span data-stu-id="79098-264">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="79098-265">依使用者標記篩選</span><span class="sxs-lookup"><span data-stu-id="79098-265">Filter by user tags</span></span>

<span data-ttu-id="79098-266">您現在可以排序和篩選系統或自訂使用者標記，以快速抓住威脅的範圍。</span><span class="sxs-lookup"><span data-stu-id="79098-266">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="79098-267">若要深入瞭解，請參閱 [使用者標記](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="79098-267">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79098-268">依使用者標記篩選和排序目前是公開預覽。</span><span class="sxs-lookup"><span data-stu-id="79098-268">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="79098-269">在正式發行之前，您可能會充分修改此功能。</span><span class="sxs-lookup"><span data-stu-id="79098-269">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="79098-270">Microsoft 對本所提供的資訊不提供任何明示或默示的保證。</span><span class="sxs-lookup"><span data-stu-id="79098-270">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![瀏覽器中的標記欄](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="79098-272">時區改進</span><span class="sxs-lookup"><span data-stu-id="79098-272">Timezone improvements</span></span>

<span data-ttu-id="79098-273">您會看到入口網站中的電子郵件記錄以及匯出資料的時區。</span><span class="sxs-lookup"><span data-stu-id="79098-273">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="79098-274">透過電子郵件格線、[詳細資料] 飛出、電子郵件時程表及類似的電子郵件，它會在體驗上看到，所以結果集的時區也是清除的。</span><span class="sxs-lookup"><span data-stu-id="79098-274">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-275">![在瀏覽器中查看時區](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="79098-275">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="79098-276">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="79098-276">Update in the refresh process</span></span>

<span data-ttu-id="79098-277">有些使用者對自動重新整理的混淆有批註 (例如，當您變更日期時，此頁面會立即重新整理) 和手動重新整理 (其他篩選) 。</span><span class="sxs-lookup"><span data-stu-id="79098-277">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="79098-278">同樣地，移除篩選器也會導致自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="79098-278">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="79098-279">修改查詢時變更篩選可能會造成不一致的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="79098-279">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="79098-280">若要解決這些問題，我們會移至手動篩選機制。</span><span class="sxs-lookup"><span data-stu-id="79098-280">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="79098-281">從經驗的觀點來看，使用者可以從 [篩選器集和日期) 中，套用及移除不同的篩選範圍 (，然後選取 [重新整理] 按鈕，以在定義查詢之後篩選結果。</span><span class="sxs-lookup"><span data-stu-id="79098-281">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="79098-282">[重新整理] 按鈕現在也會在螢幕上強調。</span><span class="sxs-lookup"><span data-stu-id="79098-282">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="79098-283">我們也更新相關的工具提示及產品內檔。</span><span class="sxs-lookup"><span data-stu-id="79098-283">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-284">![選取 [重新整理] 以篩選結果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="79098-284">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="79098-285">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="79098-285">Chart drilldown to add to filters</span></span>

<span data-ttu-id="79098-286">您現在可以圖表圖例值新增為篩選器。</span><span class="sxs-lookup"><span data-stu-id="79098-286">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="79098-287">選取 [重新整理 **] 按鈕以** 篩選結果。</span><span class="sxs-lookup"><span data-stu-id="79098-287">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-288">![深入查看圖表以進行篩選](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="79098-288">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="79098-289">產品內資訊更新</span><span class="sxs-lookup"><span data-stu-id="79098-289">In-product information updates</span></span>

<span data-ttu-id="79098-290">產品內現在已提供其他詳細資料，例如格線內的搜尋結果總數 (請參閱) 。</span><span class="sxs-lookup"><span data-stu-id="79098-290">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="79098-291">我們已改進標籤、錯誤訊息及工具提示，以提供有關篩選、搜尋經驗及結果集的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="79098-291">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-292">![View in 產品資訊](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="79098-292">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="79098-293">威脅瀏覽器中的延伸功能</span><span class="sxs-lookup"><span data-stu-id="79098-293">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="79098-294">主要目標使用者</span><span class="sxs-lookup"><span data-stu-id="79098-294">Top targeted users</span></span>

<span data-ttu-id="79098-295">如今，我們會在惡意程式碼的 [ **主要惡意程式碼系列** ] 區段中，公開電子郵件的惡意程式碼視圖中主要目標使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="79098-295">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="79098-296">我們也會在網路釣魚和所有電子郵件視圖中擴充此視圖。</span><span class="sxs-lookup"><span data-stu-id="79098-296">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="79098-297">您將可以查看前5位目標使用者，以及每位使用者對對應視圖的嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="79098-297">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="79098-298">例如，針對網路釣魚視圖，您會看到網路釣魚嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="79098-298">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="79098-299">您可以將目標使用者的清單匯出至3000的限制，以及每個電子郵件 view 的離線分析嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="79098-299">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="79098-300">此外，選取 [嘗試次數] (例如，13在下一個影像嘗試) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就能看到該使用者的電子郵件和威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="79098-300">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-301">![主要目標使用者](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="79098-301">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="79098-302">Exchange 傳輸規則</span><span class="sxs-lookup"><span data-stu-id="79098-302">Exchange transport rules</span></span>

<span data-ttu-id="79098-303">在 [資料豐富] 的一部分中，您將可以查看套用至郵件的所有不同 Exchange transport rules (ETR) 。</span><span class="sxs-lookup"><span data-stu-id="79098-303">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="79098-304">此資訊將會出現在 [電子郵件格線] 視圖中。</span><span class="sxs-lookup"><span data-stu-id="79098-304">This information will be available in the Email grid view.</span></span> <span data-ttu-id="79098-305">若要進行查看，請選取格線中的 [ **欄選項** ]，然後從 [欄選項] 中 **新增 Exchange Transport Rule** 。</span><span class="sxs-lookup"><span data-stu-id="79098-305">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="79098-306">它也會顯示在電子郵件中的 [ **詳細資料** ] 快顯視窗中。</span><span class="sxs-lookup"><span data-stu-id="79098-306">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="79098-307">您將能看到 GUID 及已套用至郵件的傳輸規則名稱。</span><span class="sxs-lookup"><span data-stu-id="79098-307">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="79098-308">您將能夠使用傳輸規則的名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-308">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="79098-309">這是「包含」搜尋，也就是您也可以進行部分搜尋。</span><span class="sxs-lookup"><span data-stu-id="79098-309">This is a "Contains" search, which means you can do partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="79098-310">重要注意事項：</span><span class="sxs-lookup"><span data-stu-id="79098-310">Important note:</span></span>

<span data-ttu-id="79098-311">ETR 搜尋和名稱可用性取決於指派給您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="79098-311">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="79098-312">您必須具有下列其中一個角色/許可權，才能查看 ETR 名稱和搜尋。</span><span class="sxs-lookup"><span data-stu-id="79098-312">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="79098-313">如果您未指派任何這些角色，您就無法看到傳輸規則的名稱，或使用 ETR 名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-313">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="79098-314">不過，您可以在電子郵件詳細資料中看到 ETR 標籤及 GUID 資訊。</span><span class="sxs-lookup"><span data-stu-id="79098-314">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="79098-315">其他記錄流覽的電子郵件格線、電子郵件 flyouts、篩選和匯出不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="79098-315">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>

- <span data-ttu-id="79098-316">僅限 EXO-資料遺失防護：全部</span><span class="sxs-lookup"><span data-stu-id="79098-316">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="79098-317">僅限 EXO-O365SupportViewConfig： All</span><span class="sxs-lookup"><span data-stu-id="79098-317">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="79098-318">Microsoft Azure Active Directory 或 EXO-安全性系統管理員： All</span><span class="sxs-lookup"><span data-stu-id="79098-318">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
- <span data-ttu-id="79098-319">AAD 或 EXO-Security Reader： All</span><span class="sxs-lookup"><span data-stu-id="79098-319">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="79098-320">僅限 EXO-Transport Rules： All</span><span class="sxs-lookup"><span data-stu-id="79098-320">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="79098-321">僅限 EXO-View-Only 設定： All</span><span class="sxs-lookup"><span data-stu-id="79098-321">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="79098-322">在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。</span><span class="sxs-lookup"><span data-stu-id="79098-322">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-323">![Exchange 傳輸規則](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="79098-323">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="79098-324">輸入連接器</span><span class="sxs-lookup"><span data-stu-id="79098-324">Inbound connectors</span></span>

<span data-ttu-id="79098-325">連接器是一組指示，可自訂您的電子郵件流向和來源於您的 Microsoft 365 或 Office 365 組織的方式。</span><span class="sxs-lookup"><span data-stu-id="79098-325">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="79098-326">它們可讓您套用任何安全性限制或控制項。</span><span class="sxs-lookup"><span data-stu-id="79098-326">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="79098-327">在威脅瀏覽器內，您現在可以查看與電子郵件相關的連接器，並使用連接器名稱搜尋電子郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-327">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="79098-328">在 [自然] 中，連接器的搜尋是「包含」，這表示部分關鍵字搜尋也應該可以運作。</span><span class="sxs-lookup"><span data-stu-id="79098-328">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="79098-329">在主格線視圖中，[詳細資料] 飛入和匯出的 CSV，連接器會以如下所示的名稱/GUID 格式顯示：</span><span class="sxs-lookup"><span data-stu-id="79098-329">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-330">![連接器詳細資料](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="79098-330">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="79098-331">威脅瀏覽器和即時偵測中的新功能</span><span class="sxs-lookup"><span data-stu-id="79098-331">New features in Threat Explorer and Real-time detections</span></span>

- [<span data-ttu-id="79098-332">查看傳送給類比使用者和網域的網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="79098-332">View phishing emails sent to impersonated users and domains</span></span>](#view-phishing-emails-sent-to-impersonated-users-and-domains)
-  [<span data-ttu-id="79098-333">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="79098-333">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="79098-334">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="79098-334">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="79098-335">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="79098-335">Export URL click data</span></span>](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a><span data-ttu-id="79098-336">查看傳送給類比使用者和網域的網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="79098-336">View phishing emails sent to impersonated users and domains</span></span>

<span data-ttu-id="79098-337">若要識別對類比使用者的使用者和網域的網頁網路嘗試，必須新增至 *要保護的使用者* 清單中。</span><span class="sxs-lookup"><span data-stu-id="79098-337">To identify phishing attempts against users and domains that are impersonated users must be added to the list of *Users to protect*.</span></span> <span data-ttu-id="79098-338">對於網域，系統管理員必須啟用 *組織網域*，或將功能變數名稱新增至 *要保護的網域*。</span><span class="sxs-lookup"><span data-stu-id="79098-338">For domains, admins must either enable *Organization domains*, or add a domain name to *Domains to protect*.</span></span> <span data-ttu-id="79098-339">您 *可以在模擬區段的*[*反網路釣魚原則] 頁面* 上找到要保護的網域。</span><span class="sxs-lookup"><span data-stu-id="79098-339">The domains to protect are found on the *Anti-Phishing policy page* in the *Impersonation* section.</span></span>

<span data-ttu-id="79098-340">若要查看網路釣魚郵件和搜尋模擬的使用者或網域，請使用瀏覽器的 [電子郵件 > 網路釣魚視圖](threat-explorer-views.md) 。</span><span class="sxs-lookup"><span data-stu-id="79098-340">To review phish messages and search for impersonated users or domains, use the [Email > Phish view](threat-explorer-views.md) of Explorer.</span></span>

<span data-ttu-id="79098-341">本範例會使用威脅瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="79098-341">This example uses Threat Explorer.</span></span>

1. <span data-ttu-id="79098-342">在 [ [安全性 & 規範中心](https://protection.office.com) ] (中 https://protection.office.com) ，選擇 [威脅管理] > Explorer (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="79098-342">In the [Security & Compliance Center](https://protection.office.com) (https://protection.office.com), choose Threat management > Explorer (or Real-time detections).</span></span>

2. <span data-ttu-id="79098-343">在 [View] 功能表中，選擇 [電子郵件 > 網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="79098-343">In the View menu, choose Email > Phish.</span></span>

   <span data-ttu-id="79098-344">您可以在這裡選擇模擬的 **網域** 或 **模仿的使用者**。</span><span class="sxs-lookup"><span data-stu-id="79098-344">Here you can choose **impersonated domain** or **impersonated user**.</span></span>

3. <span data-ttu-id="79098-345">**請選取 [** 模擬 **網域**]，然後在 textbox 中輸入受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="79098-345">**EITHER** select **Impersonated domain**, and then type a protected domain in the textbox.</span></span>

   <span data-ttu-id="79098-346">例如，搜尋受保護的功能變數名稱（如 *contoso*、 *contoso.com* 或 *contoso.com.au*）。</span><span class="sxs-lookup"><span data-stu-id="79098-346">For example, search for protected domain names like *contoso*, *contoso.com*, or *contoso.com.au*.</span></span>

4. <span data-ttu-id="79098-347">在 [電子郵件] 索引標籤 > 詳細資料] 索引標籤下，選取任何郵件的主旨，以查看類比網域/偵測到的位置等其他類比</span><span class="sxs-lookup"><span data-stu-id="79098-347">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span></span>

5. <span data-ttu-id="79098-348">**或** 選取 [模擬 **使用者** ]，然後在 textbox 中輸入受保護使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="79098-348">**OR** Select **Impersonated user** and type a protected user's email address in the textbox.</span></span>

6. <span data-ttu-id="79098-349">在 [**電子郵件** 索引標籤詳細資料] 索引標籤中選取任何 **郵件的主旨**  >   ，以查看有關使用者或網域的其他模擬資訊和偵測 *到的位置*。</span><span class="sxs-lookup"><span data-stu-id="79098-349">Select the **Subject** of any message under **Email tab** > **Details tab** to see additional impersonation information about the user or domain, and the *Detected location*.</span></span>

:::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="顯示偵測位置之受保護使用者的威脅瀏覽器詳細資料窗格，以及偵測到使用者) 的網路釣魚模擬 (所偵測到的威脅。":::

> [!TIP]
> <span data-ttu-id="79098-351">**為了獲得最佳結果**，請使用 *完整電子郵件地址* 來搜尋受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="79098-351">**For best results**, use *full email addresses* to search protected users.</span></span> <span data-ttu-id="79098-352">當您搜尋 *firstname.lastname@contoso.com* 時（例如，調查使用者模擬時），您可以更快速且更順利地找到您的受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="79098-352">You will find your protected user quicker and more successfully if you search for *firstname.lastname@contoso.com*, for example, when investigating user impersonation.</span></span> <span data-ttu-id="79098-353">搜尋受保護的網域時，搜尋會以根域 (contoso.com，例如) ，以及功能變數名稱 (*contoso*) 。</span><span class="sxs-lookup"><span data-stu-id="79098-353">When searching for a protected domain the search will take the root domain (contoso.com, for example), and the domain name (*contoso*).</span></span> <span data-ttu-id="79098-354">搜尋根網域 *contoso.com* 將同時傳回 *contoso.com* 和功能變數名稱 *contoso* 的 impersonations。</span><span class="sxs-lookup"><span data-stu-id="79098-354">Searching for the root domain *contoso.com* will return both impersonations of *contoso.com* and the domain name *contoso*.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="79098-355">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="79098-355">Preview email header and download email body</span></span>

<span data-ttu-id="79098-356">您現在可以預覽電子郵件頭，並下載威脅瀏覽器管理員的電子郵件內文。系統管理員可以分析已下載的標頭/電子郵件，以取得威脅。</span><span class="sxs-lookup"><span data-stu-id="79098-356">You can now preview an email header and download the email body in Threat Explorer Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="79098-357">因為下載電子郵件可能會危及資訊的危險性，所以此程式是由以角色為基礎的存取控制 (RBAC) 所控制。</span><span class="sxs-lookup"><span data-stu-id="79098-357">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="79098-358">新的角色、 *預覽*，必須新增至其他角色群組 (例如安全作業或安全性系統管理員) ，以授與透過所有電子郵件消息查看下載郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="79098-358">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="79098-359">不過，若要在威脅瀏覽器) 中查看郵件所需的 (以外，查看電子郵件標頭並不需要任何其他角色。</span><span class="sxs-lookup"><span data-stu-id="79098-359">However, viewing email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="79098-360">瀏覽器和即時偵測也會取得新的欄位，可提供您的電子郵件所在位置更完整的畫面。</span><span class="sxs-lookup"><span data-stu-id="79098-360">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="79098-361">這些變更可使搜尋更輕鬆進行安全性 Op。</span><span class="sxs-lookup"><span data-stu-id="79098-361">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="79098-362">不過，主要結果是您可以快速知道問題電子郵件訊息的位置。</span><span class="sxs-lookup"><span data-stu-id="79098-362">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="79098-363">這是如何達成？</span><span class="sxs-lookup"><span data-stu-id="79098-363">How is this done?</span></span> <span data-ttu-id="79098-364">傳遞狀態現在會分解成兩個欄：</span><span class="sxs-lookup"><span data-stu-id="79098-364">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="79098-365">**傳遞動作** -電子郵件的狀態。</span><span class="sxs-lookup"><span data-stu-id="79098-365">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="79098-366">**傳遞位置** -傳送電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="79098-366">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="79098-367">*傳遞動作* 是由於現有的原則或偵測，而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="79098-367">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="79098-368">電子郵件可能的動作如下：</span><span class="sxs-lookup"><span data-stu-id="79098-368">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="79098-369">已傳遞</span><span class="sxs-lookup"><span data-stu-id="79098-369">Delivered</span></span>|<span data-ttu-id="79098-370">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="79098-370">Junked</span></span>|<span data-ttu-id="79098-371">已封鎖</span><span class="sxs-lookup"><span data-stu-id="79098-371">Blocked</span></span>|<span data-ttu-id="79098-372">已取代</span><span class="sxs-lookup"><span data-stu-id="79098-372">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="79098-373">電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以存取。</span><span class="sxs-lookup"><span data-stu-id="79098-373">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="79098-374">電子郵件已傳送至使用者的 [垃圾郵件] 或 [已刪除] 資料夾，使用者可以存取它。</span><span class="sxs-lookup"><span data-stu-id="79098-374">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="79098-375">隔離、失敗或丟棄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-375">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="79098-376">使用者無法存取這些郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-376">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="79098-377">電子郵件有惡意附件取代 .txt 檔案，以表明附件是惡意的。</span><span class="sxs-lookup"><span data-stu-id="79098-377">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="79098-378">以下是使用者可及無法看到的專案：</span><span class="sxs-lookup"><span data-stu-id="79098-378">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="79098-379">使用者可以存取</span><span class="sxs-lookup"><span data-stu-id="79098-379">Accessible to end users</span></span>|<span data-ttu-id="79098-380">使用者無法存取 </span><span class="sxs-lookup"><span data-stu-id="79098-380">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="79098-381">已傳遞</span><span class="sxs-lookup"><span data-stu-id="79098-381">Delivered</span></span>|<span data-ttu-id="79098-382">已封鎖</span><span class="sxs-lookup"><span data-stu-id="79098-382">Blocked</span></span>|
|<span data-ttu-id="79098-383">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="79098-383">Junked</span></span>|<span data-ttu-id="79098-384">已取代</span><span class="sxs-lookup"><span data-stu-id="79098-384">Replaced</span></span>|

<span data-ttu-id="79098-385">**傳遞位置** 顯示執行後續傳遞的原則及偵測結果。</span><span class="sxs-lookup"><span data-stu-id="79098-385">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="79098-386">它會連結至 **_傳遞動作_**。</span><span class="sxs-lookup"><span data-stu-id="79098-386">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="79098-387">可能的值如下：</span><span class="sxs-lookup"><span data-stu-id="79098-387">These are the possible values:</span></span>

- <span data-ttu-id="79098-388">*收件匣或資料夾*：電子郵件的收件匣或資料夾 (會根據您的電子郵件規則) 。</span><span class="sxs-lookup"><span data-stu-id="79098-388">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="79098-389">*部署或外部*：信箱不存在於雲端上，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="79098-389">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="79098-390">[垃圾郵件]*資料夾*：電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="79098-390">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="79098-391">「*刪除的郵件」資料夾*：在使用者的 [刪除的郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-391">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="79098-392">*隔離*：電子郵件是隔離的，而不是在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="79098-392">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="79098-393">*失敗*；電子郵件無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="79098-393">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="79098-394">*丟斷*：電子郵件在郵件流程中遺失。</span><span class="sxs-lookup"><span data-stu-id="79098-394">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="79098-395">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="79098-395">Email timeline</span></span>

<span data-ttu-id="79098-396">**電子郵件時程表** 是新的瀏覽器功能，可改善系統管理員的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="79098-396">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="79098-397">它會削減檢查不同位置所花費的時間，以嘗試瞭解該事件。</span><span class="sxs-lookup"><span data-stu-id="79098-397">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="79098-398">當電子郵件到達時，發生多個事件或接近該郵件時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="79098-398">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="79098-399">您的電子郵件投遞之後所發生的某些事件會在 [ **特殊動作** ] 欄中捕獲。</span><span class="sxs-lookup"><span data-stu-id="79098-399">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="79098-400">系統管理員可以合併時程表中的資訊，並在郵件投遞後採取特殊的動作，以深入瞭解其原則的運作方式（即最後一次路由傳送郵件的位置），而且在某些情況下，最後評估是什麼。</span><span class="sxs-lookup"><span data-stu-id="79098-400">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="79098-401">如需詳細資訊，請參閱 [調查並修復 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="79098-401">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="79098-402">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="79098-402">Export URL click data</span></span>

<span data-ttu-id="79098-403">您現在可以將 URL 按一下的報告匯出至 Microsoft Excel 以查看其 **網路消息識別碼** ，並 **按一下**[判斷]，以協助說明您的 URL 按一下流量的來源。</span><span class="sxs-lookup"><span data-stu-id="79098-403">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="79098-404">其運作方式如下：在「威脅管理」的 Office 365 快速啟動列上，請遵循下列連結：</span><span class="sxs-lookup"><span data-stu-id="79098-404">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="79098-405">**瀏覽器** \>**查看網路釣魚** \>**按一下** \>**Top URLs** Or **URL 上擊** \> 選取 [任何記錄] 以開啟 [URL] 浮出控制項。</span><span class="sxs-lookup"><span data-stu-id="79098-405">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="79098-406">當您在清單中選取 URL 時，您會在飛出面板上看到新的 [ **匯出** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="79098-406">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="79098-407">使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。</span><span class="sxs-lookup"><span data-stu-id="79098-407">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="79098-408">請遵循此路徑，以取得即時偵測報告中的相同位置：</span><span class="sxs-lookup"><span data-stu-id="79098-408">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="79098-409">**瀏覽器** \>**即時偵測** \>**查看網路釣魚** \>**URLs** \>**Top URLs** 或 **top 按一下** \> 選取 [任何記錄] 以開啟 [URL] 浮出 \> ] 流覽至 [**點擊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="79098-409">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="79098-410">當您使用瀏覽器或關聯的協力廠商工具來搜尋識別碼時，網路郵件識別碼會對應按一下 [回復至特定郵件]。</span><span class="sxs-lookup"><span data-stu-id="79098-410">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="79098-411">這類搜尋會識別與按一下結果關聯的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="79098-411">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="79098-412">讓相關網路郵件識別碼能夠更快速且更強大的分析。</span><span class="sxs-lookup"><span data-stu-id="79098-412">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79098-413">![瀏覽器中的按一下 tab 鍵](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="79098-413">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="79098-414">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="79098-414">See malware detected in email by technology</span></span>

<span data-ttu-id="79098-415">假設您想要查看透過 Microsoft 365 技術排序的電子郵件中偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="79098-415">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="79098-416">若要這麼做，請使用瀏覽器的 [電子郵件 > 惡意](threat-explorer-views.md#email--malware) 代碼視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="79098-416">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="79098-417">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="79098-417">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="79098-418">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="79098-418">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="79098-419">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="79098-419">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-420">![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="79098-420">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="79098-421">按一下 [ **寄件者**]，然後選擇 [ **基本** \> **偵測技術**]。</span><span class="sxs-lookup"><span data-stu-id="79098-421">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="79098-422">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="79098-422">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-423">![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="79098-423">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="79098-424">選擇 [選項]。</span><span class="sxs-lookup"><span data-stu-id="79098-424">Choose an option.</span></span> <span data-ttu-id="79098-425">然後選取 [重新整理] **按鈕，套用** 該篩選。</span><span class="sxs-lookup"><span data-stu-id="79098-425">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-426">![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="79098-426">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="79098-427">報告會進行重新整理，以顯示惡意程式碼在電子郵件中偵測到的結果，並使用您選取的技術選項。</span><span class="sxs-lookup"><span data-stu-id="79098-427">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="79098-428">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="79098-428">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="79098-429">查看網路釣魚 URL，然後按一下 [已判定資料]</span><span class="sxs-lookup"><span data-stu-id="79098-429">View phishing URL and click verdict data</span></span>

<span data-ttu-id="79098-430">假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="79098-430">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="79098-431">若要識別所按一下的 URLs，必須設定 [安全連結](safe-links.md) 。</span><span class="sxs-lookup"><span data-stu-id="79098-431">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="79098-432">請確定您已設定 [安全連結原則](set-up-safe-links-policies.md) 的 [保護] 和 [記錄] 按一下 [安全連結] 中的 [verdicts]。</span><span class="sxs-lookup"><span data-stu-id="79098-432">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="79098-433">若要查看郵件中的網路釣魚 URLs，並按一下網路釣魚郵件中 URLs，請使用瀏覽器或即時偵測的 [**電子郵件**  >  **網路釣魚**](threat-explorer-views.md#email--phish)視圖。</span><span class="sxs-lookup"><span data-stu-id="79098-433">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="79098-434">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="79098-434">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="79098-435">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="79098-435">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="79098-436">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **釣魚網絡**]。</span><span class="sxs-lookup"><span data-stu-id="79098-436">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-437">![網路釣魚內容中瀏覽器的視圖功能表](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="79098-437">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="79098-438">按一下 [ **寄件者**]，然後選擇 **URLs** \> **按一下 [判定**]。</span><span class="sxs-lookup"><span data-stu-id="79098-438">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="79098-439">選取一個或多個選項（例如 **封鎖** 和 **封鎖**），然後在與套用該篩選的選項相同的列上選取 [重新整理 **] 按鈕。**</span><span class="sxs-lookup"><span data-stu-id="79098-439">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="79098-440">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="79098-440">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-441">![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="79098-441">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="79098-442">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="79098-442">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="79098-443">**Top URLs** 是您篩選的郵件中 URLs，以及每個 URL 的電子郵件傳遞動作計數。</span><span class="sxs-lookup"><span data-stu-id="79098-443">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="79098-444">在網路釣魚電子郵件視圖中，此清單通常包含合法的 URLs。</span><span class="sxs-lookup"><span data-stu-id="79098-444">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="79098-445">攻擊者會在其郵件中混合使用良好和不良的 URLs，以嘗試傳遞，但它們會使惡意連結看起來更有趣。</span><span class="sxs-lookup"><span data-stu-id="79098-445">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="79098-446">URLs 的表格依總的電子郵件總數排序，但是此欄位是隱藏的，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="79098-446">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="79098-447">**上** 指按一下的安全連結-包裝 URLs，依總按一下計數排序。</span><span class="sxs-lookup"><span data-stu-id="79098-447">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="79098-448">此欄位也不會顯示，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="79098-448">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="79098-449">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="79098-449">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="79098-450">在網路釣魚電子郵件視圖中，這些通常是可疑或惡意的 URLs。</span><span class="sxs-lookup"><span data-stu-id="79098-450">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="79098-451">不過，此視圖可以包含不是威脅的 URLs，但位於網路釣魚郵件中。</span><span class="sxs-lookup"><span data-stu-id="79098-451">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="79098-452">在這裡未顯示 URL 按一下已開啟的連結。</span><span class="sxs-lookup"><span data-stu-id="79098-452">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="79098-453">這兩個 URL 表格會依照傳送動作和位置，顯示網路釣魚電子郵件中的最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="79098-453">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="79098-454">[！注意] 表格會顯示因警告而封鎖或訪問的 URL 按一下，因此您可以看到使用者的潛在不良連結，以及使用者已按一下的連結。</span><span class="sxs-lookup"><span data-stu-id="79098-454">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="79098-455">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="79098-455">From here, you can conduct further analysis.</span></span> <span data-ttu-id="79098-456">例如，在圖表下方，您可以在組織環境中所封鎖的電子郵件訊息中看到最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="79098-456">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-457">![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="79098-457">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="79098-458">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="79098-458">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="79098-459">在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="79098-459">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="79098-460">這可讓您在瀏覽器中篩選您關心的電子郵件訊息，找出潛在威脅的特定 URLs，然後透過 [URL 詳細資料] 對話方塊，展開您環境中的 URL 公開知識 () 而不必將 URL 篩選器新增至瀏覽器視圖本身。</span><span class="sxs-lookup"><span data-stu-id="79098-460">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="79098-461">按一下 verdicts 的轉譯</span><span class="sxs-lookup"><span data-stu-id="79098-461">Interpretation of click verdicts</span></span>

<span data-ttu-id="79098-462">在電子郵件或 URL flyouts 中，按一下上方和篩選體驗內，您會看到不同的按一下判定值：</span><span class="sxs-lookup"><span data-stu-id="79098-462">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="79098-463">**無：** 無法捕獲 URL 的判定。</span><span class="sxs-lookup"><span data-stu-id="79098-463">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="79098-464">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-464">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="79098-465">**允許：** 允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-465">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="79098-466">**封鎖：** 已封鎖使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-466">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="79098-467">**擱置的判定：** 使用者呈現在引爆擱置的頁面上。</span><span class="sxs-lookup"><span data-stu-id="79098-467">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="79098-468">**封鎖已被取代：** 封鎖使用者直接流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-468">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="79098-469">但使用者 overrode 區塊以流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-469">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="79098-470">**擱置的判定略過：** 使用者呈現的是 [引爆] 頁面。</span><span class="sxs-lookup"><span data-stu-id="79098-470">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="79098-471">但使用者 overrode 郵件以存取 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-471">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="79098-472">**錯誤：** 使用者呈現錯誤頁面，或捕獲判定結果時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="79098-472">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="79098-473">**失敗：** 捕獲判定時，發生未知的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="79098-473">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="79098-474">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="79098-474">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="79098-475">檢閱使用者回報的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="79098-475">Review email messages reported by users</span></span>

<span data-ttu-id="79098-476">假設您想要查看組織中的使用者已透過 [報告郵件增益集](enable-the-report-message-add-in.md)或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為 *垃圾* 郵件、*非垃圾* 郵件或 *網路釣魚* 的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="79098-476">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="79098-477">若要查看，請使用瀏覽器的 [**電子郵件**  >  **提交**](threat-explorer-views.md#email--submissions)視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="79098-477">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="79098-478">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="79098-478">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="79098-479">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="79098-479">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="79098-480">在 [ **View** ] 功能表中，選擇 [ **電子郵件** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="79098-480">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-481">![電子郵件瀏覽器的視圖功能表](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="79098-481">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="79098-482">按一下 [ **寄件者**]，然後選擇 [ **基本** \> **報表類型**]。</span><span class="sxs-lookup"><span data-stu-id="79098-482">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="79098-483">選取選項，**例如 [** **網路釣魚**]，然後選取 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="79098-483">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79098-484">![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="79098-484">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="79098-485">報告會重新整理以顯示組織中的人員報告為網路釣魚企圖的電子郵件相關資料。</span><span class="sxs-lookup"><span data-stu-id="79098-485">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="79098-486">您可以使用這項資訊進行進一步的分析，必要時，調整 [Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="79098-486">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="79098-487">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="79098-487">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="79098-488">*Microsoft Defender For Office 365 方案 2* 和 *Office 365 E5* 中提供自動調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="79098-488">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="79098-489">[自動化調查和回應](automated-investigation-response-office.md) 可儲存您的安全性運作小組時間和精力，以調查及緩解 cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="79098-489">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="79098-490">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="79098-490">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="79098-491">如需詳細資訊，請參閱 [範例：安全性管理員會從瀏覽器觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="79098-491">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="79098-492">更多使用 Explorer 和即時偵測的方式</span><span class="sxs-lookup"><span data-stu-id="79098-492">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="79098-493">除了本文所述的案例之外，您還可以使用更多報表選項，以供 Explorer (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="79098-493">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="79098-494">請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="79098-494">See the following articles:</span></span>

- [<span data-ttu-id="79098-495">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="79098-495">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="79098-496">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="79098-496">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](./mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="79098-497">取得威脅瀏覽器中的視圖 (和即時偵測的概覽) </span><span class="sxs-lookup"><span data-stu-id="79098-497">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="79098-498">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="79098-498">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="79098-499">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="79098-499">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="79098-500">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="79098-500">Required licenses and permissions</span></span>

<span data-ttu-id="79098-501">您必須擁有 [Microsoft Defender For Office 365](defender-for-office-365.md) ，才能使用 Explorer 或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="79098-501">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="79098-502">Explorer 會包含在 Office 365 的 Defender for Office 中方案2。</span><span class="sxs-lookup"><span data-stu-id="79098-502">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="79098-503">Office 365 方案1中包含即時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="79098-503">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="79098-504">規劃為所有應受 Defender for Office 365 保護的使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="79098-504">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="79098-505">瀏覽器和即時偵測顯示已授權使用者的偵測資料。</span><span class="sxs-lookup"><span data-stu-id="79098-505">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="79098-506">若要查看和使用 Explorer 或即時偵測，您必須具有適當的許可權，例如授與安全性管理員或安全性讀者的許可權。</span><span class="sxs-lookup"><span data-stu-id="79098-506">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="79098-507">針對安全性 & 合規性中心，您必須已指派下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="79098-507">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="79098-508">組織管理</span><span class="sxs-lookup"><span data-stu-id="79098-508">Organization Management</span></span>
  - <span data-ttu-id="79098-509">安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) </span><span class="sxs-lookup"><span data-stu-id="79098-509">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="79098-510">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="79098-510">Security Reader</span></span>

- <span data-ttu-id="79098-511">若為 Exchange Online，您必須在 Exchange 系統管理中心中指派下列其中一個角色 (<https://admin.protection.outlook.com/ecp/>) 或 [exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)：</span><span class="sxs-lookup"><span data-stu-id="79098-511">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="79098-512">組織管理</span><span class="sxs-lookup"><span data-stu-id="79098-512">Organization Management</span></span>
  - <span data-ttu-id="79098-513">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="79098-513">View-Only Organization Management</span></span>
  - <span data-ttu-id="79098-514">僅限檢視收件者</span><span class="sxs-lookup"><span data-stu-id="79098-514">View-Only Recipients</span></span>
  - <span data-ttu-id="79098-515">合規性管理</span><span class="sxs-lookup"><span data-stu-id="79098-515">Compliance Management</span></span>

<span data-ttu-id="79098-516">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="79098-516">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="79098-517">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="79098-517">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="79098-518">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="79098-518">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="79098-519">威脅瀏覽器與即時偵測的差異</span><span class="sxs-lookup"><span data-stu-id="79098-519">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="79098-520">您可以在 Office 365 的 Defender for Office 方案1中取得 *即時* 偵測報告。</span><span class="sxs-lookup"><span data-stu-id="79098-520">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="79098-521">*威脅瀏覽器* 適用于 Office 365 方案2的 Defender。</span><span class="sxs-lookup"><span data-stu-id="79098-521">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="79098-522">即時偵測報告可讓您即時查看偵測。</span><span class="sxs-lookup"><span data-stu-id="79098-522">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="79098-523">威脅瀏覽器也會這麼做，但也會提供特定攻擊的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="79098-523">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="79098-524">*所有的電子郵件* view 都可用於威脅瀏覽器，但不會出現在即時偵測報告中。</span><span class="sxs-lookup"><span data-stu-id="79098-524">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="79098-525">威脅瀏覽器中包含更多篩選功能和可用的動作。</span><span class="sxs-lookup"><span data-stu-id="79098-525">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="79098-526">如需詳細資訊，請參閱 [Microsoft defender For office 365 服務說明：每個 Defender For office 365 方案中可用的功能](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="79098-526">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="other-articles"></a><span data-ttu-id="79098-527">其他文章</span><span class="sxs-lookup"><span data-stu-id="79098-527">Other articles</span></span>

[<span data-ttu-id="79098-528">使用電子郵件實體頁面調查電子郵件</span><span class="sxs-lookup"><span data-stu-id="79098-528">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)