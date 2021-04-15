---
title: 在 Microsoft 365 Defender 中管理事件
description: 了解如何指派及更新狀態
keywords: 事件, 警示, 相關警示, 指派, 更新, 狀態, 管理, 分類, Microsoft, 365, m365
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
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760061"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="333e7-104">在 Microsoft 365 Defender 中管理事件</span><span class="sxs-lookup"><span data-stu-id="333e7-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="333e7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="333e7-105">**Applies to:**</span></span>
- <span data-ttu-id="333e7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="333e7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="333e7-107">事件管理對於確保威脅已包含並加以解決非常重要。</span><span class="sxs-lookup"><span data-stu-id="333e7-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="333e7-108">您可以在 Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上，管理事件 **& 警示 > 事件**。</span><span class="sxs-lookup"><span data-stu-id="333e7-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="333e7-109">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="333e7-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

<span data-ttu-id="333e7-111">您可以透過下列方式管理您的事件：</span><span class="sxs-lookup"><span data-stu-id="333e7-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="333e7-112">變更事件名稱</span><span class="sxs-lookup"><span data-stu-id="333e7-112">Change the incident name</span></span>
- <span data-ttu-id="333e7-113">新增事件標記。</span><span class="sxs-lookup"><span data-stu-id="333e7-113">Add incident tags.</span></span>
- <span data-ttu-id="333e7-114">指派事件給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="333e7-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="333e7-115">解決這些問題</span><span class="sxs-lookup"><span data-stu-id="333e7-115">Resolve them</span></span> 
- <span data-ttu-id="333e7-116">設定它的分類和決定</span><span class="sxs-lookup"><span data-stu-id="333e7-116">Set its classification and determination</span></span>
- <span data-ttu-id="333e7-117">新增批註。</span><span class="sxs-lookup"><span data-stu-id="333e7-117">Add comments.</span></span>

<span data-ttu-id="333e7-118">您可以從「 **管理事件** 」窗格中管理事件的事件。</span><span class="sxs-lookup"><span data-stu-id="333e7-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="333e7-119">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="333e7-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件的管理事件窗格範例":::

<span data-ttu-id="333e7-121">您可以從下列專案上的 **管理事件** 連結，顯示此窗格：</span><span class="sxs-lookup"><span data-stu-id="333e7-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="333e7-122">事件佇列中事件的屬性窗格。</span><span class="sxs-lookup"><span data-stu-id="333e7-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="333e7-123">事件的 **摘要** 頁面。</span><span class="sxs-lookup"><span data-stu-id="333e7-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="333e7-124">在調查您是否想要將警示從某個事件移動到另一個事件的情況下，您也可以從 [ **警示** ] 索引標籤，建立一個包含所有相關警示的較大或較小的事件。</span><span class="sxs-lookup"><span data-stu-id="333e7-124">In cases where, while investigating you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="333e7-125">編輯事件名稱</span><span class="sxs-lookup"><span data-stu-id="333e7-125">Edit the incident name</span></span>

<span data-ttu-id="333e7-126">事件會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別）自動指派名稱。</span><span class="sxs-lookup"><span data-stu-id="333e7-126">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="333e7-127">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="333e7-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="333e7-128">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="333e7-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="333e7-129">您可以在 [**管理事件**] 窗格上的 [**事件名稱**] 欄位中編輯事件名稱。</span><span class="sxs-lookup"><span data-stu-id="333e7-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="333e7-130">在自動事件命名功能的展示中，已存在的事件將保留其名稱。</span><span class="sxs-lookup"><span data-stu-id="333e7-130">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="333e7-131">新增事件標籤</span><span class="sxs-lookup"><span data-stu-id="333e7-131">Add incident tags</span></span>

<span data-ttu-id="333e7-132">您可以將自訂標記新增至事件，例如標示具有共同特性的事件群組。</span><span class="sxs-lookup"><span data-stu-id="333e7-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="333e7-133">您可以稍後針對所有包含特定標記的事件，篩選事件佇列。</span><span class="sxs-lookup"><span data-stu-id="333e7-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="333e7-134">當您開始輸入時，您可以選擇從選取的標記清單中進行選取。</span><span class="sxs-lookup"><span data-stu-id="333e7-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="333e7-135">指派事件</span><span class="sxs-lookup"><span data-stu-id="333e7-135">Assign incidents</span></span>

<span data-ttu-id="333e7-136">若尚未指派事件，您可以選取 [ **指派給** ] 並指定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="333e7-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="333e7-137">這樣做會指派事件的擁有權及與其相關聯的所有警示。</span><span class="sxs-lookup"><span data-stu-id="333e7-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="333e7-138">解決事件</span><span class="sxs-lookup"><span data-stu-id="333e7-138">Resolve incident</span></span>

<span data-ttu-id="333e7-139">如果事件已經修正，請選取 [ **解決事件** ]，將切換移至右邊。</span><span class="sxs-lookup"><span data-stu-id="333e7-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="333e7-140">請注意，解決事件也會解決與該事件相關的所有連結和主動警示。</span><span class="sxs-lookup"><span data-stu-id="333e7-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="333e7-141">未解析的事件會顯示為作用 **中。**</span><span class="sxs-lookup"><span data-stu-id="333e7-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="333e7-142">設定分類和決定</span><span class="sxs-lookup"><span data-stu-id="333e7-142">Set the classification and determination</span></span>

<span data-ttu-id="333e7-143">「事件分類」是指從 [ **分類** ] 欄位設定的是 true 警示或假警示。</span><span class="sxs-lookup"><span data-stu-id="333e7-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="333e7-144">如果是真正的警示，您也應該指定其 **判斷** 欄位所使用的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="333e7-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="333e7-145">指定威脅類型可協助安全小組看到威脅模式，並採取行動以保護組織。</span><span class="sxs-lookup"><span data-stu-id="333e7-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="333e7-146">新增註解</span><span class="sxs-lookup"><span data-stu-id="333e7-146">Add comments</span></span>

<span data-ttu-id="333e7-147">您可以使用 [ **批註** ] 欄位，將多個批註新增至事件。</span><span class="sxs-lookup"><span data-stu-id="333e7-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="333e7-148">每個評語都會新增至事件的歷史事件。</span><span class="sxs-lookup"><span data-stu-id="333e7-148">Each comment is added to the historical events of the incident.</span></span> <span data-ttu-id="333e7-149">您可以在 [**摘要**] 頁面上，看到 [**批註和記錄**] 連結中的事件批註和記錄。</span><span class="sxs-lookup"><span data-stu-id="333e7-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>
