---
title: Microsoft 365 Defender 中的事件
description: 調查在不同裝置、使用者和信箱看到的事件。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759481"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="9b0cc-104">Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="9b0cc-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b0cc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9b0cc-105">**Applies to:**</span></span>
- <span data-ttu-id="9b0cc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b0cc-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="9b0cc-107">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="9b0cc-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9b0cc-108">您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="9b0cc-109">Microsoft 365 Defender 中的事件是組成攻擊之故事的相關警示和相關資料的集合。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="9b0cc-110">Microsoft 365 服務和應用程式會在偵測到可疑或惡意事件或活動時建立警示。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="9b0cc-111">個別警示可提供關於已完成或進行中攻擊的重要線索。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="9b0cc-112">不過，攻擊一般會針對不同類型的實體（例如裝置、使用者和信箱）採用各種技術。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="9b0cc-113">其結果是針對您租使用者中的多個實體的多個警示。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="9b0cc-114">因為 piecing 個別警示來深入瞭解攻擊可能會非常困難而且耗時，所以 Microsoft 365 Defender 會自動將警示和相關資訊匯總到事件中。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 如何將實體中的事件與事件產生關聯":::

<span data-ttu-id="9b0cc-116">請觀看 Microsoft 365 Defender (4 分鐘) 中的事件簡短敘述。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="9b0cc-117">將相關警示分組到事件中，可讓您全面瞭解攻擊。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="9b0cc-118">例如，您可以看到：</span><span class="sxs-lookup"><span data-stu-id="9b0cc-118">For example, you can see:</span></span>

- <span data-ttu-id="9b0cc-119">攻擊的開始位置。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-119">Where the attack started.</span></span>
- <span data-ttu-id="9b0cc-120">使用的戰術。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-120">What tactics were used.</span></span>
- <span data-ttu-id="9b0cc-121">攻擊進入您租使用者的距離。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="9b0cc-122">攻擊的範圍，例如影響的裝置、使用者和信箱數目。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="9b0cc-123">所有與攻擊相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="9b0cc-124">若 [啟用](m365d-enable.md)，Microsoft 365 Defender 便可透過自動化和人工智慧，自動調查並解決警示。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="9b0cc-125">您也可以執行其他修復步驟，以解決攻擊。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="9b0cc-126">Microsoft 365 安全中心的事件及警示</span><span class="sxs-lookup"><span data-stu-id="9b0cc-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="9b0cc-127">您可以在 Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上，管理事件 **& 警示 > 事件**。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="9b0cc-128">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 security center 中的 [事件] 頁面":::

<span data-ttu-id="9b0cc-130">選取 [事件名稱] 會顯示事件摘要，並可讓您存取具有其他資訊的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 安全中心內事件摘要頁面的範例":::

<span data-ttu-id="9b0cc-132">事件的其他索引標籤如下：</span><span class="sxs-lookup"><span data-stu-id="9b0cc-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="9b0cc-133">警示</span><span class="sxs-lookup"><span data-stu-id="9b0cc-133">Alerts</span></span> 

  <span data-ttu-id="9b0cc-134">與該事件相關的所有提醒，以及其資訊。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="9b0cc-135">裝置</span><span class="sxs-lookup"><span data-stu-id="9b0cc-135">Devices</span></span>

  <span data-ttu-id="9b0cc-136">已識別為屬於事件一部分或與其相關的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="9b0cc-137">使用者</span><span class="sxs-lookup"><span data-stu-id="9b0cc-137">Users</span></span>

  <span data-ttu-id="9b0cc-138">已識別為屬於該事件或與其相關的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="9b0cc-139">信箱</span><span class="sxs-lookup"><span data-stu-id="9b0cc-139">Mailboxes</span></span>

  <span data-ttu-id="9b0cc-140">已識別為屬於事件一部分或與其相關的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="9b0cc-141">調查</span><span class="sxs-lookup"><span data-stu-id="9b0cc-141">Investigations</span></span>

  <span data-ttu-id="9b0cc-142">事件中的警示所觸發的所有自動調查。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="9b0cc-143">證據與回應</span><span class="sxs-lookup"><span data-stu-id="9b0cc-143">Evidence and Response</span></span>

  <span data-ttu-id="9b0cc-144">事件中警示中所有支援的事件及可疑的實體。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="9b0cc-145">以下是事件與其資料之間的關係，以及 Microsoft 365 security center 中事件的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="在 Microsoft 365 安全中心的事件索引標籤中，事件及其資料的關聯性":::

## <a name="next-step"></a><span data-ttu-id="9b0cc-147">下一步</span><span class="sxs-lookup"><span data-stu-id="9b0cc-147">Next step</span></span>

<span data-ttu-id="9b0cc-148">[ **事件** ] 頁面的 [事件] 佇列會列出最近的事件。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="9b0cc-149">在這裡，您可以：</span><span class="sxs-lookup"><span data-stu-id="9b0cc-149">From here, you can:</span></span>

- <span data-ttu-id="9b0cc-150">根據嚴重性及其他因素，查看應 [優先](incident-queue.md) 考慮哪些事件。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="9b0cc-151">對事件進行 [調查](investigate-incidents.md) 。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="9b0cc-152">[管理事件](manage-incidents.md)，包括重新命名、指派事件管理工作流程的標記、分類及新增標籤。</span><span class="sxs-lookup"><span data-stu-id="9b0cc-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
