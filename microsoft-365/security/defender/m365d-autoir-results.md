---
title: 自動調查的詳細資料和結果
description: 在 Microsoft 365 Defender 中查看自動調查的結果與主要調查結果
keywords: 自動, 調查, 結果, 分析, 詳細資料, 修正, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9ee2f0402e8cfd184e59dce5a382f835b706d6aa
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022548"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="337b0-104">自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="337b0-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="337b0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="337b0-105">**Applies to:**</span></span>
- <span data-ttu-id="337b0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="337b0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="337b0-107">透過 Microsoft 365 Defender，當[自動調查](m365d-autoir.md)執行時，在自動調查程式期間和之後都可以使用該調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="337b0-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="337b0-108">如果您擁有[必要權限](m365d-action-center.md#required-permissions-for-action-center-tasks)，您可以在調查詳細資料檢視中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="337b0-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="337b0-109">此 view 提供您的最新狀態，以及核准任何擱置中動作的功能。</span><span class="sxs-lookup"><span data-stu-id="337b0-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="調查詳細資料":::

## <a name="new-unified-investigation-page"></a><span data-ttu-id="337b0-111"> (NEW！ ) 整合調查頁面</span><span class="sxs-lookup"><span data-stu-id="337b0-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="337b0-112">調查頁面最近已經過更新，可納入整個裝置、電子郵件及共同作業內容的資訊。</span><span class="sxs-lookup"><span data-stu-id="337b0-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="337b0-113">新的整合調查頁面會定義一種通用語言，並提供在[Microsoft defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)和[microsoft defender for Office 365](../office-365-security/defender-for-office-365.md)中自動調查的整合體驗。</span><span class="sxs-lookup"><span data-stu-id="337b0-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="337b0-114">若要存取「統一調查」頁面，請選取您將在黃色橫幅中看到的連結：</span><span class="sxs-lookup"><span data-stu-id="337b0-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="337b0-115">Office 365 安全性 & 規範中心 (中的任何調查頁面 [https://protection.office.com](https://protection.office.com)) </span><span class="sxs-lookup"><span data-stu-id="337b0-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="337b0-116">Microsoft Defender 資訊安全中心 (中的任何調查頁面 [https://securitycenter.windows.com](https://securitycenter.windows.com)) </span><span class="sxs-lookup"><span data-stu-id="337b0-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="337b0-117">Microsoft 365 Defender 入口網站 (中的任何事件或行動中心體驗 [https://security.microsoft.com](https://security.microsoft.com)) </span><span class="sxs-lookup"><span data-stu-id="337b0-117">Any incident or Action center experience in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="337b0-118">開啟調查詳細資料檢視</span><span class="sxs-lookup"><span data-stu-id="337b0-118">Open the investigation details view</span></span>

<span data-ttu-id="337b0-119">您可以使用下列其中一種方法開啟調查詳細資料檢視：</span><span class="sxs-lookup"><span data-stu-id="337b0-119">You can open the investigation details view by using one of the following methods:</span></span>

