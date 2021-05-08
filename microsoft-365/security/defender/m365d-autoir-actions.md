---
title: 在行動中心中查看及管理動作
description: 使用「行動中心」來查看及管理修正動作
keywords: 動作, 中心, autoair, 自動化, 調查, 回應, 補救
search.appverid: met150
ms.prod: m365-security
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: e3e842f812c5675334cc25fa35544165129db2b4
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245885"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="36cbf-104">在行動中心中查看及管理動作</span><span class="sxs-lookup"><span data-stu-id="36cbf-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="36cbf-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="36cbf-105">**Applies to:**</span></span>
- <span data-ttu-id="36cbf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36cbf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="36cbf-107">Microsoft 365 Defender 中的威脅防護功能可能會導致某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="36cbf-108">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="36cbf-108">Here are some examples:</span></span>
- <span data-ttu-id="36cbf-109">[自動調查](m365d-autoir.md) 可能會導致自動或等待核准的修復動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="36cbf-110">防毒程式、反惡意程式碼和其他威脅防護功能可能會導致修復動作，例如封鎖檔案、URL 或程式，或將專案傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="36cbf-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="36cbf-111">您的安全性運作小組可以手動採取補救措施，例如在 [高級搜尋](advanced-hunting-overview.md) 期間或調查 [警示](investigate-alerts.md) 或 [事件](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="36cbf-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36cbf-112">您必須具備[適當的權限](m365d-action-center.md#required-permissions-for-action-center-tasks)，才能核准或拒絕補救動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="36cbf-113">如需詳細資訊，請參閱[在 Microsoft 365 Defender 中進行自動調查和回應的必要條件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="36cbf-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="36cbf-114">在重要中心檢查擱置的動作</span><span class="sxs-lookup"><span data-stu-id="36cbf-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="36cbf-115">務必盡快核准 (或拒絕) 擱置中的動作，這樣您的自動化調查才能及時進行和完成。</span><span class="sxs-lookup"><span data-stu-id="36cbf-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![核准或拒絕動作](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="36cbf-117">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="36cbf-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="36cbf-118">在功能窗格中，選擇 [重要訊息中心]。</span><span class="sxs-lookup"><span data-stu-id="36cbf-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="36cbf-119">在重要訊息中心的 [擱置中] 索引標籤上，選取清單中的一個項目。</span><span class="sxs-lookup"><span data-stu-id="36cbf-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="36cbf-120">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="36cbf-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="36cbf-121">查看彈出窗格中的資訊，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="36cbf-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="36cbf-122">選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="36cbf-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="36cbf-123">選取 [ **核准** ] 以啟動暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="36cbf-124">選取 [ **拒絕** ] 以避免採取暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="36cbf-125">選取 [ **移至搜尋** ] 以進入 [高級搜尋](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="36cbf-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="36cbf-126">復原完成的動作</span><span class="sxs-lookup"><span data-stu-id="36cbf-126">Undo completed actions</span></span>

<span data-ttu-id="36cbf-127">如果您已判斷某個裝置或檔案不是威脅，您可以復原採取的修正動作，不論這些動作是自動或手動採取的動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="36cbf-128">在 [ **記錄** ] 索引標籤上的 [操作中心] 中，您可以復原下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="36cbf-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="36cbf-129">動作來源</span><span class="sxs-lookup"><span data-stu-id="36cbf-129">Action source</span></span> | <span data-ttu-id="36cbf-130">支援的動作</span><span class="sxs-lookup"><span data-stu-id="36cbf-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="36cbf-131">-自動調查</span><span class="sxs-lookup"><span data-stu-id="36cbf-131">- Automated investigation</span></span> <br/><span data-ttu-id="36cbf-132">-Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="36cbf-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="36cbf-133">-手動回應動作</span><span class="sxs-lookup"><span data-stu-id="36cbf-133">- Manual response actions</span></span> | <span data-ttu-id="36cbf-134">隔離裝置</span><span class="sxs-lookup"><span data-stu-id="36cbf-134">- Isolate device</span></span> <br/><span data-ttu-id="36cbf-135">-限制執行程式碼</span><span class="sxs-lookup"><span data-stu-id="36cbf-135">- Restrict code execution</span></span> <br/><span data-ttu-id="36cbf-136">-隔離檔</span><span class="sxs-lookup"><span data-stu-id="36cbf-136">- Quarantine a file</span></span> <br/><span data-ttu-id="36cbf-137">-移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="36cbf-137">- Remove a registry key</span></span> <br/><span data-ttu-id="36cbf-138">-停止服務</span><span class="sxs-lookup"><span data-stu-id="36cbf-138">- Stop a service</span></span> <br/><span data-ttu-id="36cbf-139">-停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="36cbf-139">- Disable a driver</span></span> <br/><span data-ttu-id="36cbf-140">-移除排程任務</span><span class="sxs-lookup"><span data-stu-id="36cbf-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="36cbf-141">復原一個修正動作</span><span class="sxs-lookup"><span data-stu-id="36cbf-141">Undo one remediation action</span></span>

1. <span data-ttu-id="36cbf-142">請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="36cbf-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="36cbf-143">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="36cbf-144">在螢幕右側的窗格中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="36cbf-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="36cbf-145">復原多項修復動作</span><span class="sxs-lookup"><span data-stu-id="36cbf-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="36cbf-146">請移至「行動中心」 (https://security.microsoft.com/action-center) 並登入。</span><span class="sxs-lookup"><span data-stu-id="36cbf-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="36cbf-147">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="36cbf-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="36cbf-148">請務必選取具有相同動作類型的專案。</span><span class="sxs-lookup"><span data-stu-id="36cbf-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="36cbf-149">隨即開啟彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="36cbf-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="36cbf-150">在快顯視窗中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="36cbf-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="36cbf-151">在多個裝置間移除隔離檔</span><span class="sxs-lookup"><span data-stu-id="36cbf-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="36cbf-152">請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="36cbf-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="36cbf-153">在 [ **記錄** ] 索引標籤上，選取具有 [ **隔離** 檔] 動作類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="36cbf-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="36cbf-154">在螢幕右側的窗格中，選取 [套用至此檔案 **的 X 個實例**]，然後選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="36cbf-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="36cbf-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="36cbf-155">Next steps</span></span>

- [<span data-ttu-id="36cbf-156">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="36cbf-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="36cbf-157">瞭解如何處理誤報/負片 (如果您取得一個) </span><span class="sxs-lookup"><span data-stu-id="36cbf-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
