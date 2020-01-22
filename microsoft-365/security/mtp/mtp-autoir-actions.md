---
title: 自動化調查後核准或拒絕擱置中的動作
description: 使用重要訊息中心來管理與自動化調查和回應相關的動作
keywords: 動作, 中心, autoair, 自動化, 調查, 回應, 補救
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 35433eccf93c56a8f8bf66b50fa6728ff7585d8e
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260201"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="f7a7c-104">核准或拒絕來自自動化調查的擱置中的動作</span><span class="sxs-lookup"><span data-stu-id="f7a7c-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="f7a7c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f7a7c-105">**Applies to:**</span></span>
- <span data-ttu-id="f7a7c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="f7a7c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f7a7c-107">當自動化調查執行時，可能會導致需要核准才能繼續的一或多個[補救動作](mtp-action-center.md#remediation-actions)。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-107">When an automated investigation runs, it can result in one or more [remediation actions](mtp-action-center.md#remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="f7a7c-108">例如，可能需要刪除一組電子郵件訊息，或可能需要移除隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="f7a7c-109">務必盡快核准 (或拒絕) 擱置中的動作，這樣您的自動化調查才能及時進行和完成。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="f7a7c-110">如果您認為某個項目已未接或錯誤偵測到的自動化的調查和 Microsoft 威脅防護中的回應功能，讓我們知道 ！</span><span class="sxs-lookup"><span data-stu-id="f7a7c-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="f7a7c-111">請參閱[How to 報告中自動進行調查並 Microsoft 威脅防護中的回應 （空調） 功能，則為 false positive/負號](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="f7a7c-112">使用以下數個方法中的一個可檢閱和核准擱置中的動作：</span><span class="sxs-lookup"><span data-stu-id="f7a7c-112">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="f7a7c-113">使用重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="f7a7c-113">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- [<span data-ttu-id="f7a7c-114">使用調查詳細資料檢視</span><span class="sxs-lookup"><span data-stu-id="f7a7c-114">Use the investigation details view</span></span>](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> <span data-ttu-id="f7a7c-115">您必須具備[適當的權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，才能核准或拒絕補救動作。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-115">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="f7a7c-116">在重要訊息中心檢閱擱置中的動作</span><span class="sxs-lookup"><span data-stu-id="f7a7c-116">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="f7a7c-117">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="f7a7c-118">在功能窗格中，選擇 [重要訊息中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="f7a7c-119">在重要訊息中心的 [擱置中]\*\*\*\* 索引標籤上，選取清單中的一個項目。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="f7a7c-120">如果您選取 [調查編號]\*\*\*\* 資料行中的項目，調查詳細資料頁面會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-120">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="f7a7c-121">您可以在該處檢視調查結果，然後核准或拒絕建議的動作。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-121">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="f7a7c-122">如果您選取清單中的資料列，就會開啟飛出視窗，您可以在此檢視該項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-122">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![核准或拒絕動作](../images/air-actioncenter-itemselected.png)<br/><span data-ttu-id="f7a7c-124">使用連結來檢視相關聯的警示或調查，並核准或拒絕動作。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-124">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="f7a7c-125">在調查詳細資料檢視中檢閱擱置中的動作</span><span class="sxs-lookup"><span data-stu-id="f7a7c-125">Review a pending action in the investigation details view</span></span>

![調查詳細資料](../images/mtp-air-investdetails.png)

1. <span data-ttu-id="f7a7c-127">在 [調查詳細資料][](mtp-autoir-results.md) 頁面上，選取 [擱置中的動作]\*\*\*\* (或 [動作]\*\*\*\*) 索引標籤。此處會列出核准擱置中的項目。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-127">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="f7a7c-128">選取清單中的項目，然後選擇 [核准]\*\*\*\* 或 [拒絕]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f7a7c-128">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7a7c-129">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f7a7c-129">Next steps</span></span>

- [<span data-ttu-id="f7a7c-130">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="f7a7c-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="f7a7c-131">深入了解事件</span><span class="sxs-lookup"><span data-stu-id="f7a7c-131">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="f7a7c-132">了解搜捕</span><span class="sxs-lookup"><span data-stu-id="f7a7c-132">Learn about hunting</span></span>](advanced-hunting-overview.md)
