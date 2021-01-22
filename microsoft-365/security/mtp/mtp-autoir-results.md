---
title: 自動化調查詳細資料與結果
description: 在自動調查過程中和完成之後，您就可以查看結果和重要結果
keywords: 自動, 調查, 結果, 分析, 詳細資料, 修正, autoair
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
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930363"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="a1486-104">自動化調查詳細資料與結果</span><span class="sxs-lookup"><span data-stu-id="a1486-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a1486-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="a1486-105">**Applies to:**</span></span>
- <span data-ttu-id="a1486-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1486-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a1486-107">當 Microsoft 365 Defender 進行自動化調查時，可在自動化調查程式期間及之後獲得該調查的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a1486-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="a1486-108">如果您擁有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以在調查詳細資料檢視中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a1486-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="a1486-109">調查詳細資料檢視可提供您最新的狀態，以及核准任何待核准動作的能力。</span><span class="sxs-lookup"><span data-stu-id="a1486-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![調查詳細資料](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="a1486-111">開啟調查詳細資料檢視</span><span class="sxs-lookup"><span data-stu-id="a1486-111">Open the investigation details view</span></span>

<span data-ttu-id="a1486-112">您可以使用下列其中一種方法開啟調查詳細資料檢視：</span><span class="sxs-lookup"><span data-stu-id="a1486-112">You can open the investigation details view by using one of the following methods:</span></span>
- <span data-ttu-id="a1486-113">[選取 [控制中心] 中的項目](#select-an-item-in-the-action-center)</span><span class="sxs-lookup"><span data-stu-id="a1486-113">[Select an item in the Action center](#select-an-item-in-the-action-center)</span></span>
- [<span data-ttu-id="a1486-114">從事件詳細資料頁面中選取調查</span><span class="sxs-lookup"><span data-stu-id="a1486-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="a1486-115">選取 [控制中心] 中的項目</span><span class="sxs-lookup"><span data-stu-id="a1486-115">Select an item in the Action center</span></span>

<span data-ttu-id="a1486-116">使用 [控制中心] 查看處於待核准狀態 (在 [待核准] 索引標籤上) 或已核准 (在 [歷史記錄] 索引標籤上) 的動作。</span><span class="sxs-lookup"><span data-stu-id="a1486-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="a1486-117">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="a1486-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="a1486-118">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="a1486-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="a1486-119">在 [待核准] 或 [歷史記錄] 索引標籤上，選取一個項目。</span><span class="sxs-lookup"><span data-stu-id="a1486-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="a1486-120">如果您擁有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以核准 (或拒絕) 待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="a1486-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="a1486-121">從事件詳細資料頁面開啟調查</span><span class="sxs-lookup"><span data-stu-id="a1486-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="a1486-122">使用事件詳細資料頁面來查看事件的詳細資訊，包括觸發任何受影響裝置、使用者帳戶或信箱之資訊的警示。</span><span class="sxs-lookup"><span data-stu-id="a1486-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="a1486-123">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="a1486-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="a1486-124">在功能窗格中，選擇 [事件]。</span><span class="sxs-lookup"><span data-stu-id="a1486-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="a1486-125">選取清單中的項目以開啟事件詳細資料檢視。</span><span class="sxs-lookup"><span data-stu-id="a1486-125">Select an item in the list to open the incident details view.</span></span><br/>![事件詳細資料](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="a1486-127">在 [調查] 索引標籤上，選取清單中的調查。</span><span class="sxs-lookup"><span data-stu-id="a1486-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="a1486-128">調查詳細資料</span><span class="sxs-lookup"><span data-stu-id="a1486-128">Investigation details</span></span>

<span data-ttu-id="a1486-129">使用調查詳細資料檢視，查看與調查相關的過去、目前和待核准的活動。</span><span class="sxs-lookup"><span data-stu-id="a1486-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="a1486-130">調查詳細資料檢視類似以下影像：</span><span class="sxs-lookup"><span data-stu-id="a1486-130">The investigation details view resembles the following image:</span></span>

![調查詳細資料](../../media/mtp-air-investdetails.png)

<span data-ttu-id="a1486-132">在調查詳細資料檢視中，您可以在 [調查圖表]、[警示]、[裝置]、[身分識別]、[重要結果]、[實體]、**[記錄]**，以及 [待核准的動作] 索引標籤上查看資訊，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="a1486-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

| <span data-ttu-id="a1486-133">索引標籤</span><span class="sxs-lookup"><span data-stu-id="a1486-133">Tab</span></span> | <span data-ttu-id="a1486-134">描述</span><span class="sxs-lookup"><span data-stu-id="a1486-134">Description</span></span> |
|--------|--------|
| <span data-ttu-id="a1486-135">**調查圖表**</span><span class="sxs-lookup"><span data-stu-id="a1486-135">**Investigation graph**</span></span>   | <span data-ttu-id="a1486-136">提供調查的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="a1486-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="a1486-137">描述實體並列出發現的威脅和警示，以及是否有任何待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="a1486-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="a1486-138">您可以按一下圖表上的項目來查看更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a1486-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="a1486-139">例如，按一下 [找到的威脅] 圖示會帶您移至 [重要結果] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a1486-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
| <span data-ttu-id="a1486-140">**提醒**</span><span class="sxs-lookup"><span data-stu-id="a1486-140">**Alerts**</span></span>    | <span data-ttu-id="a1486-141">列出與調查相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="a1486-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="a1486-142">警示可能來自使用者電腦上、Office 應用程式、雲端 App 安全性和其他 Microsoft 365 Defender 功能的威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="a1486-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="a1486-143">**裝置**</span><span class="sxs-lookup"><span data-stu-id="a1486-143">**Devices**</span></span> | <span data-ttu-id="a1486-144">列出調查中包含的電腦及其修正等級。</span><span class="sxs-lookup"><span data-stu-id="a1486-144">Lists machines included in the investigation along with remediation level.</span></span>|
| <span data-ttu-id="a1486-145">**重要結果**</span><span class="sxs-lookup"><span data-stu-id="a1486-145">**Key findings**</span></span>  | <span data-ttu-id="a1486-146">列出調查結果，以及狀態和已執行或待核准的動作。</span><span class="sxs-lookup"><span data-stu-id="a1486-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="a1486-147">您可以在這個索引標籤上核准裝置和身分識別的待核准動作。</span><span class="sxs-lookup"><span data-stu-id="a1486-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
| <span data-ttu-id="a1486-148">**Entities**</span><span class="sxs-lookup"><span data-stu-id="a1486-148">**Entities**</span></span>  | <span data-ttu-id="a1486-149">列出與調查相關聯的使用者活動、檔案、處理程序、服務、驅動程式、IP 位址和持續性方法，以及狀態和採取的動作。</span><span class="sxs-lookup"><span data-stu-id="a1486-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="a1486-150">**Log**</span><span class="sxs-lookup"><span data-stu-id="a1486-150">**Log**</span></span>    | <span data-ttu-id="a1486-151">提供調查過程中所有步驟的詳細資訊，以及狀態。</span><span class="sxs-lookup"><span data-stu-id="a1486-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
| <span data-ttu-id="a1486-152">**待核准的動作**</span><span class="sxs-lookup"><span data-stu-id="a1486-152">**Pending actions**</span></span> | <span data-ttu-id="a1486-153">列出需要核准才能繼續的項目。</span><span class="sxs-lookup"><span data-stu-id="a1486-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="a1486-154">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a1486-154">Next steps</span></span>

- [<span data-ttu-id="a1486-155">與自動化調查及回應相關的核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="a1486-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="a1486-156">審查補救動作</span><span class="sxs-lookup"><span data-stu-id="a1486-156">Review remediation actions</span></span>](mtp-remediation-actions.md)
