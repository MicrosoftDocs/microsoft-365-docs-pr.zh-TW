---
title: 在 Microsoft 365 中查看自動調查的結果
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在 Microsoft 365 中的自動調查期間和之後，您可以查看結果和重要結果。
ms.date: 11/05/2020
ms.openlocfilehash: 4dc74987619c3f958c874927af6e4240b9d7e154
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357282"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a><span data-ttu-id="d9a8b-104">Microsoft 365 中自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="d9a8b-104">Details and results of an automated investigation in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d9a8b-105">在[Office 365 的 Microsoft Defender](office-365-atp.md)中進行[自動調查](office-365-air.md)時，在自動化調查程式期間和之後都會提供該調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-105">When an [automated investigation](office-365-air.md) occurs in [Microsoft Defender for Office 365](office-365-atp.md), details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="d9a8b-106">如果您有必要的許可權，您可以在 Microsoft 365 安全中心中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-106">If you have the necessary permissions, you can view those details in the Microsoft 365 security center.</span></span> <span data-ttu-id="d9a8b-107">調查詳細資料可提供您最新的狀態，以及核准任何擱置中動作的功能。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-107">Investigation details provide you with up-to-date status, and the ability to approve any pending actions.</span></span>

## <a name="investigation-status"></a><span data-ttu-id="d9a8b-108">調查狀態</span><span class="sxs-lookup"><span data-stu-id="d9a8b-108">Investigation status</span></span>

<span data-ttu-id="d9a8b-109">調查狀態會指出分析和動作的進度。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-109">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="d9a8b-110">調查執行時，會變更狀態，以指出是否發現威脅，以及是否已核准動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-110">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span>

