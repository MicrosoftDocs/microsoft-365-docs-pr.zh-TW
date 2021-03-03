---
title: 在 Microsoft Defender for Office 365 中複查和管理修正動作
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: 深入瞭解 Microsoft Defender for Office 365 方案2中自動調查和回應功能的修復動作。
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 40d0d8a14e0dd340d931a1c43425854b96702c65
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407091"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="8adda-104">在 Office 365 中複查及管理修正動作</span><span class="sxs-lookup"><span data-stu-id="8adda-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="8adda-105">隨著電子郵件的自動調查 & 共同作業會導致 verdicts （例如 *惡意* 或 *可疑*）建立某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="8adda-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="8adda-106">在 Microsoft Defender for Office 365 中，修正動作可包含：</span><span class="sxs-lookup"><span data-stu-id="8adda-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="8adda-107">封鎖 URL (按時) </span><span class="sxs-lookup"><span data-stu-id="8adda-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="8adda-108">虛刪除電子郵件訊息或聚簇</span><span class="sxs-lookup"><span data-stu-id="8adda-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="8adda-109">隔離電子郵件或電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="8adda-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="8adda-110">關閉外部郵件轉發</span><span class="sxs-lookup"><span data-stu-id="8adda-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="8adda-111">除非安全運作小組批准，否則不會採取這些修復動作。</span><span class="sxs-lookup"><span data-stu-id="8adda-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="8adda-112">我們建議您儘快檢查及核准任何擱置的動作，以便您的自動化調查能夠及時完成。</span><span class="sxs-lookup"><span data-stu-id="8adda-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="8adda-113">在某些情況下，您可以復原修復動作。</span><span class="sxs-lookup"><span data-stu-id="8adda-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="8adda-114">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8adda-114">**Applies to**</span></span>
- [<span data-ttu-id="8adda-115">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="8adda-115">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8adda-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8adda-116">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="8adda-117">核准 (或拒絕) 擱置的動作</span><span class="sxs-lookup"><span data-stu-id="8adda-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="8adda-118">請移至 Microsoft 365 security center (<https://security.microsoft.com>) 並登入。</span><span class="sxs-lookup"><span data-stu-id="8adda-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="8adda-119">在功能窗格中，選取 [ **動作中心**]。</span><span class="sxs-lookup"><span data-stu-id="8adda-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="8adda-120">在 [ **暫** 止] 索引標籤上，查看等候核准的動作清單。</span><span class="sxs-lookup"><span data-stu-id="8adda-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="8adda-121">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="8adda-121">Select an item in the list.</span></span> <span data-ttu-id="8adda-122">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="8adda-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="8adda-123">查看彈出窗格中的資訊，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="8adda-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="8adda-124">選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8adda-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="8adda-125">選取 [ **核准** ] 以啟動暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="8adda-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="8adda-126">選取 [ **拒絕** ] 以避免採取暫止的動作。</span><span class="sxs-lookup"><span data-stu-id="8adda-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="8adda-127">復原一個修正動作</span><span class="sxs-lookup"><span data-stu-id="8adda-127">Undo one remediation action</span></span>

1. <span data-ttu-id="8adda-128">請移至「行動中心」 (<https://security.microsoft.com/action-center>) 並登入。</span><span class="sxs-lookup"><span data-stu-id="8adda-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="8adda-129">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="8adda-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="8adda-130">在螢幕右側的窗格中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="8adda-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="8adda-131">復原多項修復動作</span><span class="sxs-lookup"><span data-stu-id="8adda-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="8adda-132">請移至「行動中心」 (<https://security.microsoft.com/action-center>) 並登入。</span><span class="sxs-lookup"><span data-stu-id="8adda-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="8adda-133">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="8adda-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="8adda-134">請務必選取具有相同動作類型的專案。</span><span class="sxs-lookup"><span data-stu-id="8adda-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="8adda-135">隨即開啟彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="8adda-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="8adda-136">在快顯視窗中，選取 [復原]。</span><span class="sxs-lookup"><span data-stu-id="8adda-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="8adda-137">在多個裝置間移除隔離檔</span><span class="sxs-lookup"><span data-stu-id="8adda-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="8adda-138">請移至「行動中心」 (<https://security.microsoft.com/action-center>) 並登入。</span><span class="sxs-lookup"><span data-stu-id="8adda-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="8adda-139">在 [ **記錄** ] 索引標籤上，選取具有 [ **隔離** 檔] 動作類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="8adda-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="8adda-140">在螢幕右側的窗格中，選取 [套用至此檔案 **的 X 個實例**]，然後選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="8adda-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8adda-141">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8adda-141">Next steps</span></span>

- [<span data-ttu-id="8adda-142">使用威脅瀏覽器</span><span class="sxs-lookup"><span data-stu-id="8adda-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="8adda-143">如何在自動化調查和回應功能中報告誤報/負片</span><span class="sxs-lookup"><span data-stu-id="8adda-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="8adda-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8adda-144">See also</span></span>

- [<span data-ttu-id="8adda-145">在 Office 365 中查看自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="8adda-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
