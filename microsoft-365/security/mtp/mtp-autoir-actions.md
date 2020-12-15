---
title: 自動調查後核准或拒絕擱置的動作
description: 使用重要訊息中心來管理與自動化調查和回應相關的動作
keywords: 動作, 中心, autoair, 自動化, 調查, 回應, 補救
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683357"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="1f99a-104">自動調查後核准或拒絕擱置的動作</span><span class="sxs-lookup"><span data-stu-id="1f99a-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1f99a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1f99a-105">**Applies to:**</span></span>
- <span data-ttu-id="1f99a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f99a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1f99a-107">當自動化調查執行時，可能會導致需要核准才能繼續的一或多個[補救動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)。</span><span class="sxs-lookup"><span data-stu-id="1f99a-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="1f99a-108">例如，可能需要刪除一組電子郵件訊息，或可能需要移除隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="1f99a-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="1f99a-109">務必盡快核准 (或拒絕) 擱置中的動作，這樣您的自動化調查才能及時進行和完成。</span><span class="sxs-lookup"><span data-stu-id="1f99a-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="1f99a-110">如果您認為 Microsoft 365 Defender 中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請讓我們知道！</span><span class="sxs-lookup"><span data-stu-id="1f99a-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="1f99a-111">請參閱 [如何在自動調查和回應中報告誤報/負片 (Microsoft 365 Defender 中的 AIR) 功能](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="1f99a-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="1f99a-112">您可以使用「 [行動中心](#review-a-pending-action-in-the-action-center) 」或「 [調查詳細資料」視圖](#review-a-pending-action-in-the-investigation-details-view)，檢查和核准擱置的動作。</span><span class="sxs-lookup"><span data-stu-id="1f99a-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="1f99a-113">您必須具備[適當的權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，才能核准或拒絕補救動作。</span><span class="sxs-lookup"><span data-stu-id="1f99a-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="1f99a-114">如需詳細資訊，請參閱 [Microsoft 365 Defender 中自動調查和回應的必要條件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="1f99a-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="1f99a-115">在重要訊息中心檢閱擱置中的動作</span><span class="sxs-lookup"><span data-stu-id="1f99a-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="1f99a-116">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="1f99a-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="1f99a-117">在功能窗格中，選擇 [重要訊息中心]。</span><span class="sxs-lookup"><span data-stu-id="1f99a-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="1f99a-118">在重要訊息中心的 [擱置中] 索引標籤上，選取清單中的一個項目。</span><span class="sxs-lookup"><span data-stu-id="1f99a-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="1f99a-119">如果您選取 [調查編號] 資料行中的項目，調查詳細資料頁面會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="1f99a-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="1f99a-120">您可以在該處檢視調查結果，然後核准或拒絕建議的動作。</span><span class="sxs-lookup"><span data-stu-id="1f99a-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="1f99a-121">如果您選取清單中的資料列，就會開啟飛出視窗，您可以在此檢視該項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1f99a-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![核准或拒絕動作](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="1f99a-123">使用連結來檢視相關聯的警示或調查，並核准或拒絕動作。</span><span class="sxs-lookup"><span data-stu-id="1f99a-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="1f99a-124">在調查詳細資料檢視中檢閱擱置中的動作</span><span class="sxs-lookup"><span data-stu-id="1f99a-124">Review a pending action in the investigation details view</span></span>

![調查詳細資料](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="1f99a-126">在 [調查詳細資料][](mtp-autoir-results.md) 頁面上，選取 [擱置中的動作] (或 [動作]) 索引標籤。此處會列出核准擱置中的項目。</span><span class="sxs-lookup"><span data-stu-id="1f99a-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="1f99a-127">選取清單中的項目，然後選擇 [核准] 或 [拒絕]。</span><span class="sxs-lookup"><span data-stu-id="1f99a-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1f99a-128">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1f99a-128">Next steps</span></span>

- [<span data-ttu-id="1f99a-129">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="1f99a-129">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="1f99a-130">在自動化調查和回應功能中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="1f99a-130">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