|<span data-ttu-id="d9a8b-111">狀態</span><span class="sxs-lookup"><span data-stu-id="d9a8b-111">Status</span></span>|<span data-ttu-id="d9a8b-112">描述</span><span class="sxs-lookup"><span data-stu-id="d9a8b-112">Description</span></span>|
|---|---|
|<span data-ttu-id="d9a8b-113">**啟動中**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-113">**Starting**</span></span>|<span data-ttu-id="d9a8b-114">調查已觸發並等候開始執行。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-114">The investigation has been triggered and waiting to start running.</span></span>|
|<span data-ttu-id="d9a8b-115">**正在執行**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-115">**Running**</span></span>|<span data-ttu-id="d9a8b-116">調查過程已開始且正在進行中。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-116">The investigation process has started and is underway.</span></span> <span data-ttu-id="d9a8b-117">當 [待定的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) 獲得批准時，也會發生此狀態。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-117">This state also occurs when [pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) are approved.</span></span>|
|<span data-ttu-id="d9a8b-118">**找不到威脅**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-118">**No Threats Found**</span></span>|<span data-ttu-id="d9a8b-119">調查已完成，但找不到任何威脅 (使用者帳戶、電子郵件訊息、URL 或檔案) 皆已識別。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-119">The investigation has finished and no threats (user account, email message, URL, or file) were identified.</span></span> <p> <span data-ttu-id="d9a8b-120">**提示**：如果您懷疑某項尚未錯過 (例如誤報) ，您可以使用 [威脅 Explorer](threat-explorer.md)採取動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-120">**TIP**: If you suspect something was missed (such as a false negative), you can take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="d9a8b-121">**發現威脅**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-121">**Threats Found**</span></span>|<span data-ttu-id="d9a8b-122">自動調查發現問題，但沒有任何特定的修正動作可解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-122">The automated investigation found issues, but there are no specific remediation actions to resolve those issues.</span></span> <p> <span data-ttu-id="d9a8b-123">發現某些類型的使用者活動時，可能會發生 **威脅已發現** 狀態，但沒有清除動作可供使用。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-123">The **Threats Found** status can occur when some type of user activity was identified but no cleanup actions are available.</span></span> <span data-ttu-id="d9a8b-124">範例包括下列任何使用者活動：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-124">Examples include any of the following user activities:</span></span> <ul><li><span data-ttu-id="d9a8b-125">DLP) 事件的 [資料遺失防護](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (</span><span class="sxs-lookup"><span data-stu-id="d9a8b-125">A [data loss prevention](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP) event</span></span></li><li><span data-ttu-id="d9a8b-126">傳送異常的電子郵件</span><span class="sxs-lookup"><span data-stu-id="d9a8b-126">An email sending anomaly</span></span></li><li><span data-ttu-id="d9a8b-127">傳送惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="d9a8b-127">Sent malware</span></span></li><li><span data-ttu-id="d9a8b-128">傳送網路釣魚</span><span class="sxs-lookup"><span data-stu-id="d9a8b-128">Sent phish</span></span></li></ul> <p> <span data-ttu-id="d9a8b-129">調查發現沒有惡意的 URLs、檔案或電子郵件訊息要修正，而且沒有要修正的信箱活動，例如關閉轉移規則或委派。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-129">The investigation found no malicious URLs, files, or email messages to remediate, and no mailbox activity to fix, such as turning off forwarding rules or delegation.</span></span> <p> <span data-ttu-id="d9a8b-130">**提示**：如果您懷疑某項尚未錯過 (例如誤報) ，您可以使用 [威脅 Explorer](threat-explorer.md)來調查和採取動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-130">**TIP**: If you suspect something was missed (such as a false negative), you can investigate and take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="d9a8b-131">**由系統終止**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-131">**Terminated By System**</span></span>|<span data-ttu-id="d9a8b-132">調查已停止。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-132">The investigation stopped.</span></span> <span data-ttu-id="d9a8b-133">調查可能會因下列幾點原因而停止：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-133">An investigation can stop for several reasons:</span></span> <ul><li><span data-ttu-id="d9a8b-134">調查的擱置中動作已過期。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-134">The investigation's pending actions expired.</span></span> <span data-ttu-id="d9a8b-135">等候一周的核准，待處理的動作超時。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-135">Pending actions time out after awaiting approval for one week.</span></span></li><li><span data-ttu-id="d9a8b-136">動作太多。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-136">There are too many actions.</span></span> <span data-ttu-id="d9a8b-137">例如，如果有太多使用者點擊惡意的 URLs，它可能會超出調查的執行所有分析器的能力，所以調查會暫停。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-137">For example, if there are too many users clicking on malicious URLs, it can exceed the investigation's ability to run all the analyzers, so the investigation halts.</span></span></li></ul> <p> <span data-ttu-id="d9a8b-138">**提示**：如果調查在採取動作之前暫停，請嘗試使用 [威脅瀏覽器](threat-explorer.md) 來尋找並處理威脅。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-138">**TIP**: If an investigation halts before actions were taken, try using [Threat Explorer](threat-explorer.md) to find and address threats.</span></span>|
|<span data-ttu-id="d9a8b-139">**擱置的動作**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-139">**Pending Action**</span></span>|<span data-ttu-id="d9a8b-140">調查發現威脅，例如惡意電子郵件、惡意 URL 或風險信箱設定，以及修正威脅 [等候核准](air-review-approve-pending-completed-actions.md)的動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-140">The investigation has found a threat, such as a malicious email, a malicious URL, or a risky mailbox setting, and an action to remediate that threat is [awaiting approval](air-review-approve-pending-completed-actions.md).</span></span> <p> <span data-ttu-id="d9a8b-141">當找到具有對應動作的任何威脅時，就會觸發 **擱置的動作** 狀態。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-141">The **Pending Action** state is triggered when any threat with a corresponding action is found.</span></span> <span data-ttu-id="d9a8b-142">不過，擱置中的動作清單會隨著調查的執行而增加。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-142">However, the list of pending actions can increase as an investigation runs.</span></span> <span data-ttu-id="d9a8b-143">檢查 [調查記錄](#playbook-log) 檔，查看是否有其他專案仍待完成。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-143">Check the [investigation log](#playbook-log) to see if other items are still pending completion.</span></span>|
|<span data-ttu-id="d9a8b-144">**修復**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-144">**Remediated**</span></span>|<span data-ttu-id="d9a8b-145">調查已完成且所有修正動作都已獲批准 (此) 會以完全補救的加以說明。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-145">The investigation finished and all remediation actions were approved (this is noted as fully remediated).</span></span> <p> <span data-ttu-id="d9a8b-146">**附注**：核准的修復動作可能會有錯誤，導致無法採取動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-146">**NOTE**: Approved remediation actions can have errors that prevent the actions from being taken.</span></span> <span data-ttu-id="d9a8b-147">不論是否成功完成修正動作，調查狀態不會變更。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-147">Regardless of whether remediation actions are successfully completed, the investigation status does not change.</span></span> <span data-ttu-id="d9a8b-148">檢查 [調查記錄](#playbook-log) 檔中的詳細結果。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-148">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="d9a8b-149">**部分修正**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-149">**Partially Remediated**</span></span>|<span data-ttu-id="d9a8b-150">調查產生修正動作，有些已經過核准和完成。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-150">The investigation resulted in remediation actions, and some were approved and completed.</span></span> <span data-ttu-id="d9a8b-151">其他動作仍 [有待處理](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-151">Other actions are still [pending](air-review-approve-pending-completed-actions.md).</span></span>|
|<span data-ttu-id="d9a8b-152">**已失敗**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-152">**Failed**</span></span>|<span data-ttu-id="d9a8b-153">至少有一個調查分析器遇到問題，導致無法正確完成。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-153">At least one investigation analyzer ran into a problem where it could not complete properly.</span></span> <p> <span data-ttu-id="d9a8b-154">**附注**：如果在已核准修正動作後，調查失敗，修正動作可能仍然會成功。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-154">**NOTE**: If an investigation fails after remediation actions were approved, the remediation actions might still have succeeded.</span></span> <span data-ttu-id="d9a8b-155">檢查 [調查記錄](#playbook-log) 檔中的詳細結果。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-155">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="d9a8b-156">**依節流佇列**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-156">**Queued By Throttling**</span></span>|<span data-ttu-id="d9a8b-157">在佇列中保存調查。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-157">An investigation is being held in a queue.</span></span> <span data-ttu-id="d9a8b-158">當其他調查完成時，佇列調查便會開始。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-158">When other investigations complete, queued investigations begin.</span></span> <span data-ttu-id="d9a8b-159">節流可協助避免服務效能不良。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-159">Throttling helps avoid poor service performance.</span></span>  <p> <span data-ttu-id="d9a8b-160">**提示**：擱置的動作可能會限制可執行檔新調查數目。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-160">**TIP**: Pending actions can limit how many new investigations can run.</span></span> <span data-ttu-id="d9a8b-161">請務必 [核准 (或拒絕) 擱置的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-161">Make sure to [approve (or reject) pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).</span></span>|
|<span data-ttu-id="d9a8b-162">**由節流終止**</span><span class="sxs-lookup"><span data-stu-id="d9a8b-162">**Terminated By Throttling**</span></span>|<span data-ttu-id="d9a8b-163">如果佇列中的調查保持過長，它就會停止。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-163">If an investigation is held in the queue too long, it stops.</span></span> <p> <span data-ttu-id="d9a8b-164">**提示**：您可以 [從威脅瀏覽器開始調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-164">**TIP**: You can [start an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>|
|

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="d9a8b-165">檢視調查的詳細資料</span><span class="sxs-lookup"><span data-stu-id="d9a8b-165">View details of an investigation</span></span>

1. <span data-ttu-id="d9a8b-166">請移至安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-166">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="d9a8b-167">請執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-167">Do one of the following actions:</span></span>

    - <span data-ttu-id="d9a8b-168">移至 [ **威脅管理**] \> **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-168">Go to **Threat management** \> **Dashboard**.</span></span> <span data-ttu-id="d9a8b-169">這樣會帶您前往[安全性儀表板](security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-169">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="d9a8b-170">您的 AIR 小工具會顯示在[安全性儀表板](security-dashboard.md)上方。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-170">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="d9a8b-171">選取小工具，例如 **調查摘要**。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-171">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="d9a8b-172">移至 **威脅管理** \> **調查**。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-172">Go to **Threat management** \> **Investigations**.</span></span>

    <span data-ttu-id="d9a8b-173">這兩種方法都會帶您前往調查清單。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-173">Either method takes you to a list of investigations.</span></span>

    ![AIR 的主要調查頁面](../../media/air-maininvestigationpage.png)

3. <span data-ttu-id="d9a8b-175">在調查清單中，選取 [識別碼] 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-175">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="d9a8b-176">這樣會開啟調查詳細資料頁面，從檢視中的調查圖形開始。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-176">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![AIR 調查圖形頁面](../../media/air-investigationgraphpage.png)

   <span data-ttu-id="d9a8b-178">使用各個索引標籤深入了解調查。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-178">Use the various tabs to learn more about the investigation.</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="d9a8b-179">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="d9a8b-179">View details about an alert related to an investigation</span></span>

<span data-ttu-id="d9a8b-180">某些類型的警示會觸發 Microsoft 365 中的自動調查。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-180">Certain kinds of alerts trigger automated investigation in Microsoft 365.</span></span> <span data-ttu-id="d9a8b-181">若要深入瞭解，請參閱 [觸發自動調查的警示原則](office-365-air.md#which-alert-policies-trigger-automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-181">To learn more, see [alert policies that trigger automated investigations](office-365-air.md#which-alert-policies-trigger-automated-investigations).</span></span>

<span data-ttu-id="d9a8b-182">使用下列程序來檢視與自動化調查相關聯警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-182">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="d9a8b-183">請移至安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-183">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="d9a8b-184">移至 **威脅管理** \> **調查**。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-184">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="d9a8b-185">在調查清單中，選取 [識別碼] 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-185">In the list of investigations, select an item in the **ID** column.</span></span>

4. <span data-ttu-id="d9a8b-186">開啟調查詳細資料時，選取 [警示] 索引標籤。觸發調查的任何警示都會列在此處。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-186">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="d9a8b-187">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-187">Select an item in the list.</span></span> <span data-ttu-id="d9a8b-188">隨即開啟一個飛出視窗，其中包含警示的詳細資料以及其他資訊和動作的連結。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-188">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="d9a8b-189">檢閱飛出視窗中的資訊，並視特定警示採取動作，例如 **解決**、**隱藏**，或 **通知使用者**。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-189">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span>

    - <span data-ttu-id="d9a8b-190">**解決** 等同於關閉警示</span><span class="sxs-lookup"><span data-stu-id="d9a8b-190">**Resolve** is equivalent to closing an alert</span></span>

    - <span data-ttu-id="d9a8b-191">**隱藏** 會導致原則在指定時段不觸發警示</span><span class="sxs-lookup"><span data-stu-id="d9a8b-191">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>

    - <span data-ttu-id="d9a8b-192">**通知使用者** 會啟動電子郵件，並且已輸入使用者的電子郵件地址，讓您的安全性操作小組輸入要給這些使用者的訊息。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-192">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="d9a8b-193">(這類似於使用[威脅總管](threat-explorer.md)將訊息傳送給收件者。)</span><span class="sxs-lookup"><span data-stu-id="d9a8b-193">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>

## <a name="how-to-use-the-various-tabs"></a><span data-ttu-id="d9a8b-194">如何使用各種選項卡</span><span class="sxs-lookup"><span data-stu-id="d9a8b-194">How to use the various tabs</span></span>

<span data-ttu-id="d9a8b-195">下列各節會逐步引導您完成「自動化調查」頁面上的各項索引標籤，以及如何使用此資訊。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-195">The following sections walk you through the various tabs on the automated investigations page and how you can use the information.</span></span>

### <a name="automated-investigations-page"></a><span data-ttu-id="d9a8b-196">自動調查頁面</span><span class="sxs-lookup"><span data-stu-id="d9a8b-196">Automated investigations page</span></span>

<span data-ttu-id="d9a8b-197">「自動調查」頁面會顯示您組織的調查及其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-197">The automated investigations page shows your organization's investigations and their current states.</span></span>

![AIR 的主要調查頁面](../../media/air-maininvestigationpage.png)

<span data-ttu-id="d9a8b-199">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-199">You can:</span></span>

- <span data-ttu-id="d9a8b-200">直接流覽至調查 (選取 **調查識別碼**) 。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-200">Navigate directly to an investigation (select an **Investigation ID**).</span></span>

- <span data-ttu-id="d9a8b-201">套用篩選器。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-201">Apply filters.</span></span> <span data-ttu-id="d9a8b-202">您可以選擇 **調查類型**、 **時間範圍**、 **狀態** 或兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-202">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>

- <span data-ttu-id="d9a8b-203">將資料匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-203">Export the data to a .csv file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="d9a8b-204">調查圖表</span><span class="sxs-lookup"><span data-stu-id="d9a8b-204">Investigation graph</span></span>

<span data-ttu-id="d9a8b-205">當您開啟特定調查時，您會看到 [調查圖形] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-205">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="d9a8b-206">此頁面會顯示所有不同的實體：電子郵件、使用者 (和其活動) ，以及在觸發的警示中自動調查的裝置。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-206">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 調查圖形頁面](../../media/air-investigationgraphpage.png)

<span data-ttu-id="d9a8b-208">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-208">You can:</span></span>

- <span data-ttu-id="d9a8b-209">取得目前調查的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-209">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="d9a8b-210">查看調查週期的摘要。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-210">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="d9a8b-211">選取視覺化效果中的節點，以查看該節點的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-211">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="d9a8b-212">選取頂端的索引標籤，以查看該索引標籤的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-212">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="d9a8b-213">警示調查</span><span class="sxs-lookup"><span data-stu-id="d9a8b-213">Alert investigation</span></span>

<span data-ttu-id="d9a8b-214">在調查的 [ **提醒** ] 索引標籤上，您可以看到與調查相關的警示。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-214">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="d9a8b-215">詳細資料包括觸發調查的警示，以及與調查相關的其他相關警示（如危險登入、 [DLP 原則](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 違規等等）。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-215">Details include the alert that triggered the investigation and other correlated alerts, such as risky sign-in, [DLP policy](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) violations, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="d9a8b-216">在此頁面中，安全性分析員也可以查看個別警示的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-216">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空氣提醒頁面](../../media/air-investigationalertspage.png)

<span data-ttu-id="d9a8b-218">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-218">You can:</span></span>

- <span data-ttu-id="d9a8b-219">取得目前觸發警示及任何相關警示的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-219">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="d9a8b-220">在清單中選取警示，以開啟顯示完整警示詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-220">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="d9a8b-221">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="d9a8b-221">Email investigation</span></span>

<span data-ttu-id="d9a8b-222">在調查的 [ **電子郵件** ] 索引標籤上，您可以看到原始的電子郵件，以及視為調查之一部分之類似電子郵件的聚簇。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-222">On the **Email** tab for an investigation, you can see the original emails and the clusters of similar email identified as part of the investigation.</span></span> <span data-ttu-id="d9a8b-223">[ **電子郵件** ] 索引標籤也會顯示與調查相關的電子郵件專案，例如使用者報告的電子郵件詳細資料、報告的原始電子郵件、電子郵件訊息 (s) zapped 由於惡意程式碼/網路釣魚等等。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-223">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

![航空電子郵件調查頁面](../../media/air-investigationemailpage.png)

<span data-ttu-id="d9a8b-225">透過電子郵件調查，您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-225">With email investigation, you can:</span></span>

- <span data-ttu-id="d9a8b-226">取得目前的聚簇結果及發現威脅的視覺概況。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-226">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="d9a8b-227">按一下 [叢集] 實體或威脅清單，開啟顯示完整警示詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-227">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="d9a8b-228">按一下 [**電子郵件群集詳細資料**] 索引標籤頂端的 [**在資源管理器中開啟**] 連結，進一步調查電子郵件叢集。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-228">Further investigate the email cluster by clicking the **Open in Explorer** link at the top of the **Email cluster details** tab</span></span>

![使用飛出詳細資料的航空調查電子郵件](../../media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="d9a8b-230">針對組織中的使用者傳送及接收的大量電子郵件，以及電子郵件通訊和攻擊的多使用者性質，下列程式可能需要一段時間：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-230">Given the sheer volume of email that users in an organization send and receive, plus the multi-user nature of email communications and attacks, the following process can take a significant amount of time:</span></span>

1. <span data-ttu-id="d9a8b-231">根據來自郵件頭、內文、URL 及附件的類似屬性來聚簇電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-231">Clustering email messages based on similar attributes from a message header, body, URL, and attachments.</span></span>
2. <span data-ttu-id="d9a8b-232">將惡意電子郵件與良好的電子郵件分開。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-232">Separating malicious email from the good email.</span></span>
3. <span data-ttu-id="d9a8b-233">對惡意電子郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-233">Taking action on malicious email messages.</span></span>

<span data-ttu-id="d9a8b-234">AIR 自動化此程式，儲存組織的安全性小組時間和精力。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-234">AIR automates this process, saving your organization's security team time and effort.</span></span>

#### <a name="types-of-email-clusters"></a><span data-ttu-id="d9a8b-235">電子郵件聚簇類型</span><span class="sxs-lookup"><span data-stu-id="d9a8b-235">Types of email clusters</span></span>

<span data-ttu-id="d9a8b-236">電子郵件分析步驟期間可識別三種不同類型的電子郵件簇：相似性群集 (所有調查) 、指示器叢集 (所有調查) ，以及信箱/使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-236">Three different types of email clusters can be identified during the email analysis step: similarity clusters (all investigations), indicator clusters (all investigations), and mailbox/user clusters.</span></span> <span data-ttu-id="d9a8b-237">下表說明這些類型的電子郵件聚簇。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-237">The following table describes these types of email clusters.</span></span>

|<span data-ttu-id="d9a8b-238">電子郵件叢集</span><span class="sxs-lookup"><span data-stu-id="d9a8b-238">Email cluster</span></span>|<span data-ttu-id="d9a8b-239">描述</span><span class="sxs-lookup"><span data-stu-id="d9a8b-239">Description</span></span>|
|---|---|
|<span data-ttu-id="d9a8b-240">相似性聚簇</span><span class="sxs-lookup"><span data-stu-id="d9a8b-240">Similarity clusters</span></span>|<span data-ttu-id="d9a8b-241">搜尋使用類似寄件者和內容屬性的電子郵件所識別的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-241">Email messages identified by hunting for emails with similar sender and content attributes.</span></span> <span data-ttu-id="d9a8b-242">根據原始的偵測結果，這些聚簇會針對惡意內容進行評估。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-242">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="d9a8b-243">包含足夠惡意電子郵件偵測的電子郵件群集被視為惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-243">Email clusters that contain enough malicious email detections are considered malicious.</span></span>|
|<span data-ttu-id="d9a8b-244">指示器聚簇</span><span class="sxs-lookup"><span data-stu-id="d9a8b-244">Indicator clusters</span></span>|<span data-ttu-id="d9a8b-245">搜尋來自原始電子郵件的相同指示器實體 (檔案雜湊或 URL) 所識別的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-245">Email messages that are identified by hunting for the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="d9a8b-246">當原始檔案/URL 實體識別為惡意時，AIR 會將指示器結論套用到包含該實體的完整電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-246">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="d9a8b-247">識別為惡意程式碼的檔案，表示包含該檔案的電子郵件叢集會被視為惡意程式碼電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-247">A file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>|
|<span data-ttu-id="d9a8b-248">信箱/使用者群組</span><span class="sxs-lookup"><span data-stu-id="d9a8b-248">Mailbox/user clusters</span></span>|<span data-ttu-id="d9a8b-249">與使用者受損調查相關之使用者的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-249">Email messages related to the user involved in a user compromise investigation.</span></span> <span data-ttu-id="d9a8b-250">這些電子郵件群集可供安全性作業小組進一步分析，而且不會產生電子郵件修復動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-250">These email clusters are for further analysis by the security operations team and will not generate email remediation actions.</span></span> <p> <span data-ttu-id="d9a8b-251">「已遭破壞的使用者安全性行動手冊」會檢查所進行分析之使用者所傳送的電子郵件，以便了解從信箱傳送之電子郵件的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-251">The compromised user security playbook  reviews the emails being sent by the user being analyzed in order to understand the potential impact of the emails being sent from the mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="d9a8b-252">聚簇的目標是尋找及尋找其他相關的電子郵件訊息，這些郵件是由同一個寄件者在攻擊或活動中所傳送。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-252">The goal of clustering is to hunt and find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>  <span data-ttu-id="d9a8b-253">在某些情況下，合法的電子郵件可能會觸發調查 (例如，使用者報告行銷電子郵件) 。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-253">In some cases, legitimate email might trigger an investigation (for example, a user reports a marketing email).</span></span>  <span data-ttu-id="d9a8b-254">在這些案例中，電子郵件叢集應識別電子郵件群集是否不是惡意的-當有適當的情況時，它不會指出威脅，也 **不** 會建議移除電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-254">In these scenarios, the email clustering should identify that email clusters are not malicious – when it appropriately does so, it will **not** indicate a threat, nor will it recommend email removal.</span></span>

#### <a name="email-classifications"></a><span data-ttu-id="d9a8b-255">電子郵件分類</span><span class="sxs-lookup"><span data-stu-id="d9a8b-255">Email classifications</span></span>

<span data-ttu-id="d9a8b-256">在分析電子郵件訊息時，會將它們分類為 *惡意*、 *可疑* 或 *clean* (，但 *不是識別為威脅*) ：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-256">As email messages are analyzed, they are classified as *malicious*, *suspicious*, or *clean* (as in, *not identified as a threat*):</span></span>

- <span data-ttu-id="d9a8b-257">從信箱/使用者送出的 *惡意電子郵件* 指出可能會危及信箱/帳戶。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-257">*Malicious emails* sent from the mailbox/user  indicate potential compromise of the mailbox/account.</span></span> <span data-ttu-id="d9a8b-258">會顯示其他可能會受到惡意電子郵件影響之部分遭到破壞的使用者/信箱。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-258">Other users/mailboxes that are potentially impacted by malicious email as part of a compromise are shown.</span></span>

- <span data-ttu-id="d9a8b-259">信箱/使用者所傳送的 *可疑電子郵件* 指出可能發生遭破壞的帳戶或不需要的電子郵件活動。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-259">*Suspicious emails* sent by the mailbox/user indicate the potential for a compromised account or unwanted email activity.</span></span> <span data-ttu-id="d9a8b-260">這些郵件包括從信箱傳送的任何垃圾郵件/大宗郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-260">These messages include any spam/bulk email sent from the mailbox.</span></span>

- <span data-ttu-id="d9a8b-261">*清理電子郵件* (視為不是由信箱/使用者傳送的威脅) 電子郵件，可讓您的安全性運作小組透過已傳送的合法使用者電子郵件進行查看。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-261">*Clean emails* (emails that are considered not a threat) sent by the mailbox/user can provide your security operations team with a view of legitimate user emails sent.</span></span> <span data-ttu-id="d9a8b-262">不過，如果電子郵件帳戶遭到損害，這些電子郵件也會包含資料 exfiltration。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-262">However, these emails can also include data exfiltration if the email account is compromised.</span></span>

#### <a name="more-about-email-counts"></a><span data-ttu-id="d9a8b-263">有關電子郵件計數的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d9a8b-263">More about email counts</span></span>

<span data-ttu-id="d9a8b-264">在 [電子郵件] 索引標籤上所識別的電子郵件計數目前代表 [ **電子郵件** ] 索引標籤上顯示的所有電子郵件的總計。由於電子郵件訊息存在於多個聚簇中，因此所識別之電子郵件的實際總計數 (，並受修正動作影響) 是出現在所有聚簇和原始收件者的電子郵件中的唯一電子郵件計數。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-264">The email count identified on the email tab currently represents the sum total of all email messages that shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span>

<span data-ttu-id="d9a8b-265">根據每個收件者， [Explorer](threat-explorer.md) 和 AIR 電子郵件都是以每個收件者為基礎，因為安全性 verdicts、動作和傳遞位置會因每個收件者而異。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-265">Both [Explorer](threat-explorer.md) and AIR count email messages on a per-recipient basis, because the security verdicts, actions, and delivery locations vary on a per-recipient basis.</span></span> <span data-ttu-id="d9a8b-266">因此，傳送給三位使用者的原始電子郵件會算作三個電子郵件的總數，而不是一封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-266">Thus, an original email sent to three users counts as a total of three email messages instead of one email.</span></span>

<span data-ttu-id="d9a8b-267">在某些情況下，電子郵件會被計算兩次以上的時間，例如當電子郵件有多個動作時，或當所有動作都發生時，有多個電子郵件副本。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-267">There might be cases where an email gets counted two or more times, such as when an email has multiple actions on it, or when there are multiple copies of the email when all the actions occur.</span></span>

<span data-ttu-id="d9a8b-268">例如，在傳遞時偵測到的惡意程式碼電子郵件可能會造成封鎖的 (隔離) 電子郵件，以及取代的電子郵件 (威脅檔案，以警告檔取代，然後傳遞至使用者的信箱) 。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-268">For example, a malware email that is detected at delivery can result in both a blocked (quarantined) email and a replaced email (threat file replaced with a warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="d9a8b-269">因為系統中的電子郵件有逐字的兩個複本，所以兩者都可能會計入簇計數。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-269">Because there are literally two copies of the email in the system, both might be counted in cluster counts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9a8b-270">以下是一些需要謹記的要點：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-270">Here are a few points to keep in mind:</span></span>
>
> - <span data-ttu-id="d9a8b-271">電子郵件計數會在調查時進行計算，當您根據基礎查詢) 開啟調查 flyouts (時，會重新計算部分計數。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-271">Email counts are calculated at the time of the investigation, and some counts are recalculated when you open investigation flyouts (based on an underlying query).</span></span>
>
> - <span data-ttu-id="d9a8b-272">針對 [ **電子郵件** ] 索引標籤上的電子郵件聚簇，以及在 [叢集] 浮出控制項上顯示的電子郵件數量詞，會在調查時進行計算，而且不會變更。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-272">The email counts shown for the email clusters on the **Email** tab and the email quantity value shown on cluster flyout are calculated at the time of investigation, and do not change.</span></span>
>
> - <span data-ttu-id="d9a8b-273">電子郵件 **的 [電子郵件] 索引** 標籤底部顯示的電子郵件計數，以及 Explorer 中所顯示之電子郵件的計數，會反映在調查的初始分析之後所收到的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-273">The email count shown at the bottom of the **Email** tab of the email cluster flyout and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span>

<span data-ttu-id="d9a8b-274">因此，顯示原始數量10封電子郵件的電子郵件叢集會顯示超過15個電子郵件的電子郵件清單。在調查分析階段和系統管理員檢查調查時，會有五封以上的電子郵件訊息到貨。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-274">Thus, an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when five more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="d9a8b-275">同樣地，舊調查可能會開始顯示比 Explorer 查詢更高的計數，因為 Microsoft Defender for Office 365 方案2中的資料會在試用7天后到期，並且在30天后取得收費授權。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-275">Likewise, old investigations might start showing higher counts than Explorer queries show, because data in Microsoft Defender for Office 365 Plan 2 expires after 7 days for trials and after 30 days for paid licenses.</span></span>

<span data-ttu-id="d9a8b-276">在不同的視圖中顯示計數歷史和目前的計數，都是為了指出調查時的電子郵件影響，以及目前的影響，直到執行補救的時間為止。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-276">Showing both count historical and current counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a8b-277">在電子郵件的內容中，您可能會在調查過程中看到大量的反常威脅曲面。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-277">In the context of email, you might see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="d9a8b-278">大量的事件會指出調查事件時間與較舊的時程表之間的類似電子郵件訊息中的波峰。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-278">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="d9a8b-279">這種具有類似特性的電子郵件流量的此峰值 (例如，主旨和寄件者網域、內文相似性和寄件者 IP) 通常是電子郵件宣傳活動或攻擊的開始。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-279">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span>
> <span data-ttu-id="d9a8b-280">不過，大量、垃圾郵件和合法的電子郵件活動通常會共用這些特性。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-280">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span>
>
> <span data-ttu-id="d9a8b-281">大量的情況代表潛在威脅，而且與使用防病毒引擎、引爆或惡意信譽所識別的惡意程式碼或網路釣魚威脅相比，其可能會較低的危險。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-281">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="d9a8b-282">使用者調查</span><span class="sxs-lookup"><span data-stu-id="d9a8b-282">User investigation</span></span>

<span data-ttu-id="d9a8b-283">在 [ **使用者** ] 索引標籤上，您可以看到所有識別為調查之一部分的使用者。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-283">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="d9a8b-284">當發生事件時，使用者帳戶會出現在調查中，或指出這些使用者帳戶可能受到影響或遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-284">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="d9a8b-285">例如，在下圖中，AIR 會根據所建立的新收件匣規則，識別出損等損等現象。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-285">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="d9a8b-286"> (調查的證據) 的其他詳細資料，可透過此索引標籤內的詳細視圖取得。損壞和異常的指示也可能包括來自 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的反常偵測。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-286">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies might also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![AIR 調查使用者頁面](../../media/air-investigationuserspage.png)

<span data-ttu-id="d9a8b-288">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-288">You can:</span></span>

- <span data-ttu-id="d9a8b-289">深入瞭解已識別的使用者結果和找到的風險。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-289">Get a visual overview of identified user results and risks found.</span></span>

- <span data-ttu-id="d9a8b-290">選取使用者開啟彈出頁面，顯示完整的提醒詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-290">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="d9a8b-291">機器調查</span><span class="sxs-lookup"><span data-stu-id="d9a8b-291">Machine investigation</span></span>

<span data-ttu-id="d9a8b-292">在 [ **機器** ] 索引標籤上，您可以看到識別為調查一部分的所有機器。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-292">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span>

![AIR 調查電腦頁面](../../media/air-investigationmachinepage.png)

<span data-ttu-id="d9a8b-294">在某些行動行動中，AIR 會將電子郵件威脅與裝置相關聯 (例如，Zapped 惡意程式碼) 。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-294">As part of some playbooks, AIR correlates email threats to devices (for example, Zapped malware).</span></span> <span data-ttu-id="d9a8b-295">例如，調查會將惡意檔雜湊傳遞至 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 以進行調查。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-295">For example, an investigation passes a malicious file hash across to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="d9a8b-296">這可讓您針對使用者自動調查相關的機器，以協助確保雲端和您的端點都有解決威脅。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-296">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span>

<span data-ttu-id="d9a8b-297">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-297">You can:</span></span>

- <span data-ttu-id="d9a8b-298">取得目前的電腦及發現威脅的視覺概況。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-298">Get a visual overview of the current machines and threats found.</span></span>

- <span data-ttu-id="d9a8b-299">選取機器以開啟 Microsoft Defender Security Center 中相關 [Microsoft defender For Endpoint 調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 的視圖。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-299">Select a machine to open a view that into the related [Microsoft Defender for Endpoint investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="d9a8b-300">實體調查</span><span class="sxs-lookup"><span data-stu-id="d9a8b-300">Entity investigation</span></span>

<span data-ttu-id="d9a8b-301">在 [ **實體** ] 索引標籤上，您可以看到在調查中識別及分析的實體。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-301">On the **Entities** tab, you can see the entities identified and analyzed as part of the investigation.</span></span>

<span data-ttu-id="d9a8b-302">在這裡，您可以查看已調查的實體和實體類型的詳細資料，例如電子郵件訊息、叢集、IP 位址、使用者等等。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-302">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="d9a8b-303">您也可以查看已分析的實體數量，以及與每個實體相關聯的威脅。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-303">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span>

![AIR 調查實體頁面](../../media/air-investigationentitiespage.png)

<span data-ttu-id="d9a8b-305">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-305">You can:</span></span>

- <span data-ttu-id="d9a8b-306">取得所找到之調查實體和威脅的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-306">Get a visual overview of the investigation entities and threats found.</span></span>

- <span data-ttu-id="d9a8b-307">選取實體以開啟顯示相關實體詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-307">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中調查實體詳細資料](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="d9a8b-309">行動手冊記錄</span><span class="sxs-lookup"><span data-stu-id="d9a8b-309">Playbook log</span></span>

<span data-ttu-id="d9a8b-310">在 [ **記錄** ] 索引標籤上，您可以看到在調查過程中所發生的所有操作手冊步驟。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-310">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="d9a8b-311">記錄檔會捕獲 Office 365 自動調查功能所完成之所有 analyzer 和動作的完整清查，做為空氣的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-311">The log captures a complete inventory of all analyzers and actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="d9a8b-312">它提供所有採取步驟的清晰視圖，包括動作本身、描述，以及實際從開始到完成的持續時間。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-312">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span>

![航空調查記錄頁面](../../media/air-investigationlogpage.png)

<span data-ttu-id="d9a8b-314">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-314">You can:</span></span>

- <span data-ttu-id="d9a8b-315">請參閱行動手冊步驟的視覺概況。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-315">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="d9a8b-316">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-316">Export the results to a CSV file.</span></span>
- <span data-ttu-id="d9a8b-317">篩選視圖。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-317">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="d9a8b-318">建議的動作</span><span class="sxs-lookup"><span data-stu-id="d9a8b-318">Recommended actions</span></span>

<span data-ttu-id="d9a8b-319">在 [ **動作** ] 索引標籤上，您可以看到在調查完成之後，修正建議的所有行動手冊動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-319">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> <span data-ttu-id="d9a8b-320">動作會捕獲 Microsoft 建議您在調查結束時採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-320">Actions capture the steps Microsoft recommends you take at the end of an investigation.</span></span> <span data-ttu-id="d9a8b-321">您可以選取一或多個動作來採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-321">You can take remediation actions here by selecting one or more actions.</span></span>

<span data-ttu-id="d9a8b-322">選取 [ **核准** ] 允許開始修復。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-322">Selecting **Approve** allows remediation to begin.</span></span> <span data-ttu-id="d9a8b-323">需要 (適當的許可權-從 Explorer 和 AIR) 中執行動作時，必須要有 **搜尋和清除** 角色。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-323">(Appropriate permissions are needed - the **Search And Purge** role is required to run actions from Explorer and AIR).</span></span>

<span data-ttu-id="d9a8b-324">例如，安全性讀者可以查看動作，但不能核准。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-324">For example, a Security Reader can view actions, but not approve them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9a8b-325">您不需要核准每個動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-325">You do not have to approve every action.</span></span> <span data-ttu-id="d9a8b-326">如果您不同意建議的動作，或您的組織未選擇某些類型的動作，您可以選擇 **拒絕** 動作或完全忽略動作，不採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-326">If you do not agree with the recommended action or your organization does not choose certain types of actions, then you can choose to **Reject** the actions or simply ignore them and take no action.</span></span>
> <span data-ttu-id="d9a8b-327">核准和/或拒絕所有動作可讓調查完全關閉 (狀態會變成修正) ，但保留某些動作不完全會導致調查狀態變更為部分修正狀態。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-327">Approving and/or rejecting all actions lets the investigation fully close (status becomes remediated), while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![AIR 調查動作頁面](../../media/air-investigationactionspage.png)

<span data-ttu-id="d9a8b-329">您可以：</span><span class="sxs-lookup"><span data-stu-id="d9a8b-329">You can:</span></span>

- <span data-ttu-id="d9a8b-330">取得行動手冊-建議動作的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-330">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="d9a8b-331">選取一個或多個動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-331">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="d9a8b-332">使用批註核准或拒絕建議的動作。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-332">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="d9a8b-333">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-333">Export the results to a CSV file.</span></span>
- <span data-ttu-id="d9a8b-334">篩選視圖。</span><span class="sxs-lookup"><span data-stu-id="d9a8b-334">Filter the view.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d9a8b-335">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d9a8b-335">Next steps</span></span>

- [<span data-ttu-id="d9a8b-336">審閱及核准擱置的動作</span><span class="sxs-lookup"><span data-stu-id="d9a8b-336">Review and approve pending actions</span></span>](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
