---
title: 在 Microsoft Defender for Office 365 中檢查和管理修正動作
keywords: AIR，autoIR，Microsoft Defender for Endpoint，自動化，調查，回應，修正，威脅，高級，威脅，保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 深入瞭解 Microsoft Defender 中 Office 365 方案2的自動化調查和回應功能中的修復動作。
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028928"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="03774-104">在 Office 365 中檢查和管理修正動作</span><span class="sxs-lookup"><span data-stu-id="03774-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="03774-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="03774-105">**Applies to**</span></span>
- [<span data-ttu-id="03774-106">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="03774-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="03774-107">隨著電子郵件的自動調查 & 共同作業會導致 verdicts （例如 *惡意* 或 *可疑*）建立某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="03774-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="03774-108">在 Microsoft Defender for Office 365 中，修正動作可包含：</span><span class="sxs-lookup"><span data-stu-id="03774-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="03774-109">虛刪除電子郵件訊息或聚簇</span><span class="sxs-lookup"><span data-stu-id="03774-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="03774-110">關閉外部郵件轉發</span><span class="sxs-lookup"><span data-stu-id="03774-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="03774-111">除非安全運作小組批准，否則不會採取這些修復動作。</span><span class="sxs-lookup"><span data-stu-id="03774-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="03774-112">我們建議您儘快檢查及核准任何擱置的動作，以便您的自動化調查能夠及時完成。</span><span class="sxs-lookup"><span data-stu-id="03774-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="03774-113">在某些情況下，您可以重新考慮提交的動作。</span><span class="sxs-lookup"><span data-stu-id="03774-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="03774-114">您必須是搜尋 & 清除角色的一部分，才能採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="03774-114">You need to be part of Search & purge role before taking any actions.</span></span>


## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="03774-115">核准 (或拒絕) 擱置的動作</span><span class="sxs-lookup"><span data-stu-id="03774-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="03774-116">有四種不同的方式可尋找及採取自動調查動作：</span><span class="sxs-lookup"><span data-stu-id="03774-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="03774-117">事件佇列</span><span class="sxs-lookup"><span data-stu-id="03774-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="03774-118">控制中心</span><span class="sxs-lookup"><span data-stu-id="03774-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="03774-119">自行調查 (透過事件或警示存取) </span><span class="sxs-lookup"><span data-stu-id="03774-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="03774-120">調查和修正調查佇列</span><span class="sxs-lookup"><span data-stu-id="03774-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="03774-121">事件佇列</span><span class="sxs-lookup"><span data-stu-id="03774-121">Incident queue</span></span>
1. <span data-ttu-id="03774-122">請移至[Microsoft 365 的安全性中心](https://security.microsoft.com)並登入。</span><span class="sxs-lookup"><span data-stu-id="03774-122">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="03774-123">在功能窗格中，選取 [ **事件] & 警示 > 事件**。</span><span class="sxs-lookup"><span data-stu-id="03774-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="03774-124">選取 [事件名稱] 以開啟其 [摘要] 頁面。</span><span class="sxs-lookup"><span data-stu-id="03774-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="03774-125">選取 [ **證據與回應** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="03774-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="03774-126">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="03774-126">Select an item in the list.</span></span> <span data-ttu-id="03774-127">其側邊窗格隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="03774-127">Its side pane opens.</span></span>
6. <span data-ttu-id="03774-128">在側窗格中，進行核准或拒絕動作。</span><span class="sxs-lookup"><span data-stu-id="03774-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="03774-129">調查佇列</span><span class="sxs-lookup"><span data-stu-id="03774-129">Investigation queue</span></span> 
1. <span data-ttu-id="03774-130">請移至[Microsoft 365 的安全性中心](https://security.microsoft.com)並登入。</span><span class="sxs-lookup"><span data-stu-id="03774-130">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="03774-131">從 [警示/事件] 頁面流覽。</span><span class="sxs-lookup"><span data-stu-id="03774-131">Navigate from the alerts/incident page.</span></span> 
3. <span data-ttu-id="03774-132">在 [調查] 頁面上，移至 [ **擱置的動作** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="03774-132">On the Investigation page, go to the **pending actions** tab.</span></span> 
4. <span data-ttu-id="03774-133">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="03774-133">Select an item in the list.</span></span> <span data-ttu-id="03774-134">其側邊窗格隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="03774-134">Its side pane opens.</span></span>  
5. <span data-ttu-id="03774-135">在側窗格中，進行核准或拒絕動作。</span><span class="sxs-lookup"><span data-stu-id="03774-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="03774-136">控制中心</span><span class="sxs-lookup"><span data-stu-id="03774-136">Action center</span></span>
1. <span data-ttu-id="03774-137">請移至[Microsoft 365 的安全性中心](https://security.microsoft.com)並登入。</span><span class="sxs-lookup"><span data-stu-id="03774-137">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="03774-138">在功能窗格中，選取 [ **動作中心**]。</span><span class="sxs-lookup"><span data-stu-id="03774-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="03774-139">在 [ **暫** 止] 索引標籤上，查看等候核准的動作清單。</span><span class="sxs-lookup"><span data-stu-id="03774-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="03774-140">選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="03774-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="03774-141">選取 [ **核准** ] 以啟動暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="03774-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="03774-142">選取 [ **拒絕** ] 以避免採取暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="03774-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="03774-143">調查和修正調查佇列</span><span class="sxs-lookup"><span data-stu-id="03774-143">Investigation and remediation investigations queue</span></span>
1. <span data-ttu-id="03774-144">請移至[Microsoft 365 的安全性中心](https://security.microsoft.com)並登入。</span><span class="sxs-lookup"><span data-stu-id="03774-144">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="03774-145">開啟暫止的調查。</span><span class="sxs-lookup"><span data-stu-id="03774-145">Open pending investigations.</span></span> 
3. <span data-ttu-id="03774-146">在 [調查] 頁面上，移至 [ **擱置的動作** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="03774-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="03774-147">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="03774-147">Select an item in the list.</span></span> <span data-ttu-id="03774-148">其側邊窗格隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="03774-148">Its side pane opens.</span></span>  
5. <span data-ttu-id="03774-149">在側窗格中，進行核准或拒絕動作。</span><span class="sxs-lookup"><span data-stu-id="03774-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="03774-150">變更或撤銷一個修正動作</span><span class="sxs-lookup"><span data-stu-id="03774-150">Change or undo one remediation action</span></span>

<span data-ttu-id="03774-151">有兩種不同的方式可重新考慮提交的動作：</span><span class="sxs-lookup"><span data-stu-id="03774-151">There are two different ways to reconsider submitted actions:</span></span>
   - <span data-ttu-id="03774-152">透過「 [整合」行動中心](https://security.microsoft.com/action-center)。</span><span class="sxs-lookup"><span data-stu-id="03774-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
   - <span data-ttu-id="03774-153">雖然[Office 的動作中心](https://security.microsoft.com/threatincidents)。</span><span class="sxs-lookup"><span data-stu-id="03774-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>
   
## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="03774-154">變更或撤銷整合動作中心</span><span class="sxs-lookup"><span data-stu-id="03774-154">Change or undo through the unified action center</span></span>
1. <span data-ttu-id="03774-155">移至 [ [整合] 動作中心](https://security.microsoft.com/action-center) 並登入。</span><span class="sxs-lookup"><span data-stu-id="03774-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="03774-156">在 [ **記錄** ] 索引標籤上，選取您要變更或撤銷的動作。</span><span class="sxs-lookup"><span data-stu-id="03774-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="03774-157">在螢幕右側的窗格中，選取適當的動作 (**移至 [收件** 匣]、[ **移至垃圾** 郵件]、[ **移至刪除的郵件**]、[\* 虛刪除] 或 [ **實刪除** ]) 。</span><span class="sxs-lookup"><span data-stu-id="03774-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, \*\*soft delete", or **hard delete**).</span></span>

 ## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="03774-158">變更或撤銷 Office 的活動中心</span><span class="sxs-lookup"><span data-stu-id="03774-158">Change or undo through the Office action center</span></span> 
1. <span data-ttu-id="03774-159">請移至[Office 的動作中心](https://security.microsoft.com/threatincidents)並登入。</span><span class="sxs-lookup"><span data-stu-id="03774-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="03774-160">選取適當的修復。</span><span class="sxs-lookup"><span data-stu-id="03774-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="03774-161">在側窗格中，按一下 [郵件提交專案]，然後等候載入清單。</span><span class="sxs-lookup"><span data-stu-id="03774-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span> 
4. <span data-ttu-id="03774-162">等候上方的動作按鈕以啟用並選取動作按鈕以變更動作類型。</span><span class="sxs-lookup"><span data-stu-id="03774-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span> 
5. <span data-ttu-id="03774-163">這將會建立適當的動作。</span><span class="sxs-lookup"><span data-stu-id="03774-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03774-164">後續步驟</span><span class="sxs-lookup"><span data-stu-id="03774-164">Next steps</span></span>

- [<span data-ttu-id="03774-165">使用威脅瀏覽器</span><span class="sxs-lookup"><span data-stu-id="03774-165">Use Threat Explorer</span></span>](threat-explorer.md) 
- [<span data-ttu-id="03774-166">系統管理/Manual 動作</span><span class="sxs-lookup"><span data-stu-id="03774-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="03774-167">如何在自動化調查和回應功能中報告誤報/負片</span><span class="sxs-lookup"><span data-stu-id="03774-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="03774-168">另請參閱</span><span class="sxs-lookup"><span data-stu-id="03774-168">See also</span></span>

- [<span data-ttu-id="03774-169">在 Office 365 中查看自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="03774-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
