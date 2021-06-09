---
title: 在 Microsoft Defender for Endpoint 中檢查提醒
description: 檢查警示資訊，包含詳細說明的警示案例，以及階層每個步驟的詳細資料。
keywords: 事件，事件，機器，裝置，使用者，警示，警示，調查，圖形，證據
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844019"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="2f488-104">在 Microsoft Defender for Endpoint 中檢查提醒</span><span class="sxs-lookup"><span data-stu-id="2f488-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2f488-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2f488-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f488-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f488-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="2f488-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2f488-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f488-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2f488-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="2f488-109">Microsoft Defender for Endpoint 中的 [警示] 頁面會透過結合與所選警示相關的攻擊信號和警示，提供完整的警示內容，以建立詳細的警示案例。</span><span class="sxs-lookup"><span data-stu-id="2f488-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="2f488-110">快速進行會審、調查，並對影響組織的警示採取有效的動作。</span><span class="sxs-lookup"><span data-stu-id="2f488-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="2f488-111">瞭解它們的觸發原因，以及其對一個位置的影響。</span><span class="sxs-lookup"><span data-stu-id="2f488-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="2f488-112">若要深入瞭解，請參閱本概述。</span><span class="sxs-lookup"><span data-stu-id="2f488-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="2f488-113">提醒入門</span><span class="sxs-lookup"><span data-stu-id="2f488-113">Getting started with an alert</span></span>

<span data-ttu-id="2f488-114">在 [Defender for Endpoint] 中選取警示的名稱時，會將您置於警示頁面上。</span><span class="sxs-lookup"><span data-stu-id="2f488-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="2f488-115">在 [警示] 頁面上，所有的資訊都會顯示在所選警示的內容中。</span><span class="sxs-lookup"><span data-stu-id="2f488-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="2f488-116">每個提醒頁面包含4個區段：</span><span class="sxs-lookup"><span data-stu-id="2f488-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="2f488-117">**提醒標題** 會顯示警示的名稱，而且可以提醒您，不論您在頁面上選取的是哪一個警示已開始您目前的調查。</span><span class="sxs-lookup"><span data-stu-id="2f488-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="2f488-118">[**受影響資產**](#review-affected-assets) 列出此警示所影響的裝置和使用者卡，以供進一步資訊和動作使用。</span><span class="sxs-lookup"><span data-stu-id="2f488-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="2f488-119">**警示案例** 會顯示與該警示相關的所有實體，並以樹狀檢視互連。</span><span class="sxs-lookup"><span data-stu-id="2f488-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="2f488-120">當您第一次在選取的警示頁面上移動時，標題中的警示會是焦點中的警示。</span><span class="sxs-lookup"><span data-stu-id="2f488-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="2f488-121">警示案例中的實體可展開和按一下，以提供額外的資訊，並可讓您在警示頁面的內容中採取動作，以加速回應。</span><span class="sxs-lookup"><span data-stu-id="2f488-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="2f488-122">使用警示案例開始您的調查。</span><span class="sxs-lookup"><span data-stu-id="2f488-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="2f488-123">瞭解如何 [調查 Microsoft Defender For Endpoint 中的通知](/microsoft-365/security/defender-endpoint/investigate-alerts)。</span><span class="sxs-lookup"><span data-stu-id="2f488-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="2f488-124">[ **詳細資料] 窗格** 會先顯示選取警示的詳細資料，以及與此警示相關的詳細資料和動作。</span><span class="sxs-lookup"><span data-stu-id="2f488-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="2f488-125">如果您選取預警案例中的任何受影響的資產或實體，詳細資料窗格會變更，以提供所選物件的上下文資訊和動作。</span><span class="sxs-lookup"><span data-stu-id="2f488-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="2f488-126">請注意警示的偵測狀態。</span><span class="sxs-lookup"><span data-stu-id="2f488-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="2f488-127">已避免-已避免嘗試的可疑動作。</span><span class="sxs-lookup"><span data-stu-id="2f488-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="2f488-128">例如，檔案不是寫入磁片或執行。</span><span class="sxs-lookup"><span data-stu-id="2f488-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="2f488-129">![阻止顯示威脅的警示頁面](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="2f488-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="2f488-130">封鎖-已執行可疑行為，然後遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="2f488-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="2f488-131">例如，已執行某個進程，但由於後來出現可疑行為，所以處理常式已終止。</span><span class="sxs-lookup"><span data-stu-id="2f488-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="2f488-132">![已封鎖顯示威脅的警示頁面](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="2f488-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="2f488-133">偵測–偵測到攻擊，而且可能仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="2f488-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="2f488-134">![偵測到顯示威脅的警示頁面](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="2f488-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="2f488-135">您也可以在警示的詳細資料窗格中查看 *自動調查詳細資料* ，以查看已採取的動作，以及讀取建議動作的警示描述。</span><span class="sxs-lookup"><span data-stu-id="2f488-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![[詳細資料] 窗格中 [警示描述] 和 [自動調查] 區段已反白顯示的程式碼片段](images/alert-air-and-alert-description.png)

<span data-ttu-id="2f488-137">警示開啟時，詳細資料窗格中提供的其他資訊包括 MITRE 技巧、來源及其他上下文詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f488-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="2f488-138">審閱受影響的資產</span><span class="sxs-lookup"><span data-stu-id="2f488-138">Review affected assets</span></span>

<span data-ttu-id="2f488-139">選取「受影響的資產」區段中的裝置或使用者卡片，會在詳細資料窗格中切換到裝置或使用者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f488-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="2f488-140">**對於裝置**，詳細資料窗格會顯示裝置本身的相關資訊，例如 Domain、作業系統和 IP。</span><span class="sxs-lookup"><span data-stu-id="2f488-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="2f488-141">也可以使用作用中的警示及該裝置上登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="2f488-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="2f488-142">您可以透過隔離裝置、限制應用程式執行或執行防病毒掃描，立即採取行動。</span><span class="sxs-lookup"><span data-stu-id="2f488-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="2f488-143">或者，您也可以收集調查套件、啟動自動調查，或是移至 [裝置] 頁面，以從裝置的查看角度進行調查。</span><span class="sxs-lookup"><span data-stu-id="2f488-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![選取裝置時的詳細資料窗格片段](images/device-page-details.png)

- <span data-ttu-id="2f488-145">**針對使用者**，詳細資料窗格會顯示詳細的使用者資訊，例如使用者的 SAM 名稱和 SID，以及此使用者執行的登入類型，以及與其相關的任何警示和事件。</span><span class="sxs-lookup"><span data-stu-id="2f488-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="2f488-146">您可以選取 [ *開啟使用者] 頁面* ，繼續從該使用者的觀點進行調查。</span><span class="sxs-lookup"><span data-stu-id="2f488-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![選取使用者時詳細資料窗格的程式碼片段](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="2f488-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="2f488-148">Related topics</span></span>

- [<span data-ttu-id="2f488-149">查看和組織事件佇列</span><span class="sxs-lookup"><span data-stu-id="2f488-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="2f488-150">調查事件</span><span class="sxs-lookup"><span data-stu-id="2f488-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="2f488-151">管理事件</span><span class="sxs-lookup"><span data-stu-id="2f488-151">Manage incidents</span></span>](manage-incidents.md)
