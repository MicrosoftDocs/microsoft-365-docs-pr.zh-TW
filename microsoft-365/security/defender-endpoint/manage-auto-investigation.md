---
title: 檢查自動調查後的修復動作
description: 在自動調查後，複查和核准 (或拒絕) 修正動作。
keywords: autoir，自動化，調查，偵測，修正，動作，擱置，已核准
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: 410972bd823c3a3c4fda53cacc225014d83f3457
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844007"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a><span data-ttu-id="833e6-104">在自動調查後複查修正動作</span><span class="sxs-lookup"><span data-stu-id="833e6-104">Review remediation actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a><span data-ttu-id="833e6-105">補救動作</span><span class="sxs-lookup"><span data-stu-id="833e6-105">Remediation actions</span></span>

<span data-ttu-id="833e6-106">當 [自動調查](automated-investigations.md) 執行時，會針對每個證據調查產生一個判定。</span><span class="sxs-lookup"><span data-stu-id="833e6-106">When an [automated investigation](automated-investigations.md) runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="833e6-107">Verdicts 可能是 *惡意*、 *可疑* 或 *沒有發現威脅*。</span><span class="sxs-lookup"><span data-stu-id="833e6-107">Verdicts can be *Malicious*, *Suspicious*, or *No threats found*.</span></span> 

<span data-ttu-id="833e6-108">根據</span><span class="sxs-lookup"><span data-stu-id="833e6-108">Depending on</span></span>

- <span data-ttu-id="833e6-109">威脅類型</span><span class="sxs-lookup"><span data-stu-id="833e6-109">the type of threat,</span></span> 
- <span data-ttu-id="833e6-110">產生的判定和</span><span class="sxs-lookup"><span data-stu-id="833e6-110">the resulting verdict, and</span></span> 
- <span data-ttu-id="833e6-111">如何設定組織的 [裝置群組](/microsoft-365/security/defender-endpoint/machine-groups) 、</span><span class="sxs-lookup"><span data-stu-id="833e6-111">how your organization's [device groups](/microsoft-365/security/defender-endpoint/machine-groups) are configured,</span></span> 

<span data-ttu-id="833e6-112">修正動作可以自動進行，也可以只在組織的安全性運作小組核准時進行。</span><span class="sxs-lookup"><span data-stu-id="833e6-112">remediation actions can occur automatically or only upon approval by your organization’s security operations team.</span></span> 

<span data-ttu-id="833e6-113">以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="833e6-113">Here are a few examples:</span></span>

- <span data-ttu-id="833e6-114">**範例 1**： Fabrikam 的裝置群組會自動設定為 **完整修正威脅** (建議設定) 。</span><span class="sxs-lookup"><span data-stu-id="833e6-114">**Example 1**: Fabrikam's device groups are set to **Full - remediate threats automatically** (the recommended setting).</span></span> <span data-ttu-id="833e6-115">在此情況下，會自動對被視為惡意調查的偽像執行修正動作。 (請參閱 [複查已完成的動作](#review-completed-actions)) 。</span><span class="sxs-lookup"><span data-stu-id="833e6-115">In this case, remediation actions are taken automatically for artifacts that are considered to be malicious following an automated investigation (see [Review completed actions](#review-completed-actions)).</span></span>

