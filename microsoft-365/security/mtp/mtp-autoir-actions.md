---
title: 核准或拒絕自動調查後擱置的動作
description: 使用重要訊息中心來管理與自動化調查和回應相關的動作
keywords: 動作, 中心, autoair, 自動化, 調查, 回應, 補救
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930375"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="e3c50-104">核准或拒絕自動調查後擱置的動作</span><span class="sxs-lookup"><span data-stu-id="e3c50-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3c50-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e3c50-105">**Applies to:**</span></span>
- <span data-ttu-id="e3c50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3c50-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e3c50-107">當自動化調查執行時，可能會導致需要核准才能繼續的一或多個[補救動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)。</span><span class="sxs-lookup"><span data-stu-id="e3c50-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="e3c50-108">例如，可能需要刪除一組電子郵件訊息，或可能需要移除隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="e3c50-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="e3c50-109">務必盡快核准 (或拒絕) 擱置中的動作，這樣您的自動化調查才能及時進行和完成。</span><span class="sxs-lookup"><span data-stu-id="e3c50-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="e3c50-110">如果您認為 Microsoft 365 Defender 中的自動化調查及回應功能偵測到遺漏或錯誤，請告訴我們！</span><span class="sxs-lookup"><span data-stu-id="e3c50-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="e3c50-111">瞭解如何 [在 Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md)的 AIR (自動化調查及回應中) 誤報/負數。</span><span class="sxs-lookup"><span data-stu-id="e3c50-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="e3c50-112">您可以使用控制中心或調查詳細資料檢視來審查及核准[擱置](#review-a-pending-action-in-the-action-center)[中的動作](#review-a-pending-action-in-the-investigation-details-view)。</span><span class="sxs-lookup"><span data-stu-id="e3c50-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="e3c50-113">您必須具備[適當的權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，才能核准或拒絕補救動作。</span><span class="sxs-lookup"><span data-stu-id="e3c50-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="e3c50-114">詳細資訊請參閱 Microsoft [365 Defender 中自動化調查及回應的先決條件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="e3c50-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="e3c50-115">在重要訊息中心檢閱擱置中的動作</span><span class="sxs-lookup"><span data-stu-id="e3c50-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="e3c50-116">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="e3c50-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="e3c50-117">在功能窗格中，選擇 [重要訊息中心]。</span><span class="sxs-lookup"><span data-stu-id="e3c50-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="e3c50-118">在重要訊息中心的 [擱置中] 索引標籤上，選取清單中的一個項目。</span><span class="sxs-lookup"><span data-stu-id="e3c50-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="e3c50-119">如果您選取 [調查編號] 資料行中的項目，調查詳細資料頁面會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="e3c50-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="e3c50-120">您可以在該處檢視調查結果，然後核准或拒絕建議的動作。</span><span class="sxs-lookup"><span data-stu-id="e3c50-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="e3c50-121">如果您選取清單中的資料列，就會開啟飛出視窗，您可以在此檢視該項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e3c50-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![核准或拒絕動作](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="e3c50-123">使用連結來檢視相關聯的警示或調查，並核准或拒絕動作。</span><span class="sxs-lookup"><span data-stu-id="e3c50-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="e3c50-124">在調查詳細資料檢視中檢閱擱置中的動作</span><span class="sxs-lookup"><span data-stu-id="e3c50-124">Review a pending action in the investigation details view</span></span>

![調查詳細資料](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="e3c50-126">在 [調查詳細資料][](mtp-autoir-results.md) 頁面上，選取 [擱置中的動作] (或 [動作]) 索引標籤。此處會列出核准擱置中的項目。</span><span class="sxs-lookup"><span data-stu-id="e3c50-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="e3c50-127">選取清單中的項目，然後選擇 [核准] 或 [拒絕]。</span><span class="sxs-lookup"><span data-stu-id="e3c50-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="e3c50-128">復原已完成的動作</span><span class="sxs-lookup"><span data-stu-id="e3c50-128">Undo completed actions</span></span>

<span data-ttu-id="e3c50-129">如果您確定裝置或檔案並非威脅，您可以復原已採取的補救動作，不論這些動作是自動或手動執行。</span><span class="sxs-lookup"><span data-stu-id="e3c50-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="e3c50-130">在控制中心的歷程記錄上，您可以復原下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="e3c50-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="e3c50-131">動作來源</span><span class="sxs-lookup"><span data-stu-id="e3c50-131">Action source</span></span> | <span data-ttu-id="e3c50-132">支援的動作</span><span class="sxs-lookup"><span data-stu-id="e3c50-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="e3c50-133">- 自動化調查</span><span class="sxs-lookup"><span data-stu-id="e3c50-133">- Automated investigation</span></span> <br/><span data-ttu-id="e3c50-134">- Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="e3c50-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="e3c50-135">- 手動回應動作</span><span class="sxs-lookup"><span data-stu-id="e3c50-135">- Manual response actions</span></span> | <span data-ttu-id="e3c50-136">- 隔離裝置</span><span class="sxs-lookup"><span data-stu-id="e3c50-136">- Isolate device</span></span> <br/><span data-ttu-id="e3c50-137">- 限制程式碼執行</span><span class="sxs-lookup"><span data-stu-id="e3c50-137">- Restrict code execution</span></span> <br/><span data-ttu-id="e3c50-138">- 隔離檔案</span><span class="sxs-lookup"><span data-stu-id="e3c50-138">- Quarantine a file</span></span> <br/><span data-ttu-id="e3c50-139">- 移除註冊表鍵</span><span class="sxs-lookup"><span data-stu-id="e3c50-139">- Remove a registry key</span></span> <br/><span data-ttu-id="e3c50-140">- 停止服務</span><span class="sxs-lookup"><span data-stu-id="e3c50-140">- Stop a service</span></span> <br/><span data-ttu-id="e3c50-141">- 停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="e3c50-141">- Disable a driver</span></span> <br/><span data-ttu-id="e3c50-142">- 移除排程任務</span><span class="sxs-lookup"><span data-stu-id="e3c50-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="e3c50-143">復原補救動作</span><span class="sxs-lookup"><span data-stu-id="e3c50-143">To undo a remediation action</span></span>

1. <span data-ttu-id="e3c50-144">請前往控制中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 並登出。</span><span class="sxs-lookup"><span data-stu-id="e3c50-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="e3c50-145">在歷程 **記錄上** ，選取要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="e3c50-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="e3c50-146">在畫面右側窗格中，選取 **復原。**</span><span class="sxs-lookup"><span data-stu-id="e3c50-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="e3c50-147">若要從跨多部裝置隔離移除檔案</span><span class="sxs-lookup"><span data-stu-id="e3c50-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="e3c50-148">請前往控制中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 並登出。</span><span class="sxs-lookup"><span data-stu-id="e3c50-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="e3c50-149">在歷程 **記錄 Tab** 上，選取具有動作類型 **隔離檔案的檔案**。</span><span class="sxs-lookup"><span data-stu-id="e3c50-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="e3c50-150">在畫面右邊的窗格中，選取此檔案的更多X 個實例，然後 **選取復原。**</span><span class="sxs-lookup"><span data-stu-id="e3c50-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3c50-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e3c50-151">Next steps</span></span>

- [<span data-ttu-id="e3c50-152">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="e3c50-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="e3c50-153">在自動化調查與回應功能中處理誤對/負數</span><span class="sxs-lookup"><span data-stu-id="e3c50-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
