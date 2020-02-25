---
title: 管理 Microsoft 威脅防護中的事件
description: 了解如何指派及更新狀態
keywords: 事件, 警示, 相關警示, 指派, 更新, 狀態, 管理, 分類, Microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b8f7e3bbb6d2348c3f19e8df251d700d8adf8e33
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235082"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="66198-104">管理 Microsoft 威脅防護中的事件</span><span class="sxs-lookup"><span data-stu-id="66198-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="66198-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="66198-105">**Applies to:**</span></span>
- <span data-ttu-id="66198-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="66198-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="66198-107">管理事件對確保控制及解決威脅至關重要。</span><span class="sxs-lookup"><span data-stu-id="66198-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="66198-108">在 Microsoft 威脅防護中，您可管理裝置、使用者和信箱的事件。</span><span class="sxs-lookup"><span data-stu-id="66198-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="66198-109">您可以從 **[事件佇列]** 選取事件來管理事件。</span><span class="sxs-lookup"><span data-stu-id="66198-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="66198-110">您可以編輯事件名稱、解決事件、設定其分類及判斷。</span><span class="sxs-lookup"><span data-stu-id="66198-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="66198-111">您也可以將事件指派給自己、新增事件標籤和註解。</span><span class="sxs-lookup"><span data-stu-id="66198-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="66198-112">在調查時，若您要將警示從某事件移到另一個事件，也可以從 [警示] 索引標籤執行此動作，以建立包含所有相關警示的較大或較小事件。</span><span class="sxs-lookup"><span data-stu-id="66198-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="66198-113">編輯事件名稱</span><span class="sxs-lookup"><span data-stu-id="66198-113">Edit incident name</span></span>
<span data-ttu-id="66198-114">根據預設，系統會為事件指派一個編號。</span><span class="sxs-lookup"><span data-stu-id="66198-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="66198-115">您可以修改事件名稱，以更符合您偏好的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="66198-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="66198-116">指派事件</span><span class="sxs-lookup"><span data-stu-id="66198-116">Assign incidents</span></span>
<span data-ttu-id="66198-117">如果尚未指派事件，您可以選取 **[指派給我]** 將事件指派給自己。</span><span class="sxs-lookup"><span data-stu-id="66198-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="66198-118">這樣做不僅表示您承擔該事件的擁有權，還包括所有與該事件相關的警示。</span><span class="sxs-lookup"><span data-stu-id="66198-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="66198-119">設定狀態和分類</span><span class="sxs-lookup"><span data-stu-id="66198-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="66198-120">事件狀態</span><span class="sxs-lookup"><span data-stu-id="66198-120">Incident status</span></span>
<span data-ttu-id="66198-121">您可以在調查進行的過程中變更事件的狀態來將事件分類 (例如：**作用中**或**已解決**)。</span><span class="sxs-lookup"><span data-stu-id="66198-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="66198-122">這可協助您組織及管理小組回應事件的方式。</span><span class="sxs-lookup"><span data-stu-id="66198-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="66198-123">例如，您的 SOC 分析師可檢閱當天的緊急**作用中**事件，並決定是否將該事件指派給自己進行調查。</span><span class="sxs-lookup"><span data-stu-id="66198-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="66198-124">如果事件已修補，您的 SOC 分析師可將事件設為**已解決**。</span><span class="sxs-lookup"><span data-stu-id="66198-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="66198-125">解決事件將會自動關閉屬於該事件且仍開啟的所有警報。</span><span class="sxs-lookup"><span data-stu-id="66198-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="66198-126">分類及判斷</span><span class="sxs-lookup"><span data-stu-id="66198-126">Classification and determination</span></span>
<span data-ttu-id="66198-127">您可以選擇不要設定分類，或決定將事件指定為 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="66198-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="66198-128">這樣做可協助小組查看模式及深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="66198-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="66198-129">新增註解</span><span class="sxs-lookup"><span data-stu-id="66198-129">Add comments</span></span>
<span data-ttu-id="66198-130">您可以新增註解及檢視與事件相關的歷史活動，以查看先前所做的變更。</span><span class="sxs-lookup"><span data-stu-id="66198-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="66198-131">對警示進行變更或新增註解時，便會記錄在 [註解和記錄] 區段中。</span><span class="sxs-lookup"><span data-stu-id="66198-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="66198-132">新增的註解會立即顯示在窗格中。</span><span class="sxs-lookup"><span data-stu-id="66198-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="66198-133">新增事件標籤</span><span class="sxs-lookup"><span data-stu-id="66198-133">Add incident tags</span></span>
<span data-ttu-id="66198-134">您可以為事件新增自訂標籤，例如使用常見特性來標記一組事件。</span><span class="sxs-lookup"><span data-stu-id="66198-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="66198-135">您可以稍後篩選包含特定標籤的所有事件的事件佇列。</span><span class="sxs-lookup"><span data-stu-id="66198-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