- <span data-ttu-id="833e6-116">**範例 2**： Contoso 的裝置會包含在裝置群組中，此裝置群組是針對 **任何修正要求核准** 所設定的。</span><span class="sxs-lookup"><span data-stu-id="833e6-116">**Example 2**: Contoso's devices are included in a device group that is set for **Semi - require approval for any remediation**.</span></span> <span data-ttu-id="833e6-117">在此案例中，Contoso 的安全操作小組必須在自動調查後複查及核准所有修正動作 (請參閱 [複查擱置的動作](#review-pending-actions)) 。</span><span class="sxs-lookup"><span data-stu-id="833e6-117">In this case, Contoso's security operations team must review and approve all remediation actions following an automated investigation (see [Review pending actions](#review-pending-actions)).</span></span>

- <span data-ttu-id="833e6-118">**範例 3**： Tailspin 玩具的裝置群組設定為 **無自動回應** (不建議) 。</span><span class="sxs-lookup"><span data-stu-id="833e6-118">**Example 3**: Tailspin Toys has their device groups set to **No automated response** (not recommended).</span></span> <span data-ttu-id="833e6-119">在此情況下，不會進行自動調查。</span><span class="sxs-lookup"><span data-stu-id="833e6-119">In this case, automated investigations do not occur.</span></span> <span data-ttu-id="833e6-120">未採取任何修正動作或擱置，而且不會在其裝置的 [動作中心](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) 記錄任何動作 (請參閱 [Manage device groups](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)) 。</span><span class="sxs-lookup"><span data-stu-id="833e6-120">No remediation actions are taken or pending, and no actions are logged in the [Action center](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) for their devices (see [Manage device groups](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)).</span></span>

<span data-ttu-id="833e6-121">不論是自動或核准，自動調查都可能會產生一或多項修正動作：</span><span class="sxs-lookup"><span data-stu-id="833e6-121">Whether taken automatically or upon approval, an automated investigation can result in one or more of the remediation actions:</span></span>
- <span data-ttu-id="833e6-122">隔離檔</span><span class="sxs-lookup"><span data-stu-id="833e6-122">Quarantine a file</span></span>
- <span data-ttu-id="833e6-123">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="833e6-123">Remove a registry key</span></span> 
- <span data-ttu-id="833e6-124">終止進程</span><span class="sxs-lookup"><span data-stu-id="833e6-124">Kill a process</span></span> 
- <span data-ttu-id="833e6-125">停止服務</span><span class="sxs-lookup"><span data-stu-id="833e6-125">Stop a service</span></span> 
- <span data-ttu-id="833e6-126">停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="833e6-126">Disable a driver</span></span> 
- <span data-ttu-id="833e6-127">移除排程任務</span><span class="sxs-lookup"><span data-stu-id="833e6-127">Remove a scheduled task</span></span>

## <a name="review-pending-actions"></a><span data-ttu-id="833e6-128">審閱擱置的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-128">Review pending actions</span></span>

1. <span data-ttu-id="833e6-129">請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="833e6-129">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="833e6-130">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="833e6-130">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="833e6-131">檢查 [ **暫** 止] 索引標籤上的專案。</span><span class="sxs-lookup"><span data-stu-id="833e6-131">Review the items on the **Pending** tab.</span></span> 
4. <span data-ttu-id="833e6-132">選取動作開啟其彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="833e6-132">Select an action to open its flyout pane.</span></span>
5. <span data-ttu-id="833e6-133">在飛入窗格中，複查資訊，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="833e6-133">In the flyout pane, review the information, and then take one of the following steps:</span></span>
   - <span data-ttu-id="833e6-134">選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="833e6-134">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="833e6-135">選取 [ **核准** ] 以啟動暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-135">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="833e6-136">選取 [ **拒絕** ] 以避免採取暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-136">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="833e6-137">選取 [ **移至搜尋** ] 以進入 [高級搜尋](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="833e6-137">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="review-completed-actions"></a><span data-ttu-id="833e6-138">查看已完成的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-138">Review completed actions</span></span>

1. <span data-ttu-id="833e6-139">請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="833e6-139">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="833e6-140">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="833e6-140">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="833e6-141">檢查 [ **記錄** ] 索引標籤上的專案。</span><span class="sxs-lookup"><span data-stu-id="833e6-141">Review the items on the **History** tab.</span></span> 
4. <span data-ttu-id="833e6-142">選取專案，以查看有關修正動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="833e6-142">Select an item to view more details about that remediation action.</span></span>
 
## <a name="undo-completed-actions"></a><span data-ttu-id="833e6-143">復原完成的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-143">Undo completed actions</span></span>

<span data-ttu-id="833e6-144">如果您已判斷某個裝置或檔案不是威脅，您可以復原採取的修正動作，不論這些動作是自動或手動採取的動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-144">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="833e6-145">在 [ **記錄** ] 索引標籤上的 [操作中心] 中，您可以復原下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="833e6-145">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="833e6-146">動作來源</span><span class="sxs-lookup"><span data-stu-id="833e6-146">Action source</span></span> | <span data-ttu-id="833e6-147">支援的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-147">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="833e6-148">-自動調查</span><span class="sxs-lookup"><span data-stu-id="833e6-148">- Automated investigation</span></span> <br/><span data-ttu-id="833e6-149">-Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="833e6-149">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="833e6-150">-手動回應動作</span><span class="sxs-lookup"><span data-stu-id="833e6-150">- Manual response actions</span></span> | <span data-ttu-id="833e6-151">隔離裝置</span><span class="sxs-lookup"><span data-stu-id="833e6-151">- Isolate device</span></span> <br/><span data-ttu-id="833e6-152">-限制執行程式碼</span><span class="sxs-lookup"><span data-stu-id="833e6-152">- Restrict code execution</span></span> <br/><span data-ttu-id="833e6-153">-隔離檔</span><span class="sxs-lookup"><span data-stu-id="833e6-153">- Quarantine a file</span></span> <br/><span data-ttu-id="833e6-154">-移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="833e6-154">- Remove a registry key</span></span> <br/><span data-ttu-id="833e6-155">-停止服務</span><span class="sxs-lookup"><span data-stu-id="833e6-155">- Stop a service</span></span> <br/><span data-ttu-id="833e6-156">-停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="833e6-156">- Disable a driver</span></span> <br/><span data-ttu-id="833e6-157">-移除排程任務</span><span class="sxs-lookup"><span data-stu-id="833e6-157">- Remove a scheduled task</span></span> |

### <a name="to-undo-multiple-actions-at-one-time"></a><span data-ttu-id="833e6-158">一次取消執行多個動作</span><span class="sxs-lookup"><span data-stu-id="833e6-158">To undo multiple actions at one time</span></span>

1. <span data-ttu-id="833e6-159">請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="833e6-159">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="833e6-160">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-160">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="833e6-161">請務必選取具有相同動作類型的專案。</span><span class="sxs-lookup"><span data-stu-id="833e6-161">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="833e6-162">隨即開啟彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="833e6-162">A flyout pane opens.</span></span>
3. <span data-ttu-id="833e6-163">在快顯視窗中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="833e6-163">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="833e6-164">在多個裝置間移除隔離檔</span><span class="sxs-lookup"><span data-stu-id="833e6-164">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="833e6-165">請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="833e6-165">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="833e6-166">在 [ **記錄** ] 索引標籤上，選取具有 [ **隔離** 檔] 動作類型的專案。</span><span class="sxs-lookup"><span data-stu-id="833e6-166">On the **History** tab, select an item that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="833e6-167">在飛入窗格中，選取 [套用 **至此檔案的 X 個實例**]，然後選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="833e6-167">In the flyout pane, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a><span data-ttu-id="833e6-168">自動化層級、自動調查結果和結果動作</span><span class="sxs-lookup"><span data-stu-id="833e6-168">Automation levels, automated investigation results, and resulting actions</span></span>

<span data-ttu-id="833e6-169">自動化層級會影響是否會自動或只在核准時採取某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-169">Automation levels affect whether certain remediation actions are taken automatically or only upon approval.</span></span> <span data-ttu-id="833e6-170">在某些情況下，您的安全性作業小組也會有更多步驟，視自動調查的結果而定。</span><span class="sxs-lookup"><span data-stu-id="833e6-170">Sometimes your security operations team has more steps to take, depending on the results of an automated investigation.</span></span> <span data-ttu-id="833e6-171">下表摘要說明自動化層級、自動化調查的結果，以及每個案例中應執行的動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-171">The following table summarizes automation levels, results of automated investigations, and what to do in each case.</span></span> 

|<span data-ttu-id="833e6-172">裝置群組設定</span><span class="sxs-lookup"><span data-stu-id="833e6-172">Device group setting</span></span> | <span data-ttu-id="833e6-173">自動調查結果</span><span class="sxs-lookup"><span data-stu-id="833e6-173">Automated investigation results</span></span> | <span data-ttu-id="833e6-174">處理方式</span><span class="sxs-lookup"><span data-stu-id="833e6-174">What to do</span></span> |
|:---|:---|:---|
|<span data-ttu-id="833e6-175">**完整修正威脅會自動** (建議設定) </span><span class="sxs-lookup"><span data-stu-id="833e6-175">**Full - remediate threats automatically** (the recommended setting)</span></span> |<span data-ttu-id="833e6-176">對一條證據達成 *惡意的蓄意* 性。</span><span class="sxs-lookup"><span data-stu-id="833e6-176">A verdict of *Malicious* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-177">系統會自動採取適當的修復動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-177">Appropriate remediation actions are taken automatically.</span></span> |[<span data-ttu-id="833e6-178">查看已完成的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-178">Review completed actions</span></span>](#review-completed-actions) |
|<span data-ttu-id="833e6-179">**自動修正威脅**</span><span class="sxs-lookup"><span data-stu-id="833e6-179">**Full - remediate threats automatically**</span></span> |<span data-ttu-id="833e6-180">有一條證據會達到 *可疑* 的判定。</span><span class="sxs-lookup"><span data-stu-id="833e6-180">A verdict of *Suspicious* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-181">修正動作正待核准，繼續進行。</span><span class="sxs-lookup"><span data-stu-id="833e6-181">Remediation actions are pending approval to proceed.</span></span> | [<span data-ttu-id="833e6-182">核准 (或拒絕) 擱置的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-182">Approve (or reject) pending actions</span></span>](#review-pending-actions) |
|<span data-ttu-id="833e6-183">**半要求進行任何修正的核准**</span><span class="sxs-lookup"><span data-stu-id="833e6-183">**Semi - require approval for any remediation**</span></span>  |<span data-ttu-id="833e6-184">針對某個證據，會達到對 *惡意* 或 *可疑* 的判定。</span><span class="sxs-lookup"><span data-stu-id="833e6-184">A verdict of either *Malicious* or *Suspicious* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-185">修正動作正待核准，繼續進行。</span><span class="sxs-lookup"><span data-stu-id="833e6-185">Remediation actions are pending approval to proceed.</span></span>  |[<span data-ttu-id="833e6-186">核准 (或拒絕) 擱置的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-186">Approve (or reject) pending actions</span></span>](#review-pending-actions) |
|<span data-ttu-id="833e6-187">**半自動要求核心資料夾修正的核准**</span><span class="sxs-lookup"><span data-stu-id="833e6-187">**Semi - require approval for core folders remediation**</span></span> |<span data-ttu-id="833e6-188">對一條證據達成 *惡意的蓄意* 性。</span><span class="sxs-lookup"><span data-stu-id="833e6-188">A verdict of *Malicious* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-189">如果專案是檔案或可執行檔，且位於作業系統目錄中，例如 Windows 資料夾或 Program files 資料夾，則修正動作會等候等候核准。</span><span class="sxs-lookup"><span data-stu-id="833e6-189">If the artifact is a file or executable and is in an operating system directory, such as the Windows folder or the Program files folder, then remediation actions are pending approval.</span></span> <br/><br/><span data-ttu-id="833e6-190">如果專案 *不* 在作業系統目錄中，就會自動採取修復動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-190">If the artifact is *not* in an operating system directory, remediation actions are taken automatically.</span></span> |<span data-ttu-id="833e6-191">1. [核准 (或拒絕) 擱置的動作](#review-pending-actions)</span><span class="sxs-lookup"><span data-stu-id="833e6-191">1. [Approve (or reject) pending actions](#review-pending-actions)</span></span><br/><br/><span data-ttu-id="833e6-192">2. [檢查完成的動作](#review-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="833e6-192">2. [Review completed actions](#review-completed-actions)</span></span> |
|<span data-ttu-id="833e6-193">**半自動要求核心資料夾修正的核准**</span><span class="sxs-lookup"><span data-stu-id="833e6-193">**Semi - require approval for core folders remediation**</span></span> |<span data-ttu-id="833e6-194">有一條證據會達到 *可疑* 的判定。</span><span class="sxs-lookup"><span data-stu-id="833e6-194">A verdict of *Suspicious* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-195">修正動作正待核准。</span><span class="sxs-lookup"><span data-stu-id="833e6-195">Remediation actions are pending approval.</span></span>  |<span data-ttu-id="833e6-196">[核准 (或拒絕) 擱置的動作](#review-pending-actions)。</span><span class="sxs-lookup"><span data-stu-id="833e6-196">[Approve (or reject) pending actions](#review-pending-actions).</span></span>|
|<span data-ttu-id="833e6-197">**非 temp 資料夾修正的半要求核准**</span><span class="sxs-lookup"><span data-stu-id="833e6-197">**Semi - require approval for non-temp folders remediation**</span></span> |<span data-ttu-id="833e6-198">對一條證據達成 *惡意的蓄意* 性。</span><span class="sxs-lookup"><span data-stu-id="833e6-198">A verdict of *Malicious* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-199">如果專案是不在暫存資料夾中的檔案或可執行檔，例如使用者的 [下載] 資料夾或 temp 資料夾，則修正動作會等候進行核准。</span><span class="sxs-lookup"><span data-stu-id="833e6-199">If the artifact is a file or executable that is not in a temporary folder, such as the user's downloads folder or temp folder, remediation actions are pending approval.</span></span> <br/><br/><span data-ttu-id="833e6-200">如果專案是暫存資料夾中的檔案或可執行檔 *，便會* 自動採取修正動作。</span><span class="sxs-lookup"><span data-stu-id="833e6-200">If the artifact is a file or executable that *is* in a temporary folder, remediation actions are taken automatically.</span></span>  |<span data-ttu-id="833e6-201">1. [核准 (或拒絕) 擱置的動作](#review-pending-actions)</span><span class="sxs-lookup"><span data-stu-id="833e6-201">1. [Approve (or reject) pending actions](#review-pending-actions)</span></span><br/><br/><span data-ttu-id="833e6-202">2. [檢查完成的動作](#review-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="833e6-202">2. [Review completed actions](#review-completed-actions)</span></span>  |
|<span data-ttu-id="833e6-203">**非 temp 資料夾修正的半要求核准**</span><span class="sxs-lookup"><span data-stu-id="833e6-203">**Semi - require approval for non-temp folders remediation**</span></span> |<span data-ttu-id="833e6-204">有一條證據會達到 *可疑* 的判定。</span><span class="sxs-lookup"><span data-stu-id="833e6-204">A verdict of *Suspicious* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-205">修正動作正待核准。</span><span class="sxs-lookup"><span data-stu-id="833e6-205">Remediation actions are pending approval.</span></span> |[<span data-ttu-id="833e6-206">核准 (或拒絕) 擱置的動作</span><span class="sxs-lookup"><span data-stu-id="833e6-206">Approve (or reject) pending actions</span></span>](#review-pending-actions)  | 
|<span data-ttu-id="833e6-207">任何 **完整** 或 **半成品** 的自動化層級</span><span class="sxs-lookup"><span data-stu-id="833e6-207">Any of the **Full** or **Semi** automation levels</span></span> |<span data-ttu-id="833e6-208">對某項證據的判定，未 *找到任何威脅* 。</span><span class="sxs-lookup"><span data-stu-id="833e6-208">A verdict of *No threats found* is reached for a piece of evidence.</span></span> <br/><br/><span data-ttu-id="833e6-209">不會採取任何修正動作，也不會有任何動作正待核准。</span><span class="sxs-lookup"><span data-stu-id="833e6-209">No remediation actions are taken, and no actions are pending approval.</span></span> |[<span data-ttu-id="833e6-210">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="833e6-210">View details and results of automated investigations</span></span>](/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|<span data-ttu-id="833e6-211">不建議使用 **自動回應** () </span><span class="sxs-lookup"><span data-stu-id="833e6-211">**No automated response** (not recommended)</span></span>|<span data-ttu-id="833e6-212">不會執行自動調查，因此不會達到 verdicts，也不會採取任何修正動作，也不會等候核准。</span><span class="sxs-lookup"><span data-stu-id="833e6-212">No automated investigations run, so no verdicts are reached, and no remediation actions are taken or awaiting approval.</span></span> |[<span data-ttu-id="833e6-213">考慮設定或變更您的裝置群組，以使用 **完整** 或 **半** 個自動化</span><span class="sxs-lookup"><span data-stu-id="833e6-213">Consider setting up or changing your device groups to use **Full** or **Semi** automation</span></span>](/microsoft-365/security/defender-endpoint/machine-groups) |

<span data-ttu-id="833e6-214">在 Microsoft Defender for Endpoint 中，所有的 verdicts 都會在「 [行動中心](auto-investigation-action-center.md#new-a-unified-action-center)」追蹤。</span><span class="sxs-lookup"><span data-stu-id="833e6-214">In Microsoft Defender for Endpoint, all verdicts are tracked in the [Action center](auto-investigation-action-center.md#new-a-unified-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="833e6-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="833e6-215">Next steps</span></span>

- [<span data-ttu-id="833e6-216">深入瞭解即時回應功能</span><span class="sxs-lookup"><span data-stu-id="833e6-216">Learn about live response capabilities</span></span>](live-response.md)
- [<span data-ttu-id="833e6-217">使用高級搜尋主動搜尋威脅</span><span class="sxs-lookup"><span data-stu-id="833e6-217">Proactively hunt for threats with advanced hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="833e6-218">解決適用於端點的 Microsoft Defender 中的誤判/漏報</span><span class="sxs-lookup"><span data-stu-id="833e6-218">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="833e6-219">另請參閱</span><span class="sxs-lookup"><span data-stu-id="833e6-219">See also</span></span>

- [<span data-ttu-id="833e6-220">自動化調查的概述</span><span class="sxs-lookup"><span data-stu-id="833e6-220">Overview of automated investigations</span></span>](automated-investigations.md)
