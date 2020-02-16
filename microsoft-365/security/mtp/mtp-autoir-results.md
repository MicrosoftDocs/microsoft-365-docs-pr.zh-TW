---
title: 檢視自動調查的詳細資料和結果
description: 在自動調查過程中和完成之後，您就可以查看結果和重要結果
keywords: 自動, 調查, 結果, 分析, 詳細資料, 修正, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 08aa1f0c252d931ab1abf078b1c0cfcf7d9b43a2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083748"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="12ecf-104">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="12ecf-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="12ecf-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="12ecf-105">**Applies to:**</span></span>
- <span data-ttu-id="12ecf-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="12ecf-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="12ecf-107">當您在 Microsoft 威脅防護中進行自動調查時，可在與自動調查處理期間以及處理完成後取得該調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="12ecf-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="12ecf-108">如果您擁有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以在調查詳細資料檢視中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="12ecf-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="12ecf-109">調查詳細資料檢視可提供您最新的狀態，以及核准任何待核准動作的能力。</span><span class="sxs-lookup"><span data-stu-id="12ecf-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![調查詳細資料](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="12ecf-111">開啟調查詳細資料檢視</span><span class="sxs-lookup"><span data-stu-id="12ecf-111">Open the investigation details view</span></span>

<span data-ttu-id="12ecf-112">您可以使用下列其中一種方法開啟調查詳細資料檢視：</span><span class="sxs-lookup"><span data-stu-id="12ecf-112">You can open the investigation details view by using one of the following methods:</span></span>
- <span data-ttu-id="12ecf-113">[選取 [控制中心] 中的項目](#select-an-item-in-the-action-center)</span><span class="sxs-lookup"><span data-stu-id="12ecf-113">[Select an item in the Action center](#select-an-item-in-the-action-center)</span></span>
- [<span data-ttu-id="12ecf-114">從事件詳細資料頁面中選取調查</span><span class="sxs-lookup"><span data-stu-id="12ecf-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="12ecf-115">選取 [控制中心] 中的項目</span><span class="sxs-lookup"><span data-stu-id="12ecf-115">Select an item in the Action center</span></span>

<span data-ttu-id="12ecf-116">使用 [控制中心] 查看處於待核准狀態 (在 [待核准]\*\*\*\* 索引標籤上) 或已核准 (在 [歷史記錄]\*\*\*\* 索引標籤上) 的動作。</span><span class="sxs-lookup"><span data-stu-id="12ecf-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="12ecf-117">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="12ecf-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="12ecf-118">在功能窗格中，選擇 [控制中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12ecf-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="12ecf-119">在 [待核准]\*\*\*\* 或 [歷史記錄]\*\*\*\* 索引標籤上，選取一個項目。</span><span class="sxs-lookup"><span data-stu-id="12ecf-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="12ecf-120">如果您擁有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以核准 (或拒絕) 待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="12ecf-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="12ecf-121">從事件詳細資料頁面開啟調查</span><span class="sxs-lookup"><span data-stu-id="12ecf-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="12ecf-122">使用事件詳細資料頁面來查看事件的詳細資訊，包括觸發任何受影響裝置、使用者帳戶或信箱之資訊的警示。</span><span class="sxs-lookup"><span data-stu-id="12ecf-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="12ecf-123">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="12ecf-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="12ecf-124">在功能窗格中，選擇 [事件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12ecf-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="12ecf-125">選取清單中的項目以開啟事件詳細資料檢視。</span><span class="sxs-lookup"><span data-stu-id="12ecf-125">Select an item in the list to open the incident details view.</span></span><br/>![事件詳細資料](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="12ecf-127">在 [調查]\*\*\*\* 索引標籤上，選取清單中的調查。</span><span class="sxs-lookup"><span data-stu-id="12ecf-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="12ecf-128">調查詳細資料</span><span class="sxs-lookup"><span data-stu-id="12ecf-128">Investigation details</span></span>

<span data-ttu-id="12ecf-129">使用調查詳細資料檢視，查看與調查相關的過去、目前和待核准的活動。</span><span class="sxs-lookup"><span data-stu-id="12ecf-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="12ecf-130">調查詳細資料檢視類似以下影像：</span><span class="sxs-lookup"><span data-stu-id="12ecf-130">The investigation details view resembles the following image:</span></span>

![調查詳細資料](../../media/mtp-air-investdetails.png)

<span data-ttu-id="12ecf-132">在調查詳細資料檢視中，您可以在 [調查圖表]\*\*\*\*、[警示]\*\*\*\*、[裝置]\*\*\*\*、[身分識別]\*\*\*\*、[重要結果]\*\*\*\*、[實體]\*\*\*\*、**[記錄]**，以及 [待核准的動作]\*\*\*\* 索引標籤上查看資訊，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="12ecf-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="12ecf-133">索引標籤</span><span class="sxs-lookup"><span data-stu-id="12ecf-133">Tab</span></span>    |<span data-ttu-id="12ecf-134">描述</span><span class="sxs-lookup"><span data-stu-id="12ecf-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="12ecf-135">調查圖表</span><span class="sxs-lookup"><span data-stu-id="12ecf-135">Investigation graph</span></span>    |<span data-ttu-id="12ecf-136">提供調查的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="12ecf-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="12ecf-137">描述實體並列出發現的威脅和警示，以及是否有任何待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="12ecf-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="12ecf-138">您可以按一下圖表上的項目來查看更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="12ecf-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="12ecf-139">例如，按一下 [找到的威脅] \*\*\*\* 圖示會帶您移至 [重要結果]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="12ecf-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="12ecf-140">警示</span><span class="sxs-lookup"><span data-stu-id="12ecf-140">Alerts</span></span> |<span data-ttu-id="12ecf-141">列出與調查相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="12ecf-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="12ecf-142">警示可能來自使用者電腦上的威脅防護功能、Office 應用程式、雲端 App 安全性及其他 Microsoft 365 威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="12ecf-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="12ecf-143">裝置</span><span class="sxs-lookup"><span data-stu-id="12ecf-143">Devices</span></span>|<span data-ttu-id="12ecf-144">列出調查中包含的電腦及其修正等級。</span><span class="sxs-lookup"><span data-stu-id="12ecf-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="12ecf-145">重要結果</span><span class="sxs-lookup"><span data-stu-id="12ecf-145">Key findings</span></span>   |<span data-ttu-id="12ecf-146">列出調查結果，以及狀態和已執行或待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="12ecf-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="12ecf-147">您可以在這個索引標籤上核准裝置和身分識別的待核准動作。</span><span class="sxs-lookup"><span data-stu-id="12ecf-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="12ecf-148">實體</span><span class="sxs-lookup"><span data-stu-id="12ecf-148">Entities</span></span>   |<span data-ttu-id="12ecf-149">列出與調查相關聯的使用者活動、檔案、處理程序、服務、驅動程式、IP 位址和持續性方法，以及狀態和採取的動作。</span><span class="sxs-lookup"><span data-stu-id="12ecf-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="12ecf-150">記錄</span><span class="sxs-lookup"><span data-stu-id="12ecf-150">Log</span></span>    |<span data-ttu-id="12ecf-151">提供調查過程中所有步驟的詳細資訊，以及狀態。</span><span class="sxs-lookup"><span data-stu-id="12ecf-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="12ecf-152">待核准的動作</span><span class="sxs-lookup"><span data-stu-id="12ecf-152">Pending actions</span></span>    |<span data-ttu-id="12ecf-153">列出需要核准才能繼續的項目。</span><span class="sxs-lookup"><span data-stu-id="12ecf-153">Lists items that require approval to proceed.</span></span>|

## <a name="remediation-actions-following-automated-investigation"></a><span data-ttu-id="12ecf-154">自動調查後的修正動作</span><span class="sxs-lookup"><span data-stu-id="12ecf-154">Remediation actions following automated investigation</span></span>

<span data-ttu-id="12ecf-155">當自動調查完成後，會對所涉及的每個證據做出裁決，並確定修正動作。</span><span class="sxs-lookup"><span data-stu-id="12ecf-155">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="12ecf-156">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="12ecf-156">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="12ecf-157">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="12ecf-157">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="12ecf-158">裁決</span><span class="sxs-lookup"><span data-stu-id="12ecf-158">Verdict</span></span>    |<span data-ttu-id="12ecf-159">範圍</span><span class="sxs-lookup"><span data-stu-id="12ecf-159">Area</span></span>   |<span data-ttu-id="12ecf-160">結果</span><span class="sxs-lookup"><span data-stu-id="12ecf-160">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="12ecf-161">惡意</span><span class="sxs-lookup"><span data-stu-id="12ecf-161">Malicious</span></span>  |<span data-ttu-id="12ecf-162">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="12ecf-162">Devices (endpoints)</span></span>    |<span data-ttu-id="12ecf-163">自動採取修正動作</span><span class="sxs-lookup"><span data-stu-id="12ecf-163">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="12ecf-164">惡意</span><span class="sxs-lookup"><span data-stu-id="12ecf-164">Malicious</span></span>  |<span data-ttu-id="12ecf-165">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="12ecf-165">Email content (URLs or attachments)</span></span> | <span data-ttu-id="12ecf-166">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="12ecf-166">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="12ecf-167">可疑</span><span class="sxs-lookup"><span data-stu-id="12ecf-167">Suspicious</span></span> |<span data-ttu-id="12ecf-168">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="12ecf-168">Devices or email content</span></span> |<span data-ttu-id="12ecf-169">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="12ecf-169">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="12ecf-170">無害</span><span class="sxs-lookup"><span data-stu-id="12ecf-170">Clean</span></span>  |<span data-ttu-id="12ecf-171">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="12ecf-171">Devices or email content</span></span>   |<span data-ttu-id="12ecf-172">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="12ecf-172">No remediation actions are needed</span></span>|

[<span data-ttu-id="12ecf-173">在控制中心檢閱待核准的動作</span><span class="sxs-lookup"><span data-stu-id="12ecf-173">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="12ecf-174">如果您認為某個項目已未接或錯誤偵測到的自動化的調查和 Microsoft 威脅防護中的回應功能，讓我們知道 ！</span><span class="sxs-lookup"><span data-stu-id="12ecf-174">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="12ecf-175">請參閱[How to 報告中自動進行調查並 Microsoft 威脅防護中的回應 （空調） 功能，則為 false positive/負號](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="12ecf-175">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="12ecf-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="12ecf-176">Next steps</span></span>

- <span data-ttu-id="12ecf-177">[取得 [控制中心] 權限的概況](mtp-action-center.md#required-permissions-for-action-center-tasks)</span><span class="sxs-lookup"><span data-stu-id="12ecf-177">[Get an overview of Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks)</span></span>
- [<span data-ttu-id="12ecf-178">核准或拒絕與自動化調查相關的動作並回應</span><span class="sxs-lookup"><span data-stu-id="12ecf-178">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

