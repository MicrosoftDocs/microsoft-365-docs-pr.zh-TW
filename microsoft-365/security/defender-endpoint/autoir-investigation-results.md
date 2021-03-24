---
title: 自動調查的詳細資料和結果
description: 在自動調查過程中和完成之後，您就可以查看結果和重要結果
keywords: 自動, 調查, 結果, 分析, 詳細資料, 修正, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/02/2021
ms.openlocfilehash: c11d9cd1ce4c2ca49315ec62b51c23ef981555f4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059924"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="09113-104">自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="09113-104">Details and results of an automated investigation</span></span>

<span data-ttu-id="09113-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="09113-105">**Applies to:**</span></span>
- <span data-ttu-id="09113-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="09113-106">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="09113-107">使用 Microsoft Defender for Endpoint 時，當 [自動調查](automated-investigations.md) 執行時，該調查的詳細資料就會在自動調查程式期間和之後使用。</span><span class="sxs-lookup"><span data-stu-id="09113-107">With Microsoft Defender for Endpoint, when an [automated investigation](automated-investigations.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="09113-108">如果您擁有必要權限，您可以在調查詳細資料檢視中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="09113-108">If you have the necessary permissions, you can view those details in an investigation details view.</span></span> <span data-ttu-id="09113-109">調查詳細資料檢視可提供您最新的狀態，以及核准任何待核准動作的能力。</span><span class="sxs-lookup"><span data-stu-id="09113-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

## <a name="new-unified-investigation-page"></a><span data-ttu-id="09113-110"> (NEW！ ) 整合調查頁面</span><span class="sxs-lookup"><span data-stu-id="09113-110">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="09113-111">調查頁面最近已經過更新，可納入整個裝置、電子郵件及共同作業內容的資訊。</span><span class="sxs-lookup"><span data-stu-id="09113-111">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="09113-112">新的整合調查頁面會定義一種通用語言，並提供跨 [Microsoft defender For Endpoint](microsoft-defender-advanced-threat-protection.md)  和 [Microsoft defender for Office 365](/microsoft-365/security/defender-365-security/office-365-atp)進行自動調查的整合體驗。</span><span class="sxs-lookup"><span data-stu-id="09113-112">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md)  and [Microsoft Defender for Office 365](/microsoft-365/security/defender-365-security/office-365-atp).</span></span> 

> [!TIP]
> <span data-ttu-id="09113-113">若要深入瞭解變更的相關資訊，請參閱 [ (NEW！ ) 整合調查] 頁面](/microsoft-365/security/mtp/mtp-autoir-results)。</span><span class="sxs-lookup"><span data-stu-id="09113-113">To learn more about what's changing, see [(NEW!) Unified investigation page](/microsoft-365/security/mtp/mtp-autoir-results).</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="09113-114">開啟調查詳細資料檢視</span><span class="sxs-lookup"><span data-stu-id="09113-114">Open the investigation details view</span></span>