- <span data-ttu-id="337b0-120">[選取 [控制中心] 中的項目](#select-an-item-in-the-action-center)</span><span class="sxs-lookup"><span data-stu-id="337b0-120">[Select an item in the Action center](#select-an-item-in-the-action-center)</span></span>
- [<span data-ttu-id="337b0-121">從事件詳細資料頁面中選取調查</span><span class="sxs-lookup"><span data-stu-id="337b0-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="337b0-122">選取 [控制中心] 中的項目</span><span class="sxs-lookup"><span data-stu-id="337b0-122">Select an item in the Action center</span></span>

<span data-ttu-id="337b0-123">改進的 [動作中心](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 會透過您的裝置、電子郵件 & 共同作業內容和身分識別的方式，將 [修正動作](m365d-remediation-actions.md) 彙集在一起。</span><span class="sxs-lookup"><span data-stu-id="337b0-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="337b0-124">列出的動作包括自動或手動採取的修復動作。</span><span class="sxs-lookup"><span data-stu-id="337b0-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="337b0-125">在 [行動中心] 中，您可以查看等候核准的動作，以及已核准或已完成的動作。</span><span class="sxs-lookup"><span data-stu-id="337b0-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="337b0-126">您也可以流覽到更多詳細資料，例如調查頁面。</span><span class="sxs-lookup"><span data-stu-id="337b0-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="337b0-127">您必須具有核准、拒絕或復原動作的 [特定許可權](m365d-action-center.md#required-permissions-for-action-center-tasks) 。</span><span class="sxs-lookup"><span data-stu-id="337b0-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="337b0-128">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="337b0-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="337b0-129">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="337b0-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="337b0-130">在 [待核准] 或 [歷史記錄] 索引標籤上，選取一個項目。</span><span class="sxs-lookup"><span data-stu-id="337b0-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="337b0-131">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="337b0-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="337b0-132">查看彈出窗格中的資訊，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="337b0-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="337b0-133">選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="337b0-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="337b0-134">選取 [ **核准** ] 以啟動暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="337b0-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="337b0-135">選取 [ **拒絕** ] 以避免採取暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="337b0-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="337b0-136">選取 [ **移至搜尋** ] 以進入 [高級搜尋](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="337b0-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="337b0-137">從事件詳細資料頁面開啟調查</span><span class="sxs-lookup"><span data-stu-id="337b0-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="337b0-138">使用事件詳細資料頁面來查看事件的詳細資訊，包括觸發任何受影響裝置、使用者帳戶或信箱之資訊的警示。</span><span class="sxs-lookup"><span data-stu-id="337b0-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="337b0-139">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="337b0-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="337b0-140">在功能窗格中，選擇 [**事件] & 警示**  >  **事件**。</span><span class="sxs-lookup"><span data-stu-id="337b0-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="337b0-141">選取清單中的專案，然後選擇 [ **開啟事件] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="337b0-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="337b0-142">選取 [ **調查** ] 索引標籤，然後在清單中選取調查。</span><span class="sxs-lookup"><span data-stu-id="337b0-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="337b0-143">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="337b0-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="337b0-144">選取 [ **開啟調查] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="337b0-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="337b0-145">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="337b0-145">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="事件詳細資料":::

## <a name="investigation-details"></a><span data-ttu-id="337b0-147">調查詳細資料</span><span class="sxs-lookup"><span data-stu-id="337b0-147">Investigation details</span></span>

<span data-ttu-id="337b0-148">使用調查詳細資料檢視，查看與調查相關的過去、目前和待核准的活動。</span><span class="sxs-lookup"><span data-stu-id="337b0-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="337b0-149">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="337b0-149">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="調查詳細資料":::

<span data-ttu-id="337b0-151">在調查詳細資料檢視中，您可以在 [調查圖表]、[警示]、[裝置]、[身分識別]、[重要結果]、[實體]、**[記錄]**，以及 [待核准的動作] 索引標籤上查看資訊，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="337b0-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="337b0-152">您在 [調查詳細資料] 頁面看到的特定索引標籤取決於您的訂閱所包含的專案。</span><span class="sxs-lookup"><span data-stu-id="337b0-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="337b0-153">例如，如果您的訂閱不包含適用于 Office 365 方案2的 Microsoft Defender，您就不會看到 [**信箱**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="337b0-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="337b0-154">索引標籤</span><span class="sxs-lookup"><span data-stu-id="337b0-154">Tab</span></span> | <span data-ttu-id="337b0-155">描述</span><span class="sxs-lookup"><span data-stu-id="337b0-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="337b0-156">**調查圖表**</span><span class="sxs-lookup"><span data-stu-id="337b0-156">**Investigation graph**</span></span>   | <span data-ttu-id="337b0-157">提供調查的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="337b0-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="337b0-158">描述實體並列出發現的威脅和警示，以及是否有任何待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="337b0-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="337b0-159">您可以在圖形上選取一個專案，以查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="337b0-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="337b0-160">例如，選取 **證據** 圖示會帶您前往 [ **證據** ] 索引標籤，您可以在其中看到偵測到的實體及其 verdicts。</span><span class="sxs-lookup"><span data-stu-id="337b0-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="337b0-161">**提醒**</span><span class="sxs-lookup"><span data-stu-id="337b0-161">**Alerts**</span></span>    | <span data-ttu-id="337b0-162">列出與調查相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="337b0-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="337b0-163">警示可能來自使用者裝置上的威脅防護功能、Office 應用程式、Microsoft Cloud App Security 及其他 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="337b0-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="337b0-164">**裝置**</span><span class="sxs-lookup"><span data-stu-id="337b0-164">**Devices**</span></span> | <span data-ttu-id="337b0-165">列出調查中包含的裝置及其修正層級。</span><span class="sxs-lookup"><span data-stu-id="337b0-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="337b0-166"> (修正層級會對應至 [裝置群組的自動化層級](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)。 ) </span><span class="sxs-lookup"><span data-stu-id="337b0-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="337b0-167">**信箱**</span><span class="sxs-lookup"><span data-stu-id="337b0-167">**Mailboxes**</span></span> |<span data-ttu-id="337b0-168">列出受偵測到之威脅影響的信箱。</span><span class="sxs-lookup"><span data-stu-id="337b0-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="337b0-169">**使用者**</span><span class="sxs-lookup"><span data-stu-id="337b0-169">**Users**</span></span>  | <span data-ttu-id="337b0-170">列出受偵測到之威脅影響的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="337b0-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="337b0-171">**證據**</span><span class="sxs-lookup"><span data-stu-id="337b0-171">**Evidence**</span></span> | <span data-ttu-id="337b0-172">列出由警示或調查引發的證據片段。</span><span class="sxs-lookup"><span data-stu-id="337b0-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="337b0-173">包括 verdicts (*惡意*、 *可疑*、 *未知* 或 *未發現威脅*) 和修正狀態。</span><span class="sxs-lookup"><span data-stu-id="337b0-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="337b0-174">**Entities**</span><span class="sxs-lookup"><span data-stu-id="337b0-174">**Entities**</span></span>  | <span data-ttu-id="337b0-175">提供每個已分析之實體的詳細資料，包括每個實體類型的判定 (*惡意*、 *可疑* 或沒有) 中 *找到的威脅* 。</span><span class="sxs-lookup"><span data-stu-id="337b0-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="337b0-176">**Log**</span><span class="sxs-lookup"><span data-stu-id="337b0-176">**Log**</span></span>    | <span data-ttu-id="337b0-177">提供觸發警示之後所採取之所有調查動作的按時間排序的詳細視圖。</span><span class="sxs-lookup"><span data-stu-id="337b0-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="337b0-178">**擱置的動作歷程記錄**</span><span class="sxs-lookup"><span data-stu-id="337b0-178">**Pending actions history**</span></span> | <span data-ttu-id="337b0-179">列出需要核准才能繼續的項目。</span><span class="sxs-lookup"><span data-stu-id="337b0-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="337b0-180">請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 核准擱置的動作。</span><span class="sxs-lookup"><span data-stu-id="337b0-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="337b0-181">後續步驟</span><span class="sxs-lookup"><span data-stu-id="337b0-181">Next steps</span></span>

- [<span data-ttu-id="337b0-182">檢視和管理補救動作</span><span class="sxs-lookup"><span data-stu-id="337b0-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="337b0-183">深入瞭解修復動作</span><span class="sxs-lookup"><span data-stu-id="337b0-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