<span data-ttu-id="09113-115">您可以使用下列其中一種方法開啟調查詳細資料檢視：</span><span class="sxs-lookup"><span data-stu-id="09113-115">You can open the investigation details view by using one of the following methods:</span></span>
- <span data-ttu-id="09113-116">[選取 [控制中心] 中的項目](#select-an-item-in-the-action-center)</span><span class="sxs-lookup"><span data-stu-id="09113-116">[Select an item in the Action center](#select-an-item-in-the-action-center)</span></span>
- [<span data-ttu-id="09113-117">從事件詳細資料頁面中選取調查</span><span class="sxs-lookup"><span data-stu-id="09113-117">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="09113-118">選取 [控制中心] 中的項目</span><span class="sxs-lookup"><span data-stu-id="09113-118">Select an item in the Action center</span></span>

<span data-ttu-id="09113-119">改進的 [動作中心](auto-investigation-action-center.md) 會透過您的裝置、電子郵件 & 共同作業內容和身分識別，將 [修正動作](manage-auto-investigation.md#remediation-actions) 彙集在一起。</span><span class="sxs-lookup"><span data-stu-id="09113-119">The improved [Action center](auto-investigation-action-center.md) brings together [remediation actions](manage-auto-investigation.md#remediation-actions) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="09113-120">列出的動作包括自動或手動採取的修復動作。</span><span class="sxs-lookup"><span data-stu-id="09113-120">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="09113-121">在 [行動中心] 中，您可以查看等候核准的動作，以及已核准或已完成的動作。</span><span class="sxs-lookup"><span data-stu-id="09113-121">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="09113-122">您也可以流覽到更多詳細資料，例如調查頁面。</span><span class="sxs-lookup"><span data-stu-id="09113-122">You can also navigate to more details, such as an investigation page.</span></span>

1. <span data-ttu-id="09113-123">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="09113-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="09113-124">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="09113-124">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="09113-125">在 [待核准] 或 [歷史記錄] 索引標籤上，選取一個項目。</span><span class="sxs-lookup"><span data-stu-id="09113-125">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="09113-126">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="09113-126">Its flyout pane opens.</span></span>
4. <span data-ttu-id="09113-127">查看彈出窗格中的資訊，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="09113-127">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="09113-128">選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="09113-128">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="09113-129">選取 [ **核准** ] 以啟動暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="09113-129">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="09113-130">選取 [ **拒絕** ] 以避免採取暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="09113-130">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="09113-131">選取 [ **移至搜尋** ] 以進入 [高級搜尋](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="09113-131">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="09113-132">從事件詳細資料頁面開啟調查</span><span class="sxs-lookup"><span data-stu-id="09113-132">Open an investigation from an incident details page</span></span>

<span data-ttu-id="09113-133">使用事件詳細資料頁面來查看事件的詳細資訊，包括觸發任何受影響裝置、使用者帳戶或信箱之資訊的警示。</span><span class="sxs-lookup"><span data-stu-id="09113-133">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="09113-134">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="09113-134">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="09113-135">在功能窗格中，選擇 [**事件] & 警示**  >  **事件**。</span><span class="sxs-lookup"><span data-stu-id="09113-135">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 
3. <span data-ttu-id="09113-136">選取清單中的專案，然後選擇 [ **開啟事件] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="09113-136">Select an item in the list, and then choose **Open incident page**.</span></span>
4. <span data-ttu-id="09113-137">選取 [ **調查** ] 索引標籤，然後在清單中選取調查。</span><span class="sxs-lookup"><span data-stu-id="09113-137">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="09113-138">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="09113-138">Its flyout pane opens.</span></span>
5. <span data-ttu-id="09113-139">選取 [ **開啟調查] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="09113-139">Select **Open investigation page**.</span></span> 

## <a name="investigation-details"></a><span data-ttu-id="09113-140">調查詳細資料</span><span class="sxs-lookup"><span data-stu-id="09113-140">Investigation details</span></span>

<span data-ttu-id="09113-141">使用調查詳細資料檢視，查看與調查相關的過去、目前和待核准的活動。</span><span class="sxs-lookup"><span data-stu-id="09113-141">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="09113-142">調查詳細資料檢視類似以下影像：</span><span class="sxs-lookup"><span data-stu-id="09113-142">The investigation details view resembles the following image:</span></span>

<span data-ttu-id="09113-143">在調查詳細資料檢視中，您可以在 [調查圖表]、[警示]、[裝置]、[身分識別]、[重要結果]、[實體]、**[記錄]**，以及 [待核准的動作] 索引標籤上查看資訊，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="09113-143">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="09113-144">您在 [調查詳細資料] 頁面看到的特定索引標籤取決於您的訂閱所包含的專案。</span><span class="sxs-lookup"><span data-stu-id="09113-144">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="09113-145">例如，如果您的訂閱不包含 Microsoft Defender for Office 365 方案2，您就不會看到 [ **信箱** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="09113-145">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="09113-146">索引標籤</span><span class="sxs-lookup"><span data-stu-id="09113-146">Tab</span></span> | <span data-ttu-id="09113-147">描述</span><span class="sxs-lookup"><span data-stu-id="09113-147">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="09113-148">**調查圖表**</span><span class="sxs-lookup"><span data-stu-id="09113-148">**Investigation graph**</span></span>   | <span data-ttu-id="09113-149">提供調查的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="09113-149">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="09113-150">描述實體並列出發現的威脅和警示，以及是否有任何待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="09113-150">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="09113-151">您可以在圖形上選取一個專案，以查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="09113-151">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="09113-152">例如，選取 **證據** 圖示會帶您前往 [ **證據** ] 索引標籤，您可以在其中看到偵測到的實體及其 verdicts。</span><span class="sxs-lookup"><span data-stu-id="09113-152">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="09113-153">**提醒**</span><span class="sxs-lookup"><span data-stu-id="09113-153">**Alerts**</span></span>    | <span data-ttu-id="09113-154">列出與調查相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="09113-154">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="09113-155">提醒可能來自使用者裝置上的威脅防護功能、Office 應用程式、雲端 App 安全性及其他 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="09113-155">Alerts can come from threat protection features on a user's device, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="09113-156">**裝置**</span><span class="sxs-lookup"><span data-stu-id="09113-156">**Devices**</span></span> | <span data-ttu-id="09113-157">列出調查中包含的裝置及其修正層級。</span><span class="sxs-lookup"><span data-stu-id="09113-157">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="09113-158"> (修正層級會對應至 [裝置群組的自動化層級](automation-levels.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="09113-158">(Remediation levels correspond to the [automation level for device groups](automation-levels.md).)</span></span> |
| <span data-ttu-id="09113-159">**信箱**</span><span class="sxs-lookup"><span data-stu-id="09113-159">**Mailboxes**</span></span> |<span data-ttu-id="09113-160">列出受偵測到之威脅影響的信箱。</span><span class="sxs-lookup"><span data-stu-id="09113-160">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="09113-161">**使用者**</span><span class="sxs-lookup"><span data-stu-id="09113-161">**Users**</span></span>  | <span data-ttu-id="09113-162">列出受偵測到之威脅影響的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="09113-162">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="09113-163">**證據**</span><span class="sxs-lookup"><span data-stu-id="09113-163">**Evidence**</span></span> | <span data-ttu-id="09113-164">列出由警示/調查產生的證據片段。</span><span class="sxs-lookup"><span data-stu-id="09113-164">Lists pieces of evidence raised by alerts/investigations.</span></span> <span data-ttu-id="09113-165">包括 verdicts (*惡意*、 *可疑* 或 *未找到威脅*) 和修正狀態。</span><span class="sxs-lookup"><span data-stu-id="09113-165">Includes verdicts (*Malicious*, *Suspicious*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="09113-166">**Entities**</span><span class="sxs-lookup"><span data-stu-id="09113-166">**Entities**</span></span>  | <span data-ttu-id="09113-167">提供每個已分析之實體的詳細資料，包括每個實體類型的判定 (*惡意*、 *可疑* 或沒有) 中 *找到的威脅* 。</span><span class="sxs-lookup"><span data-stu-id="09113-167">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="09113-168">**Log**</span><span class="sxs-lookup"><span data-stu-id="09113-168">**Log**</span></span>    | <span data-ttu-id="09113-169">提供觸發警示之後所採取之所有調查動作的按時間排序的詳細視圖。</span><span class="sxs-lookup"><span data-stu-id="09113-169">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="09113-170">**待核准的動作**</span><span class="sxs-lookup"><span data-stu-id="09113-170">**Pending actions**</span></span> | <span data-ttu-id="09113-171">列出需要核准才能繼續的項目。</span><span class="sxs-lookup"><span data-stu-id="09113-171">Lists items that require approval to proceed.</span></span> <span data-ttu-id="09113-172">請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 核准擱置的動作。</span><span class="sxs-lookup"><span data-stu-id="09113-172">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="09113-173">另請參閱</span><span class="sxs-lookup"><span data-stu-id="09113-173">See also</span></span>

- [<span data-ttu-id="09113-174">在自動調查後複查修正動作</span><span class="sxs-lookup"><span data-stu-id="09113-174">Review remediation actions following an automated investigation</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="09113-175">查看和組織 Microsoft Defender for Endpoint 事件佇列</span><span class="sxs-lookup"><span data-stu-id="09113-175">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>](view-incidents-queue.md)